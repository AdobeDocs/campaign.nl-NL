---
product: campaign
title: Planner
description: Meer informatie over de workflowactiviteit van de planner
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 8%

---

# Planner {#scheduler}



De **Planner** is een blijvende taak die zijn overgang op de tijden activeert die door zijn programma worden gespecificeerd.

De **[!UICONTROL Scheduler]**-activiteit kan dus worden beschouwd als een geplande start. De regels voor het positioneren van de activiteit in het diagram zijn hetzelfde als voor de **[!UICONTROL Start]**-activiteit. Deze activiteit mag geen binnenkomende overgang hebben.

## Best practices {#best-practices}

**herstart werkschema na het veranderen van plannertiming** - wanneer het veranderen van de geplande tijd van de **[!UICONTROL Scheduler]** activiteit, is het belangrijk om het werkschema opnieuw te beginnen. Dit zorgt ervoor dat de workflow op de bijgewerkte tijden wordt uitgevoerd. Als u de workflow niet opnieuw start, wordt deze verder uitgevoerd volgens het oude schema.

**de frequentie van de Planner van de Beperking** - vermijd het plannen van werkschema&#39;s om vaker dan om de 15 minuten in werking te stellen. Het runnen van hen kan meer vaak systeemprestaties degraderen en in gegevensbestandcongestie resulteren.

**Gebruik één Planner per tak** - elke tak van uw werkschema zou slechts één **[!UICONTROL Scheduler]** activiteit moeten hebben. Voor meer informatie over beste praktijken voor het gebruiken van activiteiten in werkschema&#39;s, verwijs naar de [ best practices van het Werkschema pagina ](workflow-best-practices.md#using-activities).

**verhindert werkschemagezamenlijke uitvoeringen** - als een werkschema door een planner wordt teweeggebracht, ben in gedachten dat de veelvoudige instanties van het werkschema tezelfdertijd zouden kunnen lopen. Bijvoorbeeld, als een planner de werkstroom elk uur teweegbrengt, maar de werkschemauitvoering meer dan een uur vergt, zou u kunnen eindigen met overlappende uitvoeringen.Overweeg opstellende controles om veelvoudige gelijktijdige uitvoeringen te verhinderen. [ Leer hoe te om gelijktijdige veelvoudige werkschemauitvoeringen ](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions) te verhinderen.

**Rekening voor vertraagde overgangen** - de Overgangen die door de planner worden teweeggebracht zouden kunnen worden vertraagd als het werkschema langlopende taken (als invoer) uitvoert, of als de wfserver module tijdelijk is tegengehouden. Om dit te verlichten, beperk de activeringstijden van de planner om taken te verzekeren die binnen een bepaald tijdvenster lopen.

## De planneractiviteit configureren {#configuring-scheduler-activity}

De planner bepaalt het activeringsprogramma van de overgang. Dubbelklik op het grafische object en klik vervolgens op **[!UICONTROL Change...]** om het te configureren

![](assets/s_user_segmentation_scheduler.png)

Met een wizard kunt u de frequentie en de geldigheidsperiode van de activiteit definiëren. De configuratiestappen zijn als volgt:

1. Selecteer de activeringsfrequentie en klik op **[!UICONTROL Next]** .

   ![](assets/s_user_segmentation_scheduler2.png)

1. Geef de activeringstijden en -dagen op. De parameters voor deze stap zijn afhankelijk van de frequentie die u in de vorige stap hebt geselecteerd. Als u ervoor kiest om de activiteit meerdere keren per dag te lanceren, zullen de configuratieopties als volgt zijn:

   ![](assets/s_user_segmentation_scheduler3.png)

1. Bepaal de geldigheidsperiode van het programma of specificeer hoe vaak het zal worden uitgevoerd.

   ![](assets/s_user_segmentation_scheduler4.png)

1. Controleer de configuratie en klik op **[!UICONTROL Finish]** om op te slaan.

   ![](assets/s_user_segmentation_scheduler5.png)
