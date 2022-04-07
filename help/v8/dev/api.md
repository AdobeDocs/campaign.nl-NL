---
title: Aan de slag met campagne-API's
description: Aan de slag met campagne-API's
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 94fc2739c538f3aa8b11e0ea69d08f1bfffb5d32
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 3%

---

# Aan de slag met [!DNL Campaign] API&#39;s{#gs-ac-api}

[!DNL Adobe Campaign] wordt geleverd met een set JavaScript-functies die u kunt gebruiken:

* in scripts - in [!DNL Adobe Campaign] workflows
* via API&#39;s - van externe systemen

U kunt JavaScript API&#39;s gebruiken om te schrijven in de Campagnecloud-database of om te lezen vanuit de database:

* Bedrijfsspecifieke API&#39;s waarmee u op elk object kunt reageren: leveringen, workflows, abonnementen enzovoort. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* Algemene API&#39;s voor gegevenstoegang voor het opvragen van gegevens van het gegevensmodel. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

Campagne v8 werkt met twee databases: een lokale database voor de gebruikersinterface voor realtime berichten en eenheidquery&#39;s en schrijven via API&#39;s, en een Cloud-database voor het uitvoeren van campagnes, rapportage, gegevensinvoer, batchquery&#39;s en het uitvoeren van workflows.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8 wordt geleverd met een maximale doorvoer (TPS) van onze API-laag. Als u de limiet overschrijdt, treedt een standaard HTTP-fout op (429). Als gebruiker van Beheerde Cloud Services kunt u contact opnemen met Adobe om de snelheid voor elke API aan te passen.

## Vereisten

Voor gebruik [!DNL Adobe Campaign] APIs, moet u met de volgende onderwerpen vertrouwd zijn:

* JavaScript
* SOAP-protocol
* [!DNL Adobe Campaign] datamodel

Voor het gebruik van API&#39;s en interactie met [!DNL Adobe Campaign], moet u ook vertrouwd zijn met uw gegevensmodel.

>[!NOTE]
>U kunt een volledige beschrijving van uw gegevensmodel genereren. Meer informatie in [deze pagina](datamodel.md).

## [!DNL Campaign] API-stagingmechanisme

Met [!DNL Campaign] Cloud-database, unitaire oproepen worden niet aanbevolen vanwege prestaties (latentie en gelijktijdige uitvoering). Batchbewerking heeft altijd de voorkeur. Om optimale prestaties van APIs te waarborgen, blijft de Campagne API vraag op het lokale gegevensbestandniveau behandelen.

![](../assets/do-not-localize/glass.png) [Het mechanisme voor API-staging wordt in deze pagina beschreven](staging.md)

## Nieuwe API&#39;s

Er zijn nieuwe API&#39;s beschikbaar voor het beheer van gegevenssynchronisatie tussen [!DNL Campaign] lokale database en Cloud-database. Er is ook een nieuw mechanisme geïntroduceerd om API-aanroepen op lokaal databaseniveau af te handelen om latentie te voorkomen en de algehele prestaties te verbeteren.

![](../assets/do-not-localize/glass.png) [Nieuwe API&#39;s worden in deze pagina beschreven](new-apis.md)

**Verwante onderwerpen**

* [Best practices voor het gegevensmodel](datamodel-best-practices.md)
