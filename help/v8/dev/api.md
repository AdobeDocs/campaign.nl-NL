---
title: Aan de slag met campagne-API's
description: Aan de slag met campagne-API's
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 2%

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


**Verwante onderwerpen**

* [Best practices voor het gegevensmodel](datamodel-best-practices.md)
