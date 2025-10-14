---
title: Databron wijzigen
description: Meer informatie over de activiteit van de gegevensbron van de Verandering
feature: Workflows, Data Management, Federated Data Access
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 2%

---

# Databron wijzigen {#change-data-source}

Gebruik de **[!UICONTROL Change data source]** activiteit om de gegevensbron van a [&#x200B; werkschema werkende lijst &#x200B;](use-workflow-data.md#workflow-temporary-work-table) te veranderen. Deze activiteit verstrekt meer flexibiliteit om gegevens over verschillende gegevensbronnen zoals Federated Data Access (FDA), het gegevensbestand van de Wolk van de Campagne (FFDA) en het Lokale gegevensbestand van de Campagne te beheren.

De workflow **[!UICONTROL Working table]** wordt gebruikt om gegevens af te handelen en te delen met de workflowactiviteiten.

Standaard wordt **[!UICONTROL Working table]** gemaakt in dezelfde database als de bron van de gegevens waarop u een query wilt uitvoeren.
Wanneer u bijvoorbeeld een query uitvoert op de tabel **[!UICONTROL Recipients]** die is opgeslagen in de Cloud-database, maakt de workflow een **[!UICONTROL Working table]** in dezelfde Cloud-database.

Gebruik een **[!UICONTROL Change Data Source]** -activiteit om een andere gegevensbron voor uw **[!UICONTROL Working table]** te gebruiken.

Wanneer u de **[!UICONTROL Change Data Source]** -activiteit gebruikt, moet u terugschakelen naar de Cloud-database om door te gaan met de workflowuitvoering.

>[!IMPORTANT]
>
>De activiteiten **[!UICONTROL Change Dimension]** en **[!UICONTROL Change Data source]** mogen niet in één rij worden toegevoegd. Als u beide activiteiten opeenvolgend moet gebruiken, zorg ervoor u een **[!UICONTROL Enrichement]** activiteit binnen tussen hen omvat. Dit zorgt voor een correcte uitvoering en voorkomt mogelijke conflicten of fouten.

Als u de **[!UICONTROL Change Data Source]** -activiteit wilt gebruiken, moet u:

1. Maak een workflow.

1. Vraag de beoogde ontvangers naar een **[!UICONTROL Query]** -activiteit.

   Voor meer informatie over de **[!UICONTROL Query]** activiteit, verwijs naar deze [&#x200B; pagina &#x200B;](query.md#create-a-query).

1. Voeg een **[!UICONTROL Change data source]** activiteit toe.

   ![](assets/change-data-source.png)

1. Bewerk de **[!UICONTROL Change data source]** -activiteit om **[!UICONTROL Default data source]** te selecteren.

   De het werk lijst, die het resultaat van uw vraag bevat, wordt dan verplaatst naar het standaard Lokale gegevensbestand van de Campagne.

   ![](assets/change-data-source_2.png)

1. Voeg een **[!UICONTROL JavaScript code]** activiteit toe om unitaire verrichtingen op de het werk lijst uit te voeren.

   Voor meer informatie over de **[!UICONTROL JavaScript code]** activiteit, verwijs naar [&#x200B; deze pagina &#x200B;](sql-code-and-javascript-code.md#javascript-code).

1. Voeg nog een **[!UICONTROL Change data source]** -activiteit toe om terug te schakelen naar de Cloud-database.

1. Bewerk deze activiteit en selecteer **[!UICONTROL Active FDA external account]** en de bijbehorende **[!UICONTROL External database]** externe account.

   ![](assets/change-data-source_3.png)

1. U kunt nu uw workflow starten.
