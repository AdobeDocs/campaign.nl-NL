---
product: campaign
title: SQL-code en JavaScript-code
description: Meer informatie over workflowactiviteiten voor SQL- en JavaScript-codes
feature: Workflows
exl-id: 8c385847-a320-4cd9-9048-2bf9daf2ee07
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 7%

---

# SQL-code en JavaScript-code{#sql-code-and-javascript-code}



## SQL-code {#sql-code}

An **[!UICONTROL SQL code]** activiteit voert een SQL manuscript uit. Het script is een JST-sjabloon.

![](assets/sql_code.png)

* **[!UICONTROL Script]**

   Het centrale gebied van de editor bevat het script dat moet worden uitgevoerd. Dit script is een JST-sjabloon en kan daarom worden geconfigureerd volgens de workflowcontext.

* **[!UICONTROL Processing errors]**

   Zie [Verwerkingsfouten](monitor-workflow-execution.md#processing-errors).

## JavaScript-code en geavanceerde JavaScript-code {#javascript-code}

**[!UICONTROL JavaScript code]** en **[!UICONTROL Advanced JavaScript code]** activiteiten voeren een JavaScript-script uit in de context van een workflow. Raadpleeg de volgende secties voor meer informatie over scripts:

* [JavaScript-scripts en -sjablonen](javascript-scripts-and-templates.md)
* [Voorbeelden van JavaScript-code in workflows](javascript-in-workflows.md)

### Uitvoeringstijd {#exec-delay}

Vanaf release 20.2 is er een uitvoeringstijd toegevoegd aan de **[!UICONTROL JavaScript code]** en **[!UICONTROL Advanced JavaScript code]** activiteiten. Standaard kan de uitvoeringsfase niet langer duren dan 1 uur. Na deze vertraging wordt het proces afgebroken met een foutbericht en mislukt de uitvoering van de activiteit.

U kunt deze vertraging wijzigen in het dialoogvenster **[!UICONTROL Stop execution after]** in deze activiteiten beschikbaar.

Als u deze limiet wilt negeren, moet u de waarde instellen op **0**.

### JavaScript-code {#js-code-desc}

![](assets/javascript_code.png)

* **[!UICONTROL Script]**: Het centrale gebied van de editor bevat het script dat moet worden uitgevoerd.

* **[!UICONTROL Process errors]**: Zie [Verwerkingsfouten](monitor-workflow-execution.md#processing-errors).

### Geavanceerde JavaScript-code {#adv-js-code-desc}

![](assets/advanced_javascript_code.png)

* **[!UICONTROL First call]**: De eerste streek van de redacteur bevat het manuscript om tijdens de eerste vraag uit te voeren.
* **[!UICONTROL Next calls]**: De tweede streek van de redacteur bevat het manuscript om tijdens de volgende vraag uit te voeren.
* **[!UICONTROL Transitions]**: U kunt verschillende uitvoerovergangen voor activiteiten definiëren.
* **[!UICONTROL Schedule]**: De **[!UICONTROL Schedule]** kunt u plannen wanneer de activiteit wordt geactiveerd.

Geavanceerde JavaScript-code is een permanente taak die regelmatig wordt opgevraagd als deze niet is gemarkeerd als voltooid. Om de taak te beëindigen en toekomstige terugroepingen te verhinderen, moet u gebruiken **task.setCompleted()** in de **[!UICONTROL Next calls]** sectie:

```
task.postEvent(task.transitionByName("ok")); // to transition to Ok branch
task.setCompleted();

return 0;
```
