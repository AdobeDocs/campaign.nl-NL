---
product: Adobe Campaign
title: Pushmelding verzenden met Adobe Campaign
description: Aan de slag met pushmeldingen in Campagne
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: b0fcdefb638a2424e9464cf520724cc492fabc55
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 0%

---

# Pushmeldingen maken en verzenden

Met de levering van mobiele apps kunt u meldingen verzenden naar iOS- en Android-systemen.

Als u pushberichten wilt verzenden in Adobe Campaign, moet u:

1. De Campagneomgeving configureren
1. Maak een informatieservice voor mobiele toepassingen van het type Mobiele toepassing.
1. Voeg de iOS- en Android-versies van de toepassing toe aan deze service.
1. Maak een levering voor zowel iOS als Android.

[!DNL :arrow_upper_right:] Leer hoe u aan de slag kunt met de mobiele app in de  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Integreren met Adobe SDK

### Campagne SDK integreren

De campagne-SDK vereenvoudigt de integratie van uw mobiele toepassing in het Adobe Campaign-platform.

[!DNL :arrow_upper_right:] Leer hoe u de Campagne SDK kunt integreren met uw app in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### Campagneextensie configureren in Launch

U kunt Adobe Experience Platform Launch SDK integreren met Campagne door de extensie Campaign Classic te gebruiken.

[!DNL :arrow_upper_right:] Meer informatie in de documentatie van  [Adobe Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Uw toepassingsinstellingen configureren in Campagne

U moet de instellingen voor iOS- en Android-apps definiëren in Adobe Campaign.

[!DNL :arrow_upper_right:] De configuratierichtlijnen voor iOS worden beschreven in de documentatie van  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

[!DNL :arrow_upper_right:] De configuratierichtlijnen voor Android worden beschreven in de  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Uw eerste pushmelding maken

In deze sectie worden de elementen beschreven die specifiek zijn voor de levering van iOS- en Android-berichten.

[!DNL :arrow_upper_right:] Alle stappen voor het maken van pushmeldingen worden beschreven in de documentatie bij  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)

>[!CAUTION]
>
>Met Campagne v8 is mobiele registratie nu **asynchroon**. [Meer informatie](../dev/staging.md)

Als u een nieuwe levering wilt maken, bladert u naar het tabblad **[!UICONTROL Campaigns]**, klikt u op **[!UICONTROL Deliveries]** en klikt u op de knop **[!UICONTROL Create]** boven de lijst met bestaande leveringen.

![](assets/delivery_step_1.png)

### Meldingen verzenden op iOS {#sending-notifications-on-ios}

1. Selecteer de **[!UICONTROL Deliver on iOS]** leveringsmalplaatje en klik **[!UICONTROL Continue]**.

   ![](assets/push-template-ios.png)

1. Als u het doel van de melding wilt definiëren, klikt u op de koppeling **[!UICONTROL To]** en vervolgens op **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. Selecteer **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, selecteer de service die relevant is voor uw mobiele toepassing en selecteer vervolgens de iOS-versie van de toepassing.

   ![](assets/push-ios-subscribers.png)

1. Selecteer het berichttype: **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** of **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. Voer in het veld **[!UICONTROL Title]** het label in van de titel die u in het bericht wilt weergeven.

1. Voer **[!UICONTROL Message]** en **[!UICONTROL Value of the badge]** in op basis van het gekozen berichttype.

1. Met **[!UICONTROL Action button]** kunt u een label definiëren voor de actieknop die wordt weergegeven in de waarschuwingsberichten (**action_loc_key** veld van de payload).

1. Selecteer in het veld **[!UICONTROL Play a sound]** het geluid dat door de mobiele terminal moet worden afgespeeld wanneer het bericht wordt ontvangen.

1. Voer in het veld **[!UICONTROL Application variables]** de waarde van elke variabele in. U kunt bijvoorbeeld een specifiek toepassingsscherm configureren dat wordt weergegeven wanneer de gebruiker het bericht activeert.

1. Zodra het bericht wordt gevormd, klik **[!UICONTROL Preview]** lusje om voorproef de bericht.

   ![](assets/push-ios-preview.png)

### Meldingen verzenden op Android {#sending-notifications-on-android}

1. Selecteer de leveringssjabloon **[!UICONTROL Deliver on Android (android)]**.

   <!--![](assets/push-template-android.png)-->

1. Als u het doel van de melding wilt definiëren, klikt u op de koppeling **[!UICONTROL To]** en vervolgens op **[!UICONTROL Add]**.

   <!--![](assets/nmac_delivery_android_2.png)-->

1. Selecteer **[!UICONTROL Subscribers of an Android mobile application]**, kies de dienst relevant voor uw mobiele toepassing (in dit geval Neotrips), dan selecteer de Android versie van de toepassing.

   <!--![](assets/push-android-select-target.png)-->

1. Voer vervolgens de inhoud voor het bericht in.

   <!--![](assets/push-android-content.png)-->

1. Klik op het pictogram **[!UICONTROL Insert emoticon]** om emoticons in te voegen bij uw pushmelding.

1. Voer in het veld **[!UICONTROL Application variables]** de waarde van elke variabele in. U kunt bijvoorbeeld een specifiek toepassingsscherm configureren dat wordt weergegeven wanneer de gebruiker het bericht activeert.

1. Zodra het bericht wordt gevormd, klik **[!UICONTROL Preview]** lusje om voorproef de bericht.

   <!--![](assets/push-android-preview.png)-->

## Uw pushmeldingen testen, verzenden en controleren

Als u een bewijs wilt verzenden en de uiteindelijke levering wilt verzenden, gebruikt u hetzelfde proces als voor e-mailleveringen.

Nadat u berichten hebt verzonden, kunt u de leveringen controleren en volgen.