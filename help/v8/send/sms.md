---
product: Adobe Campaign
title: SMS verzenden met Adobe Campaign
description: Aan de slag met SMS in de campagne
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: 35814053bff993d0b130bf598c8601c3f5adc407
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 1%

---

# SMS maken en verzenden

Gebruik Adobe Campaign om persoonlijke SMS-berichten te verzenden.

[!DNL :arrow_upper_right:] Leer hoe u aan de slag kunt met SMS-kanalen in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html)

>[!NOTE]
>
>Met Adobe Campaign kunt u ook pushmeldingen verzenden voor mobiele apparaten via de optie **Adobe Campaign Mobile App Channel (NMAC)**. Meer informatie vindt u in [deze sectie](push.md).

## Sms-kanaal configureren

Als u naar een mobiele telefoon wilt verzenden, hebt u het volgende nodig:

* Een externe account die een connector en type bericht opgeeft.

* Een leveringssjabloon waarin naar deze externe account wordt verwezen.

[!DNL :arrow_upper_right:]  Leer hoe u een SMS-kanaal configureert in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages)

Voordat u begint met het verzenden van SMS:

* Zorg ervoor dat de ontvangende profielen minstens een mobiele telefoon in hun profiel bevatten.
* Bekijk de Adobe Campaign Classic [Best practices voor levering](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages) die ook van toepassing zijn op Campagne v8.

Bovendien moet u met het protocol en de montages van SMS vertrouwd zijn. Doorloop de verbindingsopstelling tussen Adobe Campaign en een leverancier SMPP in [dit document](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages).

## Je eerste SMS-levering maken

1. Als u een nieuwe levering wilt maken, bladert u naar het tabblad **[!UICONTROL Campaigns]**, klikt u op **[!UICONTROL Deliveries]** en klikt u op de knop **[!UICONTROL Create]** boven de lijst met bestaande leveringen.

   ![](assets/delivery_step_1.png)

   [!DNL :arrow_upper_right:] Raadpleeg de  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages) voor algemene informatie over het maken van een levering.

1. Selecteer een leveringssjabloon die verwijst naar de relevante externe account om SMS-leveringen te verzenden.

   ![](assets/sms-template-list.png)

   [!DNL :arrow_upper_right:] Leer hoe u een externe SMPP-account kunt maken in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account)

   [!DNL :arrow_upper_right:] Leer hoe u een leveringssjabloon kunt maken voor mobiele apparaten in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template)

1. Identificeer uw levering met een etiket, code, en beschrijving.

1. Klik **[!UICONTROL Continue]** om het venster van de berichtconfiguratie te bevestigen en te tonen.

1. Typ de inhoud van het bericht in de sectie **[!UICONTROL Text content]** van de wizard, inclusief de velden voor het aanpassen van de inhoud.

   ![](assets/sms-content.png)

1. Selecteer de doelpopulatie.

De belangrijkste stappen om een SMS te creëren en te ontwerpen zijn gedetailleerd in Campaign Classic v7 documentatie:

* Een sms maken

   [!DNL :arrow_upper_right:] [Meer informatie over het maken van een SMS-verzending](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages)

* De SMS-inhoud ontwerpen

   [!DNL :arrow_upper_right:] [Leer hoe u de SMS-inhoud definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content)

* Selecteer het publiek van uw e-mail

   [!DNL :arrow_upper_right:] [Leer hoe u de doelpopulatie definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)

[!DNL :bulb:] De stappen om een publiek te bepalen zijn gedetailleerd op  [deze pagina](../start/audiences.md).

## Je SMS testen

Als u de weergave van het bericht met de bijbehorende personalisatie wilt bekijken, klikt u op **[!UICONTROL Preview]** en selecteert u een ontvanger.

![](assets/sms-preview.png)

Raadpleeg de volgende secties van de Campaign Classic v7-documentatie voor het verzenden van een proefdruk:

* Een levering valideren en proefdrukken verzenden
   [!DNL :arrow_upper_right:] [Belangrijke stappen om een levering te valideren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* Seedadressen toevoegen
   [!DNL :arrow_upper_right:] [Meer informatie over zaadadressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## SMS-leveringen verzenden en controleren

De belangrijkste stappen om een SMS te verzenden en te controleren zijn gedetailleerd in Campaign Classic v7 documentatie:

* SMS-leveringen verzenden, controleren en volgen

   [!DNL :arrow_upper_right:] [Meer informatie over de tools voor het verzenden, controleren en volgen van SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages)
* Problemen met SMS-leveringen oplossen

   [!DNL :arrow_upper_right:] [Meer informatie over probleemoplossing via SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages)
