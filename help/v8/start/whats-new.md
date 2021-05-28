---
solution: Campaign v8
product: Adobe Campaign
title: Nieuw in Campagne v8
description: Meer mogelijkheden
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: a48e69a3f34c48ed4828bf29b8a02a3dc07bfa7e
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Nieuwe functies in Adobe Campaign v8? {#ac-gs-what-is-new}

Adobe Campaign v8 biedt aanzienlijke verbeteringen op het gebied van infrastructuur, beveiliging, leverbaarheid en bewaking. Door gebruik te maken van [[!DNL Snowflake]](https://www.snowflake.com/), een clouddatabasetechnologie, verbetert Adobe Campaign aanzienlijk de schaal en snelheid ervan, met de mogelijkheid om een groter aantal klantprofielen te beheren, evenals veel hogere leveringspercentages en transacties per uur.

De belangrijkste mogelijkheden omvatten:

* **Snelheid en schaal**. Adobe Campaign v8 gebruikt de Cloud Database Manager, waardoor query&#39;s tot 200x sneller kunnen worden uitgevoerd, op multipetabyte schaal, een groter aantal berichten per uur met maximaal 20M/uur of 1M/uur voor transactieberichten, en tot 200M actieve profielen kunnen worden beheerd met de mogelijkheid om 1B te bereiken.

* **Verbindingen met de Adobe Experience Platform**. Adobe Campaign v8 biedt ondersteuning voor gegevensconnectors met Adobe Experience Platform/RT-CDP, Unified Customer Profile en native integratie met Journey Orchestration. Deze investeringen zullen de Adobe Campaign klantenervaring optimaliseren en nieuwe gebruiksgevallen zoals de capaciteit openen om geïndividualiseerde klantenreizen in real time aan campagnes toe te voegen.

* **Beheerde Cloud Services**. Adobe Campaign v8 is beschikbaar als een best-in-class Beheerde Cloud Services, die pro-actief toezicht, het geschikte alarm, en de dienstbestuur verstrekt. De waarde voor de teller is een flexibeler en scalable dwars-kanaal campagnebeheer.

>[!CAUTION]
>
>Momenteel is Campagne v8 alleen **beschikbaar als beheerde Cloud Service en kan deze niet worden geïmplementeerd op een locatie of in een hybride omgeving.**
>
>Migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.
>
>Als u niet zeker bent van uw implementatiemodel of een vraag hebt, neemt u contact op met uw accountteam.


## Schalen

Campagne v8 biedt end-to-end schaal bij elke stap van het proces, van het richten tot de definitieve rapportering:

* Schaal het gegevensvolume dat u kunt verwerken (tot 8 TB)
* Schaal de prestaties van vragen voor segmentatie en het richten maar ook gegevensopname en uitgang
* De voorbereiding van de levering schalen (van uren tot minuten)

## Vereenvoudiging en prestatieverbetering

Campagne v8 brengt het concept van **Volledige Federated Data Access** (FDA): alle gegevens bevinden zich nu op afstand in de cloud-database.

Met deze nieuwe architectuur vereenvoudigt Campagne v8 gegevensbeheer: er is geen index vereist voor de Cloud Database. U hoeft alleen de tabellen te maken, de gegevens te kopiëren en te starten.

[!DNL Snowflake] Is de Campagne Cloud Database, het zal u snelheid en duurzaamheid brengen: geen overbelasting van de pieken van de systeemactiviteit.

De Cloud-databasetechnologie vereist geen specifiek onderhoud om het prestatieniveau te garanderen.

## Geïntegreerd ecosysteem

U kunt Campagne met een reeks krachtige oplossingen van Adobe integreren, zoals: Adobe Analytics, Workfront, Journey Orchestration, Real-Time CDP en meer.

U kunt ook voorspellende optimalisatie van de verzendtijd en voorspellende betrokkenheidsscoring configureren met Journey AI en de openingssnelheden verhogen, klikken en inkomsten verhogen.

[!DNL :bulb:] [Meer informatie over de integratie van campagnes](../connect/integration.md)

