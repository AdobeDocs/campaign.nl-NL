---
product: campaign
title: Leveringscontrole
description: Meer informatie over de activiteit van de workflow voor leveringsbeheer
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 09fe638d-5e1c-49d1-9196-6300c1e56703
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 2%

---

# Leveringscontrole{#delivery-control}

A **de controle van de Levering** - typeactie laat u beginnen, pauzeren, of een levering tegenhouden.

Dit kan de levering zijn die in de overgang wordt gespecificeerd, uitdrukkelijk geselecteerde levering, of een levering die door een manuscript wordt berekend. Voor meer op dit, verwijs naar [&#x200B; Levering &#x200B;](delivery.md).

![](assets/edit_diffusion_act.png)

Als u **[!UICONTROL Start]** selecteert, voert de activiteit alle stappen uit die nodig zijn om de levering te starten (doelberekening, inhoudsvoorbereiding, levering). Als sommige van deze stappen al zijn uitgevoerd door een eerdere workflowactiviteit, worden ze niet opnieuw uitgevoerd. Bijvoorbeeld, als de doelschatting reeds door een **[!UICONTROL Delivery]** typeactiviteit (verwijs naar [&#x200B; Levering &#x200B;](delivery.md)) werd uitgevoerd, zal de **[!UICONTROL Act on the delivery]** activiteit de resterende stappen (inhoudspreiding en levering) lanceren.

De volgende opties zijn beschikbaar:

* **[!UICONTROL Generate an outbound transition]**

  Creeert een uitgaande overgang die aan het eind van uitvoering zal worden geactiveerd. U kunt kiezen al dan niet om het doel van de uitgaande levering terug te winnen.

* **[!UICONTROL Processing errors]**

  Verwijs naar [&#x200B; de fouten van de Verwerking &#x200B;](monitor-workflow-execution.md#processing-errors).

## Invoerparameters {#input-parameters}

* deliveryId

  Leverings-id als de geselecteerde actie **[!UICONTROL Specified in the transition]** is.
