---
title: AEP SDK en Campagne integreren
description: Leer hoe u Adobe Experience Platform Mobile SDK kunt integreren met uw app
feature: Push
role: Admin, Developer
level: Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 1a75f411-3f71-4114-b738-277820dc6138
source-git-commit: 784c74aaff23dbf1f35c6e8153f90610048e1c07
workflow-type: tm+mt
source-wordcount: '1679'
ht-degree: 4%

---

# Pushmeldingskanaal configureren {#push-notification-configuration}

Als u pushmeldingen wilt verzenden met Adobe Campaign, moet u eerst uw omgeving en app configureren zoals in deze pagina wordt beschreven. In Adobe Campaign is het kanaal voor het verzenden van pushmeldingen het mobiele app-kanaal.

>[!CAUTION]
>
>In 2024 komt er een versie met enkele belangrijke wijzigingen voor de service FCM (Android Firebase Cloud Messaging). Deze kunnen van invloed zijn op uw Adobe Campaign-implementatie. De configuratie van uw lidmaatschapsservices voor Android-pushberichten moet mogelijk worden bijgewerkt om deze wijziging te ondersteunen. U kunt het nu al controleren en actie ondernemen.

Voordat u pushberichten met Adobe Campaign gaat verzenden, moet u ervoor zorgen dat er configuraties en integratie zijn in de mobiele app en voor tags in Adobe Experience Platform. Adobe Experience Platform Mobile SDK biedt client-side integratie-API&#39;s voor uw mobiele apparaten via met Android en iOS compatibele SDK&#39;s.

Voer de volgende stappen uit om uw app in te stellen met Adobe Experience Platform Mobile SDK&#39;s:

