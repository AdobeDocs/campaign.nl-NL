---
title: Opmerkingen bij de release Campagne v8 (console) 2024
description: Lijst met functies en verbeteringen die beschikbaar zijn in de 2024-campagne v8-versies
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 13%

---

# Opmerkingen bij de release 2024 {#2024-rn}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen, en moeilijke situaties die met **komen 2024 de Versies van de Campagne v8**. Voor de recentste versie, verwijs naar [ deze pagina ](release-notes.md).

Voor om het even welke nieuwe implementatie of verbetering aan een bestaand milieu, installeer [ de recentste versie ](release-notes.md).


>[!BEGINSHADEBOX]

**In deze pagina**

* Campagne v8.7 - [ Versie 8.7.1 ](#release-8-7-1) | [ Versie 8.7.2 ](#release-8-7-2)
* Campagne v8.6 - [ Versie 8.6.1 ](#release-8-6-1) | [ Versie 8.6.2 ](#release-8-6-2) | [ Versie 8.6.3 ](#release-8-6-3)
* Campagne v8.5 - [ Versie 8.5.3 ](#release-8-5-3)

>[!ENDSHADEBOX]

## Release 8.7.2 {#release-8-7-2}

_sep 3, 2024_

>[!AVAILABILITY]
>
>Deze versie is in **beperkte beschikbaarheid** (Limited Availability, ofwel LA). Het is beperkt tot klanten die **van Adobe Campaign Standard aan Adobe Campaign v8** migreren, en kan niet op een ander milieu worden opgesteld.
>
>Als gebruiker die van Campaign Standard aan Campagne v8 overgaat, leer meer over deze overgang in [ het document van het Webgebruikersinterface van de Campagne v8 ](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nieuwe functies {#new-8-7-2}

* **Nieuwe SMS die schakelaar verzenden** - SMS die schakelaar verzenden is gemoderniseerd en verbeterd om de verbindingen van de zendwijzeSMPP toe te laten, blijvende verbindingen toe te laten SMPP, en betere verenigbaarheid voor milieu&#39;s te verzekeren die van Adobe Campaign Standard overgaan. Een nieuwe externe SMS-account is nu beschikbaar voor alle nieuwe SMS-implementaties. De bestaande implementatie wordt nog steeds ondersteund, maar de aanbeveling is om over te stappen op deze nieuwe, moderne en uitgebreide aansluiting. [Meer informatie](../send/sms/sms.md).

* **Rich Push Bericht (GA)** - u kunt rijke dupberichten nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. Met deze versie is een set sjablonen voor uitgebreide pushmeldingen nu beschikbaar voor uw iOS- en Android-apps. [Meer informatie](../send/rich-push-android.md).

* **het Brandmerken** - de Brandende opties zijn nu beschikbaar voor alle kanalen, met inbegrip van SMS en Directe post. [Meer informatie](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=nl-NL){target="_blank"}

### Oplossingen {#fixes-8-7-2}

De volgende problemen zijn opgelost in deze release:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-7 7795, NEO-78843, NEO-79328.

## Release 8.7.1 {#release-8-7-1}

_vrijdag 2 mei 2024_

>[!AVAILABILITY]
>
>Deze versie is in **beperkte beschikbaarheid** (Limited Availability, ofwel LA). Het is beperkt tot klanten die **van Adobe Campaign Standard aan Adobe Campaign v8** migreren, en kan niet op een ander milieu worden opgesteld.
>
>Als gebruiker die van Campaign Standard aan Campagne v8 overgaat, leer meer over deze overgang in [ het document van het Webgebruikersinterface van de Campagne v8 ](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nieuwe functies {#new-8-7-1}

* **de rijke malplaatjes van het Bericht van de Duw** - u kunt rijke dupberichten via Android nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. [Meer informatie](../send/rich-push-ios.md).

* **Branding** - als Campaign Standard migreerde gebruiker, kunnen uw technische beheerders één of verscheidene merken nu bepalen om de parameters te centraliseren die de identiteit van een merk beïnvloeden. Dit zijn onder andere het merklogo, het domein van de toegangs-URL voor de landingspagina&#39;s of de instellingen voor de tracking van berichten. U kunt deze merken maken en deze koppelen aan berichten of bestemmingspagina&#39;s. Deze configuratie wordt beheerd in malplaatjes. [Meer informatie](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=nl-NL){target="_blank"}

* **Rest APIs** - als Campaign Standard gemigreerde gebruiker, kunt u Rest APIs gebruiken om integraties voor Adobe Campaign tot stand te brengen en uw eigen ecosysteem te bouwen door Adobe Campaign met het paneel van technologieën te verbinden die u gebruikt. [Meer informatie](../dev/api/get-started-apis.md)

* **Dynamische Rapportering** - als Campaign Standard gemigreerde gebruiker, kunt u tot Dynamische Rapportering toegang hebben die volledig klantgerichte en real-time rapporten verstrekt om het effect van uw marketing activiteiten te meten. Het voegt toegang tot profielgegevens toe, toelatend demografische analyse door profieldimensies zoals geslacht, stad en leeftijd naast functionele e-mailcampagnegegevens zoals opent en klikt. [Meer informatie](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=nl-NL){target="_blank"}

### Compatibiliteitsupdates {#comp-8-7-1}

De volgende FDA-connectors zijn toegevoegd. Verwijs naar deze [ pagina ](compatibility-matrix.md#FederatedDataAccessFDA).

* Databases worden nu ondersteund als externe database met FDA (Adobe Campaign Federated Data Access).

* Er is nu een nieuwe Amazon Redshift FDA ODBC-connector beschikbaar. Het biedt verbeterde connectiviteit, gemakkelijker onderhoud en verbeterde compatibiliteit. Deze nieuwe versie brengt de volgende verbeteringen aan:

   * De nieuwe schakelaar is gebaseerd op de interface ODBC die zich op onze meest recente schakelaars FDA richt. Dit zorgt voor langdurige ondersteuning.
   * Het introduceert ook een nieuw mechanisme voor het laden van gegevens gebruikend s3 emmers, beduidend verbeterend prestaties.

  De oudere schakelaar kan nog worden gebruikt. Neem contact op met uw Adobe-vertegenwoordiger als u de nieuwe versie wilt uitproberen.

### Migratie naar externe server-naar-server-referentie {#change-8-7-1}

Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. Adobe zal de migratie van JWT naar OAuth voor uw uitgaande integraties uitvoeren, zoals de integratie van Campaign-Analytics en de integratie van Experience Cloud-triggers.

Als u binnenkomende integratie met Campagne hebt uitgevoerd, moet u uw Technische Rekening zoals die in [ wordt gedetailleerd deze documentatie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"} migreren. De bestaande geloofsbrieven van de Rekening van de Dienst (JWT) zullen tot **30 juni, 2025** blijven werken.

### Algemene verbeteringen {#improvements-8-7-1}

* Diverse schema&#39;s zijn veranderd van 32 in 64 beetjes. Dit geldt alleen voor klanten die vanuit Campaign Standard migreren. [Meer informatie](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=nl-NL){target="_blank"}

* In Campagnetabellen worden de volgende kenmerken nu standaard ingevuld op de datum en tijd van de server: `lastModified` en `created` . De kenmerkwaarde `createdBy-id` wordt nu standaard met de huidige aanmeldings-id gevuld. Waarden die door gebruikers in API-aanroepen worden opgegeven, worden genegeerd. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Om de beveiliging van alle communicatie tussen toepassingen te verbeteren, wordt mTLS nu ondersteund voor externe API-aanroepen.

### Oplossingen {#fixes-8-7-1}

De volgende problemen zijn opgelost in deze release:

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-6 7814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-637 05, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054



## Release 8.6.3 {#release-8-6-3}

_woensdag 30 juli 2024_

### Nieuwe functies {#new-8-6-3}

* **Rich Push Bericht** - u kunt rijke dupberichten nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. Met deze versie is een set sjablonen voor uitgebreide pushmeldingen nu beschikbaar voor uw iOS- en Android-apps. [Meer informatie](../send/rich-push-android.md).

* Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. [Meer informatie](release-notes-2024.md#change-8-7-1)

### Algemene verbeteringen {#improvements-8-6-3}

* Om de beveiliging van alle communicatie tussen toepassingen te verbeteren, wordt mTLS nu ondersteund voor externe API-aanroepen.

### Oplossingen {#fixes-8-6-3}

De volgende problemen zijn opgelost in deze release:

NEO-79328, NEO-7843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-725 04, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## 24 mei updates {#may-updates}

De volgende wijziging is vrijgegeven in mei en is nu beschikbaar voor gebruikers van Campaign v8:

* **Nieuwe Uitgebreide Veiligheid toe:voegen-op**: Om uw netwerkverbinding veiliger te maken en betere veiligheid voor uw middelen te verstrekken, biedt Adobe Campaign een nieuwe Uitgebreide Veiligheid toe:voegen-op aan, die twee eigenschappen omvat: Veilige integratie CMK en Veilig een tunnel graven van VPN. [Meer informatie](../config/enhanced-security.md)

## Release 8.6.2 {#release-8-6-2}

_feb 23, 2024_

### Oplossingen {#fixes-8-6-2}

In deze release wordt het volgende probleem opgelost:

* Oplossing voor een prestatieprobleem dat zich kon voordoen op de mid-sourcing-instantie (NEO-72595).

## Release 8.6.1 {#release-8-6-1}

_feb 14, 2024_

### Nieuwe functies {#new-8-6-1}

* Beginnend deze versie, hebt u toegang tot het nieuwe **gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud. Experience Cloud is een geïntegreerde Adobe-reeks met digitale marketingtoepassingen, producten en services. Via de intuïtieve interface hebt u snel toegang tot uw cloudtoepassingen, productfuncties en services. Leer hoe te met Adobe Experience Cloud te verbinden, en tot de interface van het Web van Adobe Campaign [ in deze pagina ](campaign-ui.md#ac-web-ui) toegang te hebben.

  >[!AVAILABILITY]
  >
  >De gebruikersinterface van het Web van de campagne is slechts beschikbaar aan gebruikers die met Adobe Campaign met hun Adobe ID verbinden. Leer meer over [ het Systeem van Adobe Identity Management (IMS) ](https://helpx.adobe.com/nl/enterprise/using/identity.html){target="_blank"}.
  >

* Adobe Campaign v8 integreert nu met **Adobe Experience Manager as a Cloud Service**, met auteursrecht uitsluitend beschikbaar via het Gebruikersinterface van het Web van Adobe Campaign. [Meer informatie](../connect/ac-aem.md)

* U kunt uw **bibliotheek van Adobe Experience Manager Assets** naast uw Experience Cloud Assets nu gebruiken zelfs als de Integratie met het pakket van Adobe Experience Cloud op uw instantie van Adobe Campaign geïnstalleerd is. [Meer informatie](../connect/ac-aem.md#assets-library)

### Algemene verbeteringen {#improvements-8-6-1}

* De campagne v8.6 brengt betere productie voor **e-maillevering volgindicatoren**. Met onze geoptimaliseerde processen wordt de opname- en computertijd minder lang en kunt u de belangrijkste indicatoren voor de levering veel sneller controleren.


### Leverbaarheid-updates {#deliverability-8-6-1}

* Tegen februari 2024 verzendt een bedrijf meer dan 5000 e-mailberichten via Google of Yahoo! zal moeten beginnen gebruikend een authentificatietechnologie die als op domein-gebaseerde Rapportering en Conformiteit van de Authentificatie van het Bericht (DMARC) wordt bekend. Zorg ervoor dat DMARC-record is ingesteld voor alle subdomeinen die u gebruikt met Adobe Campaign. [Meer informatie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=nl){target="_blank"}

* Vanaf 1 juni 2024, Google en Yahoo! voldoen aan uitschrijven met één klik voor lijsten. Adobe Campaign biedt nu ondersteuning voor deze optie. [Meer informatie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=nl-NL#list-unsubscribe){target="_blank"}


### Oplossingen {#fixes-8-6-1}

De volgende problemen zijn opgelost in deze release:

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-6 3973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-629 64, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789



## Release 8.5.3 {#release-8-5-3}

_woensdag 28 mei 2024_

### Migratie naar externe server-naar-server-referentie {#change-8-5-3}

Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. [Meer informatie](#change-8-7-1)

### Oplossingen {#fixes-8-5-3}

De volgende problemen zijn opgelost in deze release:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-5 2542