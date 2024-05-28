---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 338432b41276317f1f07a92f0106e20177b5becd
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 4%

---

# Laatste versies {#latest-release}

Adobe Campaign wordt regelmatig bijgewerkt. Deze regelmatige frequentie van updates is bedoeld om de nieuwste en beste in uw handen te krijgen, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Adobe raadt alle klanten ten zeerste aan een upgrade uit te voeren naar de nieuwste versie. Deze pagina bevat nieuwe mogelijkheden, verbeteringen en oplossingen die worden geleverd met de nieuwste releases van Campagne v8 (console). Meer informatie over campagneversies en updates in [deze pagina](upgrades.md).

Als Beheerde gebruiker van Cloud Servicen, wordt uw instantie bevorderd door Adobe met elke nieuwe versie. Adobe zal contact met u opnemen en uw omgevingen upgraden. Campagne-clientconsole **moet worden geüpgraded naar dezelfde versie** als Campagneservers. Leer hoe u uw clientconsole kunt upgraden in [deze pagina](../start/connect.md#upgrade-ac-console).

Als klant moet u er bovendien voor zorgen dat u de meest recente ondersteunde versies van de systemen gebruikt die in de [Compatibiliteitsmatrix](compatibility-matrix.md).

## Release 8.5.3 {#release-8-5-3}

_28 mei 2024_

### Migratie naar externe server-naar-server-referentie {#change-8-5-3}

Beginnend deze versie, met de referentie van de Rekening van de Dienst (JWT) die door Adobe wordt verouderd, steunen de uitgaande integraties van de Campagne met de oplossingen en apps van de Adobe nu op server-aan-server referentie OAuth. [Meer informatie](#change-8-7-1)

### Oplossingen {#fixes-8-5-3}

De volgende problemen zijn opgelost in deze release:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-595 44, NEO-52542

## Release 8.7.1 {#release-8-7-1}

_2 mei 2024_

>[!AVAILABILITY]
>
>Deze release bevindt zich in **Beperkte beschikbaarheid** (LA). Alleen klanten die migreren **van Adobe Campaign Standard naar Adobe Campaign v8**, en kan niet worden ingezet op een andere omgeving.
>
>Als gebruiker van het Campaign Standard die naar Campagne v8 overgaat, meer over deze overgang in [Campagne voor gebruikersinterfacedocumentatie op het web versie 8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Nieuwe functies {#new-8-7-1}

* **Sjablonen voor uitgebreide pushmeldingen** - U kunt nu uitgebreide pushmeldingen verzenden via Android. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. [Meer informatie](../send/rich-push.md).

* **Branding** - Als gemigreerde gebruiker van een Campaign Standard kunnen uw technische beheerders nu een of meerdere merken definiëren om de parameters die de identiteit van een merk beïnvloeden, te centraliseren. Dit zijn onder andere het merklogo, het domein van de toegangs-URL voor de landingspagina&#39;s of de instellingen voor de tracking van berichten. U kunt deze merken maken en deze koppelen aan berichten of bestemmingspagina&#39;s. Deze configuratie wordt beheerd in malplaatjes. [Meer informatie](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html){target="_blank"}

* **Rest APIs** - Als gemigreerde gebruiker van een Campaign Standard kunt u Rest API&#39;s gebruiken om integratie voor Adobe Campaign te maken en uw eigen ecosysteem te bouwen door Adobe Campaign te koppelen aan het deelvenster met technologieën dat u gebruikt. [Meer informatie](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html){target="_blank"}

* **Dynamische rapportage** - Als gemigreerde gebruiker van het Campaign Standard, kunt u tot Dynamische Rapportering toegang hebben die volledig klantgerichte en real-time rapporten verstrekt om de invloed van uw marketing activiteiten te meten. Het voegt toegang tot profielgegevens toe, toelatend demografische analyse door profieldimensies zoals geslacht, stad en leeftijd naast functionele e-mailcampagnegegevens zoals opent en klikt. [Meer informatie](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

* **Nieuwe add-on voor uitgebreide beveiliging**: Om uw netwerkverbinding veiliger te maken en betere beveiliging voor uw bronnen te bieden, biedt Adobe Campaign een nieuwe add-on voor uitgebreide beveiliging, die twee functies bevat: Secure CMK-integratie en Secure VPN tunneling. [Meer informatie](../config/enhanced-security.md)


### Compatibiliteitsupdates {#comp-8-7-1}

* Databases worden nu ondersteund als externe database met FDA (Adobe Campaign Federated Data Access). Meer informatie vindt u [op deze pagina](compatibility-matrix.md#FederatedDataAccessFDA).

### Migratie naar externe server-naar-server-referentie {#change-8-7-1}

Beginnend deze versie, met de referentie van de Rekening van de Dienst (JWT) die door Adobe wordt verouderd, steunen de uitgaande integraties van de Campagne met de oplossingen en apps van de Adobe nu op server-aan-server referentie OAuth. De Adobe zal JWT aan migratie OAuth voor uw uitgaande integratie, zoals de integratie van Campaign-Analytics of de integratie van Triggers van het Experience Cloud uitvoeren.

Als u ingebouwde integratie met Campagne hebt uitgevoerd, moet u uw Technische Rekening migreren zoals die in [deze documentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. JWT-referenties (Existing Service Account) blijven werken tot **27 januari 2025**. Daarnaast blijft de Developer Console ondersteuning bieden voor het maken van nieuwe JWT-referenties (Service Account) tot **3 juni 2024**. Een nieuwe referentie van de Rekening van de Dienst (JWT) kan niet aan een project na deze datum worden gecreeerd of worden toegevoegd.


### Algemene verbeteringen {#improvements-8-7-1}

* Diverse schema&#39;s zijn veranderd van 32 in 64 beetjes. Dit geldt alleen voor klanten die vanuit Campaign Standard migreren. [Meer informatie](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html){target="_blank"}

* In Campagnetabellen worden de volgende kenmerken nu standaard ingevuld op de datum en tijd van de server: `lastModified` en `created`. De `createdBy-id` kenmerkwaarde wordt nu standaard met de huidige aanmeldings-id gevuld. Waarden die door gebruikers in API-aanroepen worden opgegeven, worden genegeerd. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### Oplossingen {#fixes-8-7-1}

De volgende kwesties zijn in deze release vastgelegd: NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-641 99, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-5 8596, NEO-58314, NEO-58004, NEO-40054
