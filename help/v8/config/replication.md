---
title: Technische workflows en gegevensreplicatie
description: Technische workflows en gegevensreplicatie
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: eb8ad88ffd9dbaaf1f9ace2e88ba4486711bc72d
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 2%

---

# Technische workflows en gegevensreplicatie

## Technische workflows{#tech-wf}

Adobe Campaign wordt geleverd met een reeks ingebouwde technische workflows. Technische workflows voeren processen of taken uit, die regelmatig op de server worden gepland.

Deze werkschema&#39;s voeren onderhoudsverrichtingen op het gegevensbestand uit, hefboomwerking de volgende informatie in de leveringslogboeken, creeer terugkomende campagnes, en meer.

![](../assets/do-not-localize/book.png) De volledige lijst van technische werkstromen wordt in detail beschreven in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target=&quot;_blank&quot;}


Naast deze technische workflows is Campagne v8 gebaseerd op specifieke technische workflows voor het beheer van [gegevensreplicatie](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Deze workflow voert automatische replicatie uit van ingebouwde tabellen die aanwezig moeten zijn in de lokale database (Postgres) en de Cloud-database ([!DNL Snowflake]). Het is gepland om elk uur uit te voeren, dagelijks. Indien **lastModified** het gebied bestaat, gebeurt de replicatie incrementeel, anders wordt de volledige lijst herhaald. De volgorde van de tabellen in de onderstaande array is de volgorde die wordt gebruikt door de replicatieworkflow.
* **[!UICONTROL Replicate Staging data]**
Deze werkstroom dupliceert het opvoeren van gegevens voor unitaire vraag. Het is gepland om elk uur uit te voeren, dagelijks.
* **[!UICONTROL Deploy FFDA immediately]**\
   Deze workflow voert een directe implementatie uit naar de Cloud-database.
* **[!UICONTROL Replicate FFDA data immediately]**
Deze workflow dupliceert de XS-gegevens voor een bepaalde externe account.

Deze technische workflows zijn beschikbaar via de **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** knooppunt van Campagneverkenner. **Ze mogen niet worden gewijzigd.**

Indien nodig kunt u de gegevenssynchronisatie handmatig starten. Klik met de rechtermuisknop op de knop **Planner** activiteit en selecteer **Taak/taken in behandeling nu uitvoeren**.

## Datareplicatie{#data-replication}

Sommige ingebouwde tabellen worden gerepliceerd van de lokale database van Campagne naar [!DNL Snowflake] Cloud-database via speciale workflows die hierboven zijn beschreven.

Begrijp welke gegevensbestanden Adobe Campaign v8 gebruikt, waarom gegevens worden herhaald, welke gegevens worden herhaald en hoe het replicatieproces werkt.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Beleid voor gegevensreplicatie

Het replicatiebeleid is gebaseerd op de grootte van de tabellen. Sommige tabellen worden in real-time gerepliceerd, andere worden per uur gerepliceerd. Sommige tabellen bevatten incrementele updates wanneer andere worden vervangen.

Naast de ingebouwde **Referentietabellen dupliceren** technische werkstroom, kunt u gegevensreplicatie in uw werkschema&#39;s dwingen.

U kunt:

* specifieke **Javascript-code** activiteit met de volgende code:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* specifieke **nlmodule** activiteit met het volgende bevel:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)



**Verwante onderwerpen**

![](../assets/do-not-localize/book.png) Leer hoe u aan de slag kunt met workflows in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) Toegang tot bewaarperioden van gegevens in [deze sectie](../dev/datamodel-best-practices.md#data-retention)
