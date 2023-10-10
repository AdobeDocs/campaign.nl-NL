---
product: campaign
title: Planner
description: Meer informatie over de workflowactiviteit van de planner
feature: Workflows
role: User
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 10%

---

# Planner {#scheduler}



De **Planner** is een blijvende taak die zijn overgang op de tijden activeert die door zijn programma worden gespecificeerd.

De **[!UICONTROL Scheduler]**-activiteit kan dus worden beschouwd als een geplande start. De regels voor het positioneren van de activiteit in het diagram zijn hetzelfde als voor de **[!UICONTROL Start]**-activiteit. Deze activiteit mag geen binnenkomende overgang hebben.

## Best practices {#best-practices}

* Plan geen workflow die meer dan om de 15 minuten wordt uitgevoerd, aangezien dit de algehele systeemprestaties kan belemmeren en blokken in de database kan maken.

* Nooit meer gebruiken dan één **[!UICONTROL Scheduler]** activiteit per vertakking in een werkstroom. Zie [Werken met activiteiten](workflow-best-practices.md#using-activities).

* Het gebruiken van een planneractiviteit kan tot verscheidene uitvoeringen van een werkschema leiden die tezelfdertijd lopen. Bijvoorbeeld, kunt u een planner hebben die de werkschemauitvoering elk uur teweegbrengt, maar soms neemt de uitvoering van het volledige werkschema meer dan een uur.

  U kunt de uitvoering overslaan als de workflow al wordt uitgevoerd. Raadpleeg voor meer informatie over het voorkomen van gelijktijdige uitvoering van een workflow de [deze pagina](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions).

* Merk op dat de overgang verscheidene uren later kan worden geactiveerd als het werkschema een taak op lange termijn, zoals het invoeren uitvoerde, of als de wfserver module voor een tijd werd tegengehouden. In dit geval, kan het noodzakelijk zijn om de uitvoering van de taak te beperken die door de planner tot een bepaalde tijdwaaier wordt geactiveerd.

## De planneractiviteit configureren {#configuring-scheduler-activity}

De planner bepaalt het activeringsprogramma van de overgang. Om het te vormen, klik het grafische voorwerp tweemaal, dan klik **[!UICONTROL Change...]**

![](assets/s_user_segmentation_scheduler.png)

Met een wizard kunt u de frequentie en de geldigheidsperiode van de activiteit definiëren. De configuratiestappen zijn als volgt:

1. Selecteer de activeringsfrequentie en klik op **[!UICONTROL Next]**.

   ![](assets/s_user_segmentation_scheduler2.png)

1. Geef de activeringstijden en -dagen op. De parameters voor deze stap zijn afhankelijk van de frequentie die u in de vorige stap hebt geselecteerd. Als u ervoor kiest om de activiteit meerdere keren per dag te lanceren, zullen de configuratieopties als volgt zijn:

   ![](assets/s_user_segmentation_scheduler3.png)

1. Bepaal de geldigheidsperiode van het programma of specificeer hoe vaak het zal worden uitgevoerd.

   ![](assets/s_user_segmentation_scheduler4.png)

1. Controleer de configuratie en klik op **[!UICONTROL Finish]** opslaan.

   ![](assets/s_user_segmentation_scheduler5.png)
