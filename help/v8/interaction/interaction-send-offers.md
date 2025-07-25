---
title: Een voorstel verzenden met Campagne-interactie
description: Meer weten over het verzenden van een voorstel?
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: d39b1768-4c39-4d64-b9b6-d9c9424a2b0d
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 2%

---

# Een voorstel verzenden{#send}

Opdat een aanbieding door de motor van de Aanbieding wordt geselecteerd, is het goedgekeurd en beschikbaar in a **Levend** milieu. [Meer informatie](interaction-offer.md#approve-offers)

Aanbiedingspresentatie via een uitgaand communicatiekanaal wordt uitgevoerd via direct mail, e-mail of mobiele leveringen. U kunt de eenheidswijze met Transactieoverseinen (het Centrum van het Bericht) ook gebruiken.

## Een voorstel invoegen in een levering {#offer-into-a-delivery}

Volg onderstaande stappen om voorstellen voor aanbiedingen in te voegen in een levering:

1. In het leveringsvenster, klik het **pictogram van Aanbiedingen**.

   ![](assets/offer_delivery_001.png)

1. Selecteer de ruimte die overeenkomt met uw aanbiedingsomgeving.

   ![](assets/offer_delivery_002.png)

1. Als u de keuze van de motor van de aanbiedingen wilt verfijnen, selecteert u de categorie waaruit de aan te bieden aanbieding(en) deel uitmaakt of een of meer thema&#39;s. We raden u aan slechts één van deze velden tegelijk te gebruiken om overbelasting van de beperkingen te voorkomen.

   ![](assets/offer_delivery_003.png)

   ![](assets/offer_delivery_004.png)

1. Geef het aantal voorstellen op dat u in de leveringstekst wilt invoegen.

   ![](assets/offer_delivery_005.png)

1. Selecteer indien nodig de optie **[!UICONTROL Exclude non-eligible recipients]** . [Meer informatie](#parameters-for-calling-offer-engine)

   ![](assets/offer_delivery_006.png)

1. Selecteer zo nodig de optie **[!UICONTROL Do not display anything if no offers are selected]** . [Meer informatie](#parameters-for-calling-offer-engine)

   ![](assets/offer_delivery_007.png)

1. Voeg de eigenschappen in de leveringsinhoud in met behulp van de samenvoegvelden. Het aantal beschikbare voorstellen hangt van de manier af de motorvraag wordt gevormd en hun orde hangt van de prioriteit van aanbiedingen af.

   ![](assets/offer_delivery_008.png)

1. Voltooi de inhoud, test en verzend uw levering.

   ![](assets/offer_delivery_010.png)


### Parameters van de Offertenmotor {#parameters-for-calling-offer-engine}

* **[!UICONTROL Space]**: ruimte van de aanbiedingsomgeving die moet worden geselecteerd om de engine voor voorstellen te activeren.
* **[!UICONTROL Category]** : specifieke map waarin aanbiedingen worden gesorteerd. Als er geen categorie is opgegeven, worden alle aanbiedingen in de omgeving in aanmerking genomen door de Offertenengine, tenzij er een thema is geselecteerd.
* **[!UICONTROL Themes]**: sleutelwoorden die stroomopwaarts in de categorieën worden gedefinieerd. Deze fungeren als een filter en u kunt het aantal aanbiedingen dat moet worden weergegeven, verfijnen door ze in een set categorieën te selecteren.
* **[!UICONTROL Number of propositions]**: het aantal aanbiedingen dat door de engine wordt geretourneerd en dat in de hoofdtekst van de levering kan worden ingevoegd. Als zij niet in het bericht worden opgenomen, zullen de aanbiedingen nog worden geproduceerd, maar niet voorgesteld.
* **[!UICONTROL Exclude non-eligible recipients]**: met deze optie kunt u de uitsluiting activeren of deactiveren van ontvangers voor wie er onvoldoende geschikte voorstellen zijn. Het aantal in aanmerking komende voorstellen kan lager zijn dan het gevraagde aantal voorstellen. Als deze doos wordt gecontroleerd, zullen de ontvangers die niet genoeg voorstellen hebben van de levering worden uitgesloten. Als u deze optie niet selecteert, worden deze ontvangers niet uitgesloten, maar hebben ze niet het gewenste aantal voorstellen.
* **[!UICONTROL Do not display anything if no offer is selected]** : met deze optie kunt u kiezen hoe het bericht wordt verwerkt als een van de voorstellen niet bestaat. Als dit selectievakje is ingeschakeld, wordt de representatie van het ontbrekende voorstel niet weergegeven en wordt er geen inhoud weergegeven in het bericht voor dit voorstel. Als de doos niet wordt gecontroleerd, wordt het bericht zelf geannuleerd tijdens het verzenden en de ontvangers zullen geen berichten meer ontvangen.

## Aanbiedingen verzenden in workflows{#offer-via-wf}

Met behulp van verschillende workflowactiviteiten kunt u bepalen hoe aanbiedingen worden weergegeven:

* Verrijking
* Aanbiedingsengine
* Aanbiedingen per cel

### Verrijking {#enrichment}

De **Verrijking** activiteit laat u aanbiedingen of verbindingen aan aanbiedingen voor leveringsontvangers toevoegen.[Meer informatie](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=nl-NL){target="_blank"}.

Bijvoorbeeld, kunt u de gegevens voor een ontvankelijke vraag vóór een levering verrijken.

![](assets/int_enrichment_offer1.png)

Er zijn twee methoden om voorstellen voor aanbiedingen op te geven.

* Het specificeren van een aanbieding of een de motorvraag van de Aanbieding.
* Verwijzen naar een koppeling naar een aanbieding.

#### Geef een aanbieding of een oproep aan de Offertenmotor op {#specifying-an-offer-or-a-call-to-the-offer-engine}

Na het vormen van uw **Vraag** activiteit:

1. Voeg en open een **Verrijking** activiteit toe.
1. Selecteer op het tabblad **[!UICONTROL Enrichment]** de optie **[!UICONTROL Add data]** .
1. Selecteer **[!UICONTROL An offer proposition]** in de typen gegevens die u wilt toevoegen.

   ![](assets/int_enrichment_offer2.png)

1. Geef een id en een label op voor het voorstel dat wordt toegevoegd.
1. Geef de selectie van de aanbieding op. Hiervoor zijn twee opties mogelijk:

   * **[!UICONTROL Search for the best offer in a category]**: controleer deze optie en specificeer de parameters van de de vraagvraag van de motor van de Aanbieding (aanbieding ruimte, categorie of thema(s), contactdatum, aantal aan te houden aanbiedingen). De motor berekent automatisch de aanbieding(en) die volgens deze parameters moet worden toegevoegd. U wordt aangeraden het veld **[!UICONTROL Category]** of **[!UICONTROL Theme]** in te vullen en niet beide tegelijk.

     ![](assets/int_enrichment_offer3.png)

   * **[!UICONTROL A pre-defined offer]**: controleer deze optie en specificeer een aanbiedingsruimte, een specifieke aanbieding, en een contactdatum om de aanbieding direct te vormen die u, zonder de motor van de Aanbieding te roepen wilt toevoegen.

     ![](assets/int_enrichment_offer4.png)

1. Dan vorm een leveringsactiviteit die aan uw gekozen kanaal beantwoordt. [Meer informatie](#offer-into-a-delivery)

   >[!NOTE]
   >
   >Het aantal voorstellen dat beschikbaar is voor de voorvertoning is afhankelijk van de configuratie die wordt uitgevoerd in de verrijkingsactiviteit in plaats van een mogelijke configuratie die rechtstreeks in de levering wordt uitgevoerd.

#### Verwijzen naar een link naar een aanbieding {#referencing-a-link-to-an-offer}

U kunt een verbinding aan een aanbieding in een **Verrijking** activiteit ook van verwijzingen voorzien.

Hiervoor voert u de volgende stappen uit:

1. Selecteer **[!UICONTROL Add data]** op het tabblad **[!UICONTROL Enrichment]** van de activiteit.
1. Selecteer **[!UICONTROL A link]** in het venster waarin u het type gegevens kiest dat u wilt toevoegen.
1. Selecteer het type koppeling dat u wilt maken en het doel ervan. In dit geval is het doel het aanbiedingsschema.

   ![](assets/int_enrichment_link1.png)

1. Specificeer zich tussen de binnenkomende lijstgegevens in de verrijkingsactiviteit (hier de ontvankelijke lijst) en de aanbiedingstabel aan. U kunt bijvoorbeeld een aanbiedingscode koppelen aan een ontvanger.

   ![](assets/int_enrichment_link2.png)

1. Dan vorm een leveringsactiviteit die aan uw gekozen kanaal beantwoordt. [Meer informatie](#offer-into-a-delivery)

   >[!NOTE]
   >
   >Het aantal voorvertoningen dat beschikbaar is voor de voorvertoning, is afhankelijk van de configuratie die in de levering wordt uitgevoerd.

#### Waarden en gewichten voor aanbiedingen in de winkel {#storing-offer-rankings-and-weights}

Door gebrek, wanneer een **Verrijking** activiteit wordt gebruikt om aanbiedingen te leveren, worden hun classificaties en hun gewichten niet opgeslagen in de propositielijst.

>[!NOTE]
>
>Deze informatie wordt standaard opgeslagen door de activiteit **[!UICONTROL Offer engine]** .

U kunt deze gegevens echter als volgt opslaan:

1. Creeer een vraag aan de motor van de Aanbieding in een verrijkingsactiviteit die na een vraag en vóór een leveringsactiviteit wordt geplaatst. [Meer informatie](#specifying-an-offer-or-a-call-to-the-offer-engine)
1. Selecteer **[!UICONTROL Edit additional data...]** in het hoofdvenster van de activiteit.

   ![](assets/ita_enrichment_rankweight_1.png)

1. Voeg de kolommen **[!UICONTROL @rank]** toe voor de positie en **[!UICONTROL @weight]** voor het gewicht van de aanbieding.

   ![](assets/ita_enrichment_rankweight_2.png)

1. Bevestig uw toevoeging en sla uw workflow op.

De levering slaat automatisch de rangschikking en het gewicht van de aanbiedingen op. Deze informatie is zichtbaar op het tabblad **[!UICONTROL Offers]** van de levering.

### Aanbiedingsengine {#offer-engine}

Met de activiteit **[!UICONTROL Offer engine]** kunt u ook een aanroep naar de engine voor voorstellen opgeven voordat de levering plaatsvindt.

Voor meer op de **motor van de Aanbieding** activiteit, verwijs naar [ deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/offer-engine.html?lang=nl-NL){target="_blank"}.

Deze activiteit werkt op het zelfde beginsel zoals de **Verrijking** activiteit met een motorvraag, door de binnenkomende bevolkingsgegevens met een aanbieding te verrijken die door de motor wordt berekend, vóór een levering.

![](assets/int_offerengine_activity2.png)

Na het vormen van uw **Vraag** activiteit:

1. Voeg een **[!UICONTROL Offer engine]** -activiteit toe en open deze.
1. Vul de verschillende beschikbare velden in om de oproep tot het indienen van voorstellen voor motorparameters op te geven (ruimte, categorie of thema(&#39;s), contactdatum, aantal aanbiedingen dat u wilt behouden). De motor berekent automatisch de aanbieding(en) die volgens deze parameters moet worden toegevoegd.

   >[!CAUTION]
   >
   >Als u deze activiteit gebruikt, zullen slechts de aanbiedingsvoorstellen die in de levering worden gebruikt worden opgeslagen.

   ![](assets/int_offerengine_activity1.png)

1. Dan vorm een leveringsactiviteit die aan uw gekozen kanaal beantwoordt. [Meer informatie](#inserting-an-offer-proposition-into-a-delivery)

### Aanbiedingen per cel {#offers-by-cell}

Met de activiteit **[!UICONTROL Offers by cell]** kunt u de binnenkomende populatie (bijvoorbeeld van een query) in verschillende segmenten verdelen en een aanbieding opgeven om voor elk van deze segmenten voor te stellen.

Voor meer op de **Aanbieding door cel** activiteit, verwijs naar [ deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/offers-by-cell.html?lang=nl-NL){target="_blank"}.

Hiervoor gebruikt u het volgende proces:

1. Voeg de **[!UICONTROL Offers by cell]** activiteit toe zodra u de doelpopulatie hebt gespecificeerd, dan open het.
1. Selecteer op het tabblad **[!UICONTROL General]** de aanbiedingsruimte waarop u de aanbiedingen wilt weergeven.
1. Geef op het tabblad **[!UICONTROL Cells]** de verschillende subsets op met de knop **[!UICONTROL Add]** :

   * Geef de subsetpopulatie op met behulp van de beschikbare regels voor filteren en beperken.
   * Selecteer vervolgens het voorstel dat u aan de subset wilt presenteren. De beschikbare aanbiedingen zijn die welke in aanmerking komen op het aanbiedingsmilieu dat in de vorige stap werd geselecteerd.

     ![](assets/int_offer_per_cell1.png)

1. Dan vorm een leveringsactiviteit die aan uw gekozen kanaal beantwoordt.

<!--

## Delivering with delivery outlines {#delivering-with-delivery-outlines}

You can also present offers in a delivery using delivery outlines.

For more information on delivery outlines, refer to the Campaign - MRM guide.

1. Create a new campaign or access an existing campaign.
1. Access the delivery outlines via the campaign's **[!UICONTROL Edit]** > **[!UICONTROL Documents]** tab.
1. Add an outline then insert as many offers as you like into it by right-clicking on the outline and selecting **[!UICONTROL New]** > **[!UICONTROL Offer]**, then save the campaign.


1. Create a delivery whose delivery outlines you have access to (for example, a direct mail delivery).
1. When editing the delivery, click **[!UICONTROL Select a delivery outline]**.

   >[!NOTE]
   >
   >Depending on the type of delivery, this option can be found in the **[!UICONTROL Properties]** > **[!UICONTROL Advanced]** menu (for email deliveries for example).


1. Using the **[!UICONTROL Offers]** button, you can then configure the offer space as well as the number of offers to present in the delivery.


1. Add the propositions into the delivery body using the personalization fields (for more on this, refer to the [Inserting an offer proposition into a delivery](#inserting-an-offer-proposition-into-a-delivery) section), or in the case of a direct mail delivery, by editing the extraction file format.

   Propositions will be selected from the offers referenced in the delivery outline.

   >[!NOTE]
   >
   >Information regarding the offer rankings and weights is only saved in the proposition table if the offers are generated directly in the delivery.
-->
