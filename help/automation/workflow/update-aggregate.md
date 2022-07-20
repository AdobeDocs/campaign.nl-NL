---
product: campaign
title: Samenvoeging bijwerken
description: Meer informatie over de workflowactiviteit voor het bijwerken van aggregaten
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%

---

# Samenvoeging bijwerken{#update-aggregate}

Voor rapportagedoeleinden worden aggregaten op kubueniveau gedefinieerd. A **[!UICONTROL Workflow]** is beschikbaar wanneer het vormen van een aggregaat.

Voor meer informatie over kubussen en het gebruik van aggregaten in Adobe Campaign raadpleegt u [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html){target=&quot;_blank&quot;}.


Als u een aggregaat wilt bijwerken, bewerkt u de **[!UICONTROL Update aggregate]** en selecteer de kubus en aggregaat die u wilt bijwerken.

U kunt een **Volledige update** of **Gedeeltelijke update**.

Standaard wordt een volledige update uitgevoerd tijdens elke berekening. Als u een gedeeltelijke update wilt inschakelen, selecteert u de desbetreffende optie en definieert u de updatevoorwaarden.

**Goede praktijken**: a **[!UICONTROL Scheduler]** de activiteit kan worden gebruikt om de frequentie van de berekening - updates te specificeren.

![](assets/scheduler-and-cube-aggregate.png)
