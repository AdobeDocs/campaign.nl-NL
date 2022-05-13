---
title: Get started with Campaign FFDA deployment
description: Get started with Campaign FFDA deployment
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 13d19f0052880c0b0930e96441163f26038c071a
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 1%

---

# [!DNL Campaign] Implementatie van FFDA{#gs-ac-ffda}

Door gebruik te maken van [[!DNL Snowflake]](https://www.snowflake.com/), een clouddatabasetechnologie, de implementatie van Adobe Campaign Enterprise Full Federated Access (FFDA) verbetert de schaal en snelheid van de implementatie aanzienlijk, met de mogelijkheid om een groter aantal klantprofielen te beheren, alsook veel hogere leveringspercentages en transacties per uur.

## Voordelen {#ffda-benefits}

Campaign v8 Enterprise (FFDA) biedt end-to-end schaalmogelijkheden in elke stap van het proces, van het activeren tot de uiteindelijke rapportage:

* Schaal het gegevensvolume dat u kunt verwerken (tot 8 TB)
* Schaal de prestaties van vragen voor segmentatie en het richten maar ook gegevensopname en uitgang
* Scale the delivery preparation (from hours to minutes)

This is a foundational change in the software architecture. Data is now remote and Campaign federates the whole data, including Profiles. [!DNL Campaign] processen worden nu van begin tot eind geschaald, van het richten tot berichtuitvoering: gegevensinvoer, segmentatie, doelgerichtheid, query&#39;s, leveringen worden nu doorgaans in minuten uitgevoerd. Deze nieuwe versie lost de hele uitdaging van het schrapen op terwijl het handhaven van het zelfde niveau van flexibiliteit &amp; rekbaarheid. Het aantal profielen is bijna onbeperkt en het bewaren van gegevens kan worden uitgebreid.

Opslag in de cloud wordt uitgevoerd in **[!DNL Snowflake]**: een nieuwe ingebouwde **externe rekening** zorgt voor connectiviteit met de Cloud Database. Het wordt gevormd door Adobe en moet niet worden gewijzigd. [Meer informatie](../config/external-accounts.md)

Any built-in schema/table which needs to be moved or replicated in Cloud Database comes with a built-in schema extension under the **xxl** namespace. Deze extensies bevatten alle vereiste wijzigingen om ingebouwde schema&#39;s van de [!DNL Campaign] lokale database naar de [!DNL Snowflake] Cloud-database en hun structuur dienovereenkomstig aanpassen: nieuwe UUID, bijgewerkte koppelingen enz.

>[!CAUTION]
>
> Klantgegevens worden niet opgeslagen in de lokale [!DNL Campaign] database. As a consequence, any custom table needs to be create in the Cloud database.

## Campagne Enterprise (FFDA)-architectuur{#ffda-archi}

In an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 works with two databases: a local [!DNL Campaign] database for the user interface real-time messaging and unitary queries and write through APIs, and a Cloud [!DNL Snowflake] database for campaign execution, batch queries and workflow execution.

Campaign v8 Enterprise brings the concept of **Full Federated Data Access** (FFDA): all data is now remote on the Cloud Database.

Er zijn specifieke API&#39;s beschikbaar voor het beheer van gegevens tussen de lokale en de clouddatabase. Leer hoe deze nieuwe API&#39;s werken en hoe u deze kunt gebruiken in [deze pagina](new-apis.md).

De algemene communicatie tussen servers en processen wordt uitgevoerd volgens het volgende schema:

![](assets/architecture.png)

* De uitvoerings en stuitbeheersmodules zijn onbruikbaar gemaakt op de instantie.
* The application is configured to perform message execution on a remote &quot;mid-sourced&quot; server that is driven using SOAP calls (over HTTP or HTTPS).

De [!DNL Snowflake] de databank aan de kant van de marketing wordt gebruikt om :

* Alle klantgegevens opslaan: profielen, aangepaste gegevens zoals transacties, producten, locaties, enz.
* Sla alle gebeurtenissen en gedragsgegevens op die door Campagne worden gegenereerd of verzameld, zoals leveringslogboeken, trackinglogboeken, push-registraties, enzovoort.
* Sla alle gegevensaggregaten van het bovenstaande op.
* Een kopie (h+1) van referentietabellen opslaan (zoals leveringen, opsommingen, landen, enz.) die worden gebruikt in workflows, campagnes en rapporten.
* Alle batchprocessen en werkbelastingen uitvoeren


The PostgreSQL database on the marketing instance is used to:

* Bepaalde werklasten uitvoeren, zoals API&#39;s met een laag volume.
* Store all Campaign data, including delivery and campaign settings, workflow and service definitions.
* Alle ingebouwde referentietabellen opslaan (opsommingen, landen, enz.) waarnaar wordt gerepliceerd [!DNL Snowflake].

   However, you cannot:
   * Maak aanpassingen voor klantgegevens, maak bijvoorbeeld geen huishoudelijke tabel in PostgreSQL, maar alleen in Snowflake
   * Sla leveringslogboeken, trackinglogboeken enz. op. inzake de FFDA-doeldimensie.
   * groot gegevensvolume opslaan.


De PostgreSQL-database in de mid-sourcing-instantie wordt gebruikt om:

* Batch- en real-time (RT)-leveringen uitvoeren.
* Send delivery and tracking logs - note that delivery and tracking log IDs are UUIDs and not 32-bit IDs.
* Collect and store tracking data.


## Impacts{#ffda-impacts}

### [!DNL Campaign] API-stagingmechanisme{#staging-api}

Met [!DNL Campaign] Cloud-database, unitaire oproepen worden niet aanbevolen vanwege prestaties (latentie en gelijktijdige uitvoering). Batchbewerking heeft altijd de voorkeur. Om optimale prestaties van APIs te waarborgen, blijft de Campagne API vraag op het lokale gegevensbestandniveau behandelen.

![](../assets/do-not-localize/glass.png) [Het mechanisme voor API-staging wordt in deze pagina beschreven](staging.md)

### Nieuwe API&#39;s{#new-apis}

Er zijn nieuwe API&#39;s beschikbaar voor het beheer van gegevenssynchronisatie tussen [!DNL Campaign] lokale database en Cloud-database. Er is ook een nieuw mechanisme geïntroduceerd om API-aanroepen op lokaal databaseniveau af te handelen om latentie te voorkomen en de algehele prestaties te verbeteren.

![](../assets/do-not-localize/glass.png) [Nieuwe API&#39;s worden in deze pagina beschreven](new-apis.md)


### Datareplicatie{#data-replication}

Een specifieke technische workflow behandelt de replicatie van tabellen die aan beide zijden aanwezig moeten zijn (Campagne maken van lokale database en Cloud-database). Deze workflow wordt elke uur geactiveerd en is afhankelijk van een nieuwe ingebouwde JavaScript-bibliotheek.

>[!NOTE]
>
> Multiple replication policies have been created, based on the size of the table (XS, XL, etc.).
> Sommige tabellen worden in real-time gerepliceerd, andere worden per uur gerepliceerd. Sommige tabellen bevatten incrementele updates, andere worden volledig bijgewerkt.

[Meer informatie over gegevensreplicatie](replication.md)

### ID-beheer{#id-mgt-ffda}

Campaign v8 objects now use a **Universally Unique ID (UUID)**, which allows for unlimited unique values to identify data.

Deze id is gebaseerd op een tekenreeks en is niet opeenvolgend. De primaire sleutel is geen numerieke waarde in Campagne v8, en u moet gebruiken **autouuid** en **automatische** in uw schema&#39;s.

In Campaign Classic v7 en eerdere versies wordt de uniciteit van een sleutel binnen een schema (dat wil zeggen tabel) op het niveau van de database-engine verwerkt. Meer in het algemeen, omvatten de Klassieke motoren van het Gegevensbestand zoals PostSQL, Oracle, of SQL Server een inheems mechanisme om het opnemen van gedupliceerde rijen te verhinderen die op een kolom of een reeks kolommen via primaire sleutels en/of unieke indexen worden gebaseerd. De gedupliceerde identiteitskaart bestaat niet in deze versies wanneer de juiste index en de primaire sleutels op het niveau van het Gegevensbestand worden geplaatst.

Adobe Campaign v8 wordt geleverd met Snowflake als de kerndatabase. Aangezien het dramatisch de schaal van vragen verhoogt, verstrekt de verdeelde architectuur van het gegevensbestand van Snowflake dergelijke mechanismen om dan de eenheid van een sleutel binnen een lijst te beheren te dwingen. Als gevolg hiervan verhindert niets met Adobe Campaign v8 de inname van dubbele sleutels in een tabel. End-users are now responsible for ensuring consistency of Keys within the Adobe Campaign database. [Meer informatie](keys.md)

**Verwante onderwerpen**

* [Best practices voor het gegevensmodel](../dev/datamodel-best-practices.md)
