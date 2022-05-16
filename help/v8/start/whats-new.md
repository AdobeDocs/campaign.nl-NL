---
title: Nieuw in Campagne v8
description: Belangrijke mogelijkheden in Campagne v8 ontdekken
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 6%

---

# Nieuwe functies in Adobe Campaign v8? {#ac-gs-what-is-new}

Adobe Campaign v8 biedt aanzienlijke verbeteringen op het gebied van infrastructuur, beveiliging, leverbaarheid en bewaking. Door gebruik te maken van [[!DNL Snowflake]](https://www.snowflake.com/), een clouddatabasetechnologie, verbetert Adobe Campaign de schaal en snelheid aanzienlijk, met de mogelijkheid om een groter aantal klantprofielen te beheren, alsook veel hogere leveringspercentages en transacties per uur.

## Belangrijkste mogelijkheden{#key-capabilities}

De belangrijkste mogelijkheden omvatten:

* **Snelheid en schaal**. Adobe Campaign v8 gebruikt de Cloud Database Manager, waardoor query&#39;s tot 200x sneller kunnen worden uitgevoerd, op multipetabyte schaal, een groter aantal berichten per uur met maximaal 20M/uur of 1M/uur voor transactieberichten, en tot 200M actieve profielen kunnen worden beheerd met de mogelijkheid om 1B te bereiken.

* **Verbindingen met de Adobe Experience Platform**. Adobe Campaign v8 biedt ondersteuning voor gegevensconnectors met Adobe Experience Platform/RT-CDP, Unified Customer Profile en native integratie met Journey Orchestration. Deze investeringen zullen de Adobe Campaign klantenervaring optimaliseren en nieuwe gebruiksgevallen zoals de capaciteit openen om geïndividualiseerde klantenreizen in real time aan campagnes toe te voegen.

* **Beheerde Cloud Services**. Adobe Campaign v8 is beschikbaar als een best-in-class Beheerde Cloud Services, die pro-actief toezicht, het geschikte alarm, en de dienstbestuur verstrekt. De waarde voor de teller is een flexibeler en scalable dwars-kanaal campagnebeheer.

>[!CAUTION]
>
>Momenteel is Campagne v8 **alleen** beschikbaar als Beheerde Cloud Service, en kan niet op een ongebouw of hybride milieu&#39;s worden opgesteld.
>
>Migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.
>
>Als u niet zeker bent van uw implementatiemodel of een vraag hebt, neemt u contact op met uw accountteam.

![](assets/home-page.png)

## Schalen{#scale}

Campagne v8 biedt end-to-end schaal bij elke stap van het proces, van het richten tot de definitieve rapportering:

* Schaal het gegevensvolume dat u kunt verwerken (tot 8 TB)
* Schaal de prestaties van vragen voor segmentatie en het richten maar ook gegevensopname en uitgang
* De voorbereiding van de levering schalen (van uren tot minuten)

## Self-service admin interface{#self-service-admin}

Als productbeheerder kunt u instellingen beheren en het gebruik van elk van uw Campagne v8-instanties bijhouden met **Campagne**.

Via een intuïtieve gebruikersinterface kunnen beheerders het gebruik van belangrijke elementen controleren, geavanceerde taken uitvoeren, zoals IP-adressen, maken vermelding, SFTP-opslagcontrole, sleutelbeheer en meer mogelijk. Deze zelfbedieningsinterface biedt u meer flexibiliteit en helpt u:

* Breng snel zelf wijzigingen aan in de instellingen zonder dat u hiervoor Adobe Support nodig hebt
* Configureer instellingen op basis van uw verschillende bedrijfsbehoeften op verschillende momenten
* Verbeter de beveiliging door toegangsinstellingen op basis van behoefte te controleren

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Meer informatie over het configuratiescherm voor campagnes](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html){target=&quot;_blank&quot;}



## Vereenvoudiging en prestatieverbetering{#simplification-and-perf-increase}

Campagne v8 brengt het concept **Volledige Federale Toegang van Gegevens** (FFDA): alle gegevens bevinden zich nu op afstand in de cloud-database.

Met deze nieuwe architectuur vereenvoudigt Campagne v8 gegevensbeheer: er is geen index vereist voor de Cloud Database. U hoeft alleen de tabellen te maken, de gegevens te kopiëren en te starten.

[!DNL Snowflake] Is de Campagne Cloud Database, het zal u snelheid en duurzaamheid brengen: geen overbelasting van de pieken van de systeemactiviteit.

De Cloud-databasetechnologie vereist geen specifiek onderhoud om het prestatieniveau te garanderen.

## Geïntegreerd ecosysteem

U kunt Campagne met een reeks krachtige oplossingen van Adobe integreren, zoals: Adobe Analytics, Adobe Journey Orchestration, Real-Time CDP en nog veel meer.

U kunt ook voorspellende optimalisatie van de verzendtijd en voorspellende betrokkenheidsscoring configureren met Journey AI en de openingssnelheden verhogen, klikken en inkomsten verhogen.

![](../assets/do-not-localize/glass.png) [Meer informatie over de integratie van campagnes](../connect/integration.md)

