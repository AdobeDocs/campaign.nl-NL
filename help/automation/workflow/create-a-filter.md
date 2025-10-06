---
product: campaign
title: Een filter maken
description: Leer hoe u een filter maakt bij het uitvoeren van query's
feature: Query Editor, Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8e6fd9b4-77c4-4af8-921b-c3fe104fa5bc
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 2%

---

# Een filter maken {#creating-a-filter}

De filters beschikbaar in Adobe Campaign worden bepaald via het filtreren voorwaarden die gebruikend de zelfde werkende wijze zoals wanneer het bouwen van vragen in de [&#x200B; redacteur van de Vraag &#x200B;](../../v8/start/query-editor.md) worden gecreeerd.

Het knooppunt **[!UICONTROL Administration > Configuration > Predefined filters]** bevat alle standaardfilters. Sommige worden gebruikt in lijsten en overzichten. Leer meer over [&#x200B; ingebouwd vooraf bepaalde filters &#x200B;](../../v8/audiences/create-filters.md).

De lijst met operatoren kan bijvoorbeeld worden gefilterd door **[!UICONTROL Active accounts]** :

![](assets/query_editor_filter_sample_1.png)

Het overeenkomende filter bevat de query op de **[!UICONTROL Account disabled]** -waarde van het **[!UICONTROL Operators]** -schema:

![](assets/query_editor_filter_sample_2.png)

Voor dezelfde lijst kunt u met het filter **[!UICONTROL By login or label]** de gegevens in de lijst filteren op basis van de waarde die u hebt ingevoerd in het filterveld:

![](assets/query_editor_filter_sample_3.png)

Het is als volgt samengesteld:

![](assets/query_editor_filter_sample_4.png)

Om de filtervoorwaarden aan te passen, moet de exploitantrekening één van de volgende voorwaarden controleren:

* Het label ervan bevat de tekens die in het invoerveld zijn ingevoerd.
* De operatornaam bevat de tekens die in het invoerveld zijn ingevoerd.
* De inhoud van het beschrijvingsgebied bevat de tekens die in het invoerveld worden ingevoerd.

>[!NOTE]
>
>Met de functie **[!UICONTROL Upper]** kunt u de hoofdlettergevoelige functie deactiveren.

In de kolom **[!UICONTROL Taken into account if]** kunt u de toepassingscriteria voor deze filtervoorwaarden definiëren. Hier vertegenwoordigen de tekens **$(/tmp/@text)** de inhoud van het invoerveld dat aan het filter is gekoppeld:

![](assets/query_editor_filter_sample_5.png)

Hier, **$(/tmp/@text)=&#39;office&#39;**

De **$(/tmp/@text)!=&#39;** uitdrukking past elke voorwaarde toe wanneer het inputgebied niet leeg is.
