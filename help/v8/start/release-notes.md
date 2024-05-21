---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 247d687597c6784aec49b70f9e68f50e49d169dd
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 5%

---

# Nieuwste release{#latest-release}

Adobe Campaign wordt regelmatig bijgewerkt. Deze regelmatige frequentie van updates is bedoeld om de nieuwste en beste in uw handen te krijgen, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Adobe raadt alle klanten ten zeerste aan een upgrade uit te voeren naar de nieuwste versie.

Als Beheerde gebruiker van Cloud Servicen, wordt uw instantie bevorderd door Adobe met elke nieuwe versie. Adobe zal contact met u opnemen en uw omgevingen upgraden. Campagne-clientconsole **moet worden geüpgraded naar dezelfde versie** als Campagneservers. Leer hoe u uw clientconsole in deze [page](../start/connect.md#upgrade-ac-console).

Als klant moet u er bovendien voor zorgen dat u de meest recente ondersteunde versies van de systemen gebruikt die in de [Compatibiliteitsmatrix](compatibility-matrix.md).

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

<!--
* **New Enhanced security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling.
-->

### Compatibiliteitsupdates {#comp-8-7-1}

Databases worden nu ondersteund als externe database met FDA (Adobe Campaign Federated Data Access). Meer informatie vindt u [op deze pagina](compatibility-matrix.md#FederatedDataAccessFDA).

### Algemene verbeteringen {#improvements-8-7-1}

* Diverse schema&#39;s zijn veranderd van 32 in 64 beetjes. Dit geldt alleen voor klanten die vanuit Campaign Standard migreren. [Meer informatie](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html){target="_blank"}

* In Campagnetabellen worden de volgende kenmerken nu standaard ingevuld op de datum en tijd van de server: `lastModified` en `created`. Waarden die door gebruikers in API-aanroepen worden opgegeven, worden genegeerd. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### Oplossingen {#fixes-8-7-1}

De volgende kwesties zijn in deze release vastgelegd: NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-641 99, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-5 8596, NEO-58314, NEO-58004, NEO-40054

## Release 8.6.2 {#release-8-6-2}

_23 feb. 2024_

### Oplossingen {#fixes-8-6-2}

In deze release wordt het volgende probleem opgelost:

* Oplossing voor een prestatieprobleem dat zich kon voordoen op de mid-sourcing instantie (NEO-72595).

## Release 8.6.1 {#release-8-6-1}

_14 feb. 2024_

### Nieuwe functies {#new-8-6-1}

* Vanaf deze release hebt u toegang tot de nieuwe **Gebruikersinterface Campagne Web**, beschikbaar via de centrale Adobe Experience Cloud-omgeving. Experience Cloud is de geïntegreerde familie van digitale marketingtoepassingen, producten en diensten van de Adobe. Via de intuïtieve interface hebt u snel toegang tot uw cloudtoepassingen, productfuncties en services. Leer hoe u verbinding maakt met Adobe Experience Cloud en toegang krijgt tot de Adobe Campaign Web Interface [op deze pagina](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 kan nu worden geïntegreerd met **Adobe Experience Manager as a Cloud Service**, waarbij het ontwerpen uitsluitend beschikbaar is via de Adobe Campaign Web User Interface. [Meer informatie](../connect/ac-aem.md)

* U kunt nu uw **Adobe Experience Manager Assets-bibliotheek** naast uw Experience Cloud Assets, zelfs als het Integration with the Adobe Experience Cloud package op uw Adobe Campaign-exemplaar is geïnstalleerd. [Meer informatie](../connect/ac-aem.md#assets-library)

### Algemene verbeteringen {#improvements-8-6-1}

* Campagne v8.6 zorgt voor verbeterde doorvoer voor **e-mailvolgindicatoren voor leveringen**. Met onze geoptimaliseerde processen wordt de opname- en computertijd minder lang en kunt u de belangrijkste indicatoren voor de levering veel sneller controleren.


### Leverbaarheid-updates {#deliverability-8-6-1}

* Tegen februari 2024 verzendt een bedrijf meer dan 5000 e-mailberichten via Google of Yahoo! zal moeten beginnen gebruikend een authentificatietechnologie die als op domein-gebaseerde Rapportering en Conformiteit van de Authentificatie van het Bericht (DMARC) wordt bekend. Zorg ervoor dat DMARC-record is ingesteld voor alle subdomeinen die u gebruikt met Adobe Campaign. [Meer informatie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=nl){target="_blank"}

* Vanaf 1 juni 2024, Google en Yahoo! voldoen aan uitschrijven met één klik voor lijsten. Adobe Campaign biedt nu ondersteuning voor deze optie. [Meer informatie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Oplossingen {#fixes-8-6-1}

De volgende kwesties zijn in deze release vastgelegd: NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-6387, NEO-632 94, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-6 1199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, O-50488, NEO-47789