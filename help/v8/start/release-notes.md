---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d607981e99c22bed81aa6c321b891226816a8004
workflow-type: tm+mt
source-wordcount: '2168'
ht-degree: 7%

---

# Laatste versies {#latest-release}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met Campagne v8 (console) **&#x200B;**&#x200B;komen meest recente versies. Leer meer over de versies, versies, en verbeteringen van de Campagne in [ deze pagina ](upgrades.md). Andere versies worden vermeld in de sectie Vorige releases van deze documentatie.

## Release 8.8.1 {#release-8-8-1}

_donderdag 9 juli 2025_

### Nieuwe functies {#features-8-8-1}

Eerder vrijgegeven voor een klein aantal klanten, is het volgende vermogen nu beschikbaar aan alle milieu&#39;s van FDA van de Campagne:

* **Nieuwe SMS die schakelaar verzenden** - SMS die schakelaar verzenden is gemoderniseerd en verbeterd om de verbindingen van de zendwijzeSMPP toe te laten, blijvende verbindingen toe te laten SMPP, en betere verenigbaarheid te verzekeren. Een nieuwe externe SMS-account is nu beschikbaar voor alle nieuwe SMS-implementaties. De bestaande implementatie wordt nog steeds ondersteund, maar de aanbeveling is om over te stappen op deze nieuwe, moderne en uitgebreide aansluiting. [Meer informatie](../send/sms/sms.md)

  >[!NOTE]
  >
  >Deze eigenschap is **niet** beschikbaar voor [ Plaatsingen van de Campagne FFDA ](../architecture/enterprise-deployment.md).

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

Eerder vrijgegeven in Beperkte Beschikbaarheid, is het volgende vermogen nu beschikbaar **op bestelling**:

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **Rest APIs** - u kunt Rest APIs nu gebruiken om integratie voor Adobe Campaign tot stand te brengen en uw eigen ecosysteem te bouwen door Adobe Campaign met het paneel van technologieën te verbinden die u gebruikt. De API voor Transactieberichten REST is ook beschikbaar voor het SMS-kanaal. Wanneer zowel e-mail als mobilePhone aanwezig zijn in de lading, kunt u het &quot;wishedChannel&quot;gebied gebruiken om het kanaal te specificeren. Indien niet opgegeven, wordt de e-mail standaard gebruikt, tenzij wishedChannel expliciet om SMS verzoekt. Transactionele API&#39;s die zijn gebaseerd op gebeurtenissen, zijn ook beschikbaar voor e-mails. [Meer informatie](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >Deze eigenschap is **niet** beschikbaar voor [ Plaatsingen van de Campagne FFDA ](../architecture/enterprise-deployment.md).

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

Naast de hierboven vermelde functies, wordt deze release ook geleverd met een set functionaliteiten die beschikbaar zijn via Campagne voor de webgebruikersinterface:

