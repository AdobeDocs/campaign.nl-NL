---
title: Overgang van Campaign Classic v7 naar Campaign v8
description: Lees meer over de verschillen tussen Campaign Classic v7 en Campaign v8.
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 4%

---

# Overgang van [!DNL Campaign Classic] v7 naar [!DNL Campaign] v8{#gs-matrix}

Als voormalig [!DNL Campaign Classic] v7-gebruiker mag u geen grote verstoring verwachten in de manier waarop u gewoonlijk met [!DNL Adobe Campaign] werkt. De meeste wijzigingen in v8 zijn niet zichtbaar, behalve kleine wijzigingen die in de gebruikersinterface en configuratiestappen worden doorgevoerd.

>[!AVAILABILITY]
>
>* Voor nu, is de Campagne v8 **slechts** beschikbaar als Beheerde Cloud Service, en kan niet op een op-gebouw of hybride milieu&#39;s worden opgesteld. [Meer informatie](#cloud-services)
>
>* Geautomatiseerde migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.


## Beheerde Cloud Services{#cloud-services}

Adobe Campaign v8 is beschikbaar als a **Beheerde Cloud Service**.

Adobe Campaign Managed Cloud Services biedt een Managed Cloud Services-platform voor het ontwerpen van ervaringen met klanten over meerdere kanalen en biedt een omgeving voor visuele campagneorchestratie, realtime interactiebeheer en uitvoering via meerdere kanalen. Leer meer over de Campagne Beheerde Diensten van de Wolk in de [ pagina van de productbeschrijving ](https://helpx.adobe.com/nl/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Het nieuwe aanbod combineert services van topklasse met proactief toezicht en tijdige waarschuwingen, waarbij de nadruk ligt op drie gebieden:

* **de behendigheid van de Wolk** — automatisering door Adobe, die geoptimaliseerde, gestandaardiseerde wolkenplaatsingen voor meer voorspelbare prestaties, grotere behendigheid, en betere zelfbediening productiviteit kenmerkt.
* **Ervaring van de Dienst** — pro-actieve beschikbaarheid, capaciteit, en prestaties controle en reactie om verstoringen te verhinderen, incidenten sneller op te lossen, en de overzichtsdienst regelmatig voor ononderbroken verbetering.
* **Diepe deskundigheid van de Campagne** — de high-affiniteitsdienst van de deskundige teams van de Techniek van de Klant om functionele, technische, of leveringsbehoeften te ontmoeten, plaatsingsrisico te verminderen, en veranderingsbeheer te verbeteren.

Als vroegere [!DNL Campaign Classic] gebruiker, merk op dat de meeste [!DNL Campaign Classic] v7 eigenschappen met [!DNL Campaign] v8, behalve een kleine reeks van hen beschikbaar zijn, die in [ worden vermeld deze sectie ](#gs-removed).

>Met de nieuwe cloudarchitectuur kan Campagne processen stroomlijnen, kosten verlagen, risico&#39;s beheren en de gegevensbeveiliging verbeteren. Uw Campagne v8-omgeving wordt geleverd met een speciale Virtual Private Cloud (VPC) die vooraf voor u is geconfigureerd.


## Hybride architectuur {#hybrid-archi}

De campagne v8 baseert zich op a **hybride architectuur**. Als u een overgang maakt vanuit Campaign Classic v7, moet u er rekening mee houden dat alle leveringen door de server voor midsourcing worden uitgevoerd.

Bijgevolg:

* Het interne verpletteren is **niet mogelijk** in Campagne v8, en de externe rekening is dienovereenkomstig onbruikbaar gemaakt,
* De status van de leveringen wordt niet onmiddellijk bijgewerkt - Een technisch proces wordt uitgevoerd op de marketinginstantie die de leveringsstatus tijdig zal bijwerken.


Leer meer over het verzenden van transactieberichtproeven wanneer het overgaan van v7 op [ deze pagina ](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] en [!DNL Snowflake] {#ac-gs-snowflake}

In zijn [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 werkt met twee gegevensbestanden: een lokaal [!DNL Campaign] gegevensbestand voor het gebruikersinterface overseinen in real time en unitaire vragen en schrijven door APIs, en een wolk [!DNL Snowflake] gegevensbestand voor campagneuitvoering, partijvragen en werkschemauitvoering.

De Onderneming van de campagne v8 brengt het concept **Volledige Federatieve Toegang van Gegevens** (FFDA): alle gegevens zijn nu ver op het Gegevensbestand van de Wolk. Met deze nieuwe architectuur vereenvoudigt de implementatie van Campaign v8 Enterprise (FFDA) het gegevensbeheer: er is geen index vereist voor de Cloud Database. U hoeft alleen de tabellen te maken, de gegevens te kopiëren en te starten. De Cloud-databasetechnologie vereist geen specifiek onderhoud om het prestatieniveau te garanderen.

Leer meer over [!DNL Campaign] v8 architectuur in [ deze pagina ](../architecture/architecture.md).


## Adobe ID gebruiken om verbinding te maken met campagne{#adobe-id}

Campagnegebruikers maken alleen verbinding via hun Adobe ID. Dezelfde Adobe ID wordt gebruikt om al uw Adobe-plannen en -producten voor één account te bewaren, voor alle Adobe Experience Cloud-oplossingen.

Leer hoe te met [!DNL Campaign] in [ te verbinden deze pagina ](connect.md).

## Gegevens met kubussen analyseren{#adobe-reporting}

Met de module Marketing Analytics kunt u gegevens analyseren en meten, statistieken berekenen, het maken en berekenen van rapporten vereenvoudigen en optimaliseren. Daarnaast kunt u rapporten maken en doelpopulaties samenstellen: als deze eenmaal zijn geïdentificeerd, worden ze opgeslagen in lijsten die kunnen worden gebruikt in Adobe Campaign (gericht, segmentatie, enz.).

Met Adobe Campaign v8 zijn kubusrapporten geoptimaliseerd en bieden ze meer schaalmogelijkheden dan Campaign Classic v7. In dat specifieke implementatiemodel zijn eerdere beperkingen op kubussen niet van toepassing in Campaign v8. Leer meer over kubussen in [ deze sectie ](../../v8/reporting/gs-cubes.md).

## Niet-beschikbare functies{#gs-unavailable-features}

Gelieve te merken op dat sommige mogelijkheden niet beschikbaar in de context van een [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md) van Campagne, zoals zijn:

* Beheer van marketingbronnen
* Coupons
* Webtracking
* Enquêtes

## Niet-ondersteunde functies{#gs-removed}

Sommige historische Campaign Classic v7-mogelijkheden worden niet meer ondersteund met Campagne v8, zoals:

* Social marketing met Facebook
* ACS Connector (Prime-aanbieding)
* Integratie met LDAP
* Gebruiker/wachtwoord aanmelden
* Hybride/on-premise plaatsingsmodellen


>[!NOTE]
>
>Sommige niet-beschikbare of niet-ondersteunde functies zijn mogelijk nog wel zichtbaar in de gebruikersinterface.
