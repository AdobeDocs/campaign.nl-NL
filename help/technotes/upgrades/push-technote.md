---
product: campaign
title: Aanstaande wijzigingen in het kanaal voor pushmeldingen
description: Aanstaande wijzigingen in het kanaal voor pushmeldingen
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="Ook van toepassing op Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="Is van toepassing op campagne v8"
exl-id: 45ac6f8f-eb2a-4599-a930-1c1fcaa3095b
source-git-commit: a494ac834b1febcafe04f4bb05eb74834df7b024
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 1%

---

# Wijzigingen in kanaal voor pushmelding {#push-upgrade}

Met Campagne kunt u pushmeldingen verzenden op iOS- en Android-apparaten. Hiervoor is de campagne afhankelijk van abonnementsservices voor mobiele toepassingen.

Enkele belangrijke wijzigingen in de Android Firebase Cloud Messaging (FCM)-service worden in 2024 gepubliceerd en kunnen van invloed zijn op uw Adobe Campaign-implementatie. Mogelijk moet de configuratie van uw abonnementsservices voor Android-pushberichten worden bijgewerkt om deze wijziging te ondersteunen.

Bovendien adviseert de Adobe hoogst om naar de op teken-gebaseerde verbinding aan APNs eerder dan een op certificaat-gebaseerde verbinding te bewegen, die veiliger en scalable is.

## Google Android Firebase Cloud Messaging (FCM)-service {#fcm-push-upgrade}

### Wat is er veranderd? {#fcm-changes}

Als onderdeel van de voortdurende inspanningen van Google om haar diensten te verbeteren, zullen de bestaande FCM API&#39;s worden stopgezet op **20 juni 2024**. Meer informatie over het HTTP-protocol voor Firebase Cloud Messaging vindt u in [Google Firebase-documentatie](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 en Adobe Campaign v8 ondersteunen al de nieuwste API&#39;s voor het verzenden van pushberichten. Sommige oude implementaties zijn echter nog steeds afhankelijk van de oudere API&#39;s. Deze implementaties moeten worden bijgewerkt.

### Heb je invloed op? {#fcm-impact}

Als uw huidige implementatie ondersteuning biedt voor abonnementsservices die verbinding maken met FCM via de verouderde API&#39;s, heeft dit gevolgen voor u. De overgang naar de nieuwste API&#39;s is verplicht om elke onderbreking van de service te voorkomen. In dat geval zullen de teams van de Adobe u bereiken.

Als u wilt controleren of er gevolgen voor u zijn, kunt u het filter **Services en abonnementen** volgens het onderstaande filter:

![](assets/filter-services-fcm.png)


* Als een van uw actieve pushmeldingenservice de **HTTP (verouderd)** API, heeft deze wijziging rechtstreeks invloed op uw installatie. U moet uw huidige configuraties controleren en naar de nieuwere API&#39;s gaan zoals hieronder wordt beschreven.

* Als uw opstelling exclusief gebruikmaakt van **HTTP v1** API voor Android-pushmeldingen, voldoet u al aan de eisen en hoeft u verder niets te doen.

### Hoe kan ik bijwerken? {#fcm-transition-procedure}

#### Vereisten {#fcm-transition-prerequisites}

