---
title: SMS verzenden met Adobe Campaign
description: Aan de slag met SMS in de campagne
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 1%

---

# SMS maken en verzenden

Gebruik Adobe Campaign om persoonlijke SMS-berichten te verzenden.

![](../assets/do-not-localize/book.png) Leer hoe u aan de slag kunt met SMS-kanaal in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}

>[!NOTE]
>
>Met Adobe Campaign kunt u ook pushmeldingen verzenden via mobiele apparaten **Adobe Campaign Mobile App Channel (NMAC)** optie. Meer informatie in [deze sectie](push.md).

## Sms-kanaal configureren

Als u naar een mobiele telefoon wilt verzenden, hebt u het volgende nodig:

* Een externe account die een connector en type bericht opgeeft.

* Een leveringssjabloon waarin naar deze externe account wordt verwezen.

![](../assets/do-not-localize/book.png)  Leer hoe u een SMS-kanaal configureert in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}

Voordat u begint met het verzenden van SMS:

* Zorg ervoor dat de ontvangende profielen minstens een mobiele telefoon in hun profiel bevatten.
* De Adobe Campaign Classic bekijken [Best practices voor levering](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;} die ook van toepassing zijn op Campagne v8.

Bovendien moet u met het protocol en de montages van SMS vertrouwd zijn. Doorloop de verbindingsinstelling tussen Adobe Campaign en een SMPP-provider in [dit document](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

## Je eerste SMS-levering maken

1. Blader naar de **[!UICONTROL Campaigns]** tabblad, klikt u op **[!UICONTROL Deliveries]** en klik op de knop **[!UICONTROL Create]** boven de lijst met bestaande leveringen.

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) Voor globale informatie over hoe te om een levering tot stand te brengen, verwijs naar [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

1. Selecteer een leveringssjabloon die verwijst naar de relevante externe account om SMS-leveringen te verzenden.

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) Leer hoe u een SMPP-externe account kunt maken in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png) Leer hoe u een leveringssjabloon maakt voor levering aan mobiele telefoons in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}

1. Identificeer uw levering met een etiket, code, en beschrijving.

1. Klikken **[!UICONTROL Continue]** om het venster van de berichtconfiguratie te bevestigen en te tonen.

1. Voer de inhoud van het bericht in het dialoogvenster **[!UICONTROL Text content]** van de wizard, met inbegrip van personalisatievelden zoals nodig.

   ![](assets/sms-content.png)

1. Selecteer de doelpopulatie.

De belangrijkste stappen om een SMS te creëren en te ontwerpen zijn gedetailleerd in Campaign Classic v7 documentatie:

* Een sms maken

   ![](../assets/do-not-localize/book.png) [Meer informatie over het maken van een SMS-verzending](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* De SMS-inhoud ontwerpen

   ![](../assets/do-not-localize/book.png) [Leer hoe u de SMS-inhoud definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* Selecteer het publiek van uw e-mail

   ![](../assets/do-not-localize/book.png) [Leer hoe u de doelpopulatie definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) Stappen voor het definiëren van een publiek worden gedetailleerd weergegeven op [deze pagina](../start/audiences.md).

## Je SMS testen

Als u de weergave van het bericht met de bijbehorende personalisatie wilt bekijken, klikt u op **[!UICONTROL Preview]** en selecteer een ontvanger.

![](assets/sms-preview.png)

Raadpleeg de volgende secties van de Campaign Classic v7-documentatie voor het verzenden van een proefdruk:

* Een levering valideren en proefdrukken verzenden
   ![](../assets/do-not-localize/book.png) [Belangrijke stappen om een levering te valideren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* Seedadressen toevoegen
   ![](../assets/do-not-localize/book.png) [Meer informatie over zaadadressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## SMS-leveringen verzenden en controleren

De belangrijkste stappen om een SMS te verzenden en te controleren zijn gedetailleerd in Campaign Classic v7 documentatie:

* SMS-leveringen verzenden, controleren en volgen

   ![](../assets/do-not-localize/book.png) [Meer informatie over de tools voor het verzenden, controleren en volgen van SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Problemen met SMS-leveringen oplossen

   ![](../assets/do-not-localize/book.png) [Meer informatie over probleemoplossing via SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
