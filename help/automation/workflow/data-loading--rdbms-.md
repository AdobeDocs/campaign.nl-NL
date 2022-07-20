---
product: campaign
title: Gegevens laden (RDBMS)
description: Meer informatie over de activiteit van de workflow voor het laden van gegevens (RDBMS)
feature: Workflows, Data Management Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---

# Gegevens laden (RDBMS){#data-loading-rdbms}



De **[!UICONTROL Data loading (RDBMS)]** Met deze activiteit hebt u rechtstreeks toegang tot deze externe database en kunt u alleen de gegevens verzamelen die nodig zijn voor de doelindeling.

Om prestaties te verbeteren, adviseren wij gebruikend de vraagactiviteit (waar de gegevens van een extern gegevensbestand kunnen worden gebruikt). Raadpleeg voor meer informatie hierover [Toegang tot een externe database (FDA)](accessing-an-external-database--fda-.md).

De bewerking is als volgt:

1. Selecteer de gegevensbron in de lijst en voer de naam in van de tabel die de gegevens bevat die u wilt extraheren.

   ![](assets/s_advuser_wf_sgbd_sample_1.png)

   De naam van de tabel die in het desbetreffende veld wordt ingevoerd, wordt gebruikt als sjabloon voor het verzamelen van gegevens in de externe database. De naam van de tabel die door de workflow wordt verwerkt, kan worden berekend of overgebracht door de binnenkomende overgang van de activiteit voor het laden van gegevens. Klik op de knop **[!UICONTROL Advanced..]**. en selecteer de **[!UICONTROL Specified in the transition]** of **[!UICONTROL Explicit]** optie.

   ![](assets/s_advuser_wf_sgbd_sample_5.png)

1. Klik op de knop **[!UICONTROL Select the columns to extract...]** koppeling om de gegevens te kiezen die in de database moeten worden verzameld.

   ![](assets/s_advuser_wf_sgbd_sample_2.png)

1. U kunt een filter voor deze gegevens definiëren. Om dit te doen, klik **[!UICONTROL Edit query....]** koppeling.

   De op deze manier verzamelde gegevens kunnen gedurende de gehele levenscyclus van de workflow worden gebruikt.
