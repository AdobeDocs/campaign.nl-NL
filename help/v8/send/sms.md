---
title: SMS verzenden met Adobe Campaign
description: Aan de slag met SMS in de campagne
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# SMS maken en verzenden

Gebruik Adobe Campaign om persoonlijke SMS-berichten te verzenden.

Leer hoe u aan de slag kunt met SMS-kanaal in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target="_blank"}

>[!NOTE]
>
>Met Adobe Campaign kunt u ook pushmeldingen verzenden via mobiele apparaten **Adobe Campaign Mobile App Channel (NMAC)** -optie. Lees meer in [deze sectie](push.md).

## Sms-kanaal configureren

Als u naar een mobiele telefoon wilt verzenden, hebt u het volgende nodig:

* Een externe account die een connector en type bericht opgeeft.

* Een leveringssjabloon waarin naar deze externe account wordt verwezen.

Leer hoe u een SMS-kanaal configureert in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#sending-messages){target="_blank"}

Voordat u begint met het verzenden van SMS:

* Zorg ervoor dat de ontvangende profielen minstens een mobiele telefoon in hun profiel bevatten.
* De Adobe Campaign Classic bekijken [Best practices voor levering](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"} die ook van toepassing zijn op Campagne v8.

Bovendien moet u met het protocol en de montages van SMS vertrouwd zijn. Doorloop de verbindingsinstelling tussen Adobe Campaign en een SMPP-provider in [dit document](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html#sending-messages){target="_blank"}.

## Je eerste SMS-levering maken

1. Blader naar de **[!UICONTROL Campaigns]** tabblad, klikt u op **[!UICONTROL Deliveries]** en klik op de knop **[!UICONTROL Create]** boven de lijst met bestaande leveringen.

   ![](assets/delivery_step_1.png)

   Raadpleeg voor algemene informatie over het maken van een levering de [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html#sending-messages){target="_blank"}.

1. Selecteer een leveringssjabloon die verwijst naar de relevante externe account om SMS-leveringen te verzenden.

   ![](assets/sms-template-list.png)

   Leer hoe u een SMPP-externe account kunt maken in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#creating-an-smpp-external-account){target="_blank"}

   Leer hoe u een leveringssjabloon maakt voor levering aan mobiele telefoons in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#changing-the-delivery-template){target="_blank"}

1. Identificeer uw levering met een etiket, code, en beschrijving.

1. Klikken **[!UICONTROL Continue]** om het venster van de berichtconfiguratie te bevestigen en te tonen.

1. Voer de inhoud van het bericht in het dialoogvenster **[!UICONTROL Text content]** van de wizard, met inbegrip van personalisatievelden zoals nodig.

   ![](assets/sms-content.png)

1. Selecteer de doelpopulatie.

De belangrijkste stappen om een SMS te creëren en te ontwerpen zijn gedetailleerd in Campaign Classic v7 documentatie:

* SMS maken

  [Meer informatie over het maken van een SMS-verzending](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#sending-messages){target="_blank"}

* De SMS-inhoud ontwerpen

  [Leer hoe u de SMS-inhoud definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#defining-the-sms-content){target="_blank"}

* Selecteer het publiek van uw e-mail

  [Leer hoe u de doelpopulatie definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

Stappen voor het definiëren van een publiek worden gedetailleerd weergegeven op [deze pagina](../start/audiences.md).

## Je SMS testen

Als u de weergave van het bericht met de bijbehorende personalisatie wilt bekijken, klikt u op **[!UICONTROL Preview]** en selecteer een ontvanger.

![](assets/sms-preview.png)

Raadpleeg de volgende secties van de documentatie bij Campaign Classic v7 om een bewijs te verzenden:

* Een levering valideren en proefdrukken verzenden
  [Belangrijke stappen leren om een levering te valideren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target="_blank"}
* Seedadressen toevoegen
  [Meer informatie over zaadadressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## SMS-leveringen verzenden en controleren

De belangrijkste stappen om een SMS te verzenden en te controleren zijn gedetailleerd in Campaign Classic v7 documentatie:

* SMS-leveringen verzenden, controleren en volgen

  [Meer informatie over de tools voor het verzenden, controleren en volgen van SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html#sending-messages){target="_blank"}

* Problemen met SMS-leveringen oplossen

  [Meer informatie over probleemoplossing via SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html#sending-messages){target="_blank"}
