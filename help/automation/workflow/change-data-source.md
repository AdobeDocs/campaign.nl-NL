---
title: Databron wijzigen
description: Meer informatie over de activiteit van de gegevensbron van de Verandering
feature: Workflows, Data Management, Federated Data Access
role: User
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# Databron wijzigen {#change-data-source}

Gebruik de **[!UICONTROL Change data source]** activiteit om de gegevensbron van een [werkstroomtabel](use-workflow-data.md#workflow-temporary-work-table). Deze activiteit verstrekt meer flexibiliteit om gegevens over verschillende gegevensbronnen zoals Federated Data Access (FDA), het gegevensbestand van de Wolk van de Campagne (FFDA) en het Lokale gegevensbestand van de Campagne te beheren.

De workflow **[!UICONTROL Working table]** wordt gebruikt voor het verwerken en delen van gegevens met de workflowactiviteiten.

Standaard worden de **[!UICONTROL Working table]** wordt gecreeerd in het zelfde gegevensbestand zoals de bron van de gegevens u moet vragen.
Wanneer u bijvoorbeeld het **[!UICONTROL Recipients]** tabel, opgeslagen in de Cloud-database, maakt de workflow een **[!UICONTROL Working table]** in dezelfde Cloud-database.

Een **[!UICONTROL Change Data Source]** activiteit om een verschillende gegevensbron voor uw te gebruiken **[!UICONTROL Working table]**.

Wanneer u de opdracht **[!UICONTROL Change Data Source]** moet u terugschakelen naar de Cloud-database om door te gaan met de uitvoering van de workflow.

Als u de opdracht **[!UICONTROL Change Data Source]** activiteit, moet u:

1. Een workflow maken.

1. Vraag uw beoogde ontvangers om een query met een **[!UICONTROL Query]** activiteit.

   Voor meer informatie over de **[!UICONTROL Query]** activiteit, verwijs naar deze [page](query.md#create-a-query).

1. Voeg een **[!UICONTROL Change data source]** activiteit.

   ![](assets/change-data-source.png)

1. Bewerk uw **[!UICONTROL Change data source]** te selecteren activiteit **[!UICONTROL Default data source]**.

   De het werk lijst, die het resultaat van uw vraag bevat, wordt dan verplaatst naar het standaard Lokale gegevensbestand van de Campagne.

   ![](assets/change-data-source_2.png)

1. Voeg een **[!UICONTROL JavaScript code]** activiteit om unitaire verrichtingen op de werkende lijst uit te voeren.

   Voor meer informatie over de **[!UICONTROL JavaScript code]** activiteit, verwijs naar [deze pagina](sql-code-and-javascript-code.md#javascript-code).

1. Nog een toevoegen **[!UICONTROL Change data source]** om terug te schakelen naar de Cloud-database.

1. Bewerk deze activiteit en selecteer **[!UICONTROL Active FDA external account]** en de overeenkomstige **[!UICONTROL External database]** externe rekening.

   ![](assets/change-data-source_3.png)

1. U kunt nu uw workflow starten.