1. Controle [&#x200B; eerste vereisten &#x200B;](#before-starting).
1. Opstelling a [&#x200B; mobiel markeringsbezit &#x200B;](#launch-property) in de Inzameling van Gegevens van Adobe Experience Platform.
1. Krijg Adobe Experience Platform Mobile SDK zoals gedetailleerd [&#x200B; in deze pagina &#x200B;](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (facultatief) laat registreren en levenscyclusmetriek toe, zoals gedetailleerd [&#x200B; in deze pagina &#x200B;](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (facultatief) voeg [&#x200B; Adobe Experience Platform Assurance aan uw app &#x200B;](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} toe om uw implementatie te bevestigen. Leer hoe te om de uitbreiding van Adobe Experience Platform Assurance [&#x200B; in deze pagina &#x200B;](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"} uit te voeren.
1. Vorm uw mobiele diensten van iOS en van Android in Adobe Campaign zoals gedetailleerd [&#x200B; in deze pagina &#x200B;](#push-service).
1. Installeer en vorm [&#x200B; Uitbreiding van Adobe Campaign &#x200B;](#configure-extension) in uw mobiel bezit.
1. Volg [&#x200B; de Mobiele documentatie van SDK van Adobe Experience Platform Mobile &#x200B;](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} om opstelling met Adobe Experience Platform Mobile SDKs in uw app te krijgen.

## Vereisten {#before-starting}

### Machtigingen instellen {#setup-permissions}

Voordat u een mobiele toepassing maakt, moet u er eerst voor zorgen dat u over de juiste gebruikersmachtigingen voor tags in Adobe Experience Platform beschikt of deze toewijst. Gebruikersmachtigingen voor tags in Adobe Experience Platform worden aan gebruikers toegewezen via Adobe Admin Console. Leer meer in [&#x200B; documentatie van Markeringen &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>De duimconfiguratie moet door een deskundige gebruiker worden uitgevoerd. Afhankelijk van uw implementatiemodel en persona&#39;s betrokken bij deze implementatie, zou u de volledige reeks toestemmingen aan één enkel productprofiel kunnen moeten toewijzen of toestemmingen tussen de app ontwikkelaar en **Adobe Campaign** beheerder delen.

Om **Bezit** en **bedrijf** rechten toe te wijzen, volg hieronder de stappen:

1. Open de lus **[!DNL Admin Console]** .
1. Selecteer op het tabblad **[!UICONTROL Products]** de **[!UICONTROL Adobe Experience Platform Data Collection]** -kaart.
1. Selecteer een bestaande **[!UICONTROL Product Profile]** of maak een nieuwe **[!UICONTROL New profile]** met de knop. Leer hoe te om een nieuw **[!UICONTROL New profile]** in de [&#x200B; Admin consoledocumentatie &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"} tot stand te brengen.
1. Selecteer op het tabblad **[!UICONTROL Permissions]** de optie **[!UICONTROL Property Rights]**.
1. Klik op **[!UICONTROL Add all]**. Hiermee voegt u het volgende recht toe aan uw productprofiel:
   * **[!UICONTROL Approve]**
   * **[!UICONTROL Develop]**
   * **[!UICONTROL Edit Property]**
   * **[!UICONTROL Manage Environments]**
   * **[!UICONTROL Manage Extensions]**
   * **[!UICONTROL Publish]**

   Deze toestemmingen worden vereist om de uitbreiding van Adobe Campaign te installeren en te publiceren, en app bezit in **Adobe Experience Platform Mobile SDK** te publiceren.

1. Selecteer vervolgens **[!UICONTROL Company rights]** in het linkermenu.
1. Voeg de volgende rechten toe:

   * **[!UICONTROL Manage App Configurations]**
   * **[!UICONTROL Manage Properties]**

   Deze toestemmingen worden vereist voor de mobiele toepassingsontwikkelaar aan opstellings dupgeloofsbrieven in **de Inzameling van Gegevens van Adobe Experience Platform**.

1. Klik op **[!UICONTROL Save]**.

Volg onderstaande stappen om deze **[!UICONTROL Product profile]** aan gebruikers toe te wijzen:

1. Open de lus **[!DNL Admin Console]** .
1. Selecteer op het tabblad **[!UICONTROL Products]** de **[!UICONTROL Adobe Experience Platform Data Collection]** -kaart.
1. Selecteer de eerder geconfigureerde **[!UICONTROL Product profile]**.
1. Klik op het tabblad **[!UICONTROL Users]** op **[!UICONTROL Add user]**.
1. Typ de naam of het e-mailadres van uw gebruiker en selecteer de gebruiker. Klik vervolgens op **[!UICONTROL Save]** .

   >[!NOTE]
   >
   >Als de gebruiker niet eerder in de console Admin werd gecreeerd, verwijs naar [&#x200B; gebruikersdocumentatie &#x200B;](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"} toevoegen.

### Uw app configureren {#configure-app}

De technische opstelling impliceert nauwe samenwerking tussen de toepassingsontwikkelaar en bedrijfsbeheerder. Voordat u begint met het verzenden van pushberichten met [!DNL Adobe Campaign] , moet u instellingen definiëren in [!DNL Adobe Experience Platform Data Collection] en uw mobiele app integreren met Adobe Experience Platform Mobile SDK&#39;s.

Voer de implementatiestappen uit die in de onderstaande koppelingen worden beschreven:

* Voor **Apple iOS**: Leer hoe te om uw app met APNs in [&#x200B; Documentatie van Apple &#x200B;](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"} te registreren
* Voor **Google Android**: Leer hoe te opstelling een de cliëntapp van het Overseinen van de Wolk van de Wolk van de Vuurbasis op Android in [&#x200B; Documentatie van Google &#x200B;](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

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

Als u een eigenschap voor mobiele apparaten instelt, kan de ontwikkelaar of markator van de mobiele app de mobiele SDK&#39;s configureren. Doorgaans maakt u een eigenschap voor mobiele apparaten voor elke mobiele toepassing die u wilt beheren. Leer hoe te om een mobiel bezit in [&#x200B; Adobe Experience Platform Mobiele documentatie van SDK &#x200B;](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"} tot stand te brengen en te vormen.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

Leer meer over [!DNL Adobe Experience Platform Data Collection] markeringen in [&#x200B; documentatie van Adobe Experience Platform &#x200B;](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Nadat u de nieuwe eigenschap tag hebt gemaakt, opent u de nieuwe eigenschap tag en maakt u een bibliotheek. Dit doet u als volgt:

1. Blader aan **het Publiceren Stroom** in de linkernavigatie en selecteer **Bibliotheek** toevoegen.
1. Voer de naam van de bibliotheek in en selecteer de omgeving.
1. Selecteer **toevoegen Alle Gewijzigde Middelen**, en **sparen en bouwen aan ontwikkeling**.
1. Tot slot plaats deze bibliotheek als uw werkende bibliotheek van **Uitgezochte een werkende bibliotheek** knoop.

## Uw mobiele services configureren in Campagne {#push-service}

Wanneer uw mobiele app is ingesteld in [!DNL Adobe Experience Platform Data Collection] , moet u twee services maken (een voor iOS-apparaten, een voor Android-apparaten) om pushmeldingen te kunnen verzenden vanuit **[!DNL Adobe Campaign]** .

Pushberichten worden via een speciale service naar gebruikers van de app verzonden. Wanneer gebruikers uw app installeren, abonneren zij zich op deze service: Adobe Campaign vertrouwt op deze service om alleen de abonnees van uw app als doel in te stellen. In deze service moet u iOS- en Android-apps toevoegen om op iOS- en Android-apparaten te verzenden.

Voer de onderstaande stappen uit om een service te maken voor het verzenden van pushberichten:

1. Blader naar de tab **[!UICONTROL Profiles and Targets > Services and Subscriptions]** en klik op **[!UICONTROL Create]** .

   ![](assets/new-service-push.png){width="800" align="left"}

1. Voer een **[!UICONTROL Label]** en een **[!UICONTROL Internal name]** in en selecteer een **[!UICONTROL Mobile application]** -type.

   >[!NOTE]
   >
   >Het gebrek **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** doelafbeelding is verbonden met de ontvankelijkheidstabel. Als u een andere doelafbeelding wilt gebruiken, moet u een nieuwe doeltoewijzing maken en deze invoeren in het veld **[!UICONTROL Target mapping]** van de service. Leer meer over doelafbeeldingen in [&#x200B; deze pagina &#x200B;](../audiences/target-mappings.md).

1. Vervolgens gebruikt u het pictogram **[!UICONTROL Add]** rechts in het scherm om de mobiele toepassingen te definiëren die deze service gebruiken.

>[!BEGINTABS]

>[!TAB  iOS ]

Ga als volgt te werk om een app voor iOS-apparaten te maken:

1. Selecteer **[!UICONTROL Create an iOS application]** en klik op **[!UICONTROL Next]**.

   ![](assets/new-ios-app.png){width="600" align="left"}

1. Voer in het veld **[!UICONTROL Label]** de naam van uw toepassing in.
1. (optioneel) U kunt inhoud van een pushbericht verrijken met wat **[!UICONTROL Application variables]** . Deze zijn volledig aanpasbaar en een deel van de berichtlading wordt verzonden naar het mobiele apparaat.

   In het voorbeeld hieronder, worden **mediaURl** en **mediaExt** variabelen toegevoegd om rijke pushmelding tot stand te brengen en dan de toepassing van het beeld te voorzien om binnen het bericht te tonen.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. Blader naar het **[!UICONTROL Subscription parameters]** lusje om de afbeelding met een uitbreiding van het **[!UICONTROL Subscriber applications (nms:appsubscriptionRcpte bepalen)]** schema.

1. Blader naar het tabblad **[!UICONTROL Sounds]** om het af te spelen geluid te definiëren. Klik op **[!UICONTROL Add]** en vul **[!UICONTROL Internal name]** veld in dat de naam moet bevatten van het bestand dat is ingesloten in de toepassing of de naam van het systeemgeluid.

1. Klik op **[!UICONTROL Next]** om de ontwikkeltoepassing te configureren.

1. De integratiesleutel is specifiek voor elke toepassing. De mobiele toepassing wordt aan Adobe Campaign gekoppeld.

   Zorg ervoor dat dezelfde **[!UICONTROL Integration key]** is gedefinieerd in Adobe Campaign en in de toepassingscode via de SDK.

   Leer meer in [&#x200B; de documentatie van de Ontwikkelaar &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]** is volledig aanpasbaar met tekenreekswaarde, maar moet precies hetzelfde zijn als de waarde die in de SDK is opgegeven.
   >
   > U kunt niet hetzelfde certificaat gebruiken voor de ontwikkelingsversie (sandbox) en de productieversie van de toepassing.

1. Selecteer het pictogram in het veld **[!UICONTROL Application icon]** om de mobiele toepassing in uw service aan te passen.

1. Selecteer het **[!UICONTROL Authentication mode]**. Er zijn twee modi beschikbaar:

   * (Aanbevolen) **[!UICONTROL Token-based authentication]**: vul de instellingen voor de APNs-verbinding in **[!UICONTROL Key Id]** , **[!UICONTROL Team Id]** en **[!UICONTROL Bundle Id]** en selecteer vervolgens het p8-certificaat door op **[!UICONTROL Enter the private key...]** te klikken. Voor meer op **[!UICONTROL Token-based authentication]**, verwijs naar [&#x200B; documentatie van Apple &#x200B;](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**: Klik op **[!UICONTROL Enter the certificate...]** en selecteer de p12-toets. Voer vervolgens het wachtwoord in dat door de ontwikkelaar van de mobiele toepassing is opgegeven. Dit certificaat heeft een vervaldatum en moet jaarlijks worden vernieuwd. Om een onderbreking van de dienst voor uw gebruikers te vermijden, werk uw certificaten bij alvorens zij verlopen. Certificaten zijn een jaar geldig en u moet ze bijwerken om te kunnen blijven communiceren met APN&#39;s.

1. Gebruik de knop **[!UICONTROL Test the connection]** om uw configuratie te valideren.

1. Klik op **[!UICONTROL Next]** om de productietoepassing te configureren en dezelfde stappen uit te voeren als hierboven beschreven.

1. Klik op **[!UICONTROL Finish]**.

Uw iOS-toepassing kan nu worden gebruikt in Campagne.

>[!TAB  Android ]

Ga als volgt te werk om een app voor Android-apparaten te maken:

1. Selecteer **[!UICONTROL Create an Android application]** en klik op **[!UICONTROL Next]**.

   ![](assets/new-android-app.png){width="600" align="left"}

1. Voer in het veld **[!UICONTROL Label]** de naam van uw toepassing in.
1. De integratiesleutel is specifiek voor elke toepassing. De mobiele toepassing wordt aan Adobe Campaign gekoppeld.

   Zorg ervoor dat dezelfde **[!UICONTROL Integration key]** is gedefinieerd in Adobe Campaign en in de toepassingscode via de SDK.

   Leer meer in [&#x200B; de documentatie van de Ontwikkelaar &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > **[!UICONTROL Integration key]** is volledig aanpasbaar met tekenreekswaarde, maar moet precies hetzelfde zijn als de waarde die in de SDK is opgegeven.
   >

1. Selecteer het pictogram in het veld **[!UICONTROL Application icon]** om de mobiele toepassing in uw service aan te passen.
1. Selecteer **HTTP v1** in **[!UICONTROL API version]** drop-down lijst.
1. Klik op de koppeling **[!UICONTROL Load project json file to extract project details...]** om het JSON-sleutelbestand te laden. Voor meer informatie over hoe te om uw JSON- dossier te halen, verwijs naar [&#x200B; de documentatie van de Vuurbasis van Google &#x200B;](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   U kunt ook handmatig de volgende gegevens invoeren:
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. Gebruik de knop **[!UICONTROL Test the connection]** om uw configuratie te valideren.

   >[!CAUTION]
   >
   >De knop **[!UICONTROL Test connection]** controleert niet of de server voor midsourcing (MID) toegang heeft tot de FCM-server.

1. (optioneel) U kunt desgewenst de inhoud van een pushbericht verrijken met wat **[!UICONTROL Application variables]** . Deze zijn volledig aanpasbaar en een deel van de berichtlading wordt verzonden naar het mobiele apparaat.

1. Klik op **[!UICONTROL Finish]** en vervolgens op **[!UICONTROL Save]** . Uw Android-toepassing kan nu worden gebruikt in Campagne.

Hieronder vindt u de namen van FCM-ladingen om uw pushmelding verder aan te passen:

| Berichttype | Configureerbaar berichtelement (FCM-ladenaam) | Configureerbare opties (FCM-ladenaam) |
|:-:|:-:|:-:|
| gegevensbericht | N.v.t. | validate_only |
| meldingsbericht | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]

## Adobe Campaign-extensie configureren in uw mobiele eigenschap {#configure-extension}

De **uitbreiding van Adobe Campaign Classic** voor de bevoegdheden van Adobe Experience Platform Mobile SDKs duwt berichten voor uw mobiele apps en helpt u gebruikersdrukknoppennen verzamelen en interactiemeting met de diensten van Adobe Experience Platform beheert.

Deze extensie, die geldt voor zowel Campaign Classic v7 als Campagne v8, is vooraf geïnstalleerd op uw omgeving en moet worden geconfigureerd. Voer de volgende stappen uit om de extensie voor de eigenschap mobile tag te configureren:

1. Open de eigenschap tag die u eerder hebt gemaakt.
1. Van de linkernavigatie, doorblader aan **Uitbreidingen**, en open de **Catalogus** tabel. Gebruik het onderzoeksgebied om de **Adobe Campaign Classic** uitbreiding te vinden.
1. Van de kaart van Campaign Classic, klik **installeer** knoop.
1. Ga montages in zoals die in [&#x200B; Adobe Experience Platform Mobile SDK documentatie &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"} worden beschreven.

U kunt Campagne aan uw app nu toevoegen, zoals die in [&#x200B; wordt gedetailleerd Adobe Experience Platform Mobile SDK documentatie &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.
