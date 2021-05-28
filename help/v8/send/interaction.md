---
solution: Campaign v8
product: Adobe Campaign
title: Campagne-interactie - Aanbiedingsbeheer
description: Aan de slag met het beheer van aanbiedingen
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 1%

---

# Interaction- en aanbiedingenbeheer{#interaction-and-offer-management}

Campagne wordt geleverd met een **Interactie** module die u in real time tijdens een interactie met een bepaalde contact (een klant of een doel) laat antwoorden door hen één of verscheidene aangepaste aanbiedingen te maken. Dit kunnen bijvoorbeeld eenvoudige communicatieberichten, speciale aanbiedingen voor een of meerdere producten of een service zijn.

U kunt een aanbiedingencatalogus tot stand brengen die met uw uitgaande kanalen (e-mail, direct mail, SMS) zal omzetten om de beste aanbieding te selecteren om naar een contact in een bepaalde context te verzenden. De beste selectie van aanbiedingen voor een ontvanger is gebaseerd op **subsidiabiliteitsregels**. De keuze van een aanbod uit een reeks relevante aanbiedingen wordt bepaald aan de hand van prioritaire regels. Bij het aanbieden van presentatieregels wordt rekening gehouden met de geschiedenis van de contactpersoon en kunt u voorkomen dat deze meerdere malen hetzelfde voorstel krijgt.

Met interactie kunt u een catalogus met aanbiedingen maken en beheren en de regels en toepassingsthema&#39;s configureren die aan deze aanbiedingen zijn gekoppeld. Afhankelijk van het gekozen kanaal kan de inhoud van de aanbieding worden gepersonaliseerd dankzij verschillende renderfuncties. Tot slot kunt u de simulatiemodule gebruiken om het effect van een aanbiedingspresentatie te berekenen.

## Aan de slag met voorstellen

De belangrijkste stappen die moeten worden gestart worden hieronder weergegeven.

### Uw platform configureren

Voordat u begint, moet u als beheerder **Beheerder** de volgende taken uitvoeren in ontwerpomgevingen:

