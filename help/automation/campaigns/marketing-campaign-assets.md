---
product: campaign
title: Marketingcampagne-elementen, -documenten en -leveringscontouren
description: Meer informatie over marketingcampagnedocumenten en leveringscontouren
feature: Campaigns
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# Elementen en documenten beheren {#manage-assets-documents}

U kunt verschillende documenten aan een campagne koppelen: rapporten, foto&#39;s, webpagina&#39;s, diagrammen, enz. Deze documenten kunnen elke gewenste indeling hebben.

In een campagne kunt u ook andere objecten bekijken, zoals promotiecoupons, speciale aanbiedingen voor een bepaald merk of een bepaalde winkel, enzovoort. Wanneer deze elementen in een overzicht worden opgenomen, kunnen zij met een directe postlevering worden geassocieerd. [Meer informatie](#associating-and-structuring-resources-linked-via-a-delivery-outline).


>[!CAUTION]
>
>Deze functie is ontworpen voor kleine elementen en documenten.

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## Documenten toevoegen {#add-documents}

Documenten kunnen worden gekoppeld op campagneniveau (contextuele documenten) of op programmaniveau (algemene documenten).

Voor een campagne **[!UICONTROL Documents]** bevat:

* De lijst met alle documenten die vereist zijn voor de inhoud (sjabloon, afbeeldingen, enz.) die door Adobe Campaign-operatoren met de juiste rechten lokaal kunnen worden gedownload,
* Documenten die informatie voor de router bevatten, als om het even welk.

De documenten houden verband met het programma of de campagne via de **[!UICONTROL Edit > Documents]** tab.

![](assets/op_add_document.png)

U kunt ook een document aan een campagne toevoegen vanuit de toegewezen koppeling in het dashboard.

![](assets/add_a_document_in_op.png)

Klik op de knop **[!UICONTROL Detail...]** pictogram om de inhoud van een bestand weer te geven en informatie toe te voegen:

![](assets/add_document_details.png)

In het dashboard worden de documenten die bij de campagne horen gegroepeerd in de **[!UICONTROL Document(s)]** , zoals in het volgende voorbeeld:

![](assets/edit_documents.png)

U kunt ze ook vanuit deze weergave bewerken en wijzigen.

## Leveringscontouren gebruiken {#delivery-outlines}

Een overzicht van de levering bestaat uit gestructureerde elementen (documenten, winkels, promotionele coupons, enz.) door het bedrijf en voor een bepaalde campagne worden opgericht. Het wordt gebruikt in de context van direct-mailleveringen.

Deze elementen worden gegroepeerd in leveringsoverzichten, en elk leveringsoverzicht zal met een levering worden geassocieerd; er wordt naar verwezen in het extractiebestand dat naar de **serviceprovider** om bij de levering te worden gevoegd. U kunt bijvoorbeeld een leveringsoverzicht maken dat verwijst naar een eenheid en de marketingbrochures die worden gebruikt.

Voor een campagne, laten de leveringsoverzichten u externe elementen structureren die met de levering volgens bepaalde criteria moeten worden geassocieerd: verwante eenheid, aangeboden promotieaanbieding, uitnodiging voor een plaatselijke manifestatie, enz.

>[!CAUTION]
>
>De contouren van de levering zijn beperkt tot direct-mailcampagnes.

### Een leveringsoverzicht maken {#create-an-outline}

Klik op de knop **[!UICONTROL Delivery outlines]** subtab in het dialoogvenster **[!UICONTROL Edit > Documents]** tabblad van de desbetreffende campagne.

![](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>Als dit tabblad niet wordt weergegeven, is deze functie niet beschikbaar voor deze campagne of is de directe verzending niet ingeschakeld in uw exemplaar. Zie de [campagneresjabloonconfiguratie](marketing-campaign-templates.md#campaign-templates) of op uw licentieovereenkomst.

Klik op Volgende **[!UICONTROL Add a delivery outline]** en maak de hiërarchie van contouren voor de campagne:

1. Klik met de rechtermuisknop op de basis van de structuur en selecteer **[!UICONTROL New > Delivery outlines]**.
1. Klik met de rechtermuisknop op de omtrek die u zojuist hebt gemaakt en selecteer **[!UICONTROL New > Item]** of **[!UICONTROL New > Personalization fields]**.

![](assets/del-outline-add-new-item.png)

Een overzicht kan punten, verpersoonlijkingsgebieden, en aanbiedingen bevatten:

* Items kunnen bijvoorbeeld fysieke documenten zijn waarnaar hier wordt verwezen en die hier worden beschreven en die aan de levering worden gekoppeld.
* Met velden voor personalisatie kunt u personalisatie-elementen maken die te maken hebben met leveringen in plaats van met ontvangers. Het is dus mogelijk waarden te creëren die in leveringen voor een specifiek doel moeten worden gebruikt (welkomstaanbod, korting, enz.) Ze zijn gemaakt in Adobe Campaign en geïmporteerd in de omtrek via de **[!UICONTROL Import personalization fields...]** koppeling.

   ![](assets/del-outline-perso-field.png)

   Ze kunnen ook rechtstreeks in de omtrek worden gemaakt door op de knop **[!UICONTROL Add]** rechts van de lijstzone.

   ![](assets/add-del-outline-button.png)


### Een omtrek selecteren {#select-an-outline}

Voor elke levering, kunt u het overzicht selecteren om van de sectie te associëren die voor het extractieoverzicht wordt gereserveerd, zoals in het volgende voorbeeld:

![](assets/select-delivery-outline.png)

De geselecteerde omtrek wordt vervolgens weergegeven in de onderste sectie van het venster. U kunt de afbeelding bewerken met het pictogram rechts van het veld of wijzigen met de vervolgkeuzelijst:

![](assets/delivery-outline-selected.png)

De **[!UICONTROL Summary]** tabblad van de levering geeft ook deze informatie weer:

![](assets/delivery-outline-in-dashboard.png)

### Extractieresultaat {#extraction-result}

In het dossier dat wordt uitgepakt en aan de dienstverlener wordt toegezonden, de naam van de omtrek en, in voorkomend geval, de kenmerken ervan (kosten, beschrijving enz.) worden toegevoegd aan de inhoud volgens de informatie in het uitvoermalplaatje verbonden aan de dienstverlener.

In het volgende voorbeeld worden het label, de geschatte kosten en de beschrijving van de omtrek die aan de levering is gekoppeld, toegevoegd aan het extractiebestand.

![](assets/campaign-export-template.png)

Het exportmodel moet worden gekoppeld aan de dienstverlener die voor de betrokken levering is geselecteerd. Zie [deze sectie](providers--stocks-and-budgets.md#creating-service-providers-and-their-cost-structures).
