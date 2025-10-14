---
title: Aanbieding voor campagneinteractie
description: Meer weten over het maken van een aanbieding?
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 4dc2008d-681c-4a79-8fc8-c270c9224ab9
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 3%

---

# Een aanbieding maken

Volg onderstaande stappen om een voorstel te maken:

1. Blader naar het tabblad **[!UICONTROL Campaigns]** en klik op de koppeling **[!UICONTROL Offers]** .

1. Klik op de knop **[!UICONTROL Create]**.

1. Wijzig het label en selecteer de categorie waartoe de aanbieding moet behoren.

1. Klik op **[!UICONTROL Save]** om de aanbieding te maken.

   De aanbieding is beschikbaar in het platform en zijn inhoud kan worden gevormd.

## Geschiktheidsinstellingen

U kunt nu het tabblad **[!UICONTROL Eligibility]** gebruiken om te definiëren:

* De subsidiabiliteitsperiode van de aanbieding. [Meer informatie](#eligibility-period)
* Filters op de doelpopulatie van de aanbieding. [Meer informatie](#filters-on-the-target)
* Het gewicht van het voorstel. [Meer informatie](#offer-weight)

### verkiesbaarheidsperiode voorstellen{#eligibility-period}

Definieer op het tabblad **[!UICONTROL Eligibility]** van de aanbieding de periode waarin de aanbieding in aanmerking komt. gebruikt u de vervolgkeuzelijsten om een begin- en einddatum in de kalender te selecteren.

![](assets/offer_eligibility_create_002.png)

Buiten deze periode wordt het voorstel niet geselecteerd. Als u ook de toelatingsdata voor de categorie van aanbiedingen hebt gevormd, zal de meest beperkende periode van toepassing zijn.

### Filters toevoegen aan het doel {#filters-on-the-target}

Pas op het tabblad **[!UICONTROL Eligibility]** van de aanbieding filters toe op het doel van de aanbieding.

Klik hiertoe op de koppeling **[!UICONTROL Edit query]** en selecteer het filter dat u wilt toepassen.

![](assets/offer_eligibility_create_003.png)

Als er al vooraf gedefinieerde filters zijn gemaakt, kunt u deze selecteren in de lijst met gebruikersfilters. [Meer informatie](interaction-predefined-filters.md)

![](assets/offer_eligibility_create_004.png)

### Het gewicht van de aanbieding instellen {#offer-weight}

Om de motor in staat te stellen tussen verscheidene aanbiedingen te beslissen dat het doel verkiesbaar is, moet u één of meerdere gewichten aan de aanbieding toewijzen. U kunt filters op het doel indien nodig ook toepassen of de aanbiedingsruimte beperken waarop het gewicht van toepassing is. Een aanbod met een groter gewicht krijgt de voorkeur boven een aanbod met minder gewicht.

U kunt veelvoudige gewichten voor de zelfde aanbieding vormen, bijvoorbeeld om sup-periodes, specifieke doelstellingen of zelfs een aanbiedingsruimte te onderscheiden.

Bijvoorbeeld, kan een aanbieding een gewicht van A voor contacten hebben tussen 18 en 25 jaar en een gewicht van B voor contacten boven dat gamma. Als een aanbieding de hele zomer in aanmerking komt, kan zij ook een gewicht van A in juli en een gewicht van B in augustus hebben.

>[!NOTE]
>
>Het toegewezen gewicht kan tijdelijk worden gewijzigd op basis van de parameters van de categorie waartoe de aanbieding behoort. [Meer informatie](interaction-offer-catalog.md#creating-offer-categories)

Voer de volgende stappen uit om een dikte in een aanbieding te maken:

1. Klik in het tabblad **[!UICONTROL Eligibility]** van de aanbieding op **[!UICONTROL Add]** .

   ![](assets/offer_weight_create_001.png)

1. Wijzig het label en wijs een gewicht toe. De standaardwaarde is 1.

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >Indien geen gewicht wordt opgegeven (0), wordt het streefcijfer niet in aanmerking genomen voor de aanbieding.

1. Als u het gewicht gedurende een bepaalde periode wilt toepassen, definieert u de toelatingsdata.

   ![](assets/offer_weight_create_002.png)

1. Beperk zo nodig het gewicht tot een specifieke aanbiedingsruimte.

   ![](assets/offer_weight_create_003.png)

1. Pas een filter toe op een doel.

   ![](assets/offer_weight_create_004.png)

1. Klik op **[!UICONTROL OK]** om de dikte op te slaan.

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >Als een doel in aanmerking komt voor meerdere gewichten voor een geselecteerde aanbieding, behoudt de motor het beste (hoogste) gewicht. Bij het oproepen van de motor van de Aanbieding, wordt een voorstel geselecteerd maximaal eens per contact.

### Samenvatting van de regels inzake de subsidiabiliteit van aanbiedingen {#a-summary-of-offer-eligibility-rules}

Zodra de configuratie is voltooid, zal een samenvatting van de subsidiabiliteitsregels beschikbaar zijn op het biederdashboard.

Klik op de koppeling **[!UICONTROL Schedule and eligibility rules]** om deze weer te geven.

![](assets/offer_eligibility_create_005.png)

## De inhoud van het voorstel maken {#creating-the-offer-content}

Gebruik het tabblad **[!UICONTROL Content]** om de inhoud van de aanbieding te definiëren.

![](assets/offer_content_create_001.png)

1. Definieer de verschillende parameters van de aanbiedingsinhoud.

   * **[!UICONTROL Title]**: Geef de titel op die u wilt maken, en vermeld deze in uw voorstel. Waarschuwing: dit verwijst niet naar het label van de aanbieding, dat is gedefinieerd op het tabblad **[!UICONTROL General]** .
   * **[!UICONTROL Destination URL]**: geef de URL van je aanbieding op. Het moet beginnen met &quot;http://&quot; of &quot;https://&quot;.
   * **[!UICONTROL Image URL]** : geef een URL of een toegangspad op naar de afbeelding van uw aanbieding.
   * **[!UICONTROL HTML content]** / **[!UICONTROL Text content]** : voer de tekst van uw voorstel in op het tabblad dat u wilt gebruiken. Voor het genereren van reeksspatiëring moet **[!UICONTROL HTML content]** bestaan uit HTML-elementen die kunnen worden ingesloten in een `<div>` -tekstelement. Het resultaat van een `<table>` -element op de HTML-pagina is bijvoorbeeld als volgt:

   ```
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   Leer hoe te om acceptatie URL in [&#x200B; te bepalen deze sectie &#x200B;](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted).

   ![](assets/offer_content_create_002.png)

   Als u de vereiste velden wilt zoeken zoals deze zijn gedefinieerd tijdens de configuratie van de aanbiedingsruimte, klikt u op de koppeling **[!UICONTROL Content definitions]** om de lijst weer te geven. [Meer informatie](interaction-offer-spaces.md)

   ![](assets/offer_content_create_003.png)

   In dit voorbeeld moet de aanbieding een titel, een afbeelding, HTML-inhoud en een doel-URL bevatten.

## Voorbeeld van aanbieding bekijken {#previewing-the-offer}

Zodra de aanbiedingsinhoud wordt gevormd, kunt u voorproef de aanbieding zoals het voor zijn ontvanger zal verschijnen.

Dit doet u als volgt:

1. Klik op de tab **[!UICONTROL Preview]** .

   ![](assets/offer_preview_create_001.png)

1. Selecteer de representatie van het voorstel dat u wilt bekijken.

   ![](assets/offer_preview_create_002.png)

1. Als u de inhoud van de aanbieding hebt gepersonaliseerd, selecteer het doel van de aanbieding om personalisatie te bekijken.

<!--

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../campaign/using/about-response-manager.md).

-->

## Een aanbieding goedkeuren en activeren{#approve-offers}

U kunt de aanbieding nu goedkeuren en activeren om het in het **Levende** milieu ter beschikking te stellen.

Voor meer op dit, verwijs naar [&#x200B; de documentatie van Campaign Classic v7 &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=nl-NL#approving-offer-content){target="_blank"}.

## Presentatie van aanbieding beheren{#offer-presentation}

Met Campagne kunt u de stroom van aanbiedingsvoorstellen bepalen aan de hand van presentatieregels. Deze regels, die voor de Interactie van de Campagne specifiek zijn, zijn **typologische regels**. Hiermee kunt u aanbiedingen uitsluiten op basis van de geschiedenis van voorstellen die al aan een ontvanger zijn gedaan. Er wordt naar verwezen in de omgeving.

Voor meer op dit, verwijs naar [&#x200B; de documentatie van Campaign Classic v7 &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html?lang=nl-NL#managing-offers){target="_blank"}.

## Aanbiedingssimulatie

De **module van de Simulatie** laat u de distributie van aanbiedingen testen die tot een categorie of een milieu behoren alvorens uw voorstel naar ontvangers te verzenden.

Bij de simulatie wordt rekening gehouden met de context en de subsidiabiliteitsregels die eerder op de aanbiedingen van toepassing waren, en met hun presentatieregels. Dit laat u diverse versies van uw aanbiedingsvoorstel testen en verfijnen zonder eigenlijk een aanbieding of over/onder het eisen van een doel te gebruiken, aangezien de simulatie geen effect op de gerichte ontvangers heeft.

Voor meer op de simulatie van het Aanbod, verwijs naar [&#x200B; de documentatie van Campaign Classic v7 &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.html?lang=nl-NL){target="_blank"}.
