---
title: Campagne-interactie - Aanbiedingsbeheer
description: Aan de slag met het beheer van aanbiedingen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
source-git-commit: 7234ca65f785b005b11851a5cd88add8cddeff4f
workflow-type: tm+mt
source-wordcount: '1656'
ht-degree: 1%

---

# Interacties in real time beheren

Campagne wordt geleverd met een **Interactie** die u in real time tijdens een interactie met een bepaald contact (een klant of een doel) laat antwoorden door hen één of verscheidene aangepaste aanbiedingen te maken. Dit kunnen bijvoorbeeld eenvoudige communicatieberichten, speciale aanbiedingen voor een of meerdere producten of een service zijn.

U kunt een aanbiedingencatalogus tot stand brengen die met uw uitgaande kanalen (e-mail, direct mail, SMS) zal omzetten om de beste aanbieding te selecteren om naar een contact in een bepaalde context te verzenden. De beste selectie van voorstellen voor een ontvanger is gebaseerd op **subsidiabiliteitsregels**. De keuze van een aanbod uit een reeks relevante aanbiedingen wordt bepaald aan de hand van prioritaire regels. Bij het aanbieden van presentatieregels wordt rekening gehouden met de geschiedenis van de contactpersoon en kunt u voorkomen dat deze meerdere malen hetzelfde voorstel krijgt.

Met interactie kunt u een catalogus met aanbiedingen maken en beheren en de regels en toepassingsthema&#39;s configureren die aan deze aanbiedingen zijn gekoppeld. Afhankelijk van het gekozen kanaal kan de inhoud van de aanbieding worden gepersonaliseerd dankzij verschillende renderfuncties. Tot slot kunt u de simulatiemodule gebruiken om het effect van een aanbiedingspresentatie te berekenen.

![](assets/interaction-cycle.png)

