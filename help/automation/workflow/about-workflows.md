---
product: campaign
title: Workflows
description: Automatiseer processen met workflows, beheer gegevens en doelgroepen, verzend berichten, en meer.
feature: Workflows
version: Campaign v8, Campaign Classic v7
role: User
exl-id: 297aa4e3-b672-46b5-9016-5accee8568b8
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 25%

---

# Aan de slag met workflows{#gs-workflows}

## Workflows{#about-workflows}

Adobe Campaign bevat een workflowmodule om het volledige scala aan processen en taken in de verschillende modules van de applicatieserver te organiseren. Met deze uitgebreide grafische omgeving kunt u processen ontwerpen, zoals segmentatie, uitvoering van campagnes, bestandsverwerking, menselijke participatie, enzovoort. Deze processen worden uitgevoerd en bijgehouden door de workflowengine.

U kunt bijvoorbeeld een workflow gebruiken om een bestand van een server te downloaden, het te decomprimeren en vervolgens records in de Adobe Campaign-database te importeren.

Een workflow kan ook een of meer operatoren omvatten die op de hoogte moeten worden gebracht of die keuzes kunnen maken en processen kunnen goedkeuren. Op deze manier is het mogelijk om een leveringsactie te maken, een taak toe te wijzen aan een of meer operatoren om aan content te werken, doelen op te geven en proeven goed te keuren voordat de levering wordt gestart.

Workflows vinden plaats in verschillende contexten en fasen van het campagnemanagementproces.

Adobe Campaign gebruikt workflows om:

* Workflows voor ontwerpdoelen. [Meer informatie](#targeting-workflows)
* Kanaaloverschrijdende campagnes ordenen. [Meer informatie](#campaign-workflows)
* Voer technische processen uit, zoals schoonmaak, gegevens het volgen inzameling, berekeningen, en meer. [Meer informatie](#technical-workflows)

Een werkstroom is een procesdefinitie: het werkschemadiagram, dat een vertegenwoordiging van wat verondersteld is te gebeuren is. Een werkstroom is ook een instantie van dit proces: een werkstroominstantie, die een representatie is van wat er werkelijk gebeurt.

In het werkstroomsjabloon worden de verschillende taken beschreven die moeten worden uitgevoerd en wordt beschreven hoe deze aan elkaar zijn gekoppeld. De taakmalplaatjes worden genoemd activiteiten en door pictogrammen vertegenwoordigd. Ze zijn aan elkaar gekoppeld door overgangen.

![](assets/example1.png)

## Belangrijkste beginselen

Elke werkstroom bevat:

* **[!UICONTROL Activities]**

  Een activiteit beschrijft een taakmalplaatje. De verschillende beschikbare activiteiten worden op het diagram weergegeven door pictogrammen. Elk type heeft gemeenschappelijke eigenschappen en specifieke eigenschappen. Terwijl alle activiteiten bijvoorbeeld een naam en label hebben, heeft alleen de **[!UICONTROL Approval]** -activiteit een toewijzing.

  In een workflowdiagram kan een bepaalde activiteit meerdere taken produceren, met name wanneer er een lus of terugkerende (periodieke) handelingen zijn.

  Alle werkschemaactiviteiten worden vermeld in [ deze sectie ](activities.md), met inbegrip van gebruiksgevallen en steekproeven.

* **[!UICONTROL Transitions]**

  Met overgangen kunt u activiteiten koppelen en de volgorde ervan definiëren. Een overgang koppelt een bronactiviteit aan een bestemmingsactiviteit. Er zijn diverse soorten overgangen, die van de bronactiviteit afhangen. Sommige overgangen hebben extra parameters zoals een duur, een voorwaarde of een filter.

  Een overgang die niet is gekoppeld aan een doelactiviteit, wordt oranje gekleurd en de pijlkop wordt weergegeven als een ruit.

  >[!NOTE]
  >
  >Er kan nog steeds een workflow met niet-afgesloten overgangen worden uitgevoerd: er wordt een waarschuwingsbericht gegenereerd en de workflow wordt gepauzeerd zodra de overgang is bereikt, maar er wordt geen fout gegenereerd. Het is dus mogelijk om een werkstroom te starten zonder dat deze is voltooid en om deze tijdens het proces toe te voegen.

  Voor meer informatie over hoe te om een werkschema te bouwen, verwijs naar [ deze sectie ](build-a-workflow.md).

* **[!UICONTROL Worktables]**

  De werktabel bevat alle informatie die door de overgang wordt overgedragen. Voor elke workflow worden meerdere werktabellen gebruikt. De gegevens in deze tabellen kunnen gedurende de gehele levenscyclus van de werkstroom worden versneld en gebruikt, zolang deze niet worden gewist. Onbenodigde tabellen worden immers gewist wanneer de workflow wordt gepassiveerd en mogelijk tijdens de uitvoering van de grootste workflows om overbelasting van de server te voorkomen.

  Leer meer over werkschemagegevens en lijsten in [ deze sectie ](use-workflow-data.md).

## Verwante secties

Raadpleeg de volgende secties voor hulp en tips en trucs om processen te automatiseren met workflows:

* Leer meer over werkschemaactiviteiten in [ deze pagina ](use-workflow-data.md).
* Leer hoe te om een werkschema in [ te bouwen deze sectie ](build-a-workflow.md).
* Ontdek hoe te om werkschema&#39;s te gebruiken om gegevens in Campagne in [ in te voeren deze sectie ](campaign-workflows.md).
* De beste praktijken van het werkschema zijn gedetailleerd in [ deze pagina ](workflow-best-practices.md).
* Vind begeleiding over werkschemauitvoering in [ deze sectie ](start-a-workflow.md).
* Leer hoe te om werkschema&#39;s in [ te controleren deze pagina ](monitor-workflow-execution.md).
* Leer hoe te om toegang tot gebruikers te verlenen om werkschema&#39;s in [ te gebruiken deze pagina ](managing-rights.md).
