---
title: Een kopie van uw berichten verzenden naar een BCC-adres
description: Leer hoe u e-mail BCC activeert in Adobe Campaign
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# Een kopie van uw berichten verzenden naar een BCC-adres {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## Over e-mail BCC {#gs-bcc}

U kunt Adobe Campaign zo configureren dat een kopie van de e-mails die u van uw platform hebt ontvangen, bewaard blijft. Met deze optie kunt u berichten verzenden naar een specifiek BCC-e-mailadres (Blinden Carbon Copy), vanwaar ze via een extern systeem kunnen worden verwerkt en gearchiveerd.

>[!CAUTION]
>
>Om privacyredenen moeten BCC-e-mails worden verwerkt door een archiveringssysteem dat veilig identificeerbare informatie (PII) kan opslaan.

Adobe Campaign zelf beheert gearchiveerde bestanden niet. De .eml-bestanden die overeenkomen met de verzonden e-mails kunnen vervolgens worden overgebracht naar een externe server, zoals een SMTP-e-mailserver.

De archiveringsbestemming is het BCC-e-mailadres van uw keuze, dat onzichtbaar blijft voor de ontvangers van de levering. Zodra het BCC e-mailadres wordt bepaald, moet u de specifieke optie op het [ niveau van het leveringsmalplaatje ](create-templates.md) toelaten.

>[!NOTE]
>
>Als Beheerde gebruiker van de Diensten van de Wolk, [ contacteer Adobe ](../start/campaign-faq.md#support){target="_blank"} om het BCC e-mailadres mee te delen dat voor het archiveren moet worden gebruikt.

## E-mail BCC inschakelen {#enable-bcc}

Om BCC voor een specifiek [ leveringsmalplaatje ](create-templates.md) toe te laten, volg hieronder de stappen:

1. Blader vanuit Campagneverkenner naar de map met leveringssjablonen. Standaard worden leveringssjablonen opgeslagen in de map **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Bewerk de leveringssjabloon om bij te werken met BCC.
1. Klik op de knop **[!UICONTROL Properties]**.
1. Controleer de optie **[!UICONTROL Email BCC with enhanced Momentum]** op het tabblad **[!UICONTROL Delivery]** .

   ![](assets/email-bcc.png)

1. Klik op **[!UICONTROL Ok]** om te bevestigen.

Een kopie van alle verzonden berichten voor elke levering die op deze sjabloon is gebaseerd, wordt verzonden naar het e-mailadres BCC dat voor uw platform is geconfigureerd.

## Guardrails en aanbevelingen {#recommendations-bcc}

Wanneer u e-mail BCC gebruikt met Adobe Campaign, gelden de volgende instructies en aanbevelingen:

* U kunt slechts één BCC-e-mailadres gebruiken.

* Zorg ervoor dat het BCC-adres voldoende ontvangstcapaciteit heeft om alle verzonden e-mails te archiveren.

* E-mail BCC <!--with Enhanced MTA--> levert aan het BCC e-mailadres alvorens aan de ontvangers te leveren, wat in BCC berichten kan resulteren die worden verzonden alhoewel de originele leveringen kunnen zijn teruggestuurd. Voor meer op grenzen, zie [ leveringsmislukkingen ](delivery-failures.md) begrijpen.

* E-mails die naar het BCC-adres worden verzonden, mogen niet worden geopend en doorgeklikt, omdat deze activiteiten in de **[!UICONTROL Total opens]** en **[!UICONTROL Clicks]** van de verzendanalyse in aanmerking worden genomen, kunnen leiden tot onjuiste berekeningen.

<!--Only successfully sent emails are taken in account, bounces are not.-->
