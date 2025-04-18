---
product: campaign
title: Contentmanagement
description: Contentmanagement
feature: Workflows, Data Management
role: User
exl-id: 9b225f78-1959-4e4f-aa4e-ff8a63051154
source-git-commit: c73f9f3dc7958152c284dbaf06210d09115e5df8
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 2%

---

# Contentmanagement{#content-management}

A **het beheer van de Inhoud** activiteit laat u een inhoud tot stand brengen en manipuleren en dossiers produceren die op deze inhoud worden gebaseerd. Deze inhoud kan vervolgens worden geleverd via een &#39;leveringsactiviteit&#39;.

>[!CAUTION]
>
>Inhoudsbeheer is een optionele Adobe Campaign-module. Controleer hiervoor uw licentieovereenkomst.

>[!NOTE]
>
>Met de Adobe Campaign Web User Interface kunt u inhoudsfragmenten gebruiken voor uw inhoud. Op deze manier kunnen marketinggebruikers meerdere blokken aangepaste inhoud vooraf samenstellen, dankzij herbruikbare componenten waarnaar in een of meer berichten kan worden verwezen, zodat u de inhoud van berichten snel kunt samenstellen in een verbeterd ontwerpproces. Meer over de fragmenten van de Inhoud leren, gelieve te verwijzen naar de [ documentatie van het Web van Adobe Campaign UI.](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments){target=_blank}

De eigenschappen van de activiteit zijn verdeeld in drie stappen:

* **selectie van de Inhoud**: de inhoud kan eerder zijn gecreeerd of via de activiteit kunnen worden gecreeerd.
* **de update van de Inhoud**: de taak kan het onderwerp van de inhoud wijzigen of alle inhoud van XML invoeren.
* **Actie**: de resulterende inhoud kan worden bewaard of worden geproduceerd.

  ![](assets/content_mgmt_edit.png)

1. **Inhoud**

   * **[!UICONTROL Specified in the transition]**

     Met deze optie kunt u de inhoud gebruiken die is opgegeven in de overgang, dat wil zeggen de gebeurtenis die inhoudsbeheer activeert, moet een variabele **[!UICONTROL contentId]** bevatten. Deze variabele kan door een vorig inhoudsbeheer of door om het even welk manuscript zijn geplaatst.

   * **[!UICONTROL Explicit]**

     Met deze optie kunt u reeds gemaakte inhoud selecteren via het veld **[!UICONTROL Content]** . Dit veld is alleen zichtbaar wanneer de optie **[!UICONTROL Explicit]** is geselecteerd.

     ![](assets/content_mgmt_explicit.png)

   * **[!UICONTROL Calculated by a script]**

     De inhoud-id wordt berekend door een script. In het veld **[!UICONTROL Script]** kunt u een JavaScript-sjabloon definiëren waarmee de id (primaire sleutel) van de inhoud wordt geëvalueerd. Dit veld is alleen zichtbaar wanneer de optie **[!UICONTROL Calculated by a script]** is geselecteerd.

     ![](assets/content_mgmt_script.png)

   * **[!UICONTROL New, created from a publication template]**

     Hiermee maakt u nieuwe inhoud op basis van een publicatiesjabloon. Deze nieuwe inhoud wordt opgeslagen in het bestand dat is opgegeven in het veld **[!UICONTROL String]** . In het veld **[!UICONTROL Template]** wordt de publicatiesjabloon opgegeven die moet worden gebruikt om de inhoud te maken.

     ![](assets/content_mgmt_new.png)

1. **inhoud van de Update**

   * **[!UICONTROL Subject]**

     In dit veld kunt u het onderwerp van de inhoud wijzigen.

   * **[!UICONTROL Access to data from an XML feed]**

     Met deze optie kunt u de inhoud samenstellen op basis van een XML-document dat via een XSL-stijlpagina is gedownload. Wanneer deze optie is geselecteerd, geeft het veld **[!UICONTROL URL]** de URL op voor het downloaden van XML-inhoud. Met **[!UICONTROL XSL stylesheet]** kunt u de stijlpagina opgeven die moet worden gebruikt om het gedownloade XML-document te transformeren. Deze eigenschap is optioneel.

     ![](assets/content_mgmt_xmlcontent.png)

1. **uit te voeren Actie**

   * **[!UICONTROL Save]**

     Met deze optie slaat u de gemaakte of gewijzigde inhoud op.

     De uitgaande overgang wordt slechts eenmaal geactiveerd, waarbij de inhoud in de variabele **[!UICONTROL contentId]** als parameter wordt opgeslagen.

   * **[!UICONTROL Generate]**

     Met deze optie slaat u de inhoud op en genereert u vervolgens de uitvoerbestanden voor elke transformatiesjabloon met een publicatie van het type &#39;Bestand&#39;.

     ![](assets/content_mgmt_generate.png)

     De uitgaande overgang wordt geactiveerd voor elk bestand dat wordt gegenereerd met de id van de inhoud die in de variabele **[!UICONTROL contentId]** is opgeslagen als parameter en de bestandsnaam in de variabele **[!UICONTROL filename]** .

## Invoerparameters {#input-parameters}

* contentId

Identifier van de inhoud die moet worden gebruikt als de optie **[!UICONTROL Specified in the transition]** is ingeschakeld.

## Uitvoerparameters {#output-parameters}

* contentId

  Inhoud-id.

* filename

  Volledige naam van het gegenereerde bestand als de geselecteerde actie **[!UICONTROL Generate]** is.
