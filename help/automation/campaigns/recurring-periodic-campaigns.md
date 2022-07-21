---
product: campaign
title: Herhalende en periodieke campagnes maken
description: Leer hoe u terugkerende en periodieke campagnes kunt maken en uitvoeren
feature: Campaigns, Cross Channel Orchestration, Programs
exl-id: 68c5b903-5043-4e74-b3f6-90a7f2fb3b9a
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Herhalings- en periodieke campagnes {#recurring-and-periodic-campaigns}

A **terugkerende campagne** is een campagne die op een specifiek malplaatje wordt gebaseerd, de waarvan werkschema&#39;s worden gevormd om volgens een bijbehorend programma worden uitgevoerd. Het richten wordt gedupliceerd op elke uitvoering en de diverse processen en doelpopulaties worden gevolgd.  Wanneer gevormd, leidt het terugkomen campagnes automatisch tot een nieuw werkschema (door het werkschemamalplaatje te dupliceren) en stelt het in werking. Bijvoorbeeld, als u maandelijkse herinnering aan een publiekssegment moet verzenden, vorm een terugkomende campagne zodat aan het begin van elk jaar, het 12 werkschema&#39;s, voor elke maand creeert. [Meer informatie](#create-a-recurring-campaign)

A **periodieke campagne** is een campagne die op een specifiek malplaatje wordt gebaseerd dat u campagneinstanties laat tot stand brengen die op een uitvoeringsprogramma worden gebaseerd. Campagneinstanties worden automatisch gemaakt op basis van een periodiek campagnemalplaatje, afhankelijk van de frequentie die in het sjabloonprogramma is gedefinieerd. [Meer informatie](#create-a-periodic-campaign)

## Een terugkerende campagne maken {#create-a-recurring-campaign}

Herhalende campagnes worden gecreeerd van een specifiek malplaatje dat het werkschemamalplaatje bepaalt dat en het uitvoeringsplan moet worden uitgevoerd.

### Een sjabloon maken voor terugkerende campagnes {#create-the-campaign-template}

Volg onderstaande stappen om een sjabloon voor terugkerende campagnes te maken:

1. Campagneverkenner openen en bladeren naar **[!UICONTROL Resources > Templates > Campaign templates]**.
1. De ingebouwde **[!UICONTROL Recurring campaign]** sjabloon.
   ![](assets/recurring-campaign-duplicate.png)
1. Voer de naam van de sjabloon en de duur van de campagne in.
1. Voor dit type campagne **[!UICONTROL Schedule]** wordt toegevoegd om het schema voor de uitvoering van de sjabloon te maken. Op dit tabblad kunt u de uitvoeringsdatums definiëren van de campagnes die op deze sjabloon zijn gebaseerd.
   ![](assets/recurring-campaign-schedule.png)

   De configuratiewijze van het uitvoeringsprogramma valt samen met **[!UICONTROL Scheduler]** object van de workflow. [Meer informatie](../workflow/scheduler.md).

   >[!CAUTION]
   >
   >De configuratie van het uitvoeringsschema moet zorgvuldig worden uitgevoerd. Met terugkerende campagnes worden de workflow(en) van de sjabloon gedupliceerd, afhankelijk van het opgegeven schema. Deze bewerking kan uw database overladen.

1. Geef een waarde op in het dialoogvenster **[!UICONTROL Create in advance for]** om de overeenkomstige werkstromen voor de aangegeven periode te creëren.
1. In de **[!UICONTROL Targeting and workflows]** , ontwerpt u het werkstroomsjabloon dat moet worden gebruikt in campagnes die op deze sjabloon zijn gebaseerd. Deze workflow bevat doorgaans de doelparameters en een of meer leveringen.

   >[!NOTE]
   >
   >Deze workflow moet worden opgeslagen als een terugkerende werkstroomsjabloon. Om dit te doen, geef de werkschemaeigenschappen uit en selecteer **[!UICONTROL Recurring workflow template]** in de **[!UICONTROL Execution]** tab.

   ![](assets/recurring-campaign-wf-properties.png)

### De terugkerende campagne maken {#create-the-recurring-campaign}

Als u de terugkerende campagne wilt maken en de workflows wilt uitvoeren volgens het schema dat in de sjabloon is gedefinieerd, moet u:

1. Maak een nieuwe campagne op basis van uw terugkerende campagnemalplaatje.
1. Vul het schema voor workflowuitvoering in in het dialoogvenster **[!UICONTROL Schedule]** tab. In het campagnereschema kunt u voor elke regel een automatische begindatum voor het maken of uitvoeren van de workflow invoeren.

   Voor elke regel kunt u de volgende aanvullende opties toevoegen:

   * De optie **[!UICONTROL To be approved]** optie om de goedkeuringsaanvragen voor levering in de workflow af te dwingen.
   * De optie **[!UICONTROL To be started]** om de workflow te starten wanneer de begindatum is bereikt.

   De **[!UICONTROL Create in advance for]** in dit veld kunt u alle werkstromen maken die betrekking hebben op de ingevoerde periode.

   Bij uitvoering van de **[!UICONTROL Jobs on campaigns]** de specifieke workflows worden gemaakt op basis van de voorvallen die in het campagnereschema zijn gedefinieerd. Op deze manier wordt voor elke uitvoeringsdatum een workflow gemaakt.

1. De terugkomende werkschema&#39;s worden gecreeerd automatisch van het werkschemamalplaatje huidig in de campagne. Ze zijn zichtbaar vanaf de **[!UICONTROL Targeting and workflows]** tabblad van de campagne.

   ![](assets/recurring-wf-created.png)

   Het label van een terugkerende werkstroominstantie bestaat uit zijn malplaatjelabel en het werkschemanummer, met # karakter binnen tussen.

   De werkstromen die van het programma worden gecreeerd worden automatisch geassocieerd met het in **[!UICONTROL Workflow]** kolom van de **[!UICONTROL Schedule]** tab.

   ![](assets/recurring-wf-schedule-executed.png)

   Elke workflow kan op dit tabblad worden bewerkt.

   >[!NOTE]
   >
   >De begindatum van de aan de workflow gekoppelde planningsregel is beschikbaar in een variabele van de workflow met de volgende syntaxis:\
   >`$date(instance/vars/@startPlanningDate)`

## Een periodieke campagne maken {#create-a-periodic-campaign}

Een periodieke campagne is een campagne die op een specifiek malplaatje wordt gebaseerd dat u campagneinstanties laat tot stand brengen die op een uitvoeringsprogramma worden gebaseerd. Campagneinstanties worden automatisch gemaakt op basis van een periodiek campagnemalplaatje, afhankelijk van de frequentie die in het sjabloonprogramma is gedefinieerd.

### De sjabloon voor de campagne maken {#create-the-campaign-template-1}

1. Campagneverkenner openen en bladeren naar **[!UICONTROL Resources > Templates > Campaign templates]**.
1. De ingebouwde **[!UICONTROL Periodic campaign]** sjabloon.
1. Voer de eigenschappen van de sjabloon in.

   >[!NOTE]
   >
   >De exploitant wie het malplaatje wordt toegewezen moet de aangewezen toestemmingen hebben om campagnes in het geselecteerde programma tot stand te brengen.

1. Maak de workflow die aan deze sjabloon is gekoppeld. Deze worflow wordt gedupliceerd in elke periodieke campagne die door het malplaatje wordt gecreeerd.

   >[!NOTE]
   >
   >Deze workflow is een werkstroomsjabloon. Deze kan niet worden uitgevoerd vanuit de campagnemalplaatje.

1. Voltooi zijn uitvoeringsprogramma zoals voor een terugkomende campagnemalplaatje: klik op **[!UICONTROL Add]** en definieert u de begin- en einddatum of vult u het uitvoeringsschema in via de koppeling.

   >[!CAUTION]
   >
   >De periodieke campagnemalplaatjes creëren nieuwe campagnes volgens het hierboven bepaalde programma. Het moet daarom zorgvuldig worden afgerond om overbelasting van de Adobe Campaign-databank te voorkomen.

1. Wanneer de begindatum van de uitvoering is bereikt, wordt de overeenkomende campagne automatisch gemaakt. Het neemt alle kenmerken van zijn malplaatje over.

   Elke campagne kan via het sjabloonprogramma worden bewerkt.

   Elke periodieke campagne bevat dezelfde elementen. Zodra gecreeerd, wordt het beheerd als standaardcampagne.
