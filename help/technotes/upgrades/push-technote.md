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
source-git-commit: a9aa9cb508ca1f5cdcd59e61b5be029e3de1a82f
workflow-type: tm+mt
source-wordcount: '1665'
ht-degree: 1%

---

# Wijzigingen in het kanaal voor pushmeldingen {#push-upgrade}

Met Campagne kunt u pushmeldingen verzenden op iOS- en Android-apparaten. Hiervoor is de campagne afhankelijk van abonnementsservices voor mobiele toepassingen.

Enkele belangrijke wijzigingen in de Android Firebase Cloud Messaging (FCM)-service worden in 2024 gepubliceerd en kunnen van invloed zijn op uw Adobe Campaign-implementatie. Mogelijk moet uw configuratie met abonnementsservices voor Android-pushberichten worden bijgewerkt om deze wijziging te ondersteunen.

Daarnaast raadt Adobe ten zeerste aan om over te schakelen naar de tokengebaseerde verbinding met APN&#39;s in plaats van een op een certificaat gebaseerde verbinding, die veiliger en schaalbaarder is.

## Google Android Firebase Cloud Messaging (FCM)-service {#fcm-push-upgrade}

### Wat is er veranderd? {#fcm-changes}

Als deel van Google dat voortdurend probeert om zijn diensten te verbeteren, zal erfenis FCM APIs op **22 Juli, 2024** worden opgeheven. Leer meer over het protocol van HTTP van het Overseinen van de Wolk van de Wolk van de Wolk van de Vuurstand van de Wolk van de Vuurstand van de Wolk van de Vuurstand in [ Google documentatie ](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}.

Adobe Campaign Classic v7 en Adobe Campaign v8 ondersteunen al de nieuwste API&#39;s voor het verzenden van pushberichten. Sommige oude implementaties zijn echter nog steeds afhankelijk van de oudere API&#39;s. Deze implementaties moeten worden bijgewerkt.

### Heb je invloed op? {#fcm-impact}

Als uw huidige implementatie ondersteuning biedt voor abonnementsservices die verbinding maken met FCM via de verouderde API&#39;s, heeft dit gevolgen voor u. De overgang naar de nieuwste API&#39;s is verplicht om elke onderbreking van de service te voorkomen. In dat geval zullen Adobe-teams je bereiken.

Om te controleren als u wordt beïnvloed, kunt u uw **Diensten en Abonnementen** zoals per filter hieronder filtreren:

![](assets/filter-services-fcm.png)


* Als om het even welk van uw actieve dienst van het pushbericht **HTTP (erfenis)** API gebruikt, zal uw opstelling direct door deze verandering worden beïnvloed. U moet uw huidige configuraties controleren en naar de nieuwere API&#39;s gaan zoals hieronder wordt beschreven.

* Als uw opstelling uitsluitend **HTTP v1** API voor de duw berichten van Android gebruikt, dan bent u reeds in naleving en geen verdere actie zal op uw kant worden vereist.

### Hoe kan ik bijwerken? {#fcm-transition-procedure}

#### Vereisten {#fcm-transition-prerequisites}

