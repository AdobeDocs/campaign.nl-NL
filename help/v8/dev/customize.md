---
title: Instantie aanpassen
description: Leer hoe u uw exemplaar kunt aanpassen
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---

# Instantie aanpassen {#gs-ac-custom}

Leer hoe u **De instantie Campagne aanpassen**.

>[!CAUTION]
>
>Adobe Campaign-aanpassingen zijn alleen bestemd voor deskundige gebruikers.

## Nieuwe gegevensvelden en schema&#39;s maken

Adobe Campaign maakt gebruik van gegevensschema&#39;s om:

* Definiëren hoe gegevensobjecten in de toepassing zijn gekoppeld aan onderliggende databasetabellen
* Koppelingen definiëren tussen de verschillende gegevensobjecten in de Campagne-toepassing
* De afzonderlijke velden die in elk object zijn opgenomen, definiëren en beschrijven

Als u bijvoorbeeld een veld wilt toevoegen aan een bestaande tabel, zoals de tabel met ontvangers (nms:ontvanger), moet u dat schema uitbreiden.

Er zijn twee tabeluitbreidingsmodi beschikbaar:

* Door de interface, door te gebruiken **Nieuw veld** assistent

  Leer hoe u snel een nieuw veld kunt toevoegen in Campagne in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html#configuring-campaign-classic){target="_blank"}

* Programmaticaal, door het schema uit te breiden. Leer hoe u een bestaand schema kunt uitbreiden in [deze sectie](../dev/extend-schema.md).

U kunt nieuwe lijsten in het gegevensbestand van de Campagne ook tot stand brengen en het ingebouwde datamodel uitbreiden.

Als u een geheel nieuw type gegevens wilt toevoegen dat niet in Adobe Campaign buiten het vak bestaat (bijvoorbeeld een contracttabel), kunt u rechtstreeks een aangepast schema maken. Raadpleeg voor meer informatie hierover [dit voorbeeld](../dev/create-schema.md#example--creating-a-contract-table).

**Verwante onderwerpen**

Voorbeeld van schemageditie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#configuring-campaign-classic){target="_blank"}

Hoofdlettergebruik: een veld koppelen aan een bestaande referentietabel in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#uc-link){target="_blank"}


## Invoerformulieren wijzigen

Invoerformulieren voor campagnes kunnen worden aangepast aan uw implementatie. U kunt formuliervelden toevoegen of verwijderen door de XML-inhoud te wijzigen.

Leer hoe u een bestaand invoerformulier kunt wijzigen of een nieuw formulier kunt maken in [deze sectie](../dev/forms.md).

## dashboards aanpassen{#gs-custom-dashboards}

De interface van Adobe Campaign gebruikt vele toepassingen van het Web om, tot ontvangers, leveringen, campagnes, voorraden, enz. toegang te hebben te beheren en in wisselwerking te staan. Deze worden in de interface weergegeven in de vorm van dashboards met slechts één pagina.

De ingebouwde toepassingen van het Web worden opgeslagen in **Beheer > Configuratie > Webtoepassingen** map van de Explorer.

Leer hoe u een overzichtspagina maakt in Campagne in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html#creating-a-single-page-web-application){target="_blank"}


## Lijsten aanpassen en filters maken {#gs-lists-and-filters}

Campagnemelijsten worden geleverd met vooraf gedefinieerde filters om navigatie en gegevensvizualisatie te vergemakkelijken.

Wanneer u in de boom van de Ontdekkingsreiziger van Adobe Campaign navigeert, worden de gegevens in het gegevensbestand getoond in lijsten. U kunt deze lijsten filteren, zoekopdrachten uitvoeren, informatie toevoegen, filteren en sorteren.

Leer hoe te om lijsten te vormen en een lijstconfiguratie te bewaren in [deze pagina](../start/campaign-ui.md).

U kunt filter op deze lijsten toepassen om alleen de gegevens weer te geven die de operator nodig heeft. Dan kunnen de acties op de gefiltreerde gegevens worden uitgevoerd. Met filterconfiguratie kunt u dynamisch gegevens in een lijst selecteren. Als de gegevens worden gewijzigd, worden de gefilterde gegevens bijgewerkt.

Meer informatie over filteropties in [deze pagina](../audiences/create-filters.md).
