---
title: Campagne-interactie - Aanbiedingsbeheer
description: Aan de slag met het beheer van aanbiedingen
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 1%

---

# Interacties in real time beheren

De campagne komt met een **module van de Interactie** die u in real time tijdens een interactie aan een bepaald contact laat antwoorden door hen één of verscheidene specifieke aanbiedingen voor te stellen. Deze aanbiedingen kunnen eenvoudige communicatie berichten, speciale aanbiedingen op één of verscheidene producten of de dienst zijn.

U kunt een aanbiedingencatalogus tot stand brengen die met uw uitgaande kanalen (e-mail, direct mail, SMS) omzet om de beste aanbieding te selecteren om naar een contact in een bepaalde context te verzenden. De beste aanbiedingsselectie voor een ontvanger is gebaseerd op **toelatingsregels**. De keuze van een aanbod uit een reeks relevante aanbiedingen wordt bepaald aan de hand van prioritaire regels. In de presentatieregels van het aanbod wordt rekening gehouden met de geschiedenis van de contactpersoon en wordt voorkomen dat deze meerdere malen hetzelfde voorstel krijgt.

Met interactie kunt u een catalogus met aanbiedingen maken en beheren en de regels en toepassingsthema&#39;s configureren die aan deze aanbiedingen zijn gekoppeld. Afhankelijk van het gekozen kanaal kan de inhoud van de aanbieding worden gepersonaliseerd dankzij verschillende renderfuncties. Tot slot kunt u de simulatiemodule gebruiken om het effect van een aanbiedingspresentatie te berekenen.

![](assets/interaction-cycle.png)

