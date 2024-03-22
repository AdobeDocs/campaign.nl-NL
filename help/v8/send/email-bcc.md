---
title: Een kopie van uw berichten verzenden naar een BCC-adres
description: Leer hoe u e-mail BCC activeert in Adobe Campaign
feature: Email
role: User
level: Beginner
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
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
Adobe Campaign zelf beheert gearchiveerde bestanden niet. De .eml-bestanden die overeenkomen met de verzonden e-mails kunnen vervolgens worden overgebracht naar een externe server, zoals een SMTP-e-mailserver.

De archiveringsbestemming is het BCC-e-mailadres van uw keuze, dat onzichtbaar blijft voor de ontvangers van de levering. Als het BCC-e-mailadres eenmaal is gedefinieerd, moet u de specifieke optie inschakelen in het dialoogvenster [leveringssjabloon](create-templates.md) niveau.

>[!NOTE]
>
>Als gebruiker van beheerde Cloud Servicen, [contact Adobe](../start/campaign-faq.md#support){target="_blank"} om het BCC e-mailadres mee te delen dat voor archivering moet worden gebruikt.

>[!CAUTION]
>
>Om privacyredenen moeten BCC-e-mails worden verwerkt door een archiveringssysteem dat veilig identificeerbare informatie (PII) kan opslaan.


## E-mail BCC inschakelen {#enable-bcc}

BCC inschakelen voor een specifieke [leveringssjabloon](create-templates.md)volgt u de onderstaande stappen:

1. Blader vanuit Campagneverkenner naar de map met leveringssjablonen. Standaard worden leveringssjablonen opgeslagen in de **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** map.
1. Bewerk de leveringssjabloon om bij te werken met BCC.
1. Klik op de knop **[!UICONTROL Properties]**.
1. Van de **[!UICONTROL Delivery]** tabblad, controleert u de **[!UICONTROL Email BCC]** -optie.

   ![](assets/email-bcc.png)

1. Klik op **[!UICONTROL Ok]** om te bevestigen.

Een kopie van alle verzonden berichten voor elke levering die op deze sjabloon is gebaseerd, wordt verzonden naar het e-mailadres BCC dat voor uw platform is geconfigureerd.

## Guardrails en aanbevelingen {#recommendations-bcc}

Wanneer u e-mail BCC gebruikt met Adobe Campaign, gelden de volgende instructies en aanbevelingen:

* U kunt slechts één BCC-e-mailadres gebruiken.

* Zorg ervoor dat het BCC-adres voldoende ontvangstcapaciteit heeft om alle verzonden e-mails te archiveren.

* BCC e-mailen <!--with Enhanced MTA--> levert aan het BCC e-mailadres alvorens aan de ontvangers te leveren, wat in BCC berichten kan resulteren die worden verzonden alhoewel de originele leveringen kunnen hebben teruggestuurd. Zie voor meer informatie over grenzen [Uitvoeren van fouten begrijpen](delivery-failures.md).

* E-mails naar het BCC-adres mogen niet worden geopend en er mag niet op worden geklikt, aangezien met deze activiteiten rekening wordt gehouden in de **[!UICONTROL Total opens]** en **[!UICONTROL Clicks]** kan leiden tot onjuiste berekeningen.

<!--Only successfully sent emails are taken in account, bounces are not.-->
