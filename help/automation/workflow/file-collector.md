---
product: campaign
title: Bestandsophaler
description: Meer informatie over de workflowactiviteit van de bestandscollector
feature: Workflows, Data Management
role: User
exl-id: 614becf7-4cbf-40f9-a1b1-06efa054bfd9
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Bestandsophaler{#file-collector}



De **Bestandsverzamelaar** controleert de aankomst van een of meer bestanden in een directory en activeert de overgang ervan voor elk ontvangen bestand. Voor elke gebeurtenis geldt een **[!UICONTROL filename]** De variabele bevat de volledige naam van het ontvangen bestand. De verzamelde bestanden worden naar een andere map verplaatst voor archiveringsdoeleinden en om ervoor te zorgen dat ze maar één keer worden geteld.

Standaard is de bestandscollector een permanente taak waarmee de aanwezigheid van bestanden wordt getest op de tijdstippen die in de planning zijn opgegeven.

De bestanden moeten zich op de server bevinden waarop de wfserver-module die voor deze workflow verantwoordelijk is, wordt uitgevoerd. Als meerdere wfserver-modules op één instantie worden geïmplementeerd, moet de affiniteit van de activiteiten die deze bestanden gebruiken of de algemene affiniteit van de workflow worden opgegeven.

## Properties {#properties}

Het eerste tabblad van het dialoogvenster **[!UICONTROL File collector]** Met activiteit kunt u de bronmap selecteren en, indien nodig, de verzamelde bestanden filteren. De andere tabbladen worden beschreven in [Binnenkomende e-mails](inbound-emails.md) (**[!UICONTROL Schedule]** en **[!UICONTROL Expiry]** tabs).

![](assets/file_collect_edit.png)

1. **Bestanden downloaden**

   * **[!UICONTROL Directory]**

     Map met de bestanden die moeten worden gedownload. Deze map moet vooraf op de server worden gemaakt: als deze niet bestaat, wordt een fout gegenereerd.

   * **[!UICONTROL Filter]**

     Alleen bestanden die overeenkomen met dit filter worden in aanmerking genomen. De andere bestanden in de map worden genegeerd. Als het filter leeg is, worden alle bestanden in de map in aanmerking genomen. Voorbeelden van filters: **&#42;.zip**, **import-&#42;.txt**.

   * **[!UICONTROL Stop as soon as a file has been processed]**

     Als deze optie is ingeschakeld, wordt de taak beëindigd na ontvangst van het eerste bestand. Als de map meerdere bestanden bevat die overeenkomen met het filter, wordt er slechts één bestand gebruikt. Deze optie garandeert dat slechts één gebeurtenis wordt verzonden. Het in aanmerking genomen bestand is het eerste in de lijst in alfabetische volgorde.

     Voor een niet-geplande activiteit, als er geen bestand is gevonden dat overeenkomt met het filter in de opgegeven map en als de **[!UICONTROL Process file nonexistence]** Deze optie is niet ingeschakeld. Er wordt een fout weergegeven.

   * **[!UICONTROL Execution schedule]**

     Hiermee bepaalt u de frequentie van de controle op bestandsaanwezigheid via de parameters van het dialoogvenster **[!UICONTROL Schedule]** tab.

1. **Foutafhandeling**

   De volgende twee opties zijn beschikbaar:

   * **[!UICONTROL Process file nonexistence]**

     Met deze optie wordt telkens een speciale overgang gestart wanneer er geen bestand wordt gevonden dat overeenkomt met het filter in de opgegeven map.

     Als de taak niet is gepland, wordt deze overgang slechts eenmaal geactiveerd.

   * **[!UICONTROL Processing errors]**

     Met deze optie wordt een speciale overgang weergegeven die moet worden geactiveerd wanneer een fout wordt gegenereerd. In dit geval verandert de werkstroom niet in de foutstatus en gaat de uitvoering verder

     Fouten waarmee rekening wordt gehouden, zijn fouten in het bestandssysteem (het bestand kan niet worden verplaatst, de map kan niet worden geopend, enz.).

     Deze optie verwerkt geen fouten met betrekking tot activiteitsconfiguratie, d.w.z. ongeldige waarden.

1. **Historiatie**

   Zie de **[!UICONTROL File historization]** stap hier: [Webdownload](web-download.md).

De volgorde van de bestandsverwerking kan niet worden bepaald. Als u een set bestanden opeenvolgend wilt verwerken, gebruikt u de opdracht **[!UICONTROL Stop as soon as a file has been processed]** en maakt u een lus. In dit geval worden de bestanden in alfabetische volgorde verwerkt. De **[!UICONTROL Process file nonexistence]** Met deze optie kunt u de herhaling voltooien.

![](assets/file_collect_loop.png)

## Uitvoerparameters {#output-parameters}

* bestandsnaam: volledige bestandsnaam. Dit is de bestandsnaam nadat deze naar de historiemap is verplaatst. Het pad is dus anders, maar de naam is ook anders als er al een ander bestand met dezelfde naam in de map staat. De extensie blijft behouden.
