---
title: Aan de slag met campagne-API's
description: Aan de slag met campagne-API's
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 9%

---

# Aan de slag met [!DNL Campaign] API&#39;s {#gs-ac-api}

[!DNL Adobe Campaign] wordt geleverd met een set JavaScript-functies die u kunt gebruiken:

* in Scripts - in [!DNL Adobe Campaign] workflows
* via API&#39;s - van externe systemen

U kunt JavaScript API&#39;s gebruiken om te schrijven in de Campagnecloud-database of om te lezen van de database:

* Bedrijfsspecifieke API&#39;s waarmee u op elk object kunt reageren: leveringen, workflows, abonnementen enzovoort. Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html) {target="_blank"}.
* Algemene API&#39;s voor gegevenstoegang voor het opvragen van gegevens van het gegevensmodel. Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html) {target="_blank"}.

Merk op dat in zijn [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), de Campagne met twee gegevensbestanden werkt: een lokaal gegevensbestand voor het gebruikersinterface overseinen en unitaire vragen in real time en schrijven door APIs, en een gegevensbestand van de Wolk voor campagneuitvoering, rapportering, gegevensopname, partijvragen en werkschemauitvoering.

>[!CAUTION]
>
>* Als Campagnegebruiker die van Campaign Standard overgaat, kunt u REST APIs met Campagne v8 gebruiken. [Meer informatie](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/get-started-apis){target="_blank"}.
>
>* Vanaf Campagne v8.5.1 is het verificatieproces veranderd in Campaign v8. Technische operatoren moeten gebruikmaken van Adobe Identity Management System (IMS) om verbinding te maken met Campagne. Ontdek in [deze technische opmerking](../../technotes/upgrades/ims-migration.md) hoe u uw bestaande technische account(s) kunt migreren.
>
>* [!DNL Adobe Campaign] v8 wordt geleverd met een maximale doorvoer (TPS) van onze API-laag. Als u de limiet overschrijdt, treedt een standaard HTTP-fout op (429). Als gebruiker van Beheerde Cloud Servicen kunt u contact opnemen met de Adobe om de vertraging voor elke API aan te passen.
> 

## Vereisten {#ac-api-prerequisites}

Voordat u API&#39;s van [!DNL Adobe Campaign] gebruikt, moet u vertrouwd zijn met de volgende onderwerpen:

* JavaScript
* SOAP
* [!DNL Adobe Campaign] gegevensmodel

Als u API&#39;s wilt gebruiken en met [!DNL Adobe Campaign] wilt communiceren, moet u ook bekend zijn met uw gegevensmodel.

>[!NOTE]
>U kunt een volledige beschrijving van uw gegevensmodel genereren. Meer informatie vindt u [op deze pagina](datamodel.md).


**Verwante onderwerpen**

* [Best practices voor het gegevensmodel](datamodel-best-practices.md)
