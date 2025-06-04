---
product: campaign
title: Een berekend veld voor het type opsomming toevoegen
description: Leer hoe u een berekend veld voor het type opsomming toevoegt
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 4fe2ae81-faa6-4777-a332-70c451bca75b
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Een berekend veld voor het type opsomming toevoegen {#adding-an-enumeration-type-calculated-field}

Hier willen we een query maken met een berekend veld van het type **[!UICONTROL Enumerations]** . Met dit veld wordt een extra kolom gegenereerd in het venster met de gegevensvoorvertoning. Deze kolom zal de numerieke waarden specificeren die als resultaat voor elke ontvanger (0, 1 en 2) zijn teruggekeerd. Aan elke waarde in de nieuwe kolom wordt een geslacht toegewezen: &quot;Mannelijk&quot; voor &quot;1&quot;, &quot;Vrouwelijk&quot; voor &quot;2&quot; of &quot;Niet aangegeven&quot; als de waarde gelijk is aan &quot;0&quot;.

* Welke tabel moet worden geselecteerd?

  De tabel met ontvangers (nms:ontvanger)

* Te selecteren velden in de uitvoerkolom?

  Achternaam, voornaam, geslacht

* Aan welke criteria wordt de informatie gefilterd?

  De taal van de ontvanger

Voer de volgende stappen uit:

1. Open de Algemene vraagredacteur en selecteer de Ontvangerlijst (**[!UICONTROL nms:recipient]**).
1. Selecteer **[!UICONTROL Last name]** , **[!UICONTROL First name]** en **[!UICONTROL Gender]** in het **[!UICONTROL Data to extract]** -venster.

   ![](assets/query_editor_nveau_73.png)

1. Klik in het **[!UICONTROL Sorting]** -venster op **[!UICONTROL Next]** : voor dit voorbeeld is geen sortering nodig.
1. In **[!UICONTROL Data filtering]** selecteert u **[!UICONTROL Filtering conditions]**.
1. Stel in het venster **[!UICONTROL Target element]** een filtervoorwaarde in om ontvangers die Engels spreken, te verzamelen.

   ![](assets/query_editor_nveau_74.png)

1. Klik in het **[!UICONTROL Data formatting]** -venster op **[!UICONTROL Add a calculated field]** .

   ![](assets/query_editor_nveau_75.png)

1. Ga naar het **[!UICONTROL Type]** -venster van het **[!UICONTROL Export calculated field definition]** -venster en selecteer **[!UICONTROL Enumerations]** .

   Definieer de kolom waarnaar het nieuwe berekende veld moet verwijzen. Selecteer hiertoe de kolom **[!UICONTROL Gender]** in het vervolgkeuzemenu van het veld **[!UICONTROL Source column]** . De doelwaarden komen overeen met de kolom **[!UICONTROL Gender]** .

   ![](assets/query_editor_nveau_76.png)

   Bepaal de **Source** en **3} waarden van de Bestemming: de bestemmingswaarde maakt het vraagresultaat gemakkelijker te lezen.** Deze vraag zou ontvankelijk geslacht moeten terugkeren en het resultaat zal of 0, 1, of 2 zijn.

   Voor elke &quot;bron-bestemming&quot;lijn die moet worden ingegaan, klik **[!UICONTROL Add]** in **[!UICONTROL List of enumeration values]**:

   * Voer in de kolom **[!UICONTROL Source]** de bronwaarde voor elk geslacht (0,1,2) in een nieuwe regel in.
   * Voer in de kolom **[!UICONTROL Destination]** de waarden in: &quot;Niet aangegeven&quot; voor regel &quot;0&quot;, &quot;Mannelijk&quot; voor regel &quot;1&quot; en &quot;Vrouwelijk&quot; voor regel &quot;2&quot;.

   Selecteer de functie **[!UICONTROL Keep the source value]** .

   Klik op **[!UICONTROL OK]** om het berekende veld goed te keuren.

   ![](assets/query_editor_nveau_77.png)

1. Klik in het **[!UICONTROL Data formatting]** -venster op **[!UICONTROL Next]** .
1. **[!UICONTROL start the preview of the data]** in het voorvertoningsvenster.

   De aanvullende kolom definieert het geslacht van 0, 1 en 2:

   * 0 voor &quot;Niet aangegeven&quot;
   * 1 voor &quot;Mannelijk&quot;
   * 2 voor &quot;Vrouwelijk&quot;

   ![](assets/query_editor_nveau_78.png)

   Als u bijvoorbeeld geen geslacht &quot;2&quot; opgeeft in het veld **[!UICONTROL List of enumeration values]** en de functie **[!UICONTROL Generate a warning and continue]** van het veld **[!UICONTROL In other cases]** is geselecteerd, wordt een waarschuwingslogboek weergegeven. Dit logbestand geeft aan dat geslacht &quot;2&quot; (vrouwelijk) niet is ingevoerd. Deze wordt weergegeven in het veld **[!UICONTROL Logs generated during export]** van het venster met de gegevensvoorvertoning.

   ![](assets/query_editor_nveau_79.png)

   Neem een ander voorbeeld en zeg dat de opsommingswaarde &quot;2&quot;niet is ingegaan. Selecteer de functie **[!UICONTROL Generate an error and reject the line]** : alle geslachten met &quot;2&quot;-ontvangers veroorzaken anomalieën en de andere gegevens op de regel (voornaam en achternaam, enz.) worden niet geëxporteerd. Er wordt een foutenlogboek weergegeven in het veld **[!UICONTROL Logs generated during export]** van het venster met de gegevensvoorvertoning. Dit logboek wijst erop dat de opsommingswaarde &quot;2&quot;niet ingegaan is.

   ![](assets/query_editor_nveau_80.png)
