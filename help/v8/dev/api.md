---
title: Aan de slag met campagne-API's
description: Aan de slag met campagne-API's
feature: API
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 9c7a4f7d4e84fde4b74bf6f8e0432681aa7e42d3
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 2%

---

# Aan de slag met [!DNL Campaign] API&#39;s{#gs-ac-api}

[!DNL Adobe Campaign] wordt geleverd met een set JavaScript-functies die u kunt gebruiken:

* in scripts - in [!DNL Adobe Campaign] workflows
* via API&#39;s - van externe systemen

U kunt JavaScript API&#39;s gebruiken om te schrijven in de Campagnecloud-database of om te lezen vanuit de database:

* Bedrijfsspecifieke API&#39;s waarmee u op elk object kunt reageren: leveringen, workflows, abonnementen enzovoort. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* Algemene API&#39;s voor gegevenstoegang voor het opvragen van gegevens van het gegevensmodel. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

Let op: in het [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md), de Campagne werkt met twee gegevensbestanden: een lokaal gegevensbestand voor het gebruikersinterface overseinen in real time en unitaire vragen en schrijven door APIs, en een gegevensbestand van de Wolk voor campagneuitvoering, rapportering, gegevensopname, partijvragen en werkschemauitvoering.

>[!CAUTION]
>
>* Vanaf Campagne v8.5.1 is het verificatieproces veranderd in Campaign v8. Technische operatoren moeten gebruikmaken van Adobe Identity Management System (IMS) om verbinding te maken met Campagne. Leer hoe u uw bestaande technische account(s) kunt migreren in [dit technote](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8 wordt geleverd met een maximale doorvoer (TPS) van onze API-laag. Als u de limiet overschrijdt, treedt een standaard HTTP-fout op (429). Als gebruiker van Beheerde Cloud Services kunt u contact opnemen met Adobe om de snelheid voor elke API aan te passen.
> 

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
