---
product: campaign
title: SQL-code en JavaScript-code
description: Meer informatie over workflowactiviteiten voor SQL- en JavaScript-codes
feature: Workflows
Role: User
level: Experienced
version: Campaign v8, Campaign Classic v7
exl-id: 8c385847-a320-4cd9-9048-2bf9daf2ee07
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 7%

---

# SQL-code en JavaScript-code{#sql-code-and-javascript-code}



## SQL-code {#sql-code}

Een **[!UICONTROL SQL code]** activiteit voert een SQL manuscript uit. Het script is een JST-sjabloon.

![](assets/sql_code.png)

* **[!UICONTROL Script]**

  Het centrale gebied van de editor bevat het script dat moet worden uitgevoerd. Dit script is een JST-sjabloon en kan daarom worden geconfigureerd volgens de workflowcontext.

* **[!UICONTROL Processing errors]**

  Verwijs naar [&#x200B; de fouten van de Verwerking &#x200B;](monitor-workflow-execution.md#processing-errors).

## JavaScript-code en geavanceerde JavaScript-code {#javascript-code}

**[!UICONTROL JavaScript code]** - en **[!UICONTROL Advanced JavaScript code]** -activiteiten voeren een JavaScript-script uit in de context van een workflow. Raadpleeg de volgende secties voor meer informatie over scripts:

* [JavaScript-scripts en -sjablonen](javascript-scripts-and-templates.md)
* [Voorbeelden van JavaScript-code in workflows](javascript-in-workflows.md)

### Uitvoeringstijd {#exec-delay}

Vanaf release 20.2 is er een vertraging bij de uitvoering toegevoegd aan de **[!UICONTROL JavaScript code]** - en **[!UICONTROL Advanced JavaScript code]** -activiteiten. Standaard kan de uitvoeringsfase niet langer duren dan 1 uur. Na deze vertraging wordt het proces afgebroken met een foutbericht en mislukt de uitvoering van de activiteit.

U kunt deze vertraging wijzigen in het veld **[!UICONTROL Stop execution after]** dat beschikbaar is in deze activiteiten.

Om deze grens te negeren, moet u de waarde aan **0** plaatsen.

### JavaScript-code {#js-code-desc}

![](assets/javascript_code.png)

* **[!UICONTROL Script]**: Het centrale gebied van de editor bevat het script dat moet worden uitgevoerd.

* **[!UICONTROL Process errors]**: Verwijs naar [&#x200B; de fouten van de Verwerking &#x200B;](monitor-workflow-execution.md#processing-errors).

### Geavanceerde JavaScript-code {#adv-js-code-desc}

![](assets/advanced_javascript_code.png)

* **[!UICONTROL First call]**: De eerste zone van de editor bevat het script dat tijdens de eerste aanroep moet worden uitgevoerd.
* **[!UICONTROL Next calls]**: De tweede zone van de editor bevat het script dat moet worden uitgevoerd tijdens de volgende aanroepen.
* **[!UICONTROL Transitions]**: u kunt verschillende uitvoerovergangen voor activiteiten definiëren.
* **[!UICONTROL Schedule]**: Op het tabblad **[!UICONTROL Schedule]** kunt u plannen wanneer de activiteit moet worden geactiveerd.

Advanced JavaScript is een permanente taak die regelmatig wordt teruggeroepen als het niet is gemarkeerd als voltooid. Om de taak te eindigen en toekomstige terugroepen te verhinderen, moet u **task.setCompleted () gebruiken** methode in de **[!UICONTROL Next calls]** sectie:

```
task.postEvent(task.transitionByName("ok")); // to transition to Ok branch
task.setCompleted();

return 0;
```
