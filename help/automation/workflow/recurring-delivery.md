---
product: campaign
title: Terugkerende levering
description: Meer informatie over de activiteit van de workflow Terugkerende levering
feature: Workflows
role: User, Data Engineer
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: 28742db06b9ca78a4e952fcb0e066aa5ec344416
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 12%

---

# Terugkerende levering{#recurring-delivery}



A **[!UICONTROL Recurring delivery]** De activiteit laat u een voorkomen van het leveringsmalplaatje vormen die voor een campagne specifiek is.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#recurring-delivery-video)

Deze activiteit is alleen beschikbaar via de **[!UICONTROL Targeting and workflows]** wordt gevonden in een campagne.

Dit doet u als volgt:

1. Selecteer de leveringssjabloon waarop de activiteit wordt gebaseerd.

   ![](assets/recurring_delivery_001.png)

1. Vorm het leveringsmalplaatje.

Het configuratieproces voor deze activiteit is gelijkaardig aan dat van het creëren van een leveringsmalplaatje in termen van de beschikbare opties.

Raadpleeg dit voor een voorbeeld van deze activiteit die wordt gebruikt [sectie](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## Hoe te opstelling terugkomende levering

A **terugkerende levering** wordt elke keer dat het wordt uitgevoerd, een nieuwe leveringsinstantie gemaakt. Als de workflow bijvoorbeeld eenmaal per week wordt uitgevoerd, levert dat na één jaar 52 leveringen op. Dit betekent ook dat het brede logboek en het volgen logboeken door elke leveringsinstantie zullen worden gescheiden.

![Terugkerende levering](assets/delivery_recurring.jpg)

Als u een terugkerende levering wilt tegenhouden van het lopen, zou u de campagne volledig moeten annuleren of de werkschema ophouden uitvoerend het. Als de levering vanaf het campagnemdashboard wordt gestopt, wordt de levering alleen gestopt: de volgende exemplaren van de terugkerende levering blijven bij elke workflowuitvoering worden gemaakt.

>[!NOTE]
>
>Het is niet mogelijk een bewijs van een **[!UICONTROL Recurring delivery]** type activiteit.
> 
>Om een levering via een campagnewerkschema direct tot stand te brengen, gebruik de kanaal specifieke activiteiten die (b.v. **[!UICONTROL Email delivery]**).

## Tutorial video (#repeat-delivery-video)

Deze video verklaart hoe te om een terugkomende levering en een planneractiviteit te vormen.

>[!VIDEO](https://video.tv.adobe.com/v/25040?quality=12)

Er zijn aanvullende instructievideo&#39;s beschikbaar voor campagnes [hier](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
