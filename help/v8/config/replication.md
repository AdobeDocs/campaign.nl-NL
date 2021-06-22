---
product: Adobe Campaign
title: Technische workflows en gegevensreplicatie
description: Technische workflows en gegevensreplicatie
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# Technische workflows en gegevensreplicatie

## Technische workflows{#tech-wf}

Adobe Campaign wordt geleverd met een reeks ingebouwde technische workflows. Technische workflows voeren processen of taken uit, die regelmatig op de server worden gepland.

Deze werkschema&#39;s voeren onderhoudsverrichtingen op het gegevensbestand uit, hefboomwerking de volgende informatie in de leveringslogboeken, creeer terugkomende campagnes, en meer.

[!DNL :arrow_upper_right:] De volledige lijst van technische werkschema&#39;s is gedetailleerd in  [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html) {target=&quot;_blank&quot;}


Naast deze technische workflows is Campagne v8 gebaseerd op specifieke technische workflows voor het beheer van [gegevensreplicatie](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
Deze workflow voert automatische replicatie uit van ingebouwde tabellen die aanwezig moeten zijn in de lokale database voor campagnes (Postgres) en de Cloud-database ([!DNL Snowflake]). Het is gepland om elk uur uit te voeren, dagelijks. Als **lastModified** gebied bestaat, gebeurt de replicatie incrementeel, anders wordt de volledige lijst herhaald. De volgorde van de tabellen in de onderstaande array is de volgorde die wordt gebruikt door de replicatieworkflow.
* **[!UICONTROL Replicate Staging data]**
Deze werkstroom dupliceert het opvoeren van gegevens voor unitaire vraag. Het is gepland om elk uur uit te voeren, dagelijks.
* **[!UICONTROL Deploy FFDA immediately]**\
   Deze workflow voert een directe implementatie uit naar de Cloud-database.
* **[!UICONTROL Replicate FFDA data immediately]**
Deze workflow dupliceert de XS-gegevens voor een bepaalde externe account.

Deze technische werkschema&#39;s zijn beschikbaar bij de **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** knoop van de Ontdekkingsreiziger van de Campagne. **Ze mogen niet worden gewijzigd.**

Indien nodig kunt u de gegevenssynchronisatie handmatig starten. Om dit uit te voeren, klik op **Planner** activiteit met de rechtermuisknop aan en selecteer **Voer hangende taak(en) nu uit**.

## Gegevensreplicatie{#data-replication}

Sommige ingebouwde tabellen worden gerepliceerd van de lokale database van Campagne naar de Cloud-database via speciale workflows die hierboven worden beschreven.[!DNL Snowflake]

Het replicatiebeleid is gebaseerd op de grootte van de tabellen. Sommige tabellen worden in real-time gerepliceerd, andere worden per uur gerepliceerd. Sommige tabellen hebben incrementele updates wanneer andere worden vervangen.

Naast de ingebouwde **Replicate Reference Tables** technische workflow kunt u gegevensreplicatie in uw workflows forceren.

U kunt:

* Voeg een specifieke **Javascript code** activiteit met de volgende code toe:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* Voeg een specifieke **nlmodule** activiteit met het volgende bevel toe:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)

**Verwante onderwerpen**

[!DNL :arrow_upper_right:] Leer hoe u aan de slag kunt gaan met workflows in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target=&quot;_blank&quot;}

[!DNL :bulb:] Punten voor gegevensbewaring in  [deze sectie](../dev/datamodel-best-practices.md#data-retention)
