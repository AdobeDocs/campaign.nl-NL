---
product: campaign
title: Vertakking
description: Meer informatie over de workflowactiviteit van Fork
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 7b94776c-2478-4e12-82a6-c94be12e7e22
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 1%

---

# Vertakking{#fork}



U kunt de **[!UICONTROL Fork]** -activiteit gebruiken om meerdere uitgaande overgangen te maken en verschillende activiteiten onafhankelijk binnen dezelfde workflow uit te voeren.

>[!IMPORTANT]
>
>De uitgaande overgangen die u na een **[!UICONTROL Fork]** activiteit toevoegt, worden niet gelijktijdig uitgevoerd. Dit gedrag kan van invloed zijn op de workflowprestaties. Gebruik de **[!UICONTROL Fork]** -activiteit als u verschillende activiteiten onafhankelijk moet uitvoeren. Naar keuze, kunt u zich bij de uitgaande activiteiten vóór het verdere deel van het werkschema aansluiten.

Voer de volgende stappen uit om een **[!UICONTROL Fork]** -activiteit en de bijbehorende activiteiten te configureren:

1. Open de **[!UICONTROL Fork]** -activiteit en definieer de naam en het label van de uitgaande overgangen.

   ![](assets/s_user_segmentation_fork.png)

1. Open elke uitgaande overgang en vorm het.
1. Naar keuze, om zich bij uitgaande overgangen aan te sluiten, voeg een EN-lid activiteit toe. [Meer informatie](and-join.md).

   Het volgende gedeelte van de workflow wordt alleen uitgevoerd na voltooiing van de gecombineerde uitgaande overgangen.

## Voorbeeld: segmentatie

In dit voorbeeld worden verschillende e-mails verzonden naar verschillende bevolkingsgroepen. Een **[!UICONTROL Fork]** activiteit wordt gebruikt na een vraag, om twee acties parallel uit te voeren:

* Het queryresultaat opslaan
* Segmenteer het resultaat om meerdere leveringen te verzenden

  ![&#x200B; de vorkactiviteit volgt de doorsnede van twee vragen en voorafgaat een activiteit van de lijstupdate en een gespleten activiteit.](assets/wkf_fork_example.png)

De workflow omvat de volgende activiteiten:

1. **[!UICONTROL Query]** activiteit

   Er zijn twee bevolkingsgroepen geselecteerd: vrouwen en Parisiërs.

1. **[!UICONTROL Intersection]** activiteit

   De doorsnede van de zoekresultaten, dat wil zeggen, Parisiaanse vrouwen, wordt geselecteerd.

1. **[!UICONTROL Fork]** activiteit

   De berekende populatie wordt bespaard en parallel verdeeld in twee groepen:

   1. Parisiaanse vrouwen tussen de 18 en 40 jaar
   1. Parisiaanse vrouwen ouder dan 40

1. **[!UICONTROL Delivery]** activiteit

   Er wordt een ander e-mailbericht verzonden naar elke bevolkingsgroep.

## Kwestie gebruiken: een e-mail voor een geboortedatum verzenden

Een terugkerende e-mail wordt verzonden naar een lijst met ontvangers op hun verjaardag. Een **[!UICONTROL Fork]** -activiteit wordt gebruikt om ontvangers op te nemen die op 29 februari op een schrikkeljaar zijn geboren. [&#x200B; Leer meer &#x200B;](send-a-birthday-email.md) over dit gebruiksgeval.

![&#x200B; de vorkactiviteit volgt een testactiviteit en voorafgaat twee vraagactiviteiten.](assets/birthday-workflow_usecase_1.png)

## Hoofdlettergebruik: inhoud automatiseren met een workflow


U kunt elke uitgaande overgangen dan vormen, dan hen samenvoegen gebruikend [&#x200B; EN-sluit zich &#x200B;](and-join.md) activiteit aan, indien nodig. Op deze manier wordt de rest van de workflow alleen uitgevoerd als de uitgaande overgangen van de **[!UICONTROL Fork]** -activiteit zijn voltooid.

## Verwante onderwerpen

* [AND-join-activiteit](and-join.md)
* [Kwestie gebruiken: verjaardagsbericht](send-a-birthday-email.md)
