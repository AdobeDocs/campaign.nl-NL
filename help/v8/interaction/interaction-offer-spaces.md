---
title: Spaties voor aanbiedingen voor Campagne
description: Meer informatie over het maken van aanbiedingsruimten
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 1%

---

# Plaatsingen voor aanbiedingen maken{#creating-offer-spaces}

De inhoud van de aanbiedingscatalogus wordt geconfigureerd in aanbiedingsruimten. Standaard kan de inhoud de volgende velden bevatten: **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** en **[!UICONTROL Text content]** . De gebiedsopeenvolging wordt gevormd in de aanbiedingsruimte.

Als a **technische beheerder**, kunt u aanbiedingsruimten in het milieu van het Ontwerp tot stand brengen. U moet toegang hebben tot de submap voor de aanbiedingsruimte. Nadat deze aanbiedingsruimten zijn gemaakt, worden deze automatisch gedupliceerd naar de live omgeving tijdens de goedkeuring van de aanbieding.

De HTML-rendering wordt gemaakt via een renderfunctie. De volgorde van de velden die in de renderfunctie zijn gedefinieerd, moet gelijk zijn aan de volgorde die in de inhoud is geconfigureerd.

![](assets/offer_space_create_009.png)

Volg onderstaande stappen om een nieuwe aanbiedingsruimte te maken:

1. Klik in de lijst met aanbiedingsruimten op **[!UICONTROL New]** .

   ![](assets/offer_space_create_001.png)

1. Selecteer het kanaal u wilt gebruiken en het etiket van de aanbiedingsruimte veranderen.

   ![](assets/offer_space_create_002.png)

1. Controleer de optie **[!UICONTROL Enable unitary mode]**

1. Ga naar het **[!UICONTROL Content field]** -venster en klik op **[!UICONTROL Add]** .

   ![](assets/offer_space_create_003.png)

1. Ga naar het knooppunt **[!UICONTROL Content]** en selecteer de velden in de volgende volgorde: **[!UICONTROL Title]** , then **[!UICONTROL Image URL]** , then **[!UICONTROL HTML content]** en then **[!UICONTROL Destination URL]** .

   ![](assets/offer_space_create_004.png)

1. Schakel de optie **[!UICONTROL Required]** in om elk veld verplicht te maken.

   >[!NOTE]
   >
   >Deze optie wordt gebruikt bij de voorvertoning en maakt de aanbiedingsruimten ongeldig wanneer u publiceert als een van de verplichte velden in de aanbieding ontbreekt. Als een aanbieding echter al live is op een aanbiedingsruimte, worden deze criteria niet in aanmerking genomen.

   ![](assets/offer_space_create_005.png)

