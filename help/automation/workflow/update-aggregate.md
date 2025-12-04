---
product: campaign
title: Samenvoeging bijwerken
description: Meer informatie over de workflowactiviteit voor het bijwerken van aggregaten
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 3%

---

# Samenvoeging bijwerken{#update-aggregate}

De samengevoegde groepen die in [&#x200B; worden bepaald kubussen &#x200B;](../../v8/reporting/gs-cubes.md) voor het melden van doeleinden kunnen met een specifieke activiteit worden bijgewerkt. Er is een tabblad **[!UICONTROL Workflow]** beschikbaar wanneer u het aggregaat configureert.

Leer meer over kubussen en aggregaten in [&#x200B; deze sectie &#x200B;](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Als u een aggregaat wilt bijwerken, bewerkt u de **[!UICONTROL Update aggregate]** -activiteit en selecteert u de kubus en het aggregaat die u wilt bijwerken.

U kunt a **Volledige update** of a **Gedeeltelijke update** vormen.

![](assets/update-aggregate-details.png)

Standaard wordt een volledige update uitgevoerd tijdens elke berekening. Als u een gedeeltelijke update wilt inschakelen, selecteert u de optie en definieert u de updatevoorwaarden.

![](assets/update-aggregate-partial.png)

U kunt het beste een **[!UICONTROL Scheduler]** -activiteit toevoegen om de frequentie van berekeningsupdates in te stellen.