Ten eerste treedt er een contact op tussen een klant en een bedrijf via een communicatiekanaal: het kan een website (uitgaande interactie), een e-mail, SMS, pushmelding (binnenkomende interacties) zijn. [Meer informatie](#interaction-types)

Dit contact resulteert in een vraag aan de motor van de Aanbieding. (1)

Wanneer de vraag aan de motor van de Aanbieding gebeurt, worden één of verscheidene aanbiedingen geselecteerd van de catalogus van de Aanbieding afhankelijk van het aantal aanbiedingsmontages op het voorstel. (2)

Vervolgens worden de toelatingsregels toegepast: de beste aanbiedingen worden geselecteerd op basis van de toelatingsregels, de begin- en einddatum van de aanbiedingen, de profielgegevens en het real-time gedrag van de klant. (3)

De profielvoorstellingsgeschiedenis wordt bijgewerkt zodra de selectie wordt gemaakt, om dubbel aanbod te vermijden dat wordt voorgesteld. (4)

Tot slot wordt het beste aanbod aan het doel voorgesteld. (5)

## Aan de slag met voorstellen

De belangrijkste stappen die moeten worden gestart worden hieronder weergegeven.

### Uw platform configureren

Alvorens, als Campagne **Beheerder** te beginnen, zorg ervoor u de volgende taken in ontwerpmilieu&#39;s uitvoerde:

1. Gebruikersprofielen maken. [Meer informatie](interaction-operators.md)
1. (facultatief) creeer een aanbiedingsmilieu voor elke het richten dimensie. [Meer informatie](interaction-env.md)
1. Maak typologische regels voor elke omgeving. [Meer informatie](interaction-offer.md#offer-presentation)
1. Maak aanbiedingsruimten voor elke omgeving en configureer renderfuncties. [&#x200B; Leer meer &#x200B;](interaction-offer-spaces.md)
Als de ruimte door een eenheidkanaal op bepaalde wijze wordt bepaald, moet u de geavanceerde parameters voor deze ruimte specificeren.

   >[!NOTE]
   >
   >Als de ruimte door een eenheidkanaal op bepaalde wijze wordt bepaald, moet u de geavanceerde parameters voor deze ruimte specificeren.

1. Vorm de motor van de Aanbieding voor binnenkomende interactie om één of verscheidene aanbiedingen voor te stellen en bij te werken.

   De diverse integratiemodi zijn gedetailleerd in [&#x200B; deze sectie &#x200B;](interaction-present-offers.md).

   >[!NOTE]
   >
   >Wanneer een aanbiedingsruimte op het binnenkomende kanaal van het Web wordt gecreeerd, moet u de website vormen om deze aanbieding te tonen.
   >

### De aanbiedingscatalogus maken en publiceren {#managing-the-offer-catalog-}

Als **manager van de Aanbieding** moet u:

1. Aanbiedingscategorieën maken in ontwerpomgevingen. [Meer informatie](interaction-offer-catalog.md#creating-offer-categories)
1. Maak aanbiedingen in ontwerpomgevingen. [Meer informatie](interaction-offer.md)
1. Aanbiedingen goedkeuren en publiceren op één of meerdere ruimten om ze beschikbaar te maken in live omgevingen voor de leveringsmanager. [Meer informatie](interaction-offer.md#approve-offers)

### De aanbiedingencatalogus gebruiken {#using-the-offer-catalog-}

Als manager van de a **Levering** moet u:

1. Maak een campagne.
1. Verwijs naar een aanbod in de campagne of de levering. [Meer informatie](interaction-send-offers.md).

## Verklarende woordenlijst

Ontdek de aanbiedingsspecifieke voorwaarden en de bijbehorende richtlijnen voordat u begint.

* **Milieu**: reeks die een aanbiedingscatalogus en haken (aanbiedingsruimten) omvat. Maak één omgeving door dimensie als doel in te stellen. Er zijn twee soorten omgevingen:

   * **milieu van het Ontwerp**: milieu waarin de aanbiedingen worden gecreeerd en/of de typologische regels worden bepaald (regels die de aanbiedingen zullen bepalen om aan een gerichte persoon voor te stellen of niet te presenteren). In deze tabel wordt ook de tabel van de personen waarop de aanbiedingen betrekking moeten hebben, en de tabel voor het opslaan van alle voorstellen voor aanbiedingen vastgesteld. Het knooppunt **[!UICONTROL Design environment]** bevat submappen voor beschikbare ruimte, vooraf gedefinieerde filters en categorieën van aanbiedingen. Voor elke **[!UICONTROL Design environment]** is er één overeenkomende alleen-lezen **[!UICONTROL Live environment]** , die op basis van dezelfde **[!UICONTROL Design environment]** wordt gegenereerd.
   * **Levende milieu**: milieu verbonden aan a **[!UICONTROL Design environment]**. Het bevat alleen-lezen aanbiedingen waarvan de inhoud en geschiktheid zijn goedgekeurd via de **[!UICONTROL Design environment]** . Zij zijn beschikbaar om op een Website worden getoond of in een bericht worden opgenomen.

* **ruimte van de Aanbieding**: omslag die de plaats bepaalt waar de aanbieding wordt blootgesteld. Wanneer u een spatie definieert, kunt u:
   * selecteert u het kanaal
   * kies het in unitaire wijze (door gebrek: slechts in partijwijze) kan worden gebruikt
   * de inhoud van het aanbod opbouwen met behulp van renderfuncties
   * de voorstellen specificeren die moeten worden ingediend

  Een spatie is een interface tussen het kanaal en de motor van de Aanbieding.

  >[!CAUTION]
  >
  >Een aanbiedingsruimte is geen communicatiekanaal, maar valt samen met een specifieke expositielocatie op het kanaal. Aanbiedingen die op een website worden weergegeven, kunnen bijvoorbeeld twee spaties op dezelfde pagina beslaan. In dit geval hebt u twee spaties voor hetzelfde kanaal.
  >
  >De ruimten moeten in de specificaties worden gedefinieerd en mogen tijdens het project niet worden gewijzigd.

* **catalogus van de Aanbieding**: reeks aanbiedingen die in Adobe Campaign worden bepaald die tijdens een interactie kunnen worden geselecteerd. De catalogus is hiërarchisch geordend met elk knooppunt dat overeenkomt met een categorie.
* **Categorie**: een omslag verbonden aan de aanbiedingscatalogus in een milieu, dat aanbiedingen organiseert die op aard, geschiktheidsdatum en toepassingsthema worden gebaseerd. Een categorie kan subcategorieën bevatten, die alle kenmerken van de bovenliggende categorie overnemen. Voor een categorie kunnen subsidiabiliteitsregels worden vastgesteld om deze voor meerdere aanbiedingen te delen.
* **de thema&#39;s van de Toepassing**: sleutelwoorden die in de categorie worden bepaald, die u aanbiedingen laten filtreren wanneer zij aan een binnenkomend of uitgaand kanaal worden voorgesteld door de selectie van aanbiedingen tot één of twee categorieën te beperken.

  >[!NOTE]
  >
  >De categorieën van het kind erven de thema&#39;s die in de oudercategorie worden geïdentificeerd.

* **Subsidiabiliteitsregels**: beperkingen die op een milieu, een categorie, of een aanbieding betreffende de geldigheidsperiode, het doel, en het gewicht worden toegepast. Hiermee kunt u ervoor zorgen dat een aanbieding in overeenstemming is met de beoogde contactpersoon.

  In de omgeving omvatten de subsidiabiliteitsregels presentatieregels die worden toegepast op de aanbiedingen en de doelgroepen.

  In de categorieën kunt u aan de hand van de subsidiabiliteitsregels de geldigheid van de categorie in de tijd beperken, toepassingsthema&#39;s definiëren en bepalen welke personen als doel dienen. Ze kunnen ook een vermenigvuldigingsfactor krijgen gedurende een bepaalde tijd. Op deze manier kunt u de regels voor aanbiedingen in andere rubrieken delen en wordt het beheer ervan vereenvoudigd.

  In de aanbiedingen kunt u met de subsidiabiliteitsregels de geldigheid van de aanbiedingen in de tijd beperken en bepalen welke personen het doelwit zijn.

* **Arbitrage**: het selecteren van aanbiedingen om op een milieu (in aanmerking komende aanbiedingen) te tonen. Het arbitragebeginsel rangschikt aanbiedingen op de rangorde volgens de criteria die in de categorieën, aanbiedingen en contextaanbiedingen worden bepaald.
* **Contact**: een contact van een binnenkomende interactie. Tijdens de verwerking van de motorvraag, wordt het contact geassocieerd aan een gericht afmeting. Er zijn twee soorten contacten:

   * **[!UICONTROL Identified contact]**: een contactpersoon die op vrijwillige basis op het kanaal is geïdentificeerd. In uitgaande interactie, wordt het contact automatisch geïdentificeerd.
   * **[!UICONTROL Anonymous contact]**: een contactpersoon die zich niet vrijwillig via het kanaal heeft geabonneerd maar impliciet kan worden geïdentificeerd door middel van een cookie. Deze terminologie wordt alleen gebruikt voor binnenkomende interacties.

     >[!NOTE]
     >
     >Niet-geïdentificeerde, anonieme contacten worden toegeschreven aan de bezoeker richtend dimensie.

* **Uitgaande interactie**: vraag aan de motor van de Aanbieding van een contactlijst (die voor het leveren van e-mail, direct post, enz. wordt gebruikt). De zelfde regels en de processen worden toegepast op elk contact. Dit type interactie wordt meestal verwerkt in batchmodus.
* **Binnenkomende interactie**: interactie na een inkomende vraag die door de actie van een contact op het kanaal wordt geproduceerd. Dit type interactie wordt meestal in de eenheidsmodus verwerkt.
* **wijze van de Partij**: De partijwijze laat u de beste aanbieding voor een reeks contacten selecteren. De regels inzake subsidiabiliteit/prioritering worden toegepast op alle contacten van de reeks. Deze wijze wordt gewoonlijk toegepast op uitgaande interactie.
* **Eenheid wijze**: één enkel contact wordt verwerkt tegelijkertijd. Deze wijze wordt gewoonlijk toegepast voor binnenkomende interactie en transactionele berichten.
* **wijze van de Identificatie**: verwijst naar het statuut van een contact:

   * **[!UICONTROL explicit]**: contactpersonen worden geïdentificeerd aan de hand van hun aanmelding bij de kanaalinterface.
   * **[!UICONTROL implicit]**: contactpersoon wordt geïdentificeerd door een cookie (permanent of sessie). Het kan als anoniem of geïdentificeerd contact worden verwerkt.
   * **[!UICONTROL anonymous]** : contactpersonen kunnen niet worden geïdentificeerd.

* **In aanmerking komende aanbieding**: aanbieding die de beperkingen ontmoeten die stroomopwaarts worden bepaald die aan een doel constant kunnen worden aangeboden.
* **de regels van de Presentatie**: typologische regels die in het aanbiedingsmilieu van verwijzingen worden voorzien, die u sommige aanbiedingen laten uitsluiten door de voorstellingshistorie in overweging te nemen.
* **Gewicht**: formules die u de relevantie van een aanbieding nauwkeurig laten berekenen, om de meest relevante aanbieding te selecteren. Het gewicht wordt gedefinieerd in de aanbiedingen. In aanmerking komende aanbiedingen worden in afnemende gewichtsvolgorde in aanmerking genomen.
* **teruggevend functie**: functie die in de aanbiedingsruimte wordt bepaald om zijn aanbiedingsvertegenwoordiging te construeren die op de attributen wordt gebaseerd die in de aanbieding worden bepaald. Er zijn drie verschillende renderingfuncties: HTML, XML en tekst.
* **voorstel van de Aanbieding**: resultaat van de actie die uit het voorstellen van één of verscheidene aanbiedingen aan een contact in een bepaalde ruimte (banner op een website, e-mail of SMS bijvoorbeeld) bestaat. Dit resultaat wordt opgeslagen in de lijst met aanbiedingsvoorstellen. Het is echter niet verplicht de voorstellen op te slaan.
* **Simulatie**: module die u de aanbiedingspresentatie op de gerichte ontvangers laat testen alvorens eigenlijk de aanbiedingen te verzenden.
* **Voorproef**: voorproef van de aanbieding aangezien het in zijn omslag wordt getoond. Het is toegankelijk vanuit het venster met aanbiedingsinstellingen of het contactprofiel.
* **vooraf bepaalde filters**: de vooraf bepaalde het filtreren regels kunnen rekening houden met aanbiedingsparameters (bijvoorbeeld, een aanbiedingscode). Ze kunnen opnieuw worden gebruikt nadat voorstellen zijn gemaakt.
* **vertegenwoordiging van de Aanbieding**: informatie die door het kanaal wordt gebruikt om de aanbieding te tonen. De aanbiedingsvertegenwoordiging kan van de teruggevende functie van de ruimte worden geconstrueerd waarop de aanbieding wordt vertegenwoordigd of direct in de interface (bijvoorbeeld, in het blok van HTML) ingegaan. Een aanbieding kan door de ruimte worden vertegenwoordigd.
* **proces van de Verandering**: een geactiveerd proces in een geïdentificeerd milieu, verantwoordelijk voor het leiden van de vraag aan een anoniem milieu als het contact niet uitdrukkelijk en/of impliciet geïdentificeerd is.