* Het JSON-bestand van de Android Firebase Admin SDK-service is nodig om de mobiele toepassing naar HTTP v1 te verplaatsen. Leer hoe te om dit dossier in [ documentatie van de Vuurbasis van Google ](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"} te krijgen.

* Voor Campaign Classic v7 is de ondersteuning van HTTP v1 toegevoegd in release 20.3.1. Als uw milieu op een oudere versie loopt, moet een eerste vereiste voor de overgang aan HTTP v1 uw milieu aan [ bevorderen recentste Campaign Classic bouwen ](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Voor Campagne v8 wordt HTTP v1 door alle versies gesteund, en geen verbetering is nodig.

* Als gebruiker van Campaign Classic v7 op locatie, moet u zowel de Marketing als Real-Time uitvoeringsservers bijwerken.

* Voor hybride, gehoste en beheerde Cloud Services-implementaties neemt u, naast de onderstaande overgangsprocedure, contact op met Adobe om uw Real-Time (RT) uitvoeringsserver bij te werken.

* Informatie over de Android die externe account routeert:

   * Als Campaign Classic v7-gebruiker op locatie of hybride gebruiker, controleert u of uw Android die externe account routeert, is geconfigureerd met `androidPushConnectorV2.js` . Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android#configuring-external-account-android){target="_blank"}.

   * Voor de implementatie van Hybride, Hosted en Managed Cloud Services moet u ook verbinding maken met het Adobe-team van de klantenservice om te controleren of de `androidPushConnectorV2.js (nms)` -connector is geselecteerd in Android die een externe account van uw mediumsourcingserver routeert.

#### Overgangprocedure {#fcm-transition-steps}

Ga als volgt te werk om uw omgeving te verplaatsen naar HTTP v1:

1. Blader naar uw lijst van **Diensten en Abonnementen**.
1. Maak een lijst van alle mobiele toepassingen gebruikend de **HTTP (erfenis)** API versie.
1. Voor elk van deze mobiele toepassingen, plaats de **API versie** aan **HTTP v1**.
1. Klik op de koppeling **[!UICONTROL Load project json file to extract project details...]** om het JSON-sleutelbestand rechtstreeks te laden.

   U kunt ook handmatig de volgende gegevens invoeren:

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. Klik op **[!UICONTROL Test the connection]** om te controleren of uw configuratie correct is en of de marketingserver toegang heeft tot de FCM. Voor Mid-sourcing-implementaties kan met de knop **[!UICONTROL Test connection]** niet worden gecontroleerd of de server toegang heeft tot de FCM-service (Firebase Cloud Messaging) van Android.
1. U kunt desgewenst ook de inhoud van een pushbericht verrijken met wat **[!UICONTROL Application variables]** . Deze zijn volledig aanpasbaar en een deel van de berichtlading wordt verzonden naar het mobiele apparaat.
1. Klik op **[!UICONTROL Finish]** en vervolgens op **[!UICONTROL Save]**.

   Hieronder vindt u de namen van FCM-ladingen om uw pushmelding verder aan te passen. Deze opties zijn gedetailleerd [ hier ](#fcm-apps).

   | Berichttype | Configureerbaar berichtelement (FCM-ladenaam) | Configureerbare opties (FCM-ladenaam) |
   |:-:|:-:|:-:|
   | gegevensbericht | N.v.t. | validate_only |
   | meldingsbericht | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Zodra deze veranderingen in al uw server worden toegepast, gebruiken alle **nieuwe** het bericht van de duw aan de apparaten van Android v1 API van HTTP. Bestaande push-items worden opnieuw uitgevoerd, in uitvoering en in gebruik, maar gebruiken nog steeds de HTTP (legacy) API. Leer hoe u ze in de onderstaande sectie kunt bijwerken.

#### Bestaande sjablonen bijwerken {#fcm-transition-update}

Zodra de overgangHTTP v1 wordt gedaan, moet u uw **leveringsmalplaatjes** voor de duw berichten van Android bijwerken om het aantal partijberichten te verhogen. Om dit te doen, doorblader aan de eigenschappen van uw Android leveringsmalplaatje en, in het **lusje van de Levering**, plaats de [ Hoeveelheid van de Batch van het Bericht ](../../v8/send/configure-and-send.md#delivery-batch-quantity) aan **256**. Pas deze wijziging toe op alle leveringssjablonen die worden gebruikt voor uw Android-leveringen en op al uw bestaande Android-leveringen.

U kunt ook bestaande leverings- en leveringssjablonen bijwerken die zijn gemaakt vóór de upgrade naar een versie die HTTP v1 ondersteunt. Dit doet u als volgt:

* Neem als Managed Cloud Services of Gehoste klant contact op met Adobe om uw bestaande Android-leveringssjablonen bij te werken.

* Voor on-premise omgevingen downloadt u het `fcm-httpv1-migration.js` -script en voert u dit hieronder uit.

  Download [ fcm-httpv1-migration.zip ](assets/do-not-localize/fcm-httpv1-migration-js.zip).

  >[!CAUTION]
  >
  >Het script moet worden uitgevoerd op uw on-premise marketinginstantie.


  +++Stappen om bestaande leveringen en sjablonen bij te werken (alleen op locatie)

  Voer de volgende stappen uit om alle leverings- en leveringstemplates te repareren die zijn gemaakt vóór de upgrade naar een versie die HTTP v1 ondersteunt:

   1. Exporteer uw bestaande leverings- en leveringssjablonen in een pakket, zodat u deze kunt herstellen in het geval van een onverwacht probleem tijdens de patches.
   1. Voer de volgende opdracht in Posgresql uit:

      ```sql
      pg_dump -Fp -f /sftp/<db_name>-nmsdelivery-before_rd_script.sql -t nmsdelivery -d <db_name>
      ```

   1. Standaard staat het script in de modus `dryrun` en kunt u het in die modus starten om te controleren of een deel van de levering moet worden gerepareerd.

      Opdracht

      ```sql
      nlserver javascript -instance:<instance_name> -file fcm-httpv1-migration.js 
      ```

      Uitvoer

      ```sql
      ...
      HH:MM:SS >   Processing delivery (id:123456,  label:'Deliver on Android - New', name:'DM1234')
      HH:MM:SS >   Dry run: Would update androidCheckParams for delivery (id:123456,  label:'Deliver on Android - New', name:'DM1234')
      HH:MM:SS >   Processing delivery (id:567890,  label:'Deliver on Android - New', name:'DM5678')
      HH:MM:SS >   Dry run: Would update androidCheckParams for delivery (id:567890,  label:'Deliver on Android - New', name:'DM5678')
      ...
      HH:MM:SS >   Summary (XYZ processed deliverie(s) or delivery template(s)):
      HH:MM:SS >>  - X had not patchable androidCheckParams formula!
      HH:MM:SS >   - Y had androidCheckParams formula patched.
      HH:MM:SS >   - Z ignored as alreading having androidCheckParams formula patched.
      ```

      >[!NOTE]
      >
      >De `not patchable` -leveringen moeten handmatig worden bijgewerkt. Hun ID is te vinden in het logboek.

   1. Voer het script op de uitvoeringsmodus als volgt uit om leveringen bij te werken:

      ```sql
      nlserver javascript -instance:<instance_name> -file fcm-httpv1-migration.js -arg:run
      ```

+++

### Wat is het effect op mijn Android-apps? {#fcm-apps}

Er zijn geen specifieke wijzigingen vereist in de code van de Android Mobile-toepassingen en het meldingsgedrag moet niet worden gewijzigd.

Met HTTP v1 kunt u uw pushmelding echter verder aanpassen met **[!UICONTROL HTTPV1 additional options]** .

![](assets/android-push-additional-options.png)

U kunt:

* Gebruik het veld **[!UICONTROL Ticker]** om de tekst van de markering van uw melding in te stellen.
* Gebruik het veld **[!UICONTROL Image]** om de URL van de afbeelding in te stellen die in de melding moet worden weergegeven.
* Gebruik het veld **[!UICONTROL Notification Count]** om het aantal nieuwe ongelezen gegevens in te stellen dat rechtstreeks op het toepassingspictogram moet worden weergegeven.
* Stel de optie **[!UICONTROL Sticky]** in op false, zodat het bericht automatisch wordt gesloten wanneer de gebruiker erop klikt. Indien ingesteld op true, wordt het bericht nog steeds weergegeven, zelfs wanneer de gebruiker erop klikt.
* Stel het **[!UICONTROL Notification Priority]** -niveau van uw melding in op standaard, minimum, laag of hoog.
* Stel het **[!UICONTROL Visibility]** -niveau van uw melding in op openbaar, privé of geheim.

Voor meer op **[!UICONTROL HTTP v1 additional options]** en hoe te om deze gebieden te vullen, verwijs naar [ documentatie FCM ](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.



## Apple iOS Push Notification Service (APNs) {#apns-push-upgrade}

### Wat is er veranderd? {#ios-changes}

Zoals aanbevolen door Apple, moet u uw communicatie met de APNs (Apple Push Notification service) beveiligen door stateless verificatietokens te gebruiken.

Token-gebaseerde authentificatie biedt een stateless manier om met APNs te communiceren. Stateloze communicatie is sneller dan op certificaat-gebaseerde communicatie omdat het geen APNs vereist om het certificaat, of andere informatie, met betrekking tot uw leverancierserver op te zoeken. Er zijn andere voordelen aan het gebruiken van op teken-gebaseerde authentificatie:

* U kunt hetzelfde token gebruiken van meerdere providerservers.

* U kunt één token gebruiken om meldingen te distribueren voor alle apps van uw bedrijf.

Leer meer over op token-gebaseerde verbindingen aan APNs in [ documentatie van de Ontwikkelaar van Apple ](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Classic v7 en Adobe Campaign v8 ondersteunen zowel tokengebaseerde als op certificaten gebaseerde verbindingen. Als uw implementatie afhankelijk is van een verbinding op basis van een certificaat, raadt Adobe u ten zeerste aan deze bij te werken naar een tokenverbinding.

### Heb je invloed op? {#ios-impact}

Als uw huidige implementatie afhankelijk is van op een certificaat gebaseerde aanvragen om verbinding te maken met APNs, heeft dit gevolgen voor u. De overgang naar een op een token gebaseerde verbinding wordt aanbevolen.

Om te controleren als u wordt beïnvloed, kunt u uw **Diensten en Abonnementen** zoals per filter hieronder filtreren:

![](assets/filter-services-ios.png)


* Als om het even welk van uw actieve dienst van het pushbericht de **op certificaat-gebaseerde authentificatie** wijze (.p12) gebruikt, zouden uw huidige implementaties moeten worden herzien en naar a **op token-gebaseerde authentificatie** wijze (.p8) worden bewogen zoals hieronder beschreven.

* Als uw opstelling exclusief de **op token-gebaseerde authentificatie** wijze voor de pushberichten van iOS gebruikt, dan is uw implementatie reeds bijgewerkt en geen verdere actie van uw kant zal worden vereist.

### Hoe kan ik bijwerken? {#ios-transition-procedure}

#### Vereisten {#ios-transition-prerequisites}

* Voor Campaign Classic v7, is de steun van **op token-gebaseerde authentificatie** wijze toegevoegd in versie 20.2. Als uw milieu op een oudere versie loopt, is een eerste vereiste voor deze verandering uw milieu aan [ te bevorderen de recentste Campaign Classic bouwt ](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Voor Campagne v8, **op token-gebaseerde authentificatie** wordt wijze gesteund door alle versies, en geen verbetering is nodig.

* U hebt een APNs-verificatietoken voor ondertekening nodig om de tokens te genereren die uw server gebruikt. U vraagt deze sleutel van uw Apple ontwikkelaarsrekening, zoals die in [ documentatie van de Ontwikkelaar van Apple ](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"} wordt verklaard.

* Voor Hybride, Gehoste en Managed Services plaatsingen, naast de hieronder overgangsprocedure, contacteer Adobe om uw Real-Time (RT) uitvoeringsserver bij te werken. De server voor middelste bronnen heeft geen invloed op deze server.

* Als gebruiker van Campaign Classic v7 op locatie, moet u zowel de Marketing als Real-Time uitvoeringsservers bijwerken. De server voor middelste bronnen heeft geen invloed op deze server.

#### Overgangprocedure {#ios-transition-steps}

Voer de volgende stappen uit om uw mobiele iOS-toepassingen te verplaatsen naar de op token gebaseerde verificatiemodus:

1. Blader naar uw lijst van **Diensten en Abonnementen**.
1. Maak een lijst van alle mobiele toepassingen gebruikend de **op certificaat-gebaseerde authentificatie** wijze (.p12).
1. Bewerk elk van deze mobiele toepassingen en blader naar het **Certificaat/Persoonlijke sleutel** lusje.
1. Van de **drop-down Wijze van de Authentificatie**, uitgezochte **op token-gebaseerde authentificatie** wijze (.p8).
1. Vul de instellingen voor de APNs-verbinding **[!UICONTROL Key Id]** , **[!UICONTROL Team Id]** en **[!UICONTROL Bundle Id]** in en selecteer vervolgens het p8-certificaat door op **[!UICONTROL Enter the private key...]** te klikken.

   ![](assets/token-based-certif.png)

1. Klik op **[!UICONTROL Test the connection]** om te controleren of de configuratie juist is en of de server toegang heeft tot APN&#39;s. Voor implementaties van Midden-bronnen kan de knop **[!UICONTROL Test connection]** niet controleren of de server toegang heeft tot APN&#39;s.
1. Klik op **[!UICONTROL Next]** om de productietoepassing te configureren en dezelfde stappen uit te voeren als hierboven beschreven.
1. Klik op **[!UICONTROL Finish]** en vervolgens op **[!UICONTROL Save]**.

Uw iOS-toepassing wordt nu verplaatst naar de op token gebaseerde verificatiemodus.
