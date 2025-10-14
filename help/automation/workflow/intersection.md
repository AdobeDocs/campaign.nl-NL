---
product: campaign
title: Doorsnede
description: Doorsnede
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 12777107-5ccc-4f19-9dcd-8f6cade3ee98
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---

# Doorsnede{#intersection}



Een **- type van 1&rbrace; Intersectie** activiteit leidt tot een doel van de doorsnede van de ontvangen doelstellingen.

Met een doorsnede kunt u alleen de populatie extraheren die algemeen geldt voor alle resultaten van de binnenkomende activiteit. Het doel wordt gecreëerd met alle ontvangen resultaten: alle eerdere activiteiten moeten daarom worden voltooid voordat de doorsnede kan worden uitgevoerd. Om deze activiteit te vormen, moet u een etiket voor het evenals de opties betreffende het resultaat ingaan.

![](assets/s_user_segmentation_inter.png)

Voor meer bij het vormen van en het gebruiken van de intersectieactiviteit, verwijs naar [&#x200B; het Uithalen van gezamenlijke gegevens (Intersection) &#x200B;](targeting-workflows.md#extracting-joint-data--intersection-).

Schakel de optie **[!UICONTROL Generate complement]** in als u de resterende populatie wilt verwerken. Het complement zal de samenvoeging bevatten van de resultaten van alle binnenkomende activiteiten min de doorsnede. Een extra uitgaande overgang zal dan aan de activiteit worden toegevoegd, als volgt:

![](assets/s_user_segmentation_inter_compl.png)

## Voorbeeld van doorsnede {#intersection-example}

In het volgende voorbeeld is het doel van de doorsnede het berekenen van de ontvangers gemeenschappelijk aan drie eenvoudige vragen om een lijst tot stand te brengen.

1. Voeg na drie eenvoudige query&#39;s een **[!UICONTROL Intersection]** -type activiteit in.

   In dit voorbeeld zijn de vragen gericht op mannen, ontvangers in Parijs en ontvangers tussen de 18 en 30 jaar oud.

1. Vorm de doorsnede. Selecteer hiertoe de **[!UICONTROL Keys only]** -afstemmingsmethode omdat de populaties die het resultaat zijn van de query&#39;s consistente gegevens bevatten.
1. Als u aanvullende gegevens voor de query&#39;s hebt ingevoerd, kunt u ervoor kiezen alleen die gegevens te behouden die door ontvangers worden gedeeld door het desbetreffende vakje in te schakelen.
1. Als u de rest van de gegevens wilt gebruiken (met betrekking tot de query&#39;s maar niet hun doorsnede), schakelt u het vakje **[!UICONTROL Generate complement]** in.
1. Voeg een activiteit van de lijstupdate na het intersectieresultaat toe. U kunt ook een update van de lijst toevoegen aan het complement als u dit wilt gebruiken.
1. Voer de workflow uit. Hier, zijn twee ontvangers op alle drie inputted vragen tezelfdertijd van toepassing. De aanvulling bestaat uit vijf ontvangers die slechts op één of twee van de drie vragen van toepassing zijn.

   Het resultaat van de doorsnede wordt verzonden naar de eerste update van de lijst. Als u ervoor hebt gekozen om het complement te gebruiken, wordt het ook verzonden naar de tweede lijstupdate.

   ![](assets/intersection_example.png)

## Invoerparameters {#input-parameters}

* tableName
* schema

Elke binnenkomende gebeurtenis moet een doel specificeren dat door deze parameters wordt bepaald.

## Uitvoerparameters {#output-parameters}

* tableName
* schema
* recCount

Deze reeks van drie waarden identificeert het doel resulterend uit de doorsnede. **[!UICONTROL tableName]** is de naam van de tabel waarin de doel-id&#39;s worden vastgelegd. **[!UICONTROL schema]** is het schema van de populatie (gewoonlijk **[!UICONTROL nms:recipient]** ) en **[!UICONTROL recCount]** is het aantal elementen in de tabel.
