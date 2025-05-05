---
title: Instantie aanpassen
description: Leer hoe u uw exemplaar kunt aanpassen
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Instantie aanpassen {#gs-ac-custom}

Leer hoe te **uw instantie van de Campagne** aanpassen.

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

* Door de interface, door het **Nieuwe gebied** medewerker te gebruiken

  Leer hoe te om een nieuw gebied in Campagne in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=nl-NL#configuring-campaign-classic){target="_blank"} snel toe te voegen 

* Programmaticaal, door het schema uit te breiden. Leer hoe te om een bestaand schema in [ uit te breiden deze sectie ](../dev/extend-schema.md).

U kunt ook nieuwe tabellen maken in de Campagne-database en het ingebouwde gegevensmodel uitbreiden.

Als u een geheel nieuw type gegevens wilt toevoegen dat niet in Adobe Campaign buiten het vak bestaat (bijvoorbeeld een contracttabel), kunt u rechtstreeks een aangepast schema maken. Voor meer op dit, verwijs naar [ dit voorbeeld ](../dev/create-schema.md#example--creating-a-contract-table).

**Verwante onderwerpen**

Voorbeeld van schemageditie in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=nl-NL#configuring-campaign-classic){target="_blank"} 

Het Geval van het gebruik: verbind een gebied met een bestaande verwijzingstabel in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=nl-NL#uc-link){target="_blank"} 


## Invoerformulieren wijzigen

Invoerformulieren voor campagnes kunnen worden aangepast aan uw implementatie. U kunt formuliervelden toevoegen of verwijderen door de XML-inhoud te wijzigen.

Leer hoe te om een bestaande inputvorm te wijzigen of een nieuwe vorm in [ tot stand te brengen deze sectie ](../dev/forms.md).

## dashboards aanpassen{#gs-custom-dashboards}

De interface van Adobe Campaign gebruikt vele toepassingen van het Web om, tot ontvangers, leveringen, campagnes, voorraden, enz. toegang te hebben te beheren en in wisselwerking te staan. Deze worden in de interface weergegeven in de vorm van dashboards met slechts één pagina.

De ingebouwde toepassingen van het Web worden opgeslagen in het **Beleid > Configuratie > de toepassingen van het Web** omslag van de Ontdekkingsreiziger.

Leer hoe te om een overzichtspagina in Campagne in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=nl-NL#creating-a-single-page-web-application){target="_blank"} tot stand te brengen 


## Lijsten aanpassen en filters maken {#gs-lists-and-filters}

Campagnemelijsten worden geleverd met vooraf gedefinieerde filters om navigatie en gegevensvizualisatie te vergemakkelijken.

Wanneer u in de boom van de Ontdekkingsreiziger van Adobe Campaign navigeert, worden de gegevens in het gegevensbestand getoond in lijsten. U kunt deze lijsten filteren, zoekopdrachten uitvoeren, informatie toevoegen, filteren en sorteren.

Leer hoe te om lijsten te vormen en een lijstconfiguratie in [ te bewaren deze pagina ](../start/campaign-ui.md).

U kunt filter op deze lijsten toepassen om alleen de gegevens weer te geven die de operator nodig heeft. Dan kunnen de acties op de gefiltreerde gegevens worden uitgevoerd. Met filterconfiguratie kunt u dynamisch gegevens in een lijst selecteren. Als de gegevens worden gewijzigd, worden de gefilterde gegevens bijgewerkt.

Leer meer over het filtreren opties in [ deze pagina ](../audiences/create-filters.md).
