---
product: campaign
title: Leveringscontrole
description: Meer informatie over de activiteit van de workflow voor leveringsbeheer
feature: Workflows
exl-id: 09fe638d-5e1c-49d1-9196-6300c1e56703
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 2%

---

# Leveringscontrole{#delivery-control}



A **Afleveringscontrole** Met een handeling van het type -kunt u een levering starten, pauzeren of stoppen.

Dit kan de levering zijn die in de overgang wordt gespecificeerd, uitdrukkelijk geselecteerde levering, of een levering die door een manuscript wordt berekend. Raadpleeg voor meer informatie hierover [Aflevering](delivery.md).

![](assets/edit_diffusion_act.png)

Als u **[!UICONTROL Start]**, voert de activiteit alle stappen uit die nodig zijn om de levering te starten (doelberekening, inhoudsvoorbereiding, levering). Als sommige van deze stappen al zijn uitgevoerd door een eerdere workflowactiviteit, worden ze niet opnieuw uitgevoerd. Als de doelschatting bijvoorbeeld al is uitgevoerd door een **[!UICONTROL Delivery]** tekstactiviteit (zie [Aflevering](delivery.md)), de **[!UICONTROL Act on the delivery]** de resterende stappen ( voorbereiding en levering van inhoud ) zullen worden opgestart .

De volgende opties zijn beschikbaar:

* **[!UICONTROL Generate an outbound transition]**

   Creeert een uitgaande overgang die aan het eind van uitvoering zal worden geactiveerd. U kunt kiezen al dan niet om het doel van de uitgaande levering terug te winnen.

* **[!UICONTROL Processing errors]**

   Zie [Verwerkingsfouten](monitor-workflow-execution.md#processing-errors).

## Invoerparameters {#input-parameters}

* deliveryId

Leverings-id als de geselecteerde actie **[!UICONTROL Specified in the transition]**.