Eerst, komt een contact tussen een klant en een bedrijf door een communicatiekanaal voor: het kan een website (uitgaande interactie), een e-mail, SMS, pushmelding (binnenkomende interactie) zijn. [Meer informatie](#interaction-types)

Dit contact resulteert in een vraag aan de motor van de Aanbieding. (1)

Wanneer de vraag aan de motor van de Aanbieding gebeurt, worden één of verscheidene aanbiedingen geselecteerd van de catalogus van de Aanbieding afhankelijk van het aantal aanbiedingsmontages op het voorstel. (2)

Vervolgens worden de subsidiabiliteitsregels toegepast: de beste aanbiedingen worden geselecteerd op basis van de toelatingsregels, de begin- en einddatum van aanbiedingen, de profielgegevens en het real-time gedrag van de klant. (3)

De profielvoorstellingsgeschiedenis wordt bijgewerkt zodra de selectie wordt gemaakt, om dubbel aanbod te vermijden dat wordt voorgesteld. (4)

Tot slot wordt het beste aanbod aan het doel voorgesteld. (5)

## Aan de slag met voorstellen

De belangrijkste stappen die moeten worden gestart worden hieronder weergegeven.

### Uw platform configureren

Voordat u begint, als een campagne **Beheerder**, zorg ervoor u de volgende taken in ontwerpmilieu&#39;s uitvoerde:

1. Gebruikersprofielen maken. [Meer informatie](interaction-operators.md)
1. (optioneel) Maak een aanbiedingsomgeving voor elke doeldimensie. [Meer informatie](interaction-env.md)
1. Maak typologische regels voor elke omgeving. [Meer informatie](interaction-offer.md#offer-presentation)
1. Maak aanbiedingsruimten voor elke omgeving en configureer renderfuncties. [Meer informatie](interaction-offer-spaces.md)
Als de ruimte door een eenheidkanaal op bepaalde wijze wordt bepaald, moet u de geavanceerde parameters voor deze ruimte specificeren.

   >[!NOTE]
   >
   >Als de ruimte door een eenheidkanaal op bepaalde wijze wordt bepaald, moet u de geavanceerde parameters voor deze ruimte specificeren.

1. Vorm de motor van de Aanbieding voor binnenkomende interactie om één of verscheidene aanbiedingen voor te stellen en bij te werken.

   De verschillende integratiemodi worden nader beschreven in [deze sectie](interaction-present-offers.md).

   >[!NOTE]
   >
   >Wanneer een ruimte op het binnenkomende kanaal van het Web wordt gecreeerd, is een configuratie ook noodzakelijk op de plaats waarop de aanbieding zal worden getoond.

### De aanbiedingscatalogus maken en publiceren {#managing-the-offer-catalog-}

Als **Aanbiedingsmanager** u moet de volgende taken uitvoeren:

1. Aanbiedingscategorieën maken in ontwerpomgevingen. [Meer informatie](interaction-offer-catalog.md#creating-offer-categories)
1. Aanbiedingen maken in ontwerpomgevingen. [Meer informatie](interaction-offer.md)
1. Aanbiedingen goedkeuren en publiceren op een of meerdere ruimten om deze beschikbaar te maken in live omgevingen voor de leveringsmanager. [Meer informatie](interaction-offer.md#approve-offers)

### Gebruik de aanbiedingencatalogus {#using-the-offer-catalog-}

Als **Leveringsmanager**  u moet de volgende taken uitvoeren:

1. Een campagne maken.
1. Verwijs naar een aanbod in de campagne of de levering. [Meer info](interaction-send-offers.md).


## Verklarende woordenlijst

Ontdek de aanbiedingsspecifieke voorwaarden en de bijbehorende richtlijnen voordat u begint.

* **Omgeving**: Deze set bevat een aanbiedingscatalogus en haken (aanbiedingsruimten). U moet één milieu tot stand brengen door dimensie te richten. Er zijn twee soorten omgevingen:

   * **Ontwerpomgeving**: omgeving waarin aanbiedingen worden gemaakt en/of typologieregels worden vastgesteld (regels die bepalen welke aanbiedingen aan een doelpersoon moeten worden gepresenteerd of niet). In deze tabel wordt ook de tabel van de personen voor wie de aanbiedingen bestemd zijn, en de tabel voor het opslaan van alle voorstellen voor aanbiedingen, gedefinieerd. De **[!UICONTROL Design environment]** De node bevat submappen voor de aanbiedingsruimte, vooraf gedefinieerde filters en categorieën van aanbiedingen. Voor elke **[!UICONTROL Design environment]** er is één overeenkomende alleen-lezen **[!UICONTROL Live environment]**, op basis van dezelfde **[!UICONTROL Design environment]**.
   * **Live omgeving**: milieu gekoppeld aan een **[!UICONTROL Design environment]**. Het bevat alleen-lezen aanbiedingen waarvan de inhoud en geschiktheid zijn goedgekeurd via de **[!UICONTROL Design environment]**. Zij moeten worden geselecteerd om op een Website worden voorgesteld of in een bericht worden opgenomen.

* **Ruimte voor aanbod**: map waarin de locatie wordt aangegeven waar de aanbieding wordt weergegeven. Als u een spatie definieert, kunt u het gebruikte kanaal opgeven en opgeven of het kanaal in de eenheidsmodus kan worden gebruikt (standaard: alleen in batchmodus), de inhoud van de aanbieding opbouwen met behulp van renderfuncties en de aanbieding van de aangeboden aanbiedingen specificeren. Een spatie is een interface tussen het kanaal en de motor van de Aanbieding.

   >[!CAUTION]
   >
   >Een aanbiedingsruimte is geen communicatiekanaal, maar valt samen met een specifieke expositielocatie op het kanaal. Aanbiedingen die op een website worden weergegeven, kunnen bijvoorbeeld twee spaties op dezelfde pagina beslaan. In dit geval hebben we dan twee spaties voor hetzelfde kanaal.
   >
   >De ruimten moeten in de specificaties worden gedefinieerd en mogen tijdens het project niet worden gewijzigd.

* **Aanbiedingscatalogus**: die in Adobe Campaign zijn gedefinieerd en die tijdens een interactie kunnen worden geselecteerd. De catalogus is hiërarchisch geordend met elk knooppunt dat overeenkomt met een categorie.
* **Categorie**: een map die gekoppeld is aan de aanbiedingencatalogus in een omgeving, waarin aanbiedingen worden georganiseerd op basis van aard, datum waarop voor de aanbieding in aanmerking komt en thema van de toepassing. Een categorie kan subcategorieën bevatten, die alle kenmerken van de bovenliggende categorie overnemen. Voor een categorie kunnen subsidiabiliteitsregels worden vastgesteld om deze voor meerdere aanbiedingen te delen.
* **Toepassingsthema&#39;s**: De sleutelwoorden die in de categorie worden bepaald, die u aanbiedingen laten filtreren wanneer zij aan een binnenkomend of uitgaand kanaal door de selectie van aanbiedingen tot één of twee categorieën te beperken worden voorgesteld.

   >[!NOTE]
   >
   >De categorieën van het kind erven de thema&#39;s die in de oudercategorie worden geïdentificeerd.

* **Subsidiabiliteitsregels**: beperkingen die van toepassing zijn op een omgeving, categorie of aanbieding met betrekking tot de geldigheidsperiode, het doel en het gewicht. Hiermee kunt u ervoor zorgen dat een aanbieding in overeenstemming is met de beoogde contactpersoon.

   In de omgeving omvatten de subsidiabiliteitsregels presentatieregels die worden toegepast op de aanbiedingen en de doelgroepen.

   In de categorieën kunt u met de subsidiabiliteitsregels de geldigheid van de categorie in de tijd beperken, toepassingsthema&#39;s definiëren en bepalen welke personen het doelwit moeten zijn. Zij kunnen ook gedurende een bepaalde periode een vermenigvuldigingsgewicht krijgen. Op deze manier kunt u de regels voor aanbiedingen in andere rubrieken delen en wordt het beheer ervan vereenvoudigd.

   In de aanbiedingen kunt u met de subsidiabiliteitsregels de geldigheid van de aanbiedingen in de tijd beperken en bepalen welke personen het doelwit zijn.

* **Arbitrage**: het selecteren van aanbiedingen die in een omgeving worden getoond (in aanmerking komende aanbiedingen). Het arbitragebeginsel rangschikt de aanbiedingen naar prioriteit op basis van de criteria die in de categorieën, aanbiedingen en contextaanbiedingen zijn vastgesteld.
* **Contact**: een contact van een binnenkomende interactie. Tijdens de verwerking van de motorvraag, wordt het contact geassocieerd aan een gericht afmeting. Er zijn twee soorten contacten:

   * **[!UICONTROL Identified contact]** : een contact dat vrijwillig op het kanaal is geïdentificeerd. In uitgaande interactie, wordt het contact automatisch geïdentificeerd.
   * **[!UICONTROL Anonymous contact]** : een contactpersoon die niet vrijwillig via het kanaal is geabonneerd, maar impliciet via een cookie kan worden geïdentificeerd. Deze terminologie wordt alleen gebruikt voor binnenkomende interacties.

      >[!NOTE]
      >
      >Niet-geïdentificeerde, anonieme contacten worden toegeschreven aan de bezoeker richtend dimensie.

* **Uitgaande interactie**: bellen naar de motor van de Aanbieding van een contactlijst (gebruikt voor het leveren van e-mail, direct mail, enz.). De zelfde regels en de processen worden toegepast op elk contact. Dit type interactie wordt over het algemeen verwerkt in batchmodus.
* **Binnenkomende interactie**: interactie na een inkomende vraag die door de actie van een contact op het kanaal wordt geproduceerd. Dit type interactie wordt over het algemeen in de monistische modus verwerkt.
* **Batchmodus**: in de batchmodus kunt u de beste aanbieding voor een set contactpersonen selecteren. De regels voor geschiktheid/prioritering worden toegepast op alle contactpersonen in de set. Deze wijze wordt over het algemeen gebruikt voor uitgaande interactie.
* **Eenvoudige modus**: één enkel contact wordt verwerkt tegelijkertijd. Deze wijze wordt over het algemeen gebruikt voor binnenkomende interactie en transactieberichten.
* **Identificatiemodus**: verwijst naar de status van een contactpersoon.

   * **[!UICONTROL explicit]** : het contact wordt geïdentificeerd na zijn login op de kanaalinterface.
   * **[!UICONTROL implicit]** : de contactpersoon is geïdentificeerd door een cookie (permanent of sessie). Het kan als anoniem of geïdentificeerd contact worden verwerkt.
   * **[!UICONTROL anonymous]** : het contact kan niet worden geïdentificeerd.

* **In aanmerking komende aanbieding**: bieden aan die voldoen aan de beperkingen die stroomopwaarts zijn gedefinieerd en die consistent aan een doel kunnen worden aangeboden.
* **Presentatieregels**: typologische regels waarnaar in de aanbiedingsomgeving wordt verwezen, waardoor u bepaalde aanbiedingen kunt uitsluiten door rekening te houden met de voorpositiegeschiedenis.
* **Dikte**: formules waarmee u de relevantie van een aanbieding nauwkeurig kunt berekenen, zodat u de meest relevante aanbieding kunt selecteren. Het gewicht wordt gedefinieerd in de aanbiedingen. In aanmerking komende aanbiedingen worden in afnemende gewichtsvolgorde in aanmerking genomen.
* **Renderfunctie**: in de aanbiedingsruimte gedefinieerde functie om de aanbiedingsweergave te construeren op basis van de in de aanbieding gedefinieerde kenmerken. Er zijn drie verschillende renderingfuncties: HTML, XML en tekst.
* **Voorstel**: resultaat van de actie die bestaat uit het aanbieden van een of meer aanbiedingen aan een contactpersoon in een bepaalde ruimte (bijvoorbeeld banner op een website, e-mail of SMS). Dit resultaat wordt opgeslagen in de lijst met aanbiedingsvoorstellen. Het is echter niet verplicht de voorstellen op te slaan.
* **Simulatie**: Deze module laat u de aanbiedingspresentatie op de beoogde ontvangers testen alvorens de aanbiedingen daadwerkelijk te verzenden.
* **Voorvertoning**: een voorvertoning van de aanbieding weergeven zoals deze in de bijbehorende map wordt weergegeven. Het is toegankelijk vanuit het venster met aanbiedingsinstellingen of het contactprofiel.
* **vooraf gedefinieerde filters**: Vooraf gedefinieerde filterregels kunnen rekening houden met aanbiedingsparameters (bijvoorbeeld een aanbiedingscode). Ze kunnen opnieuw worden gebruikt nadat voorstellen zijn gemaakt.
* **Voorstelling**: informatie die door het kanaal wordt gebruikt om de aanbieding te tonen. De aanbiedingsvertegenwoordiging kan van de teruggevende functie van de ruimte worden geconstrueerd waarop de aanbieding wordt vertegenwoordigd of direct in de interface (bijvoorbeeld, in het blok van HTML) ingegaan. Een aanbieding kan door de ruimte worden vertegenwoordigd.
* **Wijzigingsproces**: een geactiveerd proces in een geïdentificeerd milieu, verantwoordelijk voor het leiden van de vraag aan een anoniem milieu als het contact niet uitdrukkelijk en/of impliciet geïdentificeerd is.
