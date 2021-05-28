---
solution: Campaign v8
product: Adobe Campaign
title: Pushmelding verzenden met Adobe Campaign
description: Aan de slag met pushmeldingen in Campagne
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

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

[!DNL :arrow_upper_right:] Leer hoe u uw eerste pushmeldingen maakt in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>Met Campagne v8 mobile registration is now **asynchroon**. [Meer informatie](../dev/staging.md).