1. Gebruikersprofielen maken. [Meer informatie](interaction-operators.md).
1. (optioneel) Maak een aanbiedingsomgeving voor elke doeldimensie. [Meer informatie](interaction-env.md)
1. Maak typologische regels voor elke omgeving. [Meer informatie](interaction-offer.md#offer-presentation).
1. Maak aanbiedingsruimten voor elke omgeving en configureer renderfuncties. [Meer informatie](interaction-offer-spaces.md).
Als de ruimte door een eenheidkanaal op bepaalde wijze wordt bepaald, moet u de geavanceerde parameters voor deze ruimte specificeren.

### De aanbiedingscatalogus maken en publiceren {#managing-the-offer-catalog-}

Als **Manager van de aanbieding** moet u de volgende taken uitvoeren:

1. Aanbiedingscategorieën maken in ontwerpomgevingen. [Meer informatie](interaction-offer-catalog.md#creating-offer-categories).
1. Aanbiedingen maken in ontwerpomgevingen. [Meer informatie](interaction-offer.md).
1. Aanbiedingen goedkeuren en publiceren op een of meerdere ruimten om deze beschikbaar te maken in live omgevingen voor de leveringsmanager. [Meer informatie](interaction-offer.md#approve-offers).

### Gebruik de aanbiedingencatalogus {#using-the-offer-catalog-}

Als **Leveringsmanager** moet u de volgende taken uitvoeren:

1. Een campagne maken.
1. Verwijs naar een aanbod in de campagne of de levering. [Meer informatie](interaction-send-offers.md).


## Concepten en terminologie

Ontdek de aanbiedingsspecifieke voorwaarden en de bijbehorende richtlijnen voordat u begint.

* **De** milieu&#39;s omvatten een aanbiedingscatalogus en aanbiedingsruimten (haken). U moet één milieu tot stand brengen door dimensie te richten.
Er zijn twee soorten omgevingen:

   * **Ontwerpomgeving**: aanbiedingen worden gecreëerd in de ontwerpomgeving en in de typologieregels. De typologieregels bepalen welke aanbiedingen aan een doelpersoon moeten worden gedaan (of niet). In deze omgeving wordt ook de tabel met individuele aanbiedingen en de tabel voor het opslaan van alle voorstellen voor aanbiedingen gedefinieerd. Het knooppunt **[!UICONTROL Design environment]** bevat submappen voor beschikbare ruimte, vooraf gedefinieerde filters en categorieën aanbiedingen. Voor elke **[!UICONTROL Design environment]** is er één overeenkomstige read-only **[!UICONTROL Live environment]**, die uit zelfde **[!UICONTROL Design environment]** wordt geproduceerd.
   * **Live omgeving**: omgeving die gekoppeld is aan een  **[!UICONTROL Design environment]** aanbod met alleen-lezen aanbiedingen waarvan de inhoud en de geschiktheid via de  **[!UICONTROL Design environment]** website zijn goedgekeurd. Deze moeten worden geselecteerd om in een bericht te worden opgenomen.

* De **Aanbiedingsruimte** is een locatie (map) die de locatie definieert waar de aanbieding wordt weergegeven. Wanneer u een aanbiedingsruimte maakt, kunt u het kanaal opgeven, de inhoud van de aanbieding opbouwen met behulp van renderfuncties, de volgorde van de aanbiedingen en de modus ervan opgeven: monisatiemodus en/of batchmodus (standaard). De aanbiedingsruimte is de interface tussen het kanaal en de aanbiedingsmotor.
* De **Aanbiedingscatalogus** is een reeks aanbiedingen die zijn gedefinieerd in Adobe Campaign en die tijdens een interactie kunnen worden geselecteerd. De catalogus is hiërarchisch geordend met elk knooppunt dat overeenkomt met een categorie.
* Een **Categorie** is een map die is gekoppeld aan de aanbiedingencatalogus in een omgeving, waarin aanbiedingen worden georganiseerd op basis van de aard, de datum waarop ze in aanmerking komen en het thema van de toepassing. Een categorie kan subcategorieën bevatten, die alle kenmerken van de bovenliggende categorie overnemen. Voor een categorie kunnen subsidiabiliteitsregels worden vastgesteld om deze voor meerdere aanbiedingen te delen.
* **Toepassingsthema&#39;** s zijn trefwoorden die in de categorie zijn gedefinieerd. Hiermee kunt u aanbiedingen filteren wanneer deze worden weergegeven door de selectie van aanbiedingen te beperken tot een of twee categorieën.
* **De** subsidiabiliteitsregels zijn beperkingen die worden toegepast op een omgeving, categorie of aanbod, met betrekking tot de geldigheidsperiode, het doel en het gewicht. Hiermee kunt u ervoor zorgen dat een aanbieding in overeenstemming is met de beoogde contactpersoon.

   In de omgeving omvatten de subsidiabiliteitsregels presentatieregels die worden toegepast op de aanbiedingen en de doelgroepen.

   In de categorieën kunt u met de subsidiabiliteitsregels de geldigheid van de categorie in de tijd beperken, toepassingsthema&#39;s definiëren en bepalen welke personen het doelwit moeten zijn. Zij kunnen ook gedurende een bepaalde periode een vermenigvuldigingsgewicht krijgen. Op deze manier kunt u de regels voor aanbiedingen in andere rubrieken delen en wordt het beheer ervan vereenvoudigd.

   In de aanbiedingen kunt u met de subsidiabiliteitsregels de geldigheid van de aanbiedingen in de tijd beperken en bepalen welke personen het doelwit zijn.

* De **Arbitrage** is de handeling van het selecteren van aanbiedingen die op een milieu (in aanmerking komende aanbiedingen) zullen worden getoond. De arbitragerangschikking heeft voorrang op aanbiedingen volgens de criteria die in de categorieën, aanbiedingen en contextaanbiedingen zijn vastgesteld.
* Een **Uitgaande interactie** roept de interactie motor van een contactlijst (die voor het leveren van e-mail, direct post, enz. wordt gebruikt). De zelfde regels en de processen worden toegepast op elk contact. Dit type interactie wordt over het algemeen verwerkt in batchmodus.
* Met de **Batchmodus** kunt u de beste aanbieding voor een set contactpersonen selecteren. De regels voor geschiktheid/prioritering worden toegepast op alle contactpersonen in de set. Deze wijze wordt over het algemeen gebruikt voor uitgaande interactie.
* Met de **Eenvoudige modus** kunt u één contactpersoon tegelijk verwerken. Deze wijze wordt over het algemeen gebruikt voor transactieberichten.
* **In aanmerking komende** aanbiedingen zijn aanbiedingen die aan de vooraf gedefinieerde beperkingen voldoen en die consistent aan een doel kunnen worden aangeboden.
* **De** regels van de presentatie zijn typologische regels die in het aanbiedingsmilieu van verwijzingen worden voorzien, die u sommige aanbiedingen laten door de voorstellingshistorie in overweging te nemen uitsluiten.
* **Met** gewichtsformules kunt u de relevantie van een aanbieding nauwkeurig berekenen, zodat u de meest relevante aanbieding kunt selecteren. Het gewicht wordt gedefinieerd in de aanbiedingen. In aanmerking komende aanbiedingen worden in afnemende gewichtsvolgorde in aanmerking genomen.
* **De renderfuncties** worden gedefinieerd in de aanbiedingsruimte om de representatie van de aanbieding te construeren op basis van de kenmerken die in de aanbieding zijn gedefinieerd. Er zijn drie verschillende renderingfuncties: HTML, XML en tekst.
* **De** voorgestelde aanbieding is het resultaat van de actie die bestaat uit het aanbieden van één of meerdere aanbiedingen aan een contact in een bepaalde ruimte (banner op een website, e-mail of SMS bijvoorbeeld). Dit resultaat wordt opgeslagen in de lijst met aanbiedingsvoorstellen. Het is echter niet verplicht de voorstellen op te slaan.
* **** Simulatie is een module waarmee u de aanbiedingspresentatie op de beoogde ontvangers kunt testen voordat u de aanbiedingen daadwerkelijk verzendt.
* De **Voorvertoning** van de aanbieding toont de aanbieding aangezien deze in zijn omslag wordt getoond. Het is toegankelijk vanuit het venster met aanbiedingsinstellingen of het contactprofiel.
* **De vooraf bepaalde filters** zijn het filtreren regels kunnen rekening met aanbiedingsparameters (bijvoorbeeld, een aanbiedingscode) houden. Ze kunnen opnieuw worden gebruikt nadat voorstellen zijn gemaakt.
* Een **aanbiedingsvertegenwoordiging** is een informatie die door het kanaal wordt gebruikt om de aanbieding te tonen. De aanbiedingsvertegenwoordiging kan van de teruggevende functie van de ruimte worden geconstrueerd waarop de aanbieding wordt vertegenwoordigd of direct in de interface (bijvoorbeeld, in het blok van HTML) ingegaan. Een aanbieding kan door de ruimte worden vertegenwoordigd.