* Voor Campaign Classic v7 is de ondersteuning van HTTP v1 toegevoegd in versie 20.3.1. Als uw omgeving op een oudere versie wordt uitgevoerd, is het een eerste vereiste voor de overgang naar HTTP v1 om uw omgeving te upgraden naar de [nieuwste Campaign Classic maken](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Voor Campagne v8 wordt HTTP v1 door alle versies gesteund, en geen verbetering is nodig.

* Het JSON-bestand van de Android Firebase Admin SDK-service is vereist om de mobiele toepassing naar HTTP v1 te verplaatsen. Leer hoe u dit bestand kunt ophalen in [Google Firebase-documentatie](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Voor hybride, Gehoste en Managed Services plaatsingen, naast de hieronder overgangsprocedure, contacteer Adobe om uw Real-Time (RT) uitvoeringsserver bij te werken. De server voor middelste bronnen heeft geen invloed op deze server.

* Als Campaign Classic v7 on-premise gebruiker, moet u zowel de Marketing als Real-Time uitvoeringsservers bevorderen. De server voor middelste bronnen heeft geen invloed op deze server.

#### Overgangprocedure {#fcm-transition-steps}

Ga als volgt te werk om uw omgeving te verplaatsen naar HTTP v1:

1. Blader naar uw lijst met **Services en abonnementen**.
1. Alle mobiele toepassingen weergeven met de opdracht **HTTP (verouderd)** API-versie.
1. Stel voor elk van deze mobiele toepassingen de optie **API-versie** tot **HTTP v1**.
1. Klik op de knop **[!UICONTROL Load project json file to extract project details...]** koppeling gebruiken om uw JSON-sleutelbestand rechtstreeks te laden.

   U kunt ook handmatig de volgende gegevens invoeren:

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. Klikken **[!UICONTROL Test the connection]** om te controleren of uw configuratie correct is en of de marketingserver toegang heeft tot de FCM. Merk op dat voor implementaties van middelhoge bronnen, de **[!UICONTROL Test connection]** kan niet controleren of de server toegang heeft tot de FCM-service (Android Firebase Cloud Messaging).
1. Als optie kunt u de inhoud van een pushbericht verrijken met wat **[!UICONTROL Application variables]** indien nodig. Deze zijn volledig aanpasbaar en een deel van de berichtlading wordt verzonden naar het mobiele apparaat.
1. Klik op **[!UICONTROL Finish]** en vervolgens op **[!UICONTROL Save]**.

Hieronder vindt u de namen van FCM-ladingen om uw pushmelding verder aan te passen. Deze opties zijn gedetailleerd [hier](#fcm-apps).

| Berichttype | Configureerbaar berichtelement (FCM-ladenaam) | Configureerbare opties (FCM-ladenaam) |
|:-:|:-:|:-:|
| gegevensbericht | N.v.t. | validate_only |
| meldingsbericht | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Wanneer deze wijzigingen zijn toegepast op de gehele server, gebruiken alle nieuwe pushberichten die aan Android-apparaten worden geleverd de HTTP v1-API. Bestaande push-items worden opnieuw uitgevoerd, in uitvoering en in gebruik, maar gebruiken nog steeds de HTTP (legacy) API.

### Wat is de invloed op mijn Android-apps? {#fcm-apps}

Er zijn geen specifieke wijzigingen vereist in de code van de Android Mobile-toepassingen en het meldingsgedrag moet niet worden gewijzigd.

Met HTTP v1 kunt u uw pushmelding echter verder aanpassen met **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)

U kunt:

* Gebruik de **[!UICONTROL Ticker]** om de tekst van de markering van uw melding in te stellen.
* Gebruik de **[!UICONTROL Image]** om de URL van de afbeelding in te stellen die in uw melding moet worden weergegeven.
* Gebruik de **[!UICONTROL Notification Count]** veld om het aantal nieuwe ongelezen gegevens in te stellen dat rechtstreeks op het toepassingspictogram moet worden weergegeven.
* Stel de **[!UICONTROL Sticky]** optie aan vals zodat het bericht automatisch wordt verworpen wanneer de gebruiker het klikt. Indien ingesteld op true, wordt het bericht nog steeds weergegeven, zelfs wanneer de gebruiker erop klikt.
* Stel de **[!UICONTROL Notification Priority]** niveau van uw bericht aan gebrek, minimum, laag of hoog.
* Stel de **[!UICONTROL Visibility]** niveau van uw kennisgeving aan publiek, privé of geheim.

Voor meer informatie over de **[!UICONTROL HTTP v1 additional options]** en hoe u deze velden kunt vullen, raadpleegt u [FCM-documentatie](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.




## Apple iOS Push Notification Service (APNs) {#apns-push-upgrade}

### Wat is er veranderd? {#ios-changes}

Zoals aanbevolen door Apple, moet u uw communicatie met de APNs (Apple Push Notification service) beveiligen door stateless verificatietokens te gebruiken.

Token-gebaseerde authentificatie biedt een stateless manier om met APNs te communiceren. Stateloze communicatie is sneller dan op certificaat-gebaseerde communicatie omdat het geen APNs vereist om het certificaat, of andere informatie, met betrekking tot uw leverancierserver op te zoeken. Er zijn andere voordelen aan het gebruiken van op teken-gebaseerde authentificatie:

* U kunt hetzelfde token gebruiken van meerdere providerservers.

* U kunt één token gebruiken om meldingen te distribueren voor alle apps van uw bedrijf.

Meer informatie over op token gebaseerde verbindingen met APNs vindt u in [Apple Developer-documentatie](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Classic v7 en Adobe Campaign v8 ondersteunen zowel tokengebaseerde als op certificaten gebaseerde verbindingen. Als uw implementatie afhankelijk is van een verbinding op basis van een certificaat, raadt de Adobe u ten zeerste aan om deze bij te werken naar een tokenverbinding.

### Heb je invloed op? {#ios-impact}

Als uw huidige implementatie afhankelijk is van op een certificaat gebaseerde aanvragen om verbinding te maken met APNs, heeft dit gevolgen voor u. De overgang naar een op een token gebaseerde verbinding wordt aanbevolen.

Als u wilt controleren of er gevolgen voor u zijn, kunt u het filter **Services en abonnementen** volgens het onderstaande filter:

![](assets/filter-services-ios.png)


* Als een van uw actieve pushmeldingenservice de **Certificaatgebaseerde verificatie** -modus, moeten uw huidige implementaties worden gereviseerd en naar een **Op token gebaseerde verificatie** zoals hieronder beschreven.

* Als uw opstelling exclusief gebruikmaakt van **Op token gebaseerde verificatie** voor iOS-pushberichten, is uw implementatie al up-to-date en hoeft u verder niets te doen.

### Hoe kan ik bijwerken? {#ios-transition-procedure}

#### Vereisten {#ios-transition-prerequisites}

* Voor Campaign Classic v7 **Op token gebaseerde verificatie** mode is toegevoegd in versie 20.2. Als uw omgeving op een oudere versie wordt uitgevoerd, is een upgrade van uw omgeving naar de [nieuwste Campaign Classic maken](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Voor Campaign v8, **Op token gebaseerde verificatie** Deze modus wordt door alle releases ondersteund en er is geen upgrade nodig.

* U hebt een APNs-verificatietoken voor ondertekening nodig om de tokens te genereren die uw server gebruikt. U kunt deze sleutel aanvragen via uw Apple-ontwikkelaarsaccount, zoals wordt uitgelegd in [Apple Developer-documentatie](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

* Voor hybride, Gehoste en Managed Services plaatsingen, naast de hieronder overgangsprocedure, contacteer Adobe om uw Real-Time (RT) uitvoeringsserver bij te werken. De server voor middelste bronnen heeft geen invloed op deze server.

* Als Campaign Classic v7 on-premise gebruiker, moet u zowel de Marketing als Real-Time uitvoeringsservers bevorderen. De server voor middelste bronnen heeft geen invloed op deze server.

#### Overgangprocedure {#ios-transition-steps}

Voer de volgende stappen uit om uw mobiele iOS-toepassingen te verplaatsen naar de op token gebaseerde verificatiemodus:

1. Blader naar uw lijst met **Services en abonnementen**.
1. Alle mobiele toepassingen weergeven met de opdracht **Certificaatgebaseerde verificatie** -modus.
1. Bewerk elk van deze mobiele toepassingen en blader naar de **Certificaat/persoonlijke sleutel** tab.
1. Van de **Verificatiemodus** vervolgkeuzelijst, selecteert u **Op token gebaseerde verificatie**.
1. De APN-verbindingsinstellingen invullen **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** en **[!UICONTROL Bundle Id]** Selecteer vervolgens uw p8-certificaat door op **[!UICONTROL Enter the private key...]**.

   ![](assets/token-based-certif.png)

1. Klikken **[!UICONTROL Test the connection]** om te controleren of uw configuratie correct is en of de server toegang heeft tot APNs. Merk op dat voor implementaties van middelhoge bronnen, de **[!UICONTROL Test connection]** kan niet controleren of de server toegang heeft tot APNs.
1. Klikken **[!UICONTROL Next]** om de productietoepassing te configureren en dezelfde stappen uit te voeren als hierboven beschreven.
1. Klik op **[!UICONTROL Finish]** en vervolgens op **[!UICONTROL Save]**.

Uw iOS-toepassing wordt nu verplaatst naar de op token gebaseerde verificatiemodus.
