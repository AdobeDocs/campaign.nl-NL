---
solution: Campaign v8
product: Adobe Campaign
title: Campaign Classic v7 - Capaciteitsmatrix voor campagne v8
description: De verschillen tussen Campaign Classic v7 en Campagne v8 begrijpen
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 93004d69f33fce39f8f2abb18eec2562177a7adf
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 2%

---

# [!DNL Campaign Classic] v7 -  [!DNL Campaign] v8 - mogelijkheden{#gs-matrix}

Als bestaande [!DNL Campaign Classic] v7 gebruiker, zou u geen grote verstoring op de manier moeten verwachten u gewoonlijk met [!DNL Adobe Campaign] in wisselwerking staat. De meeste wijzigingen in v8 zijn niet zichtbaar, behalve kleine wijzigingen die in de gebruikersinterface en configuratiestappen worden doorgevoerd.

Belangrijkste wijzigingen:

* Maak segmenten tot 200x sneller
* Snellere levering
* Real-time rapportage met kubussen

Als [!DNL Campaign Classic] gebruiker, merk op dat de meeste [!DNL Campaign Classic] v7 eigenschappen beschikbaar met [!DNL Campaign] v8, behalve een kleine reeks van hen, die in [deze sectie](#gs-removed) worden vermeld. Andere zullen in toekomstige versies worden vrijgegeven. [Meer informatie in deze sectie](#gs-unavailable-features)

[!DNL :bulb:] Meer informatie over  [!DNL Campaign] v8-architectuur vindt u op  [deze pagina](../dev/architecture.md).

## Wijzigingen in productconfiguratie

### [!DNL Campaign] en  [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 werkt met twee databases: een lokale database voor de gebruikersinterface voor realtime berichten en eenheidquery&#39;s en schrijven via API&#39;s, en een Cloud-database voor het uitvoeren van campagnes, batchquery&#39;s en workflowuitvoering.

Dit is een fundamentele verandering in de softwarearchitectuur. Gegevens zijn nu extern en de campagne bevat alle gegevens, inclusief profielen. [!DNL Campaign] processen worden nu van begin tot eind geschaald, van het richten tot berichtuitvoering: gegevensinvoer, segmentatie, doelgerichtheid, query&#39;s, leveringen worden nu doorgaans in minuten uitgevoerd. Deze nieuwe versie lost de hele uitdaging van het schrapen op terwijl het handhaven van het zelfde niveau van flexibiliteit &amp; rekbaarheid. Het aantal profielen is bijna onbeperkt en het bewaren van gegevens kan worden uitgebreid.

Cloudopslag wordt uitgevoerd in **[!DNL Snowflake]**: een nieuwe ingebouwde **externe account** zorgt voor connectiviteit met de Cloud Database. Het wordt gevormd door Adobe en moet niet worden gewijzigd. [Meer informatie](../config/external-accounts.md).

Om het even welke ingebouwde schema/lijst die in het Gegevensbestand van de Wolk moet worden bewogen of worden herhaald komt met een ingebouwde schemauitbreiding onder **xxl** namespace. Die extensies bevatten alle wijzigingen die nodig zijn om ingebouwde schema&#39;s van de [!DNL Campaign] lokale database naar de [!DNL Snowflake] Cloud-database te verplaatsen en hun structuur dienovereenkomstig aan te passen: nieuwe UUID, bijgewerkte koppelingen enz.

>[!CAUTION]
>
> Klantgegevens worden niet opgeslagen in de lokale [!DNL Campaign]-database. Daarom moet elke aangepaste tabel worden gemaakt in de Cloud-database.


Er zijn specifieke API&#39;s beschikbaar voor het beheer van gegevens tussen de lokale en de clouddatabase. Leer hoe deze nieuwe APIs werken en hoe te om hen in [deze pagina ](../dev/new-apis.md) te gebruiken.

### Gegevensreplicatie

Een specifieke technische workflow behandelt de replicatie van tabellen die aan beide zijden aanwezig moeten zijn (Campagne maken van lokale database en Cloud-database). Deze workflow wordt elke uur geactiveerd en is afhankelijk van een nieuwe ingebouwde JavaScript-bibliotheek.

>[!NOTE]
>
> Er zijn meerdere replicatiebeleid gemaakt op basis van de grootte van de tabel (XS, XL, enz.).
> Sommige tabellen worden in real-time gerepliceerd, andere worden per uur gerepliceerd. Sommige tabellen bevatten incrementele updates, andere worden volledig bijgewerkt.


[Meer informatie over gegevensreplicatie](../config/replication.md)

### ID-beheer

Campagne v8-objecten gebruiken nu een **UUID (Universally Unique ID)**, waardoor onbeperkte unieke waarden zijn toegestaan om gegevens te identificeren

Deze id is gebaseerd op een tekenreeks en is niet opeenvolgend.

### Vereenvoudigd onderhoud

Campagnegebruikers hoeven geen databasedeskundigen te zijn: er is niet langer behoefte aan complexe onderhoudsbewerkingen van databases of complexe indexering van tabellen.

## Niet-beschikbare functies{#gs-unavailable-features}

Houd er rekening mee dat bepaalde mogelijkheden niet beschikbaar zijn in deze eerste versie, zoals:

* Marketing Resource Management
* Gedistribueerde marketing
* Binnenkomend Beheer van het Voorstel (de module van de Interactie)
* Campagnes optimaliseren
* Responsbeheer
* Hybride/on-premise plaatsingsmodellen

>[!CAUTION]
>
>Momenteel is Campagne v8 alleen **beschikbaar als beheerde Cloud Service en kan deze niet worden geïmplementeerd op een locatie of in een hybride omgeving.**
>
>Migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.
>
>Als u niet zeker bent van uw implementatiemodel of een vraag hebt, neemt u contact op met uw accountteam.

## Verwijderde functies{#gs-removed}

Om zich aan te passen aan het nieuwe architectuur en implementatiemodel van Campagne v8, zijn sommige historische Campaign Classic v7 mogelijkheden niet meer beschikbaar in Campaign v8.

* Coupons
* Webtracking
* Enquêtes
* Social marketing
* ACS Connector (primaire aanbieding)

