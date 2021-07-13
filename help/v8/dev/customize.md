---
product: Adobe Campaign
title: Instantie aanpassen
description: Leer hoe u uw exemplaar kunt aanpassen
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 6%

---

# Instantie aanpassen{#gs-ac-custom}

Leer hoe te om **uw instantie van de Campagne aan te passen**

>[!CAUTION]
>
>Adobe Campaign-aanpassingen zijn alleen bestemd voor deskundige gebruikers.

## Nieuwe gegevensvelden en schema&#39;s maken

Adobe Campaign maakt gebruik van gegevensschema&#39;s om:

* Definiëren hoe dataobjecten in de applicatie worden gekoppeld aan onderliggende databasetabellen
* Definiëren van koppelingen tussen de verschillende dataobjecten in de Campaign-applicatie
* Definiëren en beschrijven van de afzonderlijke velden die in elk object zijn opgenomen

Als u bijvoorbeeld een veld wilt toevoegen aan een bestaande tabel, zoals de tabel met ontvangers (nms:ontvanger), moet u dat schema uitbreiden.

Er zijn twee tabeluitbreidingsmodi beschikbaar:

* Door de interface, door de **Nieuwe field** medewerker te gebruiken

   ↗️ Leer hoe u snel een nieuw veld kunt toevoegen in Campagne in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Programmaticaal, door het schema uit te breiden

   ?? Leer hoe te om een bestaand schema in [deze sectie](../dev/extend-schema.md) uit te breiden.


U kunt nieuwe lijsten in het gegevensbestand van de Campagne ook tot stand brengen en het ingebouwde datamodel uitbreiden.

Als u een geheel nieuw type gegevens wilt toevoegen dat niet in Adobe Campaign buiten het vak bestaat (bijvoorbeeld een contracttabel), kunt u rechtstreeks een aangepast schema maken. Raadpleeg [dit voorbeeld](../dev/create-schema.md#example--creating-a-contract-table) voor meer informatie hierover.

**Verwante onderwerpen**

↗️ voorbeeld van schemageditie in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

Hoofdlettergebruik ↗️: een veld koppelen aan een bestaande referentietabel in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Invoerformulieren wijzigen

Invoerformulieren voor campagnes kunnen worden aangepast aan uw implementatie. U kunt formuliervelden toevoegen of verwijderen door de XML-inhoud te wijzigen.

?? Leer hoe u een bestaand invoerformulier wijzigt of een nieuw formulier maakt in [deze sectie](../dev/forms.md).

## dashboards aanpassen{#gs-custom-dashboards}

De interface van Adobe Campaign gebruikt vele toepassingen van het Web om, tot ontvangers, leveringen, campagnes, voorraden, enz. toegang te hebben te beheren en in wisselwerking te staan. Deze worden in de interface weergegeven in de vorm van dashboards met slechts één pagina.

De uit-van-de-doos toepassingen van het Web worden opgeslagen in het Beleid > de toepassingsknoop van de Configuratie > van het Web.

↗️ Leer hoe u een overzichtspagina maakt in Campagne in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Lijsten aanpassen en filters maken {#gs-lists-and-filters}

### Gegevens van dashboards benaderen

Campagnerelijsten worden geleverd met vooraf gedefinieerde filters om navigatie en gegevensvizualisatie te vergemakkelijken.

↗️ Meer informatie over filteropties in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Toegang krijgen tot gegevens van de Verkenner

Wanneer u in de boom van de Ontdekkingsreiziger van Adobe Campaign navigeert, worden de gegevens in het gegevensbestand getoond in lijsten. U kunt deze lijsten filteren, zoekopdrachten uitvoeren, informatie toevoegen, filteren en sorteren.

↗️ Leer hoe te om lijsten te vormen en een lijstconfiguratie in [Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started) te bewaren


U kunt filter op deze lijsten toepassen om alleen de gegevens weer te geven die de operator nodig heeft. Dan kunnen de acties op de gefiltreerde gegevens worden uitgevoerd. Met filterconfiguratie kunt u dynamisch gegevens in een lijst selecteren. Als de gegevens worden gewijzigd, worden de gefilterde gegevens bijgewerkt.

↗️ leren hoe u gegevens kunt filteren in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)
