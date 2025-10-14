---
product: campaign
title: Terugkerende levering
description: Meer informatie over de activiteit van de workflow Terugkerende levering
feature: Workflows
role: User, Data Engineer
version: Campaign v8, Campaign Classic v7
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 13%

---

# Terugkerende levering{#recurring-delivery}



Met een **[!UICONTROL Recurring delivery]** -activiteit kunt u een exemplaar van een leveringssjabloon configureren dat specifiek is voor een campagne.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#recurring-delivery-video)

Deze activiteit is alleen beschikbaar op het tabblad **[!UICONTROL Targeting and workflows]** dat in een campagne wordt gevonden.

Dit doet u als volgt:

1. Selecteer de leveringssjabloon waarop de activiteit wordt gebaseerd.

   ![](assets/recurring_delivery_001.png)

1. Vorm het leveringsmalplaatje.

Het configuratieproces voor deze activiteit is gelijkaardig aan dat van het creëren van een leveringsmalplaatje in termen van de beschikbare opties.

Voor een voorbeeld van deze activiteit die wordt gebruikt, verwijs naar deze [&#x200B; sectie &#x200B;](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## Hoe te opstelling terugkomende levering

A **terugkomende levering** zal tot een nieuwe leveringsinstantie leiden telkens als het uitvoert. Als de workflow bijvoorbeeld eenmaal per week wordt uitgevoerd, levert dat na één jaar 52 leveringen op. Dit betekent ook dat het brede logboek en het volgen logboeken door elke leveringsinstantie zullen worden gescheiden.

![Terugkerende levering](assets/delivery_recurring.jpg)

Als u een terugkerende levering wilt tegenhouden van het lopen, zou u de campagne volledig moeten annuleren of de werkschema ophouden uitvoerend het. Als u de levering stopt vanaf het Campagne-dashboard, stopt u alleen de levering: de volgende exemplaren van de terugkerende levering blijven bij elke workflowuitvoering worden gemaakt.

>[!NOTE]
>
>Het is niet mogelijk een proef van een **[!UICONTROL Recurring delivery]** type activiteit te verzenden.
> 
>Als u rechtstreeks een levering wilt maken via een campagneworkflow, gebruikt u de kanaalspecifieke activiteiten die vooraf zijn geconfigureerd (bijvoorbeeld **[!UICONTROL Email delivery]** ).

## Tutorial video (#repeat-delivery-video)

Deze video verklaart hoe te om een terugkomende levering en een planneractiviteit te vormen.

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

De extra campagne hoe-aan video&#39;s is beschikbaar [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html?lang=nl-NL){target="_blank"}.
