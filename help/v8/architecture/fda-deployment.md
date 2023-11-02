---
title: Ga aan de slag met de implementatie van FDA-Snowflake voor campagnes
description: Ga aan de slag met de implementatie van FDA-Snowflake voor campagnes
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# [!DNL Campaign] FDA [!DNL Snowflake] implementatie{#gs-fda-snowflake}

In een [!DNL Snowflake] implementatie van FDA (default); [!DNL Adobe Campaign] v8 is verbonden met [!DNL Snowflake] toegang tot gegevens via [Federale gegevenstoegang](../connect/fda.md) mogelijkheden: u kunt externe gegevens en informatie die in uw [!DNL Snowflake] database zonder de structuur van Adobe Campaign-gegevens te wijzigen.

## Voordelen{#fda-benefits}

Dit implementatiemodel biedt de volgende voordelen:

* **Opslag en prestaties**
U kunt uw historische gegevens verplaatsen naar [!DNL Snowflake] en verlaagt vervolgens de afhankelijkheid van Adobe Campaign-id&#39;s. Deze architectuur vermindert ook uw afhankelijkheid van opslag PostgreSQL en prestatiesgrenzen. Omdat minder gegevens worden opgeslagen in de Campagne-database, zijn de prestaties beter en worden de onderhoudstaken sneller uitgevoerd.

* **Uitbreiding van het gegevensmodel en gegevensbeheer**
U kunt in [!DNL Snowflake] en koppelen ze aan Adobe Campaign, bijvoorbeeld om gearchiveerde gegevens te gebruiken gedurende bewaarperioden, of om segmentatieprocessen uit te voeren met uitstekende prestaties.

  Met deze architectuur kunt u ook workflowmogelijkheden voor gegevensbeheer gebruiken in [!DNL Snowflake]. Alleen aggregaten en tijdelijke tabellen worden verplaatst naar Campagne voor personalisatie- en leveringsdoeleinden.


## Architectuur{#fda-archi}

Met dit implementatiemodel kunnen Adobe Campaign-gebruikers hun gegevens uitbreiden naar [!DNL Snowflake] en profiteer van de voordelen van één geïntegreerd gegevensplatform voor krachtige informatie over marketingcampagnegegevens in real-time. Het voorziet gebruikers van de capaciteit om diepe waarde van hun gegevens te ontgrendelen door één enkel, verenigd, en makkelijk te gebruiken platform voor gegevensanalyse aan te bieden. Het platform voor cloudgegevens vereist geen beheer omdat het oneindig geschaald kan worden uitgebreid om elk volume aan marketinggegevens van Adobe Campaign te ondersteunen.

De algemene communicatie tussen servers en processen wordt uitgevoerd volgens het volgende schema:

![](assets/fda-architecture.png)

PostgreSQL is het primaire gegevensbestand, en de Snowflake is het secundaire gegevensbestand. U kunt uw gegevensmodel uitbreiden en uw gegevens op Snowflake opslaan. Vervolgens kunt u ETL, segmentatie en rapporten uitvoeren voor een grote gegevensset met uitstekende prestaties.
