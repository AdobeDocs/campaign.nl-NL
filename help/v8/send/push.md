---
title: Pushmelding verzenden met Adobe Campaign
description: Aan de slag met pushmeldingen in Campagne
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 1bcb1b3d1e6062a8b5c0368725248edfc7e3d1b4
workflow-type: tm+mt
source-wordcount: '1748'
ht-degree: 3%

---

# Pushmeldingen maken en verzenden{#push-notifications-create}

Met de levering van mobiele apps kunt u meldingen verzenden naar iOS en Android-apparaten.

Als u pushberichten wilt verzenden in Adobe Campaign, moet u:

1. Integreer de SDK met uw app. [Meer informatie](#push-sdk)
1. Maak een informatieservice voor het type Mobiele toepassing voor uw mobiele toepassing en voeg de iOS- en Android-versies van de toepassing toe aan die service. [Meer informatie](#push-config)
1. Maak een levering voor zowel iOS als Android. [Meer informatie](#push-create)

## De SDK integreren {#push-sdk}

U kunt de Adobe Experience Platform Mobile SDK gebruiken door de Adobe Campaign-extensie te configureren in de gebruikersinterface voor gegevensverzameling. De Adobe Experience Platform Mobile SDK helpt Adobe Experience Cloud-oplossingen en -services aan te schaffen in uw mobiele apps. De configuratie SDKs wordt beheerd door de Inzameling UI van Gegevens voor flexibele configuratie en verlengbare, op regels-gebaseerde integratie. [Meer informatie in de documentatie van Adobe Developer](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.

U kunt ook de Campagne SDK integreren om de integratie van uw mobiele toepassing in het Adobe Campaign-platform te vergemakkelijken. Compatibele SDK-versies worden weergegeven in [Matrix voor campagnecompatibiliteit](../start/compatibility-matrix.md#MobileSDK).

Leer hoe u de SDK&#39;s van Campagne Android en iOS kunt integreren met uw app in [deze pagina](../config/push-config.md)

## Uw toepassingsinstellingen configureren in Campagne{#push-config}

Voordat u pushmeldingen verzendt, moet u de instellingen voor iOS- en Android-apps in Adobe Campaign definiëren.

Pushberichten worden via een speciale service naar gebruikers van de app verzonden. Wanneer gebruikers uw app installeren, abonneren zij zich op deze service: Adobe Campaign vertrouwt op deze service om alleen de abonnees van uw app als doel in te stellen. In deze service moet u uw iOS- en Android-apps toevoegen om op iOS- en Android-apparaten te verzenden.

Voer de onderstaande stappen uit om een service te maken voor het verzenden van pushberichten:

1. Bladeren naar **[!UICONTROL Profiles and Targets > Services and Subscriptions]** en klikt u op **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. Voer een **[!UICONTROL Label]** en **[!UICONTROL Internal name]** en selecteert u een **[!UICONTROL Mobile application]** type.

   >[!NOTE]
   >
   >De standaardwaarde **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** doeltoewijzing is gekoppeld aan de tabel met ontvangers. Als u een andere doelafbeelding wilt gebruiken, moet u een nieuwe doeltoewijzing maken en deze invoeren in het dialoogvenster **[!UICONTROL Target mapping]** van de dienst. Meer informatie over doeltoewijzingen in [deze pagina](../audiences/target-mappings.md).

1. Gebruik vervolgens de **[!UICONTROL Add]** pictogram aan de rechterkant om de mobiele toepassingen te definiëren die deze service gebruiken.

>[!BEGINTABS]

>[!TAB iOS]

Ga als volgt te werk om een app voor iOS-apparaten te maken:

1. Selecteer **[!UICONTROL Create an iOS application]** en klik op **[!UICONTROL Next]**.

   ![](assets/new-ios-app.png){width="600" align="left"}

1. Voer de naam van uw app in het dialoogvenster **[!UICONTROL Label]** veld.
1. (optioneel) U kunt de inhoud van een pushbericht verrijken met wat **[!UICONTROL Application variables]**. Deze zijn volledig aanpasbaar en een deel van de berichtlading wordt verzonden naar het mobiele apparaat.

   In het onderstaande voorbeeld wordt **mediaURl** en **mediaExt** variabelen worden toegevoegd om uitgebreide pushmeldingen te maken en geven de toepassing de afbeelding die binnen het bericht moet worden weergegeven.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. Bladeren naar de **[!UICONTROL Subscription parameters]** tabblad om de toewijzing te definiëren met een extensie van de optie **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** schema.

1. Bladeren naar de **[!UICONTROL Sounds]** om het af te spelen geluid te definiëren. Klikken **[!UICONTROL Add]** en vullen **[!UICONTROL Internal name]** veld dat de naam moet bevatten van het bestand dat is ingesloten in de toepassing of de naam van het systeemgeluid.

1. Klikken **[!UICONTROL Next]** om de ontwikkeltoepassing te configureren.

1. De integratiesleutel is specifiek voor elke toepassing. De mobiele toepassing wordt aan Adobe Campaign gekoppeld.

   Controleer of hetzelfde **[!UICONTROL Integration key]** wordt gedefinieerd in Adobe Campaign en in de toepassingscode via de SDK.

   Als u de Campagne SDK gebruikt, leert u meer in[deze pagina](../config/push-config.md).


   Als u Adobe Experience Platform SDK (gegevensverzameling) gebruikt, leert u meer in [deze pagina](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > De **[!UICONTROL Integration key]** is volledig aanpasbaar met tekenreekswaarde, maar moet exact hetzelfde zijn als de waarde die in de SDK is opgegeven.
   >
   > U kunt niet hetzelfde certificaat gebruiken voor de ontwikkelingsversie (sandbox) en de productieversie van de toepassing.

1. Selecteer het pictogram in het menu **[!UICONTROL Application icon]** om de mobiele toepassing in uw service aan te passen.

1. Selecteer het **[!UICONTROL Authentication mode]**. Er zijn twee modi beschikbaar:

   * (Aanbevolen) **[!UICONTROL Token-based authentication]**: De APNs-verbindingsinstellingen invullen **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** en **[!UICONTROL Bundle Id]** Selecteer vervolgens uw p8-certificaat door op **[!UICONTROL Enter the private key...]**. Voor meer informatie **[!UICONTROL Token-based authentication]**, zie [Apple-documentatie](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.

   * **[!UICONTROL Certificate-based authentication]**: Klikken **[!UICONTROL Enter the certificate...]**  Selecteer vervolgens de p12-toets en voer het wachtwoord in dat de ontwikkelaar van de mobiele toepassing heeft opgegeven.
   U kunt de verificatiemodus later wijzigen in het dialoogvenster **[!UICONTROL Certificate]** van uw mobiele toepassing.

1. Gebruik de **[!UICONTROL Test the connection]** knoop om uw configuratie te bevestigen.

1. Klikken **[!UICONTROL Next]** om de productietoepassing te configureren en dezelfde stappen uit te voeren als hierboven beschreven.

1. Klik op **[!UICONTROL Finish]**.

Uw iOS-toepassing kan nu worden gebruikt in Campagne.

>[!TAB Android]

Voer de volgende stappen uit om een app voor Android-apparaten te maken:

1. Selecteer **[!UICONTROL Create an Android application]** en klik op **[!UICONTROL Next]**.

   ![](assets/new-android-app.png){width="600" align="left"}

1. Voer de naam van uw app in het dialoogvenster **[!UICONTROL Label]** veld.
1. De integratiesleutel is specifiek voor elke toepassing. De mobiele toepassing wordt aan Adobe Campaign gekoppeld.

   Controleer of hetzelfde **[!UICONTROL Integration key]** wordt gedefinieerd in Adobe Campaign en in de toepassingscode via de SDK.

   Als u de Campagne SDK gebruikt, leert u meer in [deze pagina](../config/push-config.md).

   Als u Adobe Experience Platform SDK (gegevensverzameling) gebruikt, leert u meer in [deze pagina](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}


   >[!NOTE]
   >
   > De **[!UICONTROL Integration key]** is volledig aanpasbaar met tekenreekswaarde, maar moet exact hetzelfde zijn als de waarde die in de SDK is opgegeven.

1. Selecteer het pictogram in het menu **[!UICONTROL Application icon]** om de mobiele toepassing in uw service aan te passen.
1. Selecteren **HTTP v1** in  **[!UICONTROL API version]** vervolgkeuzelijst.
1. Klikken **[!UICONTROL Load project json file to extract project details...]** koppeling om uw JSON-sleutelbestand te laden. Voor meer informatie over het uitpakken van uw JSON-bestand raadpleegt u [Google Firebase-documentatie](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   U kunt ook handmatig de volgende gegevens invoeren:
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

1. Gebruik de **[!UICONTROL Test the connection]** knoop om uw configuratie te bevestigen.

   >[!CAUTION]
   >
   >De **[!UICONTROL Test connection]** controleert niet of de MID-server toegang heeft tot de FCM-server.

1. (optioneel) U kunt de inhoud van een pushbericht verrijken met wat **[!UICONTROL Application variables]** indien nodig. Deze zijn volledig aanpasbaar en een deel van de berichtlading wordt verzonden naar het mobiele apparaat.

1. Klik op **[!UICONTROL Finish]** en vervolgens op **[!UICONTROL Save]**. Uw Android-toepassing kan nu worden gebruikt in Campagne.

Hieronder vindt u de namen van FCM-ladingen om uw pushmelding verder aan te passen:

| Berichttype | Configureerbaar berichtelement (FCM-ladenaam) | Configureerbare opties (FCM-ladenaam) |
|:-:|:-:|:-:|
| gegevensbericht | N.v.t. | validate_only |
| meldingsbericht | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]


## Uw eerste pushmelding maken{#push-create}

In deze sectie worden de elementen beschreven die specifiek zijn voor de levering van iOS- en Android-berichten.

>[!CAUTION]
>
>In de context van een [Implementatie van ondernemingen (FFDA)](../architecture/enterprise-deployment.md), mobiele registratie is nu **asynchroon**. [Meer informatie](../architecture/staging.md)

Blader naar de **[!UICONTROL Campaigns]** tabblad, klikt u op **[!UICONTROL Deliveries]** en klik op de knop **[!UICONTROL Create]** boven de lijst met bestaande leveringen.

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

Voer de volgende stappen uit om berichten op iOS-apparaten te verzenden:

1. Selecteer **[!UICONTROL Deliver on iOS]** leveringssjabloon.

   ![](assets/push_ios_1.png)

1. Als u het doel van het bericht wilt definiëren, klikt u op de knop **[!UICONTROL To]** koppeling en klik vervolgens op **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. Selecteren **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]** Selecteer eerst de service die relevant is voor uw mobiele toepassing en selecteer vervolgens de iOS-versie van de toepassing.

   ![](assets/push_ios_3.png)

1. Kies uw **[!UICONTROL Notification type]** Tussen **[!UICONTROL General notification (Alert, Sound, Badge)]** of **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >De **Silent Push** in de modus kan een melding &quot;stil&quot; naar een mobiele toepassing worden verzonden. De gebruiker wordt niet op de hoogte gebracht van de aankomst van de melding. Deze wordt rechtstreeks naar de toepassing overgedragen.

1. In de **[!UICONTROL Title]** Voer in het veld het label in van de titel die u wilt weergeven in de lijst met meldingen die beschikbaar is in het meldingscentrum.

   In dit veld kunt u de waarde van de optie **titel** parameter van de iOS-berichtlading.

1. U kunt een **[!UICONTROL Subtitle]**, waarde van de **ondertitel** parameter van de iOS-berichtlading.

1. Voer de inhoud van het bericht in het dialoogvenster **[!UICONTROL Message content]** van de wizard.

1. Van de **[!UICONTROL Sound and Badge]** kunt u de volgende opties bewerken:

   * **[!UICONTROL Clean Badge]**: Schakel deze optie in om de waarde van de badge te vernieuwen.

   * **[!UICONTROL Value]**: Stel een nummer in dat wordt gebruikt om het aantal nieuwe ongelezen gegevens direct op het toepassingspictogram weer te geven.

   * **[!UICONTROL Critical alert mode]**: Schakel deze optie in om geluid toe te voegen aan uw melding, zelfs als de telefoon van de gebruiker is ingesteld op de focusmodus of als de iPhone is gedempt.

   * **[!UICONTROL Name]**: Selecteer het geluid dat door de mobiele terminal moet worden afgespeeld wanneer het bericht wordt ontvangen.

   * **[!UICONTROL Volume]**: volume van uw geluid van 0 tot 100.

      >[!NOTE]
      > 
      >Geluiden moeten in de toepassing worden opgenomen en worden gedefinieerd wanneer de service wordt gemaakt.
   ![](assets/push_ios_5.png)

1. Van de **[!UICONTROL Application variables]** tab, uw **[!UICONTROL Application variables]** automatisch worden toegevoegd. Met deze instructies kunt u bijvoorbeeld het berichtgedrag definiëren. U kunt dan een specifiek toepassingsscherm configureren dat wordt weergegeven wanneer de gebruiker het bericht activeert.

1. Van de **[!UICONTROL Advanced]** kunt u de volgende algemene opties bewerken:

   * **[!UICONTROL Mutable content]**: Schakel deze optie in als u wilt dat de mobiele toepassing media-inhoud kan downloaden.

   * **[!UICONTROL Thread-id]**: identifier die wordt gebruikt om gerelateerde meldingen te groeperen.

   * **[!UICONTROL Category]**: naam van de rubriek-id die knoppen voor handelingen weergeeft. Met deze meldingen kan de gebruiker sneller verschillende taken uitvoeren als reactie op een melding zonder de applicatie te openen of erin te moeten navigeren.

   ![](assets/push_ios_6.png)

1. Voor meldingen met tijdgevoeligheid kunt u de volgende opties opgeven:

   * **[!UICONTROL Target content ID]**: identifier die wordt gebruikt om aan te geven welk toepassingsvenster moet worden verzonden wanneer de melding wordt geopend.

   * **[!UICONTROL Launch image]**: naam van het startafbeeldingsbestand dat moet worden weergegeven. Als de gebruiker ervoor kiest de toepassing te starten, wordt de geselecteerde afbeelding weergegeven in plaats van het startscherm van de toepassing.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: Het systeem stelt de melding standaard in, licht het scherm aan en kan een geluid afspelen. Meldingen doorbreken niet door de focusmodi.

      * **[!UICONTROL Passive]**: Het systeem voegt het bericht toe aan de meldingslijst zonder het scherm te belichten of een geluid af te spelen. Meldingen doorbreken niet door de focusmodi.

      * **[!UICONTROL Time sensitive]** Het systeem presenteert de melding onmiddellijk, licht het scherm op, kan een geluid afspelen en door de modus Focus breken. Voor dit niveau is geen speciale toestemming van Apple vereist.

      * **[!UICONTROL Critical]** Het systeem presenteert onmiddellijk het bericht, licht omhoog het scherm, en mijdt de demtschakelaar of nadrukwijzen. Voor dit niveau is een speciale machtiging van Apple vereist.
   * **[!UICONTROL Relevance score]**: een relevantiescore instellen van 0 tot 100. Het systeem gebruikt dit om de berichten in het berichtoverzicht te sorteren.

   ![](assets/push_ios_7.png)

1. Zodra het bericht wordt gevormd, klik **[!UICONTROL Preview]** om een voorvertoning van de melding weer te geven.

   ![](assets/push-ios-preview.png)


>[!TAB Android]

Voer de volgende stappen uit om meldingen te verzenden op Android-apparaten:

1. Selecteer **[!UICONTROL Deliver on Android (android)]** leveringssjabloon.

   ![](assets/push-template-android.png)

1. Als u het doel van het bericht wilt definiëren, klikt u op de knop **[!UICONTROL To]** koppeling en klik vervolgens op **[!UICONTROL Add]**.

   ![](assets/push-android-select-target.png)

1. Selecteren **[!UICONTROL Subscribers of an Android mobile application]** kiest u de service die relevant is voor uw mobiele toepassing (in dit geval Neotrips) en selecteert u vervolgens de Android-versie van de toepassing.

   ![](assets/push-android-subscribers.png)

1. Voer vervolgens de inhoud voor het bericht in.

   ![](assets/push-android-content.png)

1. Klik op de knop **[!UICONTROL Insert emoticon]** pictogram om emoticons in te voegen in uw pushmelding.

1. In de **[!UICONTROL Application variables]** Voer de waarde van elke variabele in. U kunt bijvoorbeeld een specifiek toepassingsscherm configureren dat wordt weergegeven wanneer de gebruiker het bericht activeert.

1. Zodra het bericht wordt gevormd, klik **[!UICONTROL Preview]** om een voorvertoning van de melding weer te geven.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## Uw pushmeldingen testen, verzenden en controleren

Om een bewijs te verzenden en de uiteindelijke levering te verzenden, gebruikt u hetzelfde proces als voor andere leveringen.

Leer hoe u een levering kunt valideren in [deze pagina](preview-and-proof.md).

Leer hoe u de levering kunt bevestigen en verzenden in [deze pagina](send.md)

Nadat u berichten hebt verzonden, kunt u de leveringen controleren en volgen. Meer informatie over de redenen voor het mislukken van pushberichten vindt u in [deze pagina](delivery-failures.md#push-error-types).

