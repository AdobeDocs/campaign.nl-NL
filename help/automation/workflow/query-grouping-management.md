---
product: campaign
title: Een query uitvoeren met behulp van groeperingsbeheer
description: Leer hoe u query's uitvoert met behulp van groeperingsbeheer
feature: Query Editor
exl-id: 6fc4ef67-5d75-4c8c-8bcc-41e3ed155ca2
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# Een query uitvoeren met behulp van groeperingsbeheer {#querying-using-grouping-management}



In dit voorbeeld willen we een query uitvoeren om alle e-maildomeinen te zoeken die meer dan 30 keer zijn aangewezen tijdens eerdere leveringen.

* Welke tabel moet worden geselecteerd?

   De tabel met ontvangers (nms:ontvanger)

* Velden die moeten worden geselecteerd in uitvoerkolommen?

   E-maildomein en primaire sleutel (met aantal)

* Gegevensgroepering?

   Gebaseerd op e-maildomein met een aantal primaire sleutels boven 30. Deze bewerking wordt uitgevoerd met de **[!UICONTROL Group by + Having]** optie. **[!UICONTROL Group by + Having]** Hiermee kunt u gegevens groeperen (&quot;groeperen door&quot;) en een selectie maken van gegroepeerde objecten (&quot;hebben&quot;).

U kunt dit voorbeeld maken door de volgende stappen toe te passen:

1. Open de **[!UICONTROL Generic query editor]** en kiest u de tabel Ontvanger (**nms:ontvanger**).

   ![](assets/query_editor_02.png)

1. In de **[!UICONTROL Data to extract]** venster, selecteert u de **[!UICONTROL Email domain]** en **[!UICONTROL Primary key]** velden. Een telling uitvoeren op de **[!UICONTROL Primary key]** veld.

1. Controleer de **[!UICONTROL Handle groupings (GROUP BY + HAVING)]** doos.

   ![](assets/query_editor_nveau_29.png)

1. In de **[!UICONTROL Sorting]** -venster, sorteer de e-maildomeinen in aflopende volgorde. Om dit te doen, controleer **[!UICONTROL Yes]** in de **[!UICONTROL Descending sort]** kolom. Klik op **[!UICONTROL Next]**.

   ![](assets/query_editor_nveau_70.png)

1. In **[!UICONTROL Data filtering]** selecteert u **[!UICONTROL Filtering conditions]**. Ga naar de **[!UICONTROL Target elements]** venster en klik op **[!UICONTROL Next]**.
1. In de **[!UICONTROL Data grouping]** venster, selecteert u de **[!UICONTROL Email domain]** door te klikken **[!UICONTROL Add]**.

   Dit venster voor gegevensgroepering wordt alleen weergegeven als de **[!UICONTROL Handle groupings (GROUP BY + HAVING]**) is ingeschakeld.

   ![](assets/query_editor_blocklist_04.png)

1. In de **[!UICONTROL Grouping condition]** Geef een aantal primaire sleutels op dat groter is dan 30, omdat we alleen willen dat e-maildomeinen die als doel zijn ingesteld, meer dan 30 keer als resultaat worden geretourneerd.

   Dit venster verschijnt wanneer het **[!UICONTROL Manage groupings (GROUP BY + HAVING)]** selectievakje ingeschakeld: Hier wordt het groeperingsresultaat gefilterd (HAVING).

   ![](assets/query_editor_blocklist_05.png)

1. In de **[!UICONTROL Data formatting]** venster, klikt u op **[!UICONTROL Next]**: hier is geen opmaak nodig .
1. Klik in het venster met gegevensvoorvertoningen op **[!UICONTROL Launch data preview]**: hier worden drie verschillende e-maildomeinen geretourneerd die meer dan 30 keer als doel hebben.

   ![](assets/query_editor_blocklist_06.png)
