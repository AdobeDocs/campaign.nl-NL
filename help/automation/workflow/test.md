---
product: campaign
title: Testen
description: Meer informatie over de activiteit van de testworkflow
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---

# Testen{#test}



A **het type van de Test** activiteit activeert de eerste overgang die aan de voorwaarde verbonden aan het voldoet. Als aan geen voorwaarde wordt voldaan en als de optie **[!UICONTROL Use the default fork]** wordt geactiveerd, wordt de standaardovergang geactiveerd.

Een voorwaarde is een JavaScript-expressie die moet worden geëvalueerd op &#39;true&#39; of &#39;false&#39;. Als u de expressie wilt invoeren, klikt u op het pictogram rechts van de naam van de voorwaarde en selecteert u **[!UICONTROL Edit...]** .

![](assets/edit_test.png)

Voor meer informatie over alle extra functies van JavaScript en de methodes van SOAP van de toepassingsserver die via werkschema JavaScript toegankelijk zijn, verwijs naar [&#x200B; JSAPI documentatie &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=nl){target="_blank"}.

U kunt variabelen ook rechtstreeks vanuit deze editor invoegen. Voor meer informatie over hoe te met variabelen te werken, verwijs naar [&#x200B; deze sectie &#x200B;](javascript-scripts-and-templates.md#variables).

Voorwaarden kunnen worden toegevoegd, verwijderd of geordend in het bewerkingsvenster van de eigenschap activity, maar kunnen ook worden gewijzigd vanuit de overgang.

Als het resultaat van een berekening door verschillende voorwaarden moet worden hergebruikt, is het mogelijk om het in het initialisatiescript van de activiteit te berekenen. Het resultaat moet worden opgeslagen in een variabele van de taak die door de voorwaardenscripts (task.vars.xxx) moet worden betreden.
