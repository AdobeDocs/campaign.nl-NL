---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6d2425f7e7f35f5461151790fbda2bef2959bff4
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 12%

---

# Laatste versies {#latest-release}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met Campagne v8 (console) **&#x200B;**&#x200B;komen meest recente versies. Leer meer over de versies, versies, en verbeteringen van de Campagne in [ deze pagina ](upgrades.md). Andere versies worden vermeld in de sectie Vorige releases van deze documentatie.

>[!BEGINSHADEBOX]

**op deze pagina**

* [Release 8.6.5](#release-8-6-4)
* [Release 8.7.4](#release-8-7-4)
* [Release 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## Release 8.6.5 {#release-8-6-5}

_zaterdag 25 april 2025_

>[!AVAILABILITY]
>
>Deze versie is in **Beperkte Beschikbaarheid** (LA).

### Nieuwe functies {#features-8-6-5}

**Nieuwe SMS die schakelaar verzenden** - SMS die schakelaar verzenden is gemoderniseerd en verbeterd om de verbindingen van de zendwijzeSMPP toe te laten, blijvende verbindingen toe te laten SMPP, en betere verenigbaarheid voor milieu&#39;s te verzekeren die van Adobe Campaign Standard overgaan. Een nieuwe externe SMS-account is nu beschikbaar voor alle nieuwe SMS-implementaties. De bestaande implementatie wordt nog steeds ondersteund, maar de aanbeveling is om over te stappen op deze nieuwe, moderne en uitgebreide aansluiting. [Meer informatie](../send/sms/sms.md).

### Algemene verbeteringen {#improvements-8-6-5}

* De algemene prestaties van de toepassing zijn verbeterd in de context van een implementatie in het kader van een Enterprise-abonnement (FFDA), waaronder het verzenden van leveringsbewijzen en het opschonen van databases.

* Om de beveiliging van alle communicatie tussen toepassingen te verbeteren, wordt mTLS nu ondersteund voor externe API-aanroepen.

* Mail Transfer Agent (MTA) - Probleem opgelost met een verweesde onderliggende MTA die vast bleef zitten op de status **[!UICONTROL Start pending]**.

### Oplossingen {#fixes-8-6-5}

De volgende problemen zijn ook opgelost in deze release:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Release 8.7.4 {#release-8-7-4}

_vrijdag 10 april 2025_

>[!AVAILABILITY]
>
>Deze versie is in **beperkte beschikbaarheid** (Limited Availability, ofwel LA). Het is beperkt tot klanten die **van Adobe Campaign Standard aan Adobe Campaign v8** migreren, en kan niet op een ander milieu worden opgesteld.
>
>Als gebruiker die van Campaign Standard aan Campagne v8 overgaat, leer meer over deze overgang in [ het document van het Webgebruikersinterface van de Campagne v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nieuwe functies {#features-8-7-4}

* **REST API van SMS steun** - De Transactionele BEDRIJFSTAK API is nu beschikbaar voor het kanaal van SMS. Wanneer zowel e-mail als mobilePhone aanwezig zijn in de lading, kunt u het &quot;wishedChannel&quot;gebied gebruiken om het kanaal te specificeren. Indien niet opgegeven, wordt de e-mail standaard gebruikt, tenzij wishedChannel expliciet om SMS verzoekt.

* **Meertalige leveringen** - de aanvang van de Versie van het Gebruikersinterface van het Web van de Campagne April, zult u veelvoudige e-mailleveringen in verschillende talen kunnen verzenden, en tot de verwante dynamische rapporten toegang hebben. Deze mogelijkheid is alleen beschikbaar in de Adobe Campaign Web User Interface eind april en vereist een serverupdate naar Campagne v8.7.4.

### Oplossingen {#fixes-8-7-4}

De volgende problemen zijn opgelost in deze release:

NEO-80245, NEO-83559

## Release 8.6.4 {#release-8-6-4}

_jan 15, 2025_

### Algemene verbeteringen {#improvements-8-6-4}

* De stabiliteit van de toepassing van de campagne is verbeterd tijdens leveringsanalyse in de context van een [ plaatsing van de Onderneming (FFDA) ](../../v8/architecture/enterprise-deployment.md).
* Deze release wordt geleverd met verbeterde en verbeterde FFDA-architectuurmechanismen, waaronder sleutelbeheer, staging en gegevensreplicatie.
* De nieuwe technische werkschema&#39;s zijn geïntroduceerd voor de [ plaatsing van de Onderneming (FFDA) ](../../v8/architecture/enterprise-deployment.md). Deze werkschema&#39;s repliceren levering en verwante gegevens door parallelle replicatieverzoeken op overeenkomstige lijsten te centraliseren. Deze workflow begint met `Replicate nms` . [Meer informatie](../architecture/replication.md)
* Een nieuwe **laat controleur van de controlehond toe om werkschema te houden dat permanent** optie loopt is nu beschikbaar in de werkschemaeigenschappen. Als deze optie is ingeschakeld, worden workflows na een fout automatisch opnieuw gestart. Het opnieuw opstarten gebeurt standaard elke 30 seconden als de werkstroom nog steeds een fout vertoont. Als u dit interval wilt aanpassen, maakt u een nieuwe optie `XtkWorkflow_WatchdogRestartTimerTimeout` en stelt u een gegevenstype Geheel getal in om de nieuwe vertraging op te geven. Deze optie moet alleen worden ingeschakeld in technische workflows. [Meer informatie](../../automation/workflow/workflow-properties.md#execution)

### Beveiligingsverbeteringen {#security-8-6-4}

De verbinding met Adobe-oplossingen en -toepassingen via het **[!UICONTROL Adobe Experience Cloud]** externe account is bijgewerkt om de beveiliging te verbeteren.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Compatibiliteitsupdates {#comp-8-6-4}

De volgende FDA-connectors zijn toegevoegd. Verwijs naar deze [ pagina ](compatibility-matrix.md#FederatedDataAccessFDA).

* Databases worden nu ondersteund als externe database met FDA (Adobe Campaign Federated Data Access).

* Er is nu een nieuwe Amazon Redshift FDA ODBC-connector beschikbaar. Het biedt verbeterde connectiviteit, gemakkelijker onderhoud en verbeterde compatibiliteit. Deze nieuwe versie brengt de volgende verbeteringen aan:

   * De nieuwe schakelaar is gebaseerd op de interface ODBC die zich op onze meest recente schakelaars FDA richt. Dit zorgt voor langdurige ondersteuning.
   * Het introduceert ook een nieuw mechanisme voor het laden van gegevens gebruikend s3 emmers, beduidend verbeterend prestaties.

  De oudere schakelaar kan nog worden gebruikt. Neem contact op met uw Adobe-vertegenwoordiger als u de nieuwe versie wilt uitproberen.

### Oplossingen {#fixes-8-6-4}

De volgende problemen zijn opgelost in deze release:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-769 77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-80314 1127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, O-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-826 NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

