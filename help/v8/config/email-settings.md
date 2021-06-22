---
product: Adobe Campaign
title: Instellingen voor e-mailkanalen voor campagne
description: Instellingen voor e-mailkanalen voor campagne
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 2%

---

# Instellingen voor e-mailkanalen voor campagne

## BCC e-mailen

U kunt Adobe Campaign zo configureren dat een kopie van de e-mails die u van uw platform hebt ontvangen, bewaard blijft.

>[!NOTE]
>BCC-functionaliteit voor e-mail is optioneel. Controleer hiervoor uw licentieovereenkomst.

Adobe Campaign zelf beheert gearchiveerde bestanden niet. Het laat u toe om de berichten van uw keus naar een specifiek adres te verzenden, van waar zij kunnen worden verwerkt en worden gearchiveerd gebruikend een extern systeem.

Hiervoor worden .eml-bestanden die overeenkomen met de verzonden e-mails, overgebracht naar een externe server, zoals een SMTP-e-mailserver. De archiveringsbestemming is een BCC e-mailadres (onzichtbaar voor de leverende ontvangers) dat u moet specificeren.

Let op:

* U kunt **één** BCC e-mailadres slechts gebruiken.

* Er wordt alleen rekening gehouden met e-mailberichten die zijn verzonden, maar met bedragen.

[!DNL :speech_balloon:] Als gebruiker van Beheerde Cloud Services  [neemt u contact op met ](../start/campaign-faq.md#support) Adobe om e-mail-BCC te activeren in Campagne. Het BCC e-mailadres van uw keus moet aan het team van de Adobe worden verstrekt die het voor u zal vormen.

Zodra e-mail BCC wordt gevormd, zorg ervoor de eigenschap in het leveringsmalplaatje of in de levering door de **e-mailBCC** optie wordt toegelaten.

![](assets/email-bcc.png)


**Verwante** onderwerpen in Campaign Classic v7 documentatie:


[!DNL :arrow_upper_right:] [De spiegelpagina](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page) genereren{target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [E-mailindeling](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats) selecteren{target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Tekencodering](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding) selecteren{target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Stel het e-mailadres](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails) voor de stuiterende waarde in {target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [E-mailleveringssjablonen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html) gebruiken{target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Uitleveringsfouten](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html) begrijpen {target=&quot;_blank&quot;}
