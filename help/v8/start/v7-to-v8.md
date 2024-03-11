---
title: Overgang van Campaign Classic v7 naar Campagne v8
description: Leer meer over de verschillen tussen Campaign Classic v7 en Campaign v8.
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 55c177b6931ef2c427c8e9793b463274b8abb015
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 4%

---

# Overgang van [!DNL Campaign Classic] v7 naar [!DNL Campaign] v8{#gs-matrix}

Als voormalig [!DNL Campaign Classic] v7 gebruiker, zou u geen grote verstoring in de manier moeten verwachten u gewoonlijk met [!DNL Adobe Campaign]. De meeste wijzigingen in v8 zijn niet zichtbaar, behalve kleine wijzigingen die in de gebruikersinterface en configuratiestappen worden doorgevoerd.

>[!AVAILABILITY]
>
>* Momenteel is Campagne v8 **alleen** beschikbaar als Beheerde Cloud Service, en kan niet op een ongebouw of hybride milieu&#39;s worden opgesteld. [Meer informatie](#cloud-services)
>
>* Geautomatiseerde migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.


## Beheerde Cloud Servicen{#cloud-services}

Adobe Campaign v8 is beschikbaar als een **Beheerde Cloud Service**.

Adobe Campaign Managed Cloud Services biedt een platform voor beheerde Cloud Servicen voor het ontwerpen van klantervaringen over meerdere kanalen en biedt een omgeving voor visuele campagneorchestratie, interactiebeheer in real time en uitvoering over meerdere kanalen. Meer informatie over Cloud Servicen met beheerde campagnes in de [productbeschrijvingspagina](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Het nieuwe aanbod combineert services van topklasse met proactief toezicht en tijdige waarschuwingen, waarbij de nadruk ligt op drie gebieden:

* **Wolkenbehendigheid** — automatisering door Adobe, met geoptimaliseerde, gestandaardiseerde cloudimplementaties voor meer voorspelbare prestaties, grotere flexibiliteit en verbeterde zelfbedieningsproductiviteit.
* **Serviceervaring** — proactieve beschikbaarheid, capaciteit, en prestatiescontrole en reactie om verstoringen te voorkomen, incidenten sneller op te lossen, en de dienst regelmatig voor voortdurende verbetering te herzien.
* **Expertise in diepe campagne** — service met hoge affiniteit van deskundige Customer Engineering-teams om te voldoen aan de behoeften op het gebied van functionaliteit, techniek of leverbaarheid, het implementatierisico te beperken en wijzigingsbeheer te verbeteren.

Als voormalig [!DNL Campaign Classic] gebruiker, merk op dat het grootste deel van [!DNL Campaign Classic] v7-functies zijn beschikbaar via [!DNL Campaign] v8, met uitzondering van een kleine set, die worden vermeld in [deze sectie](#gs-removed).

>Met de nieuwe cloudarchitectuur kan Campagne processen stroomlijnen, kosten verlagen, risico&#39;s beheren en de gegevensbeveiliging verbeteren. Uw Campagne v8-omgeving wordt geleverd met een speciale Virtual Private Cloud (VPC) die vooraf voor u is geconfigureerd.


## Hybride architectuur {#hybrid-archi}

Campagne v8 is gebaseerd op een **hybride architectuur**. Als u van Campaign Classic v7 overgaat, merk op dat alle leveringen door de midsourcingserver gaan.

Bijgevolg:

* Het interne verpletteren is **niet mogelijk** in Campagne v8 en de externe rekening dienovereenkomstig is uitgeschakeld,
* De status van de leveringen wordt niet onmiddellijk bijgewerkt - Een technisch proces wordt uitgevoerd op de marketinginstantie die de leveringsstatus tijdig zal bijwerken.


![](../assets/do-not-localize/glass.png) Meer informatie over het verzenden van proefdrukken van transactieberichten tijdens het overstappen van v7 op [deze pagina](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] en [!DNL Snowflake] {#ac-gs-snowflake}

In haar [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 werkt met twee databases : een lokaal [!DNL Campaign] gegevensbestand voor het gebruikersinterface overseinen in real time en unitary vragen en schrijven door APIs, en een wolk [!DNL Snowflake] database voor de uitvoering van campagnes, batchquery&#39;s en workflowuitvoering.

Campagne v8 Enterprise introduceert het concept **Volledige Federale Toegang van Gegevens** (FFDA): alle gegevens zijn nu extern beschikbaar in de Cloud Database. Met deze nieuwe architectuur vereenvoudigt de implementatie van Campaign v8 Enterprise (FFDA) het gegevensbeheer: er is geen index vereist voor de Cloud Database. U hoeft alleen de tabellen te maken, de gegevens te kopiëren en te starten. De Cloud-databasetechnologie vereist geen specifiek onderhoud om het prestatieniveau te garanderen.

![](../assets/do-not-localize/glass.png) Meer informatie over [!DNL Campaign] v8-architectuur in [deze pagina](../architecture/architecture.md).


## Adobe ID gebruiken om verbinding te maken met campagne{#adobe-id}

Campagnegebruikers maken alleen verbinding via hun Adobe ID. Dezelfde Adobe ID wordt gebruikt om al uw Adobe plannen en producten verbonden aan één enkele rekening, voor alle oplossingen van Adobe Experience Cloud te houden.

![](../assets/do-not-localize/glass.png) Leer hoe u verbinding kunt maken met [!DNL Campaign] in [deze pagina](connect.md).

## Gegevens met kubussen analyseren{#adobe-reporting}

Met de module Marketing Analytics kunt u gegevens analyseren en meten, statistieken berekenen, het maken en berekenen van rapporten vereenvoudigen en optimaliseren. Daarnaast kunt u rapporten maken en doelpopulaties samenstellen: als deze eenmaal zijn geïdentificeerd, worden ze opgeslagen in lijsten die kunnen worden gebruikt in Adobe Campaign (gericht, segmentatie, enz.).

Met Adobe Campaign v8 zijn kubusrapporten geoptimaliseerd en bieden ze meer schaalmogelijkheden dan Campaign Classic v7. In dat specifieke implementatiemodel zijn eerdere beperkingen op kubussen niet van toepassing in Campaign v8. Meer informatie over kubussen in [deze sectie](../../v8/reporting/gs-cubes.md).

## Niet-beschikbare functies{#gs-unavailable-features}

Houd er rekening mee dat bepaalde mogelijkheden niet beschikbaar zijn in de context van een [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md) van campagne, zoals:

* Beheer van marketingbronnen
* Coupons
* Webtracking
* Enquêtes

## Niet-ondersteunde functies{#gs-removed}

Sommige historische Campaign Classic v7-mogelijkheden worden niet meer ondersteund met Campagne v8, zoals:

* Social marketing met Facebook
* ACS Connector (primaire aanbieding)
* Integratie met LDAP
* Gebruiker/wachtwoord aanmelden
* Hybride/on-premise plaatsingsmodellen


>[!NOTE]
>
>Sommige niet-beschikbare of niet-ondersteunde functies zijn mogelijk nog wel zichtbaar in de gebruikersinterface.
