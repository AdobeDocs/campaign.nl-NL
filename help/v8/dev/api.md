---
title: Aan de slag met campagne-API's
description: Aan de slag met campagne-API's
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 115b7b6824f3736e03f9fb87898f1264f9bab636
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 9%

---

# Aan de slag met [!DNL Campaign] API&#39;s {#gs-ac-api}

[!DNL Adobe Campaign] wordt geleverd met een set JavaScript-functies die u kunt gebruiken:

* in Scripts - in [!DNL Adobe Campaign] workflows
* via API&#39;s - van externe systemen

>[!NOTE]
>
>Afhankelijk van uw implementatiemodel kunt u ook REST API&#39;s gebruiken met Campagne v8. [Meer informatie](../dev/api/get-started-apis.md).

U kunt [ Campagne JavaScript APIs ](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"} gebruiken om in het wolkengegevensbestand van de Campagne te schrijven of van het gegevensbestand te lezen:

* Bedrijfsspecifieke API&#39;s waarmee u op elk object kunt reageren: leveringen, workflows, abonnementen enzovoort. Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* Algemene API&#39;s voor gegevenstoegang voor het opvragen van gegevens van het gegevensmodel. Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

Merk op dat in zijn [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), de Campagne met twee gegevensbestanden werkt: een lokaal gegevensbestand voor het gebruikersinterface overseinen en unitaire vragen in real time en schrijven door APIs, en een gegevensbestand van de Wolk voor campagneuitvoering, rapportering, gegevensopname, partijvragen en werkschemauitvoering.

>[!CAUTION]
>
>* Vanaf Campagne v8.5.1 is het verificatieproces veranderd in Campaign v8. Technische operatoren moeten het Adobe Identity Management System (IMS) gebruiken om verbinding te maken met Campagne. Ontdek in [deze technische opmerking](../../technotes/upgrades/ims-migration.md) hoe u uw bestaande technische account(s) kunt migreren.
>
>* [!DNL Adobe Campaign] v8 wordt geleverd met een maximale doorvoer (TPS) van onze API-laag. Als u de limiet overschrijdt, treedt een standaard HTTP-fout op (429). Als gebruiker van Managed Cloud Services kunt u contact opnemen met Adobe om de snelheid van elke API aan te passen.
> 

## Vereisten {#ac-api-prerequisites}

Voordat u API&#39;s van [!DNL Adobe Campaign] gebruikt, moet u vertrouwd zijn met de volgende onderwerpen:

* JavaScript
* SOAP-protocol
* [!DNL Adobe Campaign] gegevensmodel

Als u API&#39;s wilt gebruiken en met [!DNL Adobe Campaign] wilt communiceren, moet u ook bekend zijn met uw gegevensmodel.

>[!NOTE]
>U kunt een volledige beschrijving van uw gegevensmodel genereren. Meer informatie vindt u [op deze pagina](datamodel.md).


**Verwante onderwerpen**

* [Best practices voor het gegevensmodel](datamodel-best-practices.md)
* [ de documentatie van JSAPI van de Campagne ](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
