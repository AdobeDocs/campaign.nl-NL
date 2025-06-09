---
product: campaign
title: Aanbiedingsengine
description: Aanbiedingsengine
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: d77858e1-3cd5-4372-b1bc-ea4b518c958d
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 4%

---

# Aanbiedingsengine{#offer-engine}

Met de activiteit **[!UICONTROL Offer engine]** kunt u een aanroep naar de aanbiedingsengine definiëren voordat de levering plaatsvindt.

Deze activiteit werkt volgens hetzelfde principe als de verrijkingsactiviteit met een motoraanroep, door de binnenkomende bevolkingsgegevens te verrijken met een aanbod dat door de motor wordt berekend, vóór de levering.

![](assets/int_offerengine_activity2.png)

Na het vormen van uw vraag (verwijs naar deze [ sectie ](query.md)):

1. Voeg een **[!UICONTROL Offer engine]** -activiteit toe en open deze.
1. Vul de verschillende beschikbare velden in om de oproep tot het aanbieden van motorparameters op te geven (beschikbare ruimte, categorie of thema(&#39;s), contactdatum, aantal aanbiedingen dat moet worden bewaard). De motor berekent automatisch de aanbieding(en) die volgens deze parameters moet worden toegevoegd.

   >[!CAUTION]
   >
   >Als u deze activiteit gebruikt, zullen slechts de aanbiedingsvoorstellen die in de levering worden gebruikt worden opgeslagen.

   ![](assets/int_offerengine_activity1.png)

1. Dan vorm een leveringsactiviteit die aan uw gekozen kanaal beantwoordt. Verwijs naar [ de leveringen van het Kanaal 1}.](cross-channel-deliveries.md)
