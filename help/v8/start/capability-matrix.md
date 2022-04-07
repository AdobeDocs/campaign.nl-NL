---
title: Campaign Classic v7 - Capaciteitsmatrix voor campagne v8
description: De verschillen tussen Campaign Classic v7 en Campagne v8 begrijpen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 2d0b40e49afdfd71e8bb5c3f0b1d569a715420b2
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8-mogelijkheden{#gs-matrix}

Als bestaand [!DNL Campaign Classic] v7 gebruiker, zou u geen grote verstoring in de manier moeten verwachten u gewoonlijk met [!DNL Adobe Campaign]. De meeste wijzigingen in v8 zijn niet zichtbaar, behalve kleine wijzigingen die in de gebruikersinterface en configuratiestappen worden doorgevoerd.

Belangrijkste wijzigingen:

* Maak segmenten tot 200x sneller
* Snellere levering
* Real-time rapportage met kubussen

Als [!DNL Campaign Classic] gebruiker, merk op dat het grootste deel van [!DNL Campaign Classic] v7-functies zijn beschikbaar via [!DNL Campaign] v8, met uitzondering van een kleine set, die worden vermeld in [deze sectie](#gs-removed). Andere zullen in toekomstige versies worden vrijgegeven. [Meer informatie in deze sectie](#gs-unavailable-features)

![](../assets/do-not-localize/glass.png) Meer informatie over [!DNL Campaign] v8-architectuur in [deze pagina](../dev/architecture.md).

## Wijzigingen in productconfiguratie

### [!DNL Campaign] en [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 werkt met twee databases: een lokale database voor de gebruikersinterface voor realtime berichten en eenheidquery&#39;s en schrijven via API&#39;s, en een Cloud-database voor het uitvoeren van campagnes, batchquery&#39;s en workflowuitvoering.

Dit is een fundamentele verandering in de softwarearchitectuur. Gegevens zijn nu extern en de campagne bevat alle gegevens, inclusief profielen. [!DNL Campaign] processen worden nu van begin tot eind geschaald, van het richten tot berichtuitvoering: gegevensinvoer, segmentatie, doelgerichtheid, query&#39;s, leveringen worden nu doorgaans in minuten uitgevoerd. Deze nieuwe versie lost de hele uitdaging van het schrapen op terwijl het handhaven van het zelfde niveau van flexibiliteit &amp; rekbaarheid. Het aantal profielen is bijna onbeperkt en het bewaren van gegevens kan worden uitgebreid.

Opslag in de cloud wordt uitgevoerd in **[!DNL Snowflake]**: een nieuwe ingebouwde **externe rekening** zorgt voor connectiviteit met de Cloud Database. Het wordt gevormd door Adobe en moet niet worden gewijzigd. [Meer informatie](../config/external-accounts.md)

Een ingebouwd schema/tabel die moet worden verplaatst of gerepliceerd in de cloud-database, wordt geleverd met een ingebouwd schema-extensie onder de **xxl** naamruimte. Deze extensies bevatten alle vereiste wijzigingen om ingebouwde schema&#39;s van de [!DNL Campaign] lokale database naar de [!DNL Snowflake] Cloud-database en hun structuur dienovereenkomstig aanpassen: nieuwe UUID, bijgewerkte koppelingen enz.

>[!CAUTION]
>
> Klantgegevens worden niet opgeslagen in de lokale [!DNL Campaign] database. Daarom moet elke aangepaste tabel worden gemaakt in de Cloud-database.

Er zijn specifieke API&#39;s beschikbaar voor het beheer van gegevens tussen de lokale en de clouddatabase. Leer hoe deze nieuwe API&#39;s werken en hoe u deze kunt gebruiken in [deze pagina](../dev/new-apis.md).

### Datareplicatie

Een specifieke technische workflow behandelt de replicatie van tabellen die aan beide zijden aanwezig moeten zijn (Campagne maken van lokale database en Cloud-database). Deze workflow wordt elke uur geactiveerd en is afhankelijk van een nieuwe ingebouwde JavaScript-bibliotheek.

>[!NOTE]
>
> Er zijn meerdere replicatiebeleid gemaakt op basis van de grootte van de tabel (XS, XL, enz.).
> Sommige tabellen worden in real-time gerepliceerd, andere worden per uur gerepliceerd. Sommige tabellen bevatten incrementele updates, andere worden volledig bijgewerkt.

[Meer informatie over gegevensreplicatie](../config/replication.md)

### ID-beheer

Objecten van versie 8 voor campagnes gebruiken nu een **Universally Unique ID (UUID)**, waardoor onbeperkte unieke waarden gegevens kunnen identificeren.

Deze id is gebaseerd op een tekenreeks en is niet opeenvolgend. De primaire sleutel is geen numerieke waarde in Campagne v8, en u moet gebruiken **autouuid** en **automatische** in uw schema&#39;s.

In Campaign Classic v7 en eerdere versies wordt de uniciteit van een sleutel binnen een schema (dat wil zeggen tabel) op het niveau van de database-engine verwerkt. Meer in het algemeen, omvatten de Klassieke motoren van het Gegevensbestand zoals PostSQL, Oracle, of SQL Server een inheems mechanisme om het opnemen van gedupliceerde rijen te verhinderen die op een kolom of een reeks kolommen via primaire sleutels en/of unieke indexen worden gebaseerd. De gedupliceerde identiteitskaart bestaat niet in deze versies wanneer de juiste index en de primaire sleutels op het niveau van het Gegevensbestand worden geplaatst.

Adobe Campaign v8 wordt geleverd met Snowflake als de kerndatabase. Aangezien het dramatisch de schaal van vragen verhoogt, verstrekt de verdeelde architectuur van het gegevensbestand van Snowflake dergelijke mechanismen om dan de eenheid van een sleutel binnen een lijst te beheren te dwingen. Als gevolg hiervan verhindert niets met Adobe Campaign v8 de inname van dubbele sleutels in een tabel. Eindgebruikers zijn nu verantwoordelijk voor de consistentie van Toetsen in de Adobe Campaign-database. [Meer informatie](../dev/keys.md)

### Vereenvoudigd onderhoud

Campagnegebruikers hoeven geen databasedeskundigen te zijn: er is niet langer behoefte aan complexe onderhoudsbewerkingen van databases of complexe indexering van tabellen.

## Verbinding maken met campagne

Campagnegebruikers maken verbinding via hun Adobe ID. Dezelfde Adobe ID wordt gebruikt om al uw Adobe-plannen en -producten voor één account te bewaren.

![](../assets/do-not-localize/glass.png) Leer hoe u verbinding kunt maken met [!DNL Campaign] in [deze pagina](connect.md).

## Rapportage

Opmerking: Adobe Campaign-rapporten zijn geoptimaliseerd en bieden betere schaalmogelijkheden dan Campaign Classic v7. Beperkingen op kubussen zijn niet van toepassing.

## Workflow {#workflow}

Campagne v8 biedt een extra activiteit voor een doelgerichte workflow: **[!UICONTROL Change data source]**.

De **[!UICONTROL Change data source]** activiteit staat u toe om de gegevensbron van een werkschema te veranderen **[!UICONTROL Working table]** gegevens over verschillende gegevensbronnen te beheren, zoals FDA, FFDA en de lokale gegevensbank.

![](../assets/do-not-localize/glass.png) Meer informatie over de **[!UICONTROL Change data source]** activiteit in [deze pagina](../config/workflows.md#change-data-source-activity).

## Niet-beschikbare functies{#gs-unavailable-features}

Houd er rekening mee dat bepaalde mogelijkheden niet beschikbaar zijn in deze versie van Campagne, zoals:

* Marketing Resource Management
* Gedistribueerde marketing
* Responsbeheer
* Hybride/on-premise plaatsingsmodellen

>[!CAUTION]
>
>* Momenteel is Campagne v8 **alleen** beschikbaar als Beheerde Cloud Service, en kan niet op een ongebouw of hybride milieu&#39;s worden opgesteld.
>
>* Migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.
>
>* Als u niet zeker bent van uw implementatiemodel of een vraag hebt, neemt u contact op met uw accountteam.


## Niet-ondersteunde functies{#gs-removed}

Om zich aan het nieuwe architectuur en plaatsingsmodel van Campagne v8 aan te sluiten, worden sommige historische Campaign Classic v7 mogelijkheden niet meer gesteund met Campagne v8, zoals:

* Coupons
* Webtracking
* Enquêtes
* Sociale marketing met Facebook
* ACS Connector (primaire aanbieding)
* Integratie met LDAP
* Gebruiker/wachtwoord aanmelden

>[!NOTE]
>
>Sommige niet-beschikbare of niet-ondersteunde functies zijn mogelijk nog wel zichtbaar in de gebruikersinterface.