* [ Meertalige leveringsverwezenlijking ](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html#multilingual-delivery){target="_blank"}
* [ levering alarmerend ](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
* [ het Bestaan van pagina&#39;s verbeteringen ](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html){target="_blank"}
* [ Dynamische Rapportering ](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"} (slechts op bestelling)
* [ Gecentraliseerde Branding ](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

Verwijs naar UI van het Web van de Campagne [ versienota&#39;s ](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html){target="_blank"}.

### Algemene verbeteringen {#improvements-8-8-1}

* Microsoft Fabrics wordt nu ondersteund als een externe database met FDA (Adobe Campaign Federated Data Access). [Meer informatie](../config/external-accounts.md#transfer-data-external-accounts)
* Campagne v8 ondersteunt nu Android 15 en iOS 18 voor pushberichten. [Meer informatie](../start/compatibility-matrix.md#MobileSDK)
* Cloud-databases worden nu ondersteund in aanvulling op de on-premise databases voor Secure Virtual Private Network tunneling. [Meer informatie](../config/enhanced-security.md#vpn-databases)
* Er is een nieuwe set &quot;Provider ID&quot;-velden toegevoegd aan de sectie &quot;Binnenkomend verkeer&quot; van de SMS 2.0-connector. [Meer informatie](../send/sms/smpp-external-account.md#incoming-traffic)
* Ontvangers zonder abonnement via de methode &quot;mailto&quot; List-Unsubscribe worden niet meer naar quarantaine verzonden. Zij worden of unsubscribed van de dienst verbonden aan de levering, of verzonden naar de lijst van gewezen personen (de sectie van het profiel &quot;geen contact meer&quot;als geen de dienst voor de levering werd bepaald. [Meer informatie](../send/quarantines.md)
* Een vernieuwde versie van het inbox-renderrapport is nu beschikbaar in de Adobe Campaign-clientconsole. [Meer informatie](../send/inbox-rendering.md)

### Oplossingen {#fixes-8-8-1}

* Probleem verholpen waarbij automatische reacties niet werden ontvangen vanwege een ongeldige geldigheidsperiode in SMS 2.0. Dit verzekert correcte berichtlevering na migratie. (NEO-88088)
* Oplossing voor een probleem in SMS 2.0 waarbij bepaalde velden in de tabel `inSms` niet correct werden bijgewerkt, zodat de gegevens correct werden ingevoegd voor SMS-functies. (NEO-87906)

<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
-->

* Bied een stille installatiemechanisme voor de clientconsole om grootschalige upgrades mogelijk te maken zonder tussenkomst van de gebruiker. Dit lost uitdagingen met handinstallaties op. (NEO-69772)
* Problemen met de workflow voor het opruimen van databases verholpen als gevolg van ontbrekende of onjuiste kolomverwijzingen in SQL-query&#39;s. Hierdoor worden logbestanden en bezoekersgegevens op de juiste wijze gewist. (NEO-86813)
* Oplossing voor een probleem waarbij gebeurtenisdatums ontbraken in leveringslogboeken. Deze correctie zorgt voor een nauwkeurige populatie met gebeurtenisdatums, die essentieel is voor geplande triggers en workflows. (NEO-86708)
* Problemen met het invoegen van het SMS-leveringslogboek zijn opgelost in SMS 2.0, zodat u zich correct kunt aanmelden in de tabel `nmsBroadLogMid` . (NEO-86556)
* Oplossing voor problemen met het uitpakken van bestanden in de externe leveringsmodus in Direct Mail-sjablonen, zodat compatibiliteit en functionaliteit gegarandeerd zijn. (NEO-86520)
* Opgeloste kwesties van de leveringsverwerking met betrekking tot gespleten die over veelvoudige MID instanties verpletteren, die nauwkeurige updates van de leveringsstatus en productie verzekeren. (NEO-86500)
* Oplossing voor ontbrekende volggegevens in dynamische rapporten na de migratie van Campaign Standard naar Campaign v8. Hierdoor is een nauwkeurige rapportage voor leveringstrackinglogboeken gegarandeerd. (NEO-86419)
* Opgeloste workflow die problemen veroorzaakte waarbij twee keer werkstromen werden uitgevoerd, waardoor dubbele toetsovertredingen werden veroorzaakt. Deze oplossing zorgt voor een correcte afhandeling en uitvoering van gebeurtenissen. (NEO-86154)
* Compatibiliteitsproblemen verholpen met Opnieuw verschuiven van OTB SQL-functies na implementatie, zodat functies zoals `GetDate()` correct worden uitgevoerd in workflows. (NEO-85834)
* Opgeloste renderingproblemen in e-mailbuilds waarbij afbeeldingen verdwenen wanneer URL&#39;s werden toegevoegd. Deze correctie zorgt voor een correcte weergave van de afbeelding in voorvertoningen in Postvak IN. (NEO-85716)
* Gecorrigeerde rendering van gekrulde afsluitaanhalingstekens in WebUI, waardoor nauwkeurige tekenweergave in e-mailleveringen wordt gegarandeerd. (NEO-85687)
* Vaste functionaliteit voor het koppelen van spiegelpagina&#39;s, zodat de verschillende talen op de spiegelpagina&#39;s correct kunnen navigeren. (NEO-85625)
* Opgeloste problemen met de datumnotatie in de datumkiezers van de webapp, zodat deze compatibel zijn met Japanse datumnotaties (`yyyy-mm-dd`). (NEO-85234)
* Oplossing voor workflowproblemen na verwerking met alternatieve routeringsinstellingen in midsourcing, zodat de workflow correct werd uitgevoerd. (NEO-85111)
* Verbeterde leveringdoorvoer van Android bij het gebruik van golven, zodat de leveringsonderdelen in de juiste volgorde worden verwerkt op basis van planning. (NEO-84324)
* Problemen met de voorbereiding van de levering verholpen als gevolg van null-verwerkingsfouten in de functie `to_varchar` . Hierdoor wordt de campagne soepel gestart. (NEO-84108)
* Oplossing voor SFTP-verbindingsproblemen die zijn veroorzaakt door verouderde `libcurl` - en `libssh2` -versies, waardoor compatibiliteit met SFTP-servers met Azure-hosted wordt gegarandeerd. (NEO-84038)
* Probleem verholpen met Snowflake FDA-connectors waarbij fouten met sleutelpaarverificatie werden veroorzaakt, waardoor databaseverbindingen met succes werden gegarandeerd. (NEO-84024)
* Problemen met de functionaliteit van typologieregel zijn opgelost, zodat de drukregels correct worden toegepast in PUSH-leveringen. (NEO-84010)
* Oplossing voor BigQuery-queryfouten die zijn veroorzaakt door onjuiste datum- en tijdstempelvergelijkingen na de upgrade, waardoor compatibiliteit met filtervoorwaarden wordt gegarandeerd. (NEO-83826)
* Oplossing voor een probleem waarbij leveringsactiviteiten zouden mislukken als gepauzeerde leveringen werden hervat als gevolg van personalisatiefouten. Deze oplossing zorgt voor vloeiender leveringsworkflows en voorkomt fouten met betrekking tot gepauzeerde activiteiten. (NEO-83809)
* Los een kwestie in FFDA, wanneer het gebruiken van de &quot;optie van de ladingsvraag van het doelverslag&quot;op. Ondersteuning voor &#39;order by&#39;- en &#39;where&#39;-clausules is toegevoegd. (NEO-83793)
* Herhalende leveringsmislukkingen die door ongeldige waarden worden veroorzaakt die aan niet-nullable kolommen in de brede lijst worden geschreven LogRcp. worden opgelost. Deze oplossing verbetert de betrouwbaarheid van de levering en voorkomt fouten tijdens live campagnes. (NEO-83729)
* Oplossing voor een probleem waarbij zaadadressen tijdens de voorbereiding van de levering werden gedupliceerd, wat tot discrepanties in berichtaantallen leidde. Deze oplossing zorgt ervoor dat u zich nauwkeurig kunt richten en dat dubbele fouten worden voorkomen. (NEO-83703)
* Oplossing van een kritiek probleem waarbij productieleveringen na de geldigheidsperiode werden verzonden, hetgeen juridische bezwaren kan doen rijzen. Leveringen houden zich nu strikt aan de vastgestelde geldigheidstermijnen. (NEO-83350)
* Oplossing voor een ruimteprobleem dat zich voordeed bij het laden van grote gegevensvolumes in Teradata-tabellen. Deze oplossing optimaliseert gegevensverwerking en verhelpt af en toe fouten in productieomgevingen. (NEO-83252)
* Oplossing voor een technische werkschemafout met betrekking tot SendMetricsToNewRelic fouten, die vertragingen in RT gebeurtenisverwerking veroorzaakte. Deze oplossing zorgt voor een vloeiender workflowuitvoering en voorkomt terugloggen van gebeurtenissen. (NEO-83143)
* Oplossing voor een fout in de workflow voor het opschonen van databases die werd veroorzaakt door omzettingsproblemen van id naar UUID in FFDA-interactieinstanties. Deze update zorgt voor een correcte opschoonbewerking en verlaagt de systeembelasting. (NEO-83138)
* Opgeloste leveringsmislukkingen die door beperkingen op zaad-lid interne naamlengten worden veroorzaakt. Met deze correctie zijn langere interne namen mogelijk zonder dat dit invloed heeft op de personalisatie van de levering. (NEO-83044)
* Probleem verholpen waarbij leveringen vastzaten in personalisatie wegens willekeurige fouten. Deze update zorgt voor vloeiendere personalisatieprocessen en betrouwbare uitvoering van de levering. (NEO-82781)
* Oplossing voor een probleem waarbij de aanbiedingsvoorstellen niet in de console konden worden bekeken vanwege API-fouten en traagheid. Deze oplossing verbetert de reactiesnelheid van de gebruikersinterface en zorgt voor de juiste functionaliteit van de aanbieding. (NEO-82742)
* Oplossing voor periodiek vastlopen in de Adobe Campaign-console bij gebruik van aangepaste leveringsobjecten. Deze oplossing garandeert stabiliteit en betrouwbaarheid wanneer u werkt met aangepaste workflows. (NEO-82675)
* Oplossing voor problemen met trage verwerking en workflow die zijn gemeld na het migreren van v7 naar v8. Deze update optimaliseert de workflows van de campagne en zorgt voor tijdige uitvoering. (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* Oplossing voor een kritiek probleem waarbij MTA-onderliggende processen vastzaten, waarbij Push en WhatsApp-leveringen werden geblokkeerd. Deze update zorgt voor vloeiendere communicatieworkflows en voorkomt leveringsknelpunten. (NEO-82351)
* Probleem met gegevensmigratie opgelost waarbij tekenreeksvelden uit GCP-tabellen fouten veroorzaakten tijdens updates voor Teradata. Met deze correctie wordt de noodzaak van tijdelijke oplossingen verwijderd en wordt de efficiëntie van de workflow verbeterd. (NEO-82260)
* De bijgewerkte logica van de gegevensbestandschoonmaak om voor primaire gegevensbestanden in instanties van FFDA rekenschap te geven, verhinderend onnodige pogingen om niet-bestaande lijsten te zuiveren. Met deze correctie optimaliseert u opschoonbewerkingen. (NEO-81879)
* Opgeloste consolecrashes die door subworkflows in combinatie met enum gebieden worden veroorzaakt te gebruiken. Deze correctie zorgt voor stabiliteit wanneer u werkt met verrijkte workflows. (NEO-81864)
* Probleem verholpen waarbij velden met subaffiniteit in doeltoewijzingen onjuist werden gewijzigd na duplicatie van levering, waardoor de workflow mislukte. Deze update zorgt voor consistente subaffiniteitswaarden. (NEO-81809)
* Extra ondersteuning voor jokertekens in bestandsoverdrachtsactiviteiten in Adobe Campaign Classic v8, zodat gebruikers bestanden met dynamische namen (bijvoorbeeld `abc_*` ) kunnen uploaden in workflows. (NEO-81758)
* Introduceerde een optie om de markering `content-available` in iOS-pushberichten voor Adobe Campaign Classic v8 in te schakelen. Dankzij deze verbetering kunnen mobiele apps berichten opslaan in het Postvak IN en worden updates op de achtergrond ondersteund, zodat problemen met betrekking tot het verwijderen van leveringen die door APNS-beperkingen worden veroorzaakt, worden opgelost. (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* Er is een time-outconfiguratieoptie toegevoegd voor BigQuery-verbindingen in Adobe Campaign Classic v8. Deze verbetering staat gebruikers toe om de onderbrekingsperiode voor vragen aan te passen, die kwesties met vraagmislukkingen wegens standaardonderbrekingsgrenzen oplossen. (NEO-81222)
* Probleem verholpen waarbij URL&#39;s van spiegelpagina&#39;s mislukten voor leveringen die via Split en Alternate werden verzonden die externe accounts na v8-migratie routeren. Dit probleem is nu opgelost. De onderliggende leveringsonderdelen worden nu correct gekopieerd naar `mirrorPageInfo` . (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* Vaste de &quot;Toegang tot het nieuwe Web UI&quot;knoop in de cliëntconsole om aan correcte URL (`https://experience.adobe.com`) voor productieinstanties te richten. Hiermee worden problemen met ongeldige URL&#39;s in productieomgevingen opgelost. (NEO-80673)
* Probleem verholpen in de activiteit Splitsen waarbij het gebruik van zowel Sorteren als Grootte (als percentage van het segment) SQL-fouten veroorzaakte. De functionaliteit werkt nu correct. (NEO-80432)
* Probleem met vastlopen in workflows opgelost met `CCurlAzureBlobStorage::UploadStream` . De workflows worden nu uitgevoerd zonder segmentatiefouten tijdens uploads van Azure Blob Storage. (NEO-79598)
* Oplossing voor een probleem waarbij spiegelpagina&#39;s niet konden worden bekeken vanaf de clientconsole in productieomgevingen. De paginakoppelingen spiegelen werken nu correct in zowel de e-mail- als de consoleweergave. (NEO-78946)
* Probleem met leveringslogbestand verholpen waarbij sommige logbestanden ten onrechte werden gemarkeerd als &quot;Aflevering geannuleerd&quot; ondanks geslaagde berichtlevering. De hoofdoorzaak met betrekking tot verschillen in contactdatum en gebeurtenisdatum is opgelost. (NEO-78933)
* De `com.google.code.gson:gson` -bibliotheek is bijgewerkt om de beveiliging te verbeteren. (NEO-78299)
* Oplossing voor fouten met dubbele toetsrestricties in FDA-verbindingslogbestanden (`nmsconnectionlogs`) die workflowfouten veroorzaakten. De invoeglogica is aangepast om dubbele id&#39;s te voorkomen. (NEO-78050)
* Probleem verholpen waarbij in quarantaine geplaatste e-mailadressen ten onrechte als mobiel werden gemarkeerd in de adrestabel, waardoor fouten in de leveringsanalyse werden veroorzaakt. De logica voor afstemming tussen leveringsobjecten is gecorrigeerd. (NEO-76986)
* Oplossing voor een fout bij de voorbereiding van de levering bij het gebruik van controlegroepen met een Oracle-database. De SQL query generation is gecorrigeerd voor compatibiliteit met Oracle databases. (NEO-76947)
* Oplossing voor mislukte aflevering die werd veroorzaakt door het gelijktijdig maken van mappen tijdens overgangen van nieuwe maanden. De logica voor het maken van de leveringsmap is aangepast om dubbele toetsovertredingen te voorkomen. (NEO-76824)
* Problemen met conversie van tijdzones in externe accounts van Teradata zijn opgelost. De weergegeven tijdstempels worden nu correct uitgelijnd met de geconfigureerde tijdzone-instellingen. (NEO-76716)
* Verbeterde workflows voor het opschonen van databases om grote datasets efficiënt te verwerken. Er is een nieuwe aanpak geïmplementeerd waarbij rij-id&#39;s worden gebruikt en variabelen worden gebonden om de prestaties van de verwijdering te optimaliseren. (NEO-76439)
* Oplossing voor een probleem waarbij bij externe leveringen met het kanaal &quot;Ander&quot; geen uitvoerbestanden werden gegenereerd. De leveringseigenschappen omvatten nu correct de dossierweg voor geproduceerde dossiers. (NEO-75962)
* Correctie van fouten in de `ffdaReplicateStagingData` -workflow die werden veroorzaakt door grote gegevensupdates. Time-outinstellingen en tabelformaatbeheer zijn geoptimaliseerd om mislukte workflows te voorkomen. (NEO-75643)
* Probleem opgelost waarbij het voorvertonen van bestanden voor directe e-mailuitvoer ertoe leidde dat dashboards leeg werden. Het dashboard wordt nu correct weergegeven na voorvertoningen van bestanden. (NEO-75359)
* Verbeterde traceerindicatoren voor pushberichten, zodat klikken en openen worden opgenomen. Indicatoren zoals `@recipientClick` , `@personClick` en `@totalRecipientClick` houden nu rekening met kliks in mobiele meldingen. (NEO-75240)
* Correctie van fouten in opschoningsworkflows voor leveringen met externe statussen waarvoor annulering was aangevraagd. De logica voor het ophalen van databaserecords is gecorrigeerd. (NEO-74833)
* Het probleem met de tijdzoneverschillen in Rusland (UTC+3:00 Moskou) is opgelost, waarbij de uitvoertijden van `nlserver` onjuist waren. De tijdsynchronisatielogica is bijgewerkt. (NEO-74754)
* Correctie van fouten in de `defaultMidSourcingDlvStat` -workflow die werden veroorzaakt door onjuiste SQL-syntaxis voor MSSQL-databases. De logica van de vraaggeneratie is aangepast voor verenigbaarheid. (NEO-74156)
* Meerdere crashes in het webproces zijn opgelost. (NEO-73174)
* Probleem verholpen waarbij BigQuery-query mislukte wanneer apostroffen aanwezig waren in voorwaarden. De logica voor queryverwerking is bijgewerkt om speciale tekens correct te interpreteren. (NEO-72547)
* Het probleem waarbij de typologische regels met uitsluitingsfilters niet correct werkten, is opgelost. De SQL-querygeneratie voor de voorbereiding van de levering is opgelost. (NEO-72292)
* Oplossing voor verschillen in gebeurtenisdatums en contactdatums voor stuiteringsbeheer. De logica voor tijdzoneafhandeling is verbeterd. (NEO-72277)
* Verbeterde afhandeling van onjuist geconverteerde UTF-8-tekens in directe mailleveringen. Verborgen tekens worden nu correct verwerkt om mislukte aflevering te voorkomen. (NEO-72148)
* Correctie van fouten in de binnenkomende activiteit van SMS waar de filters sparen kwesties veroorzaakten. De workflow bespaart nu op de juiste wijze zonder fouten te genereren. (NEO-70427)
* Gecorrigeerde SQL vraaggeneratie voor gegroepeerde geschiktheidscriteria in aanbiedingsruimten. Ontbrekende haakjes in SQL-voorwaarden zijn toegevoegd voor een juiste filtering. (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* Correctie van af en toe optredende fouten in de workflows voor het laden van BigQuery-gegevens die werden veroorzaakt door problemen met HTTP-inhoud of overdrachtcodering. De logica voor het afhandelen van verbindingen is verbeterd. (NEO-66989)

