---
title: Aan de slag met de implementatie van Campagne-FFDA
description: Aan de slag met de implementatie van Campagne-FFDA
feature: Architecture, FFDA, Deployment
role: Admin, Developer
level: Beginner
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
source-git-commit: 3235701e0939466d4275b1e9202f82694ccdb352
workflow-type: tm+mt
source-wordcount: '1053'
ht-degree: 1%

---

# [!DNL Campaign] Implementatie van FFDA {#gs-ac-ffda}

Door [[!DNL Snowflake] &#x200B;](https://www.snowflake.com/){target="_blank"}, een technologie van het wolkengegevensbestand, de plaatsing van de Volledige Federale Toegang van de Onderneming van Adobe Campaign (FFDA) dramatisch verbetert zijn schaal en snelheid, met de capaciteit om een beduidend aantal klantenprofielen, evenals veel hogere leveringspercentages en transacties per uur te beheren.

## Voordelen {#ffda-benefits}

Campaign v8 Enterprise (FFDA) biedt end-to-end schaalmogelijkheden in elke stap van het proces, van het activeren tot de uiteindelijke rapportage:

* Schaal het gegevensvolume dat u kunt verwerken (tot 8 TB)
* Schaal de prestaties van vragen voor segmentatie en het richten maar ook gegevensopname en uitgang
* De voorbereiding van de levering schalen (van uren tot minuten)

Dit is een fundamentele verandering in de softwarearchitectuur. Gegevens zijn nu extern en de campagne bevat alle gegevens, inclusief profielen. [!DNL Campaign] -processen worden nu van begin tot eind geschaald, van &#39;targeting&#39; tot uitvoering van berichten: gegevensinvoer, segmentatie, &#39;targeting&#39;, query&#39;s en leveringen worden nu doorgaans in minuten uitgevoerd. Deze nieuwe versie lost de hele uitdaging van het schrapen op terwijl het handhaven van het zelfde niveau van flexibiliteit &amp; rekbaarheid. Het aantal profielen is bijna onbeperkt en het bewaren van gegevens kan worden uitgebreid.

De opslag van de wolk wordt uitgevoerd in **[!DNL Snowflake]**: een nieuwe ingebouwde **externe rekening** verzekert connectiviteit met het Gegevensbestand van de Wolk. Het wordt gevormd door Adobe en moet niet worden gewijzigd. [Meer informatie](../config/external-accounts.md)

Om het even welk ingebouwd schema/lijst die moet worden bewogen of in het Gegevensbestand van de Wolk worden herhaald komt met een ingebouwde schemauitbreiding onder **xxl** namespace. Die extensies bevatten alle wijzigingen die nodig zijn om ingebouwde schema&#39;s van de lokale database van [!DNL Campaign] naar de database van [!DNL Snowflake] Cloud te verplaatsen en hun structuur aan te passen aan de nieuwe UUID, bijgewerkte koppelingen, enz.

>[!CAUTION]
>
> Klantgegevens worden niet opgeslagen in de lokale [!DNL Campaign] -database. Daarom moet elke aangepaste tabel worden gemaakt in de Cloud-database.
>

## Campagne Enterprise (FFDA)-architectuur{#ffda-archi}

In een [&#x200B; plaatsing van de Onderneming (FFDA) &#x200B;](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 werkt met twee gegevensbestanden: een lokaal [!DNL Campaign] gegevensbestand voor het gebruikersinterface overseinen in real time en unitaire vragen en schrijven door APIs, en een gegevensbestand van de Wolk [!DNL Snowflake] voor campagneuitvoering, partijvragen en werkschemauitvoering.

De Onderneming van de campagne v8 brengt het concept **Volledige Federatieve Toegang van Gegevens** (FFDA): alle gegevens zijn nu ver op het Gegevensbestand van de Wolk.

Er zijn specifieke API&#39;s beschikbaar voor het beheer van gegevens tussen de lokale en de clouddatabase. Leer hoe deze nieuwe APIs werkt en hoe te om hen in [&#x200B; te gebruiken deze pagina &#x200B;](new-apis.md).

De algemene communicatie tussen servers en processen wordt uitgevoerd volgens het volgende schema:

![](assets/architecture.png)

* De uitvoerings en stuitbeheersmodules zijn onbruikbaar gemaakt op de instantie.
* De toepassing wordt gevormd om berichtuitvoering op een verre &quot;midsourced&quot;server uit te voeren die gebruikend de vraag van SOAP (over HTTP of HTTPS) wordt gedreven.

De database [!DNL Snowflake] aan de marketingzijde wordt gebruikt voor:

* Sla alle klantgegevens op: profielen, aangepaste gegevens zoals transacties, producten, locaties, enz.
* Sla alle gebeurtenissen en gedragsgegevens op die door Campagne worden gegenereerd of verzameld, zoals leveringslogboeken, trackinglogboeken, push-registraties, enzovoort.
* Sla alle gegevensaggregaten van het bovenstaande op.
* Sla een kopie (h+1) op van referentietabellen (zoals leveringen, opsommingen, landen, enz.) die worden gebruikt in workflows, campagnes en rapporten.
* Alle batchprocessen en werkbelastingen uitvoeren


De PostSQL-database van de marketinginstantie wordt gebruikt om:

* Bepaalde werklasten uitvoeren, zoals API&#39;s met een laag volume.
* Sla alle Campagnegegevens op, inclusief levering- en campagnemontages, workflow- en servicedefinities.
* Sla alle ingebouwde referentietabellen (opsommingen, landen, enz.) op die worden gerepliceerd naar [!DNL Snowflake] .

  U kunt echter niet:
   * Maak aanpassingen voor klantgegevens, maak bijvoorbeeld geen huishoudelijke tabel in PostgreSQL, maar alleen in Snowflake
   * Sla leveringslogboeken, trackinglogboeken enz. op. inzake de FFDA-doeldimensie.
   * groot gegevensvolume opslaan.


De PostgreSQL-database in de mid-sourcing-instantie wordt gebruikt om:

* Batchleveringen en real-time leveringen uitvoeren.
* Verstuur bezorgings- en trackinglogboeken - Merk op dat bezorgings- en trackinglog-id&#39;s UUID&#39;s zijn en geen 32-bits id&#39;s.
* Gegevens over bijhouden verzamelen en opslaan.


## Gevolgen{#ffda-impacts}

### [!DNL Campaign] Mechanisme voor API-staging{#staging-api}

Met de [!DNL Campaign] Cloud-database wordt het opblazen van eenheidaanroepen niet aanbevolen voor wat betreft prestaties (latentie en gelijktijdige uitvoering). Tenzij u een extreem laag volume verzendt, moeten batchbewerkingen worden gebruikt om optimale API-prestaties te garanderen. Om de prestaties te verbeteren, worden API&#39;s voor inname omgeleid naar de lokale database. [&#x200B; Leer meer op het opvoeren mechanisme van API van de Campagne &#x200B;](staging.md)

### Nieuwe API&#39;s{#new-apis}

Er zijn nieuwe API&#39;s beschikbaar voor het beheer van gegevenssynchronisatie tussen de lokale database van [!DNL Campaign] en de Cloud-database. Er is ook een nieuw mechanisme geïntroduceerd om API-aanroepen op lokaal databaseniveau af te handelen om latentie te voorkomen en de algehele prestaties te verbeteren.

[Nieuwe API&#39;s worden in deze pagina beschreven](new-apis.md)


### Gegevensreplicatie{#data-replication}

Een specifieke technische workflow behandelt de replicatie van tabellen die aan beide zijden aanwezig moeten zijn (Campagne maken van lokale database en Cloud-database). Deze workflow wordt elke uur geactiveerd en is afhankelijk van een nieuwe ingebouwde JavaScript-bibliotheek.

>[!NOTE]
>
> Er zijn meerdere replicatiebeleid gemaakt op basis van de grootte van de tabel (XS, XL, enz.).
> &#x200B;> Sommige tabellen worden in real-time gerepliceerd, andere worden per uur gerepliceerd. Sommige tabellen bevatten incrementele updates, andere worden volledig bijgewerkt.
>

[Meer informatie over gegevensreplicatie](replication.md)

### ID-beheer{#id-mgt-ffda}

De voorwerpen van de campagne v8 gebruiken nu a **Universally Unique identiteitskaart (UUID)**, die voor onbeperkte unieke waarden toestaat om gegevens te identificeren.

Deze id is gebaseerd op een tekenreeks en is niet opeenvolgend. De primaire sleutel is geen numerieke waarde in Campagne v8, en u moet **auto** gebruiken en **automatische 3&rbrace; attributen in uw schema&#39;s.**

In Campaign Classic v7 en eerdere versies wordt de uniciteit van een sleutel binnen een schema (dat wil zeggen tabel) verwerkt op het niveau van de database-engine. Meer in het algemeen, omvatten de Klassieke motoren van het Gegevensbestand zoals PostgreSQL, Oracle, of SQL Server een inheems mechanisme om het opnemen van gedupliceerde rijen te verhinderen die op een kolom of een reeks kolommen via primaire sleutels en/of unieke indexen worden gebaseerd. De gedupliceerde identiteitskaart bestaat niet in deze versies wanneer de juiste index en de primaire sleutels op het niveau van het Gegevensbestand worden geplaatst.

Adobe Campaign v8 wordt geleverd met Snowflake als de kerndatabase. Aangezien het dramatisch de schaal van vragen verhoogt, verstrekt de verdeelde architectuur van het gegevensbestand van Snowflake dergelijke mechanismen om dan de eenheid van een sleutel binnen een lijst te beheren te handhaven. Als gevolg hiervan verhindert niets met Adobe Campaign v8 de inname van dubbele sleutels in een tabel. Eindgebruikers zijn nu verantwoordelijk voor de consistentie van Toetsen in de Adobe Campaign-database. [Meer informatie](keys.md)

### Beschikbaarheid van functies {#feature-availability}

Sommige mogelijkheden zijn niet beschikbaar in de context van een plaatsing van de Onderneming (FFDA) van Campagne, zoals:

* Beheer van marketingbronnen
* Coupons
* Webtracking
* Enquêtes


**Verwante onderwerpen**

* [Best practices voor het gegevensmodel](../dev/datamodel-best-practices.md)
