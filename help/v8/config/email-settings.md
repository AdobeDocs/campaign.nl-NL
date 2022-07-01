---
title: Instellingen voor e-mailkanalen voor campagne
description: Instellingen voor e-mailkanalen voor campagne
feature: Email
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# Instellingen voor e-mailkanalen voor campagne

## BCC e-mailen {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

U kunt Adobe Campaign zo configureren dat een kopie van de e-mails die u van uw platform hebt ontvangen, bewaard blijft.

Adobe Campaign zelf beheert gearchiveerde bestanden niet. Hiermee kunt u de berichten van uw keuze naar een specifiek BCC-e-mailadres (blinde koolstofkopie) sturen, vanwaar ze via een extern systeem kunnen worden verwerkt en gearchiveerd. De .eml-bestanden die overeenkomen met de verzonden e-mails kunnen vervolgens worden overgebracht naar een externe server, zoals een SMTP-e-mailserver.

>[!CAUTION]
>
>Om privacyredenen moeten BCC-e-mails worden verwerkt door een archiveringssysteem dat veilig identificeerbare informatie (PII) kan opslaan.

De archiveringsbestemming is het BCC-e-mailadres van uw keuze, dat onzichtbaar blijft voor de ontvangers van de levering.

![](../assets/do-not-localize/speech.png)  Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support){target=&quot;_blank&quot;} om het BCC-e-mailadres door te geven dat moet worden gebruikt voor archivering.

Zodra het BCC e-mailadres wordt bepaald, moet u de specifieke optie op het leveringsniveau toelaten.

>[!CAUTION]
>
>Bij het maken van een nieuwe leverings- of leveringssjabloon **[!UICONTROL Email BCC]** is niet standaard ingeschakeld. U moet het manueel in het e-maillevering of leveringsmalplaatje toelaten.


Volg de onderstaande stappen om dit te doen:

1. Ga naar **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**, of **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Selecteer de levering van uw keuze of dupliceer de uit-van-de-doos **[!UICONTROL Email delivery]** selecteert u vervolgens de gedupliceerde sjabloon.
1. Klik op de knop **[!UICONTROL Properties]**.
1. Selecteer het tabblad **[!UICONTROL Delivery]**. 
1. Schakel de optie **[!UICONTROL Email BCC]** in.

   ![](assets/email-bcc.png)

1. Selecteer **[!UICONTROL Ok]**.

Een kopie van alle verzonden berichten voor elke levering op basis van deze sjabloon wordt verzonden naar het e-mailadres BCC dat is geconfigureerd.

Houd rekening met de volgende specifieke kenmerken en aanbevelingen:

* U kunt slechts één BCC-e-mailadres gebruiken.

* Controleer of het BCC-adres voldoende ontvangstcapaciteit heeft om alle verzonden e-mails te archiveren.

* BCC e-mailen <!--with Enhanced MTA--> levert aan het BCC e-mailadres alvorens aan de ontvangers te leveren, wat in BCC berichten kan resulteren die worden verzonden alhoewel de originele leveringen kunnen hebben teruggestuurd. Voor meer informatie over grenzen raadpleegt u [Uitvoeren van fouten begrijpen](../send/delivery-failures.md).

* Als de e-mails die naar het BCC-adres worden verzonden worden geopend en als hierop wordt geklikt, wordt hiermee rekening gehouden in het dialoogvenster **[!UICONTROL Total opens]** en **[!UICONTROL Clicks]** van de send analyse, die sommige misberekeningen zou kunnen veroorzaken.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Meer informatie in de Campaign Classic v7-documentatie**

* [De spiegelpagina genereren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [E-mailindeling selecteren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [Tekencodering selecteren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [Het e-mailadres voor stuiteren instellen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [Sjablonen voor e-mailbezorging gebruiken](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target=&quot;_blank&quot;}

* [Uitvoeren van fouten begrijpen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
