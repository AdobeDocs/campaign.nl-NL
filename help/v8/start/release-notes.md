---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: bd53d04791af91afffe683ca92fa78562640170a
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 15%

---

# Laatste versies {#latest-release}

Adobe Campaign wordt regelmatig bijgewerkt. Deze regelmatige frequentie van updates is bedoeld om de nieuwste en beste in uw handen te krijgen, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Adobe raadt alle klanten ten zeerste aan een upgrade uit te voeren naar de nieuwste versie. Deze pagina bevat nieuwe mogelijkheden, verbeteringen en oplossingen die worden geleverd met de nieuwste releases van Campagne v8 (console). Leer meer over de versies en updates van de Campagne in [ deze pagina ](upgrades.md).

Als Beheerde gebruiker van Cloud Servicen, wordt uw instantie bevorderd door Adobe met elke nieuwe versie. Adobe zal contact met u opnemen en uw omgevingen upgraden. De cliëntconsole van de campagne **moet aan de zelfde versie** worden bevorderd zoals de servers van de Campagne. Leer hoe te om uw cliëntconsole in [ te bevorderen deze pagina ](../start/connect.md#upgrade-ac-console).

Bovendien als klant, zorg ervoor dat u de recentste gesteunde versies van de systemen gebruikt die in de [ matrijs van de Verenigbaarheid ](compatibility-matrix.md) worden vermeld.



## Release 8.6.3 {#release-8-6-3}

_woensdag 30 juli 2024_

### Nieuwe functies {#new-8-6-3}

* **Rich Push Bericht** - u kunt rijke dupberichten nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. Met deze versie is een set sjablonen voor uitgebreide pushmeldingen nu beschikbaar voor uw iOS- en Android-apps. [Meer informatie](../send/rich-push.md).

* Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. [Meer informatie](release-notes.md#change-8-7-1)

### Algemene verbeteringen {#improvements-8-6-3}

* Om de beveiliging van alle communicatie tussen toepassingen te verbeteren, wordt mTLS nu ondersteund voor externe API-aanroepen.

### Oplossingen {#fixes-8-6-3}

De volgende problemen zijn opgelost in deze release:

NEO-79328, NEO-7843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-725 04, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## Release 8.5.3 {#release-8-5-3}

_Mei 28, 2024_

### Migratie naar externe server-naar-server-referentie {#change-8-5-3}

Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. [Meer informatie](#change-8-7-1)

### Oplossingen {#fixes-8-5-3}

De volgende problemen zijn opgelost in deze release:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-595 44, NEO-52542


## Meerdere updates {#may-updates}

De volgende wijziging is vrijgegeven in mei en is nu beschikbaar voor gebruikers van Campaign v8:

* **Nieuwe Uitgebreide Veiligheid toe:voegen-op**: Om uw netwerkverbinding veiliger te maken en betere veiligheid voor uw middelen te verstrekken, biedt Adobe Campaign een nieuwe Uitgebreide Veiligheid toe:voegen-op aan, die twee eigenschappen omvat: Veilige integratie CMK en Veilig een tunnel graven van VPN. [Meer informatie](../config/enhanced-security.md)


## Release 8.7.1 {#release-8-7-1}

_Mei 2, 2024_

>[!AVAILABILITY]
>
>Deze versie is in **Beperkte Beschikbaarheid** (LA). Het is beperkt tot klanten die **van Adobe Campaign Standard aan Adobe Campaign v8** migreren, en kan niet op een ander milieu worden opgesteld.
>
>Als gebruiker die van het Campaign Standard aan Campagne v8 overgaat, leer meer over deze overgang in [ het document van het Webgebruikersinterface van de Campagne v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration) {target="_blank"}.

### Nieuwe functies {#new-8-7-1}

* **de rijke malplaatjes van het Bericht van de Duw** - u kunt rijke dupberichten via Android nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. [Meer informatie](../send/rich-push.md).

* **Brandend** - als Campaign Standard gemigreerde gebruiker, kunnen uw technische beheerders één of verscheidene merken nu bepalen om de parameters te centraliseren die de identiteit van een merk beïnvloeden. Dit zijn onder andere het merklogo, het domein van de toegangs-URL voor de landingspagina&#39;s of de instellingen voor de tracking van berichten. U kunt deze merken maken en deze koppelen aan berichten of bestemmingspagina&#39;s. Deze configuratie wordt beheerd in malplaatjes. [ las meer ](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html) {target="_blank"}

* **Rest APIs** - als een Campaign Standard gemigreerde gebruiker, kunt u Rest APIs gebruiken om integratie voor Adobe Campaign tot stand te brengen en uw eigen ecosysteem te bouwen door Adobe Campaign met het paneel van technologieën te verbinden die u gebruikt. [ las meer ](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html) {target="_blank"}

* **Dynamische Rapportering** - als Campaign Standard gemigreerde gebruiker, kunt u tot Dynamische Rapportering toegang hebben die volledig klantgerichte en real-time rapporten verstrekt om het effect van uw marketing activiteiten te meten. Het voegt toegang tot profielgegevens toe, toelatend demografische analyse door profieldimensies zoals geslacht, stad en leeftijd naast functionele e-mailcampagnegegevens zoals opent en klikt. [ las meer ](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html) {target="_blank"}

### Compatibiliteitsupdates {#comp-8-7-1}

* Databases worden nu ondersteund als externe database met FDA (Adobe Campaign Federated Data Access). Meer informatie vindt u [op deze pagina](compatibility-matrix.md#FederatedDataAccessFDA).

### Migratie naar externe server-naar-server-referentie {#change-8-7-1}

Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. Adobe zal de migratie van JWT naar OAuth voor uw uitgaande integraties uitvoeren, zoals de integratie van Campaign-Analytics en de integratie van Experience Cloud-triggers.

Als u binnenkomende integratie met Campagne hebt uitgevoerd, moet u uw Technische Rekening zoals die in [ wordt gedetailleerd deze documentatie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/) migreren {target="_blank"}. De bestaande geloofsbrieven van de Rekening van de Dienst (JWT) zullen blijven werken tot **27 Januari, 2025**.

### Algemene verbeteringen {#improvements-8-7-1}

* Diverse schema&#39;s zijn veranderd van 32 in 64 beetjes. Dit geldt alleen voor klanten die vanuit Campaign Standard migreren. [ las meer ](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html) {target="_blank"}

* In Campagnetabellen worden de volgende kenmerken nu standaard ingevuld op de datum en tijd van de server: `lastModified` en `created` . De kenmerkwaarde `createdBy-id` wordt nu standaard met de huidige aanmeldings-id gevuld. Waarden die door gebruikers in API-aanroepen worden opgegeven, worden genegeerd. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Om de beveiliging van alle communicatie tussen toepassingen te verbeteren, wordt mTLS nu ondersteund voor externe API-aanroepen.

### Oplossingen {#fixes-8-7-1}

De volgende problemen zijn opgelost in deze release:

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-681 92, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-6 3706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, O-58314, NEO-58004, NEO-40054
