---
title: Processen beheren en automatiseren met Adobe Campaign-workflows
description: Aan de slag met workflows
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# Aan de slag met workflows{#gs-with-workflows}

Configureer Campagne om krachtige mogelijkheden voor automatisering van marketingcampagnes te benutten.

U kunt instellen:

* Workflows
* Recurricampagnes
* Eindvalidatiecyclus
* Waarschuwingen
* Automatisch rapport verzenden
* Gebeurtenissen geactiveerd

>[!NOTE]
>
>De gebruikersinterface van het Web van Adobe Campaign komt met een herbedacht canvas voor werkschema&#39;s, die toestaan om dynamischere en gepersonaliseerde klantenreizen tot stand te brengen. Meer over Werkschema&#39;s voor Web UI leren, gelieve te verwijzen naar [&#x200B; documentatie van het Web UI van Adobe Campaign &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/wf/gs-workflows){target=_blank}.


## Workflows ontwerpen en gebruiken {#gs-ac-wf}

Gebruik Adobe Campaign-workflows om de snelheid en schaal van elk aspect van uw marketingcampagnes te verbeteren, van het maken van segmenten en het voorbereiden van berichten tot de levering.

Meer informatie over de gebruikersinterface en uitvoering van workflows vindt u op de volgende pagina&#39;s:

* [Aan de slag met workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=nl-NL){target="_blank"}

* [Best practices voor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=nl-NL){target="_blank"}

* [&#x200B; Ingebouwde technische werkschema&#39;s &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=nl-NL){target="_blank"}

* [&#x200B; de werkschema&#39;s van de Monitor uitvoering &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=nl-NL){target="_blank"}

* [&#x200B; bouwt een publiek in een marketing campagnewerkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=nl-NL){target="_blank"}

## Workflowactiviteiten {#wf-activities}

Leer meer over de beschikbare werkschemaactiviteiten in [&#x200B; deze sectie &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=nl-NL){target="_blank"}

Workflowactiviteiten worden gegroepeerd op categorie. De vier categorieën activiteiten zijn beschikbaar:

* [&#x200B; het richten activiteiten &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=nl-NL){target="_blank"}: Vraag, Gelezen lijst, Verrijking, Vereniging, en meer
* [&#x200B; de controleactiviteiten van de Stroom &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=nl-NL){target="_blank"}: Planner, Bok, Alarm, Extern signaal, en meer
* [&#x200B; activiteiten van de Actie &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=nl-NL){target="_blank"}: De leveringen van het dwars-kanaal, code Javascript, de activiteiten van CRM, Update aggregaat, en meer
* [&#x200B; de activiteiten van de Gebeurtenis &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=nl-NL){target="_blank"}: De overdracht van het dossier, de download van het Web en meer

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=nl-NL){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=nl-NL){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

## Virtuele opslagruimten beheren {#warehouse}

Nadat u de workflow hebt gemaakt, hebt u toegang tot extra opties met de knop **[!UICONTROL Properties]** voor verdere configuratie.

Leer meer over **eigenschappen van het Werkschema** in [&#x200B; deze pagina &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=nl-NL){target="_blank"}.

Via het tabblad **[!UICONTROL Execution]** van de workflow **[!UICONTROL Properties]** kunt u de workflow aan verschillende opslagruimten koppelen en het werklastbeheer optimaliseren. Voor meer informatie over **Warehouses**, verwijs naar de [&#x200B; documentatie van Snowflake &#x200B;](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}.

![](assets/warehouse.png)

Afhankelijk van het doel van uw workflow kunt u kiezen tussen de volgende drie opslagruimten in de vervolgkeuzelijst **[!UICONTROL Warehouse]** :

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]** : wordt standaard ingesteld wanneer u een nieuwe workflow maakt.

* **[!UICONTROL Import / Export]**: moet worden ingesteld met workflows voor importeren of exporteren om de prestaties van uw activiteiten te optimaliseren.

* **[!UICONTROL Campaign Burst]**: moet worden ingesteld met campagne- of leveringsworkflows om de verwerkingstijd van de leveringen te optimaliseren.

>[!NOTE]
>
>Het **[!UICONTROL System]** -pakhuis is alleen ingesteld voor ingebouwde workflows.

## Herhalende campagnes instellen

Regelterugkerende workflows ontwerpen en telkens wanneer de workflow wordt uitgevoerd, een nieuwe leveringsinstantie maken. Als uw workflow bijvoorbeeld eenmaal per week wordt uitgevoerd, levert dat na één jaar 52 leveringen op. Dit betekent ook dat de logboeken door elke leveringsinstantie zullen worden gescheiden.

Leer hoe te om een terugkomende campagne in [&#x200B; tot stand te brengen deze pagina &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=nl-NL){target="_blank"}.


## Hefboomtriggergebeurtenissen

Het Transactionele overseinen van de Campagne van het gebruik om berichten te automatiseren die van gebeurtenissen worden geproduceerd die van informatiesystemen worden teweeggebracht. Deze transactiemeldingen kunnen bijvoorbeeld bestaan uit facturen, orderbevestiging, bevestiging van verzending, wijziging van het wachtwoord, kennisgeving van onbeschikbaarheid van het product, rekeningafschriften of het maken van websiteaccounts. Deze berichten kunnen individueel of in partij via e-mail, SMS of push berichten worden verzonden.

Leer meer over transactionele overseinenmogelijkheden in [&#x200B; deze sectie &#x200B;](../send/transactional.md).

Verbind Adobe Campaign en Adobe Analytics om gebruikersacties terug te winnen en dichtbij real-time gepersonaliseerde berichten te verzenden.

Leer hoe te om Campagne met andere oplossingen in [&#x200B; te integreren deze sectie &#x200B;](../start/connect.md)


## Gebruiksgevallen van end-to-end werkstroom{#end-to-end-uc}

Leer door gebruiksgevallen leveraging de werkstroommogelijkheden van de Campagne [&#x200B; in deze sectie &#x200B;](../../automation/workflow/workflow-use-cases.md).