1. Klik op **[!UICONTROL Edit functions]** om een renderfunctie te maken.

   Deze functies worden gebruikt om aanbiedingsvertegenwoordiging op een aanbiedingsruimte te produceren. Er zijn verschillende mogelijke indelingen: HTML of tekst.

   **Nota** - het formaat van XML is beperkt tot binnenkomende interactie die in deze versie van het product niet beschikbaar zijn. [Meer informatie](../start/v7-to-v8.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. Ga naar de tab **[!UICONTROL HTML rendering]** en selecteer **[!UICONTROL Overload the HTML rendering function]** .
1. Voeg uw renderfunctie in.

   ![](assets/offer_space_create_007.png)

## Voorzettingsstatussen voorstellen {#offer-proposition-statuses}

De status van het voorstel varieert afhankelijk van de interactie met de doelpopulatie. De module van de Interactie van de campagne komt met een reeks waarden die op het aanbiedingsvoorstel tijdens zijn levenscyclus kunnen worden toegepast. U moet het platform vormen zodat de status verandert wanneer het aanbiedingsvoorstel wordt gecreeerd en wordt goedgekeurd.

>[!NOTE]
>
>De update van de status is een **asynchroon** proces. Deze wordt uitgevoerd door de workflow voor het bijhouden van gegevens, die elk uur wordt geactiveerd.

### Statuslijst voorstel {#status-list}

De volgende statussen voor beschikbare aanbiedingen zijn beschikbaar:

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

Deze waarden worden niet standaard toegepast: ze moeten worden geconfigureerd.

>[!NOTE]
>
>De status van een aanbiedingsvoorstel wordt automatisch gewijzigd in &quot;Presenteerd&quot; als de aanbieding gekoppeld is aan een levering met de status &quot;Verzonden&quot;.

### De status van de aanbieding wanneer het voorstel wordt gecreeerd {#configuring-the-status-when-the-proposition-is-created}

Wanneer een aanbiedingsvoorstel **&#x200B;**&#x200B;wordt gecreeerd, wordt zijn status bijgewerkt.

In het **[!UICONTROL Design]** milieu, voor elke aanbiedingsruimte, vorm de status om van toepassing te zijn wanneer een voorstel wordt gecreeerd, afhankelijk van de informatie u in de aanbiedingsrapporten wilt tonen.

Hiervoor voert u de volgende stappen uit:

1. Ga naar het tabblad **[!UICONTROL Storage]** van de gewenste ruimte.
1. Selecteer de status die u wilt toepassen op het voorstel wanneer het wordt gemaakt.

   ![](assets/offer_update_status_001.png)

### De status van de aanbieding wanneer het voorstel wordt aanvaard {#configuring-the-status-when-the-proposition-is-accepted}

Zodra een aanbiedingsvoorstel **&#x200B;**&#x200B;is goedgekeurd, gebruik één van de waarden die door gebrek worden verstrekt om de nieuwe status van het voorstel te vormen. De update wordt toegepast wanneer een ontvanger op een koppeling in de aanbieding klikt.

Hiervoor voert u de volgende stappen uit:

1. Ga naar het tabblad **[!UICONTROL Storage]** van de gewenste ruimte.
1. Selecteer de status die u op het voorstel wilt toepassen wanneer het wordt goedgekeurd.

   ![](assets/offer_update_status_002.png)


**Binnenkomende interactie**

Het **[!UICONTROL Storage]** lusje laat u statussen voor **voorgestelde** bepalen en **toegelaten** aanbiedingsvoorstellen slechts. Voor binnenkomende interactie, zou de status van aanbiedingsvoorstellen direct in URL voor het roepen van de motor van de Aanbieding, eerder dan door de interface moeten worden gespecificeerd. Op deze manier kunt u opgeven welke status in andere gevallen moet worden toegepast, bijvoorbeeld wanneer een voorstel voor een aanbieding wordt afgewezen.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

Bijvoorbeeld, bevat het voorstel (herkenningsteken **40004**) dat de **Verzekerings** aanbieding van het Huis aanpast die op de **Neobank** plaats wordt getoond volgende URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

Zodra een bezoeker de aanbieding klikt, en daarom URL, wordt de **[!UICONTROL Accepted]** status (waarde **3**) toegepast op het voorstel en de bezoeker wordt opnieuw gericht aan een nieuwe pagina van de **Neobank** plaats om het verzekeringscontract uit te nemen.

>[!NOTE]
>
>Als u een andere status in de URL wilt opgeven (bijvoorbeeld als een aanbiedingsvoorstel wordt afgewezen), gebruikt u de waarde die overeenkomt met de gewenste status. Voorbeeld: **[!UICONTROL Rejected]** = &quot;5&quot;, **[!UICONTROL Presented]** = &quot;1&quot; enzovoort.
>
>Statussen en hun waarden kunnen worden opgehaald in het **[!UICONTROL Offer propositions (nms)]** gegevensschema. Raadpleeg [deze pagina](../dev/create-schema.md) voor meer informatie.

**Uitgaande interactie**

U kunt de **[!UICONTROL Interested]** -status automatisch toepassen op een aanbiedingsvoorstel wanneer de levering een koppeling bevat. Voeg eenvoudig **_urlType= &quot;11&quot;** waarde aan de verbinding toe:

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## Voorvertoning aanbod per ruimte {#offer-preview-per-space}

Op het tabblad **[!UICONTROL Preview]** kunt u de aanbiedingen bekijken waarvoor de ontvanger in aanmerking komt via een gekozen methode. In het onderstaande voorbeeld komt de begunstigde in aanmerking voor drie voorstellen per post.

![](assets/offer_space_overview_002.png)

Als een ontvanger niet in aanmerking komt voor een voorstel, wordt dit weergegeven in de voorvertoning.

![](assets/offer_space_overview_001.png)


In de voorvertoning kunnen contexten worden genegeerd wanneer deze beperkt zijn tot een spatie. Dit is het geval wanneer het interactieschema is uitgebreid om velden toe te voegen waarnaar in een ruimte wordt verwezen met een binnenkomend kanaal.

Voor meer op dit, verwijs naar deze steekproef in [&#x200B; Campaign Classic v7 documentatie &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html?lang=nl-NL){target="_blank"}.