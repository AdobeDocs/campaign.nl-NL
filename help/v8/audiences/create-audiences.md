---
title: Profielpubliek maken in campagne
description: Leer hoe u lijsten maakt en een publiek maakt
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 6fbe5616-7b8b-4504-988b-2bbbfd062548
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Een publiek in een lijst maken {#create-segments}

Met de lijsten Campagne kunt u uw publiek maken en organiseren.

Een lijst is een statische reeks contacten die in leveringsacties kunnen worden gericht of tijdens de invoer of een andere werkschemaactie worden bijgewerkt. Bijvoorbeeld, kan een populatie die uit het gegevensbestand via een vraag wordt gehaald als lijst worden opgeslagen.

Lijsten worden gemaakt en beheerd via de koppeling **[!UICONTROL Lists]** op het tabblad **[!UICONTROL Profiles and targets]** . Deze lijst is gebaseerd op de standaard Adobe Campaign-profieltabel (nms:ontvanger). [Meer informatie](../dev/datamodel.md#ootb-profiles.md)

![](assets/list-dashboard.png)

U kunt een lijst tot stand brengen gebruikend de **lijst van de Update** activiteit in een werkschema. Deze activiteit slaat de resulterende bevolking in een lijst op. Met deze lijst kunt u een nieuwe lijst maken of een bestaande lijst bijwerken. Als u lijsten wilt maken met andere typen gegevens dan de ingebouwde profielentabel, moet u een workflow uitvoeren. Als u bijvoorbeeld een query op de bezoekerslijst gebruikt en de lijst vervolgens bijwerkt, kunt u een bezoekerslijst maken. [Meer informatie](#create-a-list-wf).

Bekijk deze video voor meer informatie over Lijstbeheer in Adobe Campaign.

>[!VIDEO](https://video.tv.adobe.com/v/3426463?quality=12&captions=dut)


## Een lijst met contactpersonen maken {#create-a-list-of-contacts}

Volg onderstaande stappen om een lijst met contactpersonen te maken:

1. Klik op **[!UICONTROL Create]** en selecteer **[!UICONTROL New list]** .

   ![](assets/new-list.png)

1. Voer de informatie in op het tabblad **[!UICONTROL Edit]** van het venster voor het maken van de lijst.

   ![](assets/list-details.png)

   * Voer de naam van de lijst in het veld **[!UICONTROL Label]** in en wijzig, indien nodig, de interne naam.
   * Voeg een beschrijving voor deze lijst toe.
   * U kunt een vervaldatum opgeven: wanneer deze datum wordt bereikt, wordt de lijst gewist en automatisch verwijderd.


1. Klik op het tabblad **[!UICONTROL Content]** op **[!UICONTROL Add]** om de profielen te selecteren die tot de lijst behoren.

   ![](assets/add-profiles-to-a-list.png)

   U kunt een nieuw profiel maken en dit rechtstreeks vanuit dit venster in de lijst toevoegen met het pictogram **[!UICONTROL Create]** . Het profiel wordt toegevoegd aan de database.

1. Klik op **[!UICONTROL Save]** om de lijst op te slaan. Het wordt dan toegevoegd aan het overzicht van lijsten.


## Gefilterde contactpersonen omzetten in een lijst {#convert-data-to-a-list}

U kunt profielen selecteren en toevoegen aan een lijst. Volg onderstaande stappen om dit te doen:

1. Selecteer profielen in Campagneverkenner en klik met de rechtermuisknop.

   Deze profielen kunnen worden gefilterd om aan specifieke criteria te voldoen.

1. Selecteer **[!UICONTROL Actions > Associate selection with a list...]**.

   ![](assets/add-selection-to-a-list.png)

1. Selecteer een bestaande lijst of maak een nieuwe lijst en klik op **[!UICONTROL Next]** .

   ![](assets/select-the-list.png)

1. Klik op de knop **[!UICONTROL Start]**.

   ![](assets/record-a-list.png)

Selecteer de optie **[!UICONTROL Recreate the list]** om de bestaande inhoud uit de lijst te verwijderen en het maken van de lijst te optimaliseren (er is geen query nodig om te controleren of de profielen al aan de lijst zijn gekoppeld).

Als u de optie **[!UICONTROL No trace of this job is saved in the database]** uitschakelt, kunt u de uitvoeringsmap selecteren (of maken) waarin de informatie wordt opgeslagen die aan dit proces is gekoppeld.

In de bovenste sectie van het venster kunt u de uitvoering controleren. Met de knop **[!UICONTROL Stop]** kunt u het proces stoppen. De reeds verwerkte contacten zullen met de lijst worden verbonden.

Zodra de uitvoering is voltooid, opent u het menu **[!UICONTROL Profiles and Targets > Lists]** en selecteert u de lijst: op het tabblad **[!UICONTROL Content]** worden de profielen weergegeven die aan deze lijst zijn gekoppeld.


## Een lijst maken met een workflow  {#create-a-list-wf}

Met de activiteit **[!UICONTROL List update]** kunt u een lijst maken of een populatie toevoegen aan een lijst met ontvangers.

In het onderstaande voorbeeld maakt u een lijst met alle ontvangers tussen 25 en 40.

1. Selecteer **[!UICONTROL Profiles and targets]** en **[!UICONTROL Targeting workflows]** en maak een nieuwe workflow via de knop **[!UICONTROL Create]** .
1. Voer een label in voor deze workflow, bijvoorbeeld &#39;25-40 contactpersonen&#39;, voeg een beschrijving toe en klik op **[!UICONTROL Next]** .

   ![](assets/targeting-wf-sample.png)

1. Voeg een **[!UICONTROL Query]** -activiteit in om de doelpopulatie te definiëren en bewerk de query.

   ![](assets/targeting-wf-edit-query.png)

1. Definieer de filtervoorwaarden als volgt:

   ![](assets/targeting-wf-age-filter.png)

   Leer hoe te om een vraag in een werkschema in [ tot stand te brengen deze sectie ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=nl-NL){target="_blank"} .

1. Voeg een label voor deze query toe en sla uw wijzigingen op.
1. Voeg een **[!UICONTROL List update]** -activiteit toe en bewerk deze.

   ![](assets/list-update-activity.png)

1. Voer een label in voor de activiteit.
1. Selecteer de optie **[!UICONTROL Create the list if necessary (Computed name)]** om aan te geven dat de lijst wordt gemaakt zodra de eerste workflow is uitgevoerd en vervolgens wordt bijgewerkt met de volgende uitvoeringen.
1. Selecteer een map en voer een label voor de lijst in.
1. Selecteer de **[!UICONTROL Database of the targeting dimension]** om de tabel op te slaan.
1. Laat de optie **[!UICONTROL Purge the list if it exists (otherwise add to the list)]** ingeschakeld om ontvangers te verwijderen die niet voldoen aan de doelcriteria en om de nieuwe criteria in de lijst in te voegen.
1. Laat de optie **[!UICONTROL Create or use a list with its own table]** ook ingeschakeld.
1. Laat de optie **[!UICONTROL Generate an outbound transition]** uitgeschakeld.
1. Klik op **[!UICONTROL Ok]** en sla de workflow op.
1. Start de workflow.

   De lijst met overeenkomende ontvangers wordt dan gemaakt. U hebt toegang tot deze lijst via de vermelding **[!UICONTROL Lists]** op de startpagina.

   ![](assets/access-new-list.png)

   U kunt deze werkstroom terugkomen door een planner aan het werkschema toe te voegen. [Meer informatie](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html?lang=nl-NL){target="_blank"}.

## Een profiel uit een lijst verwijderen {#remove-a-profile-from-a-list}

Als u een profiel uit een lijst wilt verwijderen, bewerkt u de lijst, selecteert u het profiel op het tabblad **[!UICONTROL Content]** en klikt u op het pictogram **[!UICONTROL Delete]** .

## Een lijst met profielen verwijderen {#delete-a-list-of-profiles}

Als u een lijst wilt verwijderen, bladert u ernaar in Campagneverkenner, selecteert u de lijst en klikt u met de rechtermuisknop. Kies **[!UICONTROL Delete]** . U wordt in een waarschuwingsbericht gevraagd de verwijdering te bevestigen.

>[!NOTE]
>
>Wanneer u een lijst verwijdert, worden de profielen in de lijst niet gewijzigd, maar worden de gegevens in het bijbehorende profiel bijgewerkt.
