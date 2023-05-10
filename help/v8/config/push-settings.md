---
title: AEP SDK en Campagne integreren
description: Leer hoe u Adobe Experience Platform Mobile SDK kunt integreren met uw app
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: 3bef6d2544a86bf1d5efa4868b82ec59c7e36484
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 2%

---


# AEP SDK + Campagne: pushmeldingskanaal configureren {#push-notification-configuration}

Voordat u pushberichten met Adobe Campaign gaat verzenden, moet u ervoor zorgen dat er configuraties en integratie zijn in de mobiele app en voor tags in Adobe Experience Platform.

Adobe Experience Platform Mobile SDK biedt client-side integratie-API&#39;s voor uw mobiele apparaten via met Android en iOS compatibele SDK&#39;s.

Voer de volgende stappen uit om uw app in te stellen met Adobe Experience Platform Mobile SDK&#39;s:

1. Controleren [voorwaarden](#before-starting).
1. Een [eigenschap mobile tag](#launch-property) in Adobe Experience Platform Data Collection.
1. De Adobe Experience Platform Mobile SDK ophalen als gedetailleerd [op deze pagina](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (optioneel) Schakel registratie- en levenscyclusmetriek in als gedetailleerde [op deze pagina](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (optioneel) Toevoegen [Adobe Experience Platform Assurance voor uw app](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Volg [Adobe Experience Platform Mobile SDK-documentatie](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} voor installatie met Adobe Experience Platform Mobile SDK&#39;s in uw app.
1. Installeren en configureren [Adobe Campaign-extensie](#configure-extension) in uw eigenschap mobile.
1. Configureer uw mobiele iOS- en Android-services in Adobe Campaign als gedetailleerd [op deze pagina](../send/push.md#push-config).


## Vereisten {#before-starting}

### Machtigingen instellen {#setup-permissions}

Voordat u een mobiele toepassing maakt, moet u er eerst voor zorgen dat u over de juiste gebruikersmachtigingen voor tags in Adobe Experience Platform beschikt of deze toewijst. Gebruikersmachtigingen voor tags in Adobe Experience Platform worden aan gebruikers toegewezen via Adobe Admin Console. Meer informatie in [Documentatie over tags](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>De duimconfiguratie moet door een deskundige gebruiker worden uitgevoerd. Afhankelijk van uw implementatiemodel en de personen die bij deze implementatie zijn betrokken, moet u mogelijk de volledige set machtigingen toewijzen aan één productprofiel of machtigingen delen tussen de ontwikkelaar van de app en de ontwikkelaar van de **Adobe Campaign** beheerder.

Om **Eigenschap** en **Bedrijf** rechten, volgt u de onderstaande stappen:

1. Toegang krijgen tot **[!DNL Admin Console]**.
1. Van de **[!UICONTROL Products]** selecteert u de **[!UICONTROL Adobe Experience Platform Data Collection]** kaart.
1. Bestaande selecteren **[!UICONTROL Product Profile]** of maak een nieuwe met de **[!UICONTROL New profile]** knop. Leer hoe u een nieuwe **[!UICONTROL New profile]** in de [Documentatie beheerconsole](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. Selecteer op het tabblad **[!UICONTROL Permissions]** de optie **[!UICONTROL Property Rights]**.
1. Klik op **[!UICONTROL Add all]**. Hiermee voegt u het volgende recht toe aan uw productprofiel:
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Deze machtigingen zijn vereist voor het installeren en publiceren van de Adobe Campaign-extensie en het publiceren van de app-eigenschap in **Adobe Experience Platform Mobile SDK**.

1. Selecteer vervolgens **[!UICONTROL Company rights]** in het linkermenu.
1. Voeg de volgende rechten toe:

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   Deze machtigingen zijn vereist voor de ontwikkelaar van de mobiele app om pushgegevens in te stellen in **Adobe Experience Platform-gegevensverzameling**.

1. Klik op **[!UICONTROL Save]**.

Om dit toe te wijzen **[!UICONTROL Product profile]** aan gebruikers, volg de hieronder stappen:

1. Toegang krijgen tot **[!DNL Admin Console]**.
1. Van de **[!UICONTROL Products]** selecteert u de **[!UICONTROL Adobe Experience Platform Data Collection]** kaart.
1. Selecteer de eerder geconfigureerde **[!UICONTROL Product profile]**.
1. Klik op het tabblad **[!UICONTROL Users]** op **[!UICONTROL Add user]**.
1. Typ de naam of het e-mailadres van uw gebruiker en selecteer de gebruiker. Klik vervolgens op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Als de gebruiker niet eerder in de Admin console werd gecreeerd, verwijs naar [Gebruikersdocumentatie toevoegen](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Uw app configureren {#configure-app}

De technische opstelling impliceert nauwe samenwerking tussen de toepassingsontwikkelaar en bedrijfsbeheerder. Voordat u begint met het verzenden van pushberichten met [!DNL Adobe Campaign], moet u instellingen definiëren in [!DNL Adobe Experience Platform Data Collection] en integreer uw mobiele app met Adobe Experience Platform Mobile SDK&#39;s.

Voer de implementatiestappen uit die in de onderstaande koppelingen worden beschreven:

* Voor **Apple iOS**: Leer hoe u uw app registreert bij APN&#39;s in [Apple-documentatie](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* Voor **Google Android**: Leer hoe u een Firebase Cloud Messaging-clienttoepassing op Android instelt in [Google-documentatie](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## Een eigenschap voor een mobiele tag instellen in de gegevensverzameling van Adobe Experience Platform {#launch-property}

Als u een eigenschap voor mobiele apparaten instelt, kan de ontwikkelaar of markator van de mobiele app de mobiele SDK&#39;s configureren. Normaal gesproken maakt u een eigenschap mobile voor elke mobiele toepassing die u wilt beheren. Leer hoe u een mobiele eigenschap kunt maken en configureren in [Adobe Experience Platform Mobile SDK-documentatie](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

Als u de SDK&#39;s die nodig zijn voor pushmeldingen wilt gebruiken, hebt u de volgende SDK-extensies nodig, voor zowel Android als iOS:

* **[!UICONTROL Mobile Core]** (automatisch geïnstalleerd)
* **[!UICONTROL Profile]** (automatisch geïnstalleerd)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optioneel, maar aanbevolen voor foutopsporing in de mobiele implementatie.

Meer informatie over [!DNL Adobe Experience Platform Data Collection] tags in [Adobe Experience Platform-documentatie](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Nadat u de nieuwe eigenschap tag hebt gemaakt, opent u de nieuwe eigenschap tag en maakt u een bibliotheek. Dit doet u als volgt:

1. Bladeren naar **Publishing Flow** in de linkernavigatie en selecteer **Bibliotheek toevoegen**.
1. Voer de naam van de bibliotheek in en selecteer de omgeving.
1. Selecteren **Alle gewijzigde bronnen toevoegen**, en **Opslaan en samenstellen voor ontwikkeling**.
1. Stel ten slotte deze bibliotheek in als de werkbibliotheek in het dialoogvenster **Een werkbibliotheek selecteren** knop.


## Adobe Campaign-extensie configureren in uw mobiele eigenschap {#configure-extension}

De **Adobe Campaign Classic-extensie** voor Adobe Experience Platform Mobile SDK&#39;s kunt u pushmeldingen voor uw mobiele apps maken en gebruikers-pushtokens verzamelen en interactiemetingen beheren met Adobe Experience Platform-services.

Deze extensie is vooraf geïnstalleerd op uw omgeving en moet worden geconfigureerd. Voer de volgende stappen uit om de extensie voor de eigenschap mobile tag te configureren:

1. Open de eigenschap tag die u eerder hebt gemaakt.
1. Blader vanuit de linkernavigatie naar **Extensies** en opent u de **Catalogus** tab. Gebruik het zoekveld om het **Adobe Campaign Classic** extensie.
1. Klik op de Campaign Classic-kaart op de knop **Installeren** knop.
1. Voer de instellingen in zoals beschreven in [Adobe Experience Platform Mobile SDK-documentatie](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

U kunt nu campagne toevoegen aan uw app, zoals beschreven in  [Adobe Experience Platform Mobile SDK-documentatie](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Uw mobiele services configureren in Campagne{#push-service}

Zodra uw mobiele app is ingesteld in [!DNL Adobe Experience Platform Data Collection], moet u twee services maken (één voor iOS-apparaten, één voor Android-apparaten) om pushberichten te kunnen verzenden van **[!DNL Adobe Campaign]**.

Leer hoe u een service voor iOS- en Android-pushmeldingen kunt maken en configureren in [deze sectie](../send/push.md#push-config).
