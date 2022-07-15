---
title: Overgang van Campaign Classic v7 naar Campagne v8
description: De verschillen tussen Campaign Classic v7 en Campagne v8 begrijpen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 6f9f3ed4d2eef28b6683bf04b81431fd6a3e3dba
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Overgang van [!DNL Campaign Classic] v7 naar [!DNL Campaign] v8{#gs-matrix}

Als voormalig [!DNL Campaign Classic] v7 gebruiker, zou u geen grote verstoring in de manier moeten verwachten u gewoonlijk met [!DNL Adobe Campaign]. De meeste wijzigingen in v8 zijn niet zichtbaar, behalve kleine wijzigingen die in de gebruikersinterface en configuratiestappen worden doorgevoerd.

>[!AVAILABILITY]
>
>* Momenteel is Campagne v8 **alleen** beschikbaar als Beheerde Cloud Service, en kan niet op een ongebouw of hybride milieu&#39;s worden opgesteld. [Meer informatie](#cloud-services)
>
>* Geautomatiseerde migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.



## Beheerde Cloud Services{#cloud-services}

Adobe Campaign v8 is beschikbaar als een **Beheerde Cloud Service**.

Adobe Campaign Managed Cloud Services biedt een Managed Services-platform voor het ontwerpen van ervaringen met klanten over meerdere kanalen en biedt een omgeving voor visuele campagneorchestratie, realtime interactiebeheer en uitvoering via meerdere kanalen. Meer informatie over Cloud Services van Campagne Managed in de [productbeschrijvingspagina](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

Het nieuwe aanbod combineert services van topklasse met proactief toezicht en tijdige waarschuwingen, waarbij de nadruk ligt op drie gebieden:

* **Wolkenbehendigheid** — automatisering door Adobe, met geoptimaliseerde, gestandaardiseerde cloudimplementaties voor meer voorspelbare prestaties, grotere flexibiliteit en verbeterde zelfbedieningsproductiviteit.
* **Serviceervaring** — proactieve beschikbaarheid, capaciteit, en prestatiescontrole en reactie om verstoringen te voorkomen, incidenten sneller op te lossen, en de dienst regelmatig voor voortdurende verbetering te herzien.
* **Expertise in diepe campagne** — service met hoge affiniteit van deskundige Customer Engineering-teams om te voldoen aan de behoeften op het gebied van functionaliteit, techniek of leverbaarheid, het implementatierisico te beperken en wijzigingsbeheer te verbeteren.

Als voormalig [!DNL Campaign Classic] gebruiker, merk op dat het grootste deel van [!DNL Campaign Classic] v7-functies zijn beschikbaar via [!DNL Campaign] v8, met uitzondering van een kleine set, die worden vermeld in [deze sectie](#gs-removed).

>[!NOTE]
>
> Campagne v8 is gebaseerd op een hybride architectuur. Als u van Campaign Classic v7 overgaat, merk op dat alle leveringen door de midsourcingserver gaan. [Meer informatie](../architecture/architecture.md)
>
> Als gevolg hiervan is interne routering **niet mogelijk** in Campagne v8 en de externe account is dienovereenkomstig uitgeschakeld.


## [!DNL Campaign] en [!DNL Snowflake] {#ac-gs-snowflake}

Campagne v8 werkt met [!DNL Snowflake].

In haar [Implementatie van ondernemingen (FFDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 werkt met twee databases: een lokale [!DNL Campaign] database voor realtime berichten en eenheidquery&#39;s in de gebruikersinterface en schrijven via API&#39;s en een cloud [!DNL Snowflake] database voor de uitvoering van campagnes, batchquery&#39;s en workflowuitvoering.

Campagne v8 Enterprise introduceert het concept **Volledige Federale Toegang van Gegevens** (FFDA): alle gegevens bevinden zich nu op afstand in de cloud-database. Met deze nieuwe architectuur vereenvoudigt de implementatie van Campaign v8 Enterprise (FFDA) het gegevensbeheer: er is geen index vereist voor de Cloud Database. U hoeft alleen de tabellen te maken, de gegevens te kopiëren en te starten. De Cloud-databasetechnologie vereist geen specifiek onderhoud om het prestatieniveau te garanderen.

![](../assets/do-not-localize/glass.png) Meer informatie over [!DNL Campaign] v8-architectuur in [deze pagina](../architecture/architecture.md).


## Adobe ID gebruiken om verbinding te maken met campagne{#adobe-id}

Campagnegebruikers maken alleen verbinding via hun Adobe ID. Dezelfde Adobe ID wordt gebruikt om al uw Adobe-plannen en -producten voor één account te bewaren, voor alle Adobe Experience Cloud-oplossingen.

![](../assets/do-not-localize/glass.png) Leer hoe u verbinding kunt maken met [!DNL Campaign] in [deze pagina](connect.md).

## Gegevens met kubussen analyseren{#adobe-reporting}

Met de module Marketing Analytics kunt u gegevens analyseren en meten, statistieken berekenen, het maken en berekenen van rapporten vereenvoudigen en optimaliseren. Daarnaast kunt u rapporten maken en doelgroepen opbouwen: zodra ze zijn geïdentificeerd, worden ze opgeslagen in lijsten die in Adobe Campaign kunnen worden gebruikt (gericht, segmentatie, enz.).

Adobe Campaign-kubusrapporten zijn geoptimaliseerd en bieden betere schaalmogelijkheden dan Campaign Classic v7. Voormalige beperkingen op kubussen zijn niet van toepassing in Campaign v8.

## Niet-beschikbare functies{#gs-unavailable-features}

Houd er rekening mee dat bepaalde mogelijkheden niet beschikbaar zijn in deze versie van Campagne, zoals:

* Marketing Resource Management
* Hybride/on-premise plaatsingsmodellen


## Niet-ondersteunde functies{#gs-removed}

Om zich aan het nieuwe architectuur en plaatsingsmodel van Campagne v8 aan te sluiten, worden sommige historische Campaign Classic v7 mogelijkheden niet meer gesteund met Campagne v8, zoals:

* Coupons
* Webtracking
* Enquêtes
* Social marketing
* ACS Connector (primaire aanbieding)
* Integratie met LDAP
* Gebruiker/wachtwoord aanmelden

>[!NOTE]
>
>Sommige niet-beschikbare of niet-ondersteunde functies zijn mogelijk nog wel zichtbaar in de gebruikersinterface.
