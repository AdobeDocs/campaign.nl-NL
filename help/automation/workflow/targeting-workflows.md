---
title: Workflows maken die als doel dienen
description: Leer hoe u doelpubliek kunt maken in een workflow
feature: Query Editor, Data Management
exl-id: 27be9d5a-168c-470e-a480-f3c71858fc75
source-git-commit: c3f4ad0b56dd45d19eebaa4d2f06551c8fecac1d
workflow-type: tm+mt
source-wordcount: '2252'
ht-degree: 4%

---

# Een targetingworkflow maken{#target-data}

De werkstroom kan worden gebruikt om het gegevensbestand te vragen en uw gegevens te segmenteren. De het werkschemamodule van de campagne is een krachtig hulpmiddel om gegevensbeheeractiviteiten uit te voeren, gegevens te halen te verrijken en om te zetten, publiek te beheren, en populaties te verfijnen.

Met doelgerichte workflows kunt u verschillende leveringsdoelen maken. U kunt query&#39;s maken, samenvoegingen of uitsluitingen definiëren op basis van specifieke criteria, planning toevoegen dankzij workflowactiviteiten. Het resultaat van deze gerichte actie kan automatisch worden overgedragen naar een lijst die als doel van leveringsacties kan dienen

Naast deze activiteiten kunt u met de opties voor gegevensbeheer gegevens manipuleren en geavanceerde functies gebruiken om complexe doelproblemen op te lossen. Raadpleeg voor meer informatie hierover [Gegevensbeheer](targeting-workflows.md#data-management).

Al deze activiteiten vindt u op het eerste tabblad van de workflow.

>[!NOTE]
>
>De gerichte activiteiten worden nader beschreven in [deze sectie](activities.md).

Doelworkflows kunnen worden gemaakt en bewerkt via de **[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]** knooppunt van de Adobe Campaign-boom of via de **[!UICONTROL Profiles and Targets > Targeting workflows]** menu van de startpagina.

![](assets/target_wf.png)

Het richten van werkschema&#39;s binnen het kader van een campagne wordt opgeslagen met alle campagnewerkschema&#39;s.

## Belangrijke stappen om een doelworkflow te maken {#implementation-steps-}

De stappen voor het maken van een doelworkflow worden in de volgende secties beschreven:

1. **Identificeren** gegevens in de database - Zie [Query&#39;s maken](#create-queries)
1. **Voorbereiden** gegevens om aan de leveringsbehoeften te voldoen - Zie [Gegevens verrijken en wijzigen](#enrich-and-modify-data)
1. **Gebruiken** gegevens om updates of levering uit te voeren - Zie [De database bijwerken](use-workflow-data.md#update-the-database)

De resultaten van alle verrijkingen en alle handgrepen die tijdens het richten worden uitgevoerd worden opgeslagen en toegankelijk op verpersoonlijkingsgebieden, met name voor gebruik wanneer het creëren van gepersonaliseerde berichten. Raadpleeg voor meer informatie hierover [Doelgegevens](use-workflow-data.md#target-data).

## Afmetingen gericht en filteren {#targeting-and-filtering-dimensions}

Tijdens de verrichtingen van de gegevenssegmentatie, wordt de het richten sleutel in kaart gebracht aan een het filtreren dimensie. Met de doeldimensie kunt u de doelgroep van de actie definiëren: ontvangers, begunstigden van contracten, exploitant, abonnees, enz. Met de filterdimensie kunt u de populatie selecteren op basis van bepaalde criteria: contractanten, abonnees van nieuwsbrieven, enz.

Als u bijvoorbeeld klanten wilt selecteren die al meer dan vijf jaar een levensverzekeringspolis hebben, selecteert u de volgende dimensie: **Clients** en de volgende filterdimensie: **Contracthouder**. U kunt de het filtreren voorwaarden binnen de vraagactiviteit dan bepalen

Tijdens het gericht afmetingsselectiefase, slechts worden de compatibele het filtreren dimensies aangeboden in de interface.

Deze twee dimensies moeten met elkaar verband houden. De inhoud van de **[!UICONTROL Filtering dimension]** de lijst is afhankelijk van de doeldimensie die in het eerste veld is opgegeven.

Voor ontvangers (**ontvanger**), zijn de volgende filterafmetingen beschikbaar:

![](assets/query-filter-dimensions.png)

While for **Bezoekers** bevat de lijst de volgende filterafmetingen:

![](assets/query-filter-dimension-2.png)

## Query&#39;s maken {#create-queries}

### Werken met aanvullende gegevens {#select-data}

A **[!UICONTROL Query]** Met activiteit kunt u basisgegevens selecteren om de doelpopulatie samen te stellen. Raadpleeg [deze sectie](query.md#create-a-query) voor meer informatie.

U kunt ook de volgende activiteiten gebruiken om gegevens in de database te zoeken en te verfijnen: [Incrementele query](incremental-query.md), [Leeslijst](read-list.md).

Het is mogelijk aanvullende gegevens te verzamelen die gedurende de gehele levenscyclus van de werkstroom moeten worden doorgestuurd en verwerkt. Raadpleeg voor meer informatie hierover [Gegevens toevoegen](query.md#add-data) en [Aanvullende gegevens bewerken](#edit-additional-data).

### Aanvullende gegevens bewerken {#edit-additional-data}

Zodra extra gegevens zijn toegevoegd, kunt u het uitgeven of het gebruiken om het doel te raffineren dat in de vraagactiviteit wordt bepaald.

De **[!UICONTROL Edit additional data...]** Met de koppeling kunt u de toegevoegde gegevens weergeven en wijzigen of toevoegen.

![](assets/edit-additional-data.png)

Als u gegevens wilt toevoegen aan de eerder gedefinieerde uitvoerkolommen, selecteert u deze in de lijst met beschikbare velden. Als u een nieuwe uitvoerkolom wilt maken, klikt u op de knop **[!UICONTROL Add]** en selecteert u het veld en klikt u op **[!UICONTROL Edit expression]**.

![](assets/query_add_an_output_column.png)

Klik op de knop **Geavanceerde selectie** knop.

![](assets/query_add_an_output_column_formula.png)

Definieer een berekeningsmodus voor het veld dat moet worden toegevoegd, zoals bijvoorbeeld een aggregaat.

![](assets/query_add_aggregate.png)

De **[!UICONTROL Add a sub-item]** kunt u berekende gegevens aan de verzameling koppelen. Hiermee kunt u de aanvullende gegevens uit de verzameling selecteren of geaggregeerde berekeningen voor verzamelingselementen definiëren.

De subelementen worden weergegeven in de substructuur van de verzameling waaraan ze zijn toegewezen.

Verzamelingen worden weergegeven in het dialoogvenster **[!UICONTROL Collections]** subtab. U kunt de verzamelde elementen filteren door op de knop **[!UICONTROL Detail]** pictogram van de geselecteerde verzameling. Met de filterwizard kunt u de verzamelde gegevens selecteren en de filtervoorwaarden opgeven die op de gegevens in de verzameling moeten worden toegepast.

### Een doel verfijnen met behulp van aanvullende gegevens {#refine-the-target-using-additional-data}

De extra verzamelde gegevens kunnen u toelaten om gegevens het filtreren in het gegevensbestand te verfijnen. Om dit te doen, klik **[!UICONTROL Refine the target using additional data...]** koppeling: hiermee kunt u de toegevoegde gegevens overschrijven.

![](assets/wf_add_data_use_additional_data.png)

### Gegevens homogeniseren {#homogenize-data}

In **[!UICONTROL Union]** of **[!UICONTROL Intersection]** type activiteiten, kunt u verkiezen om slechts gedeelde extra gegevens te houden om de gegevens verenigbaar te houden. In dit geval bevat de tijdelijke uitvoerwerktabel van deze activiteit alleen de aanvullende gegevens die in alle binnenkomende sets worden gevonden.

![](assets/use-common-add-data-only.png)

### Afstemmen met aanvullende gegevens {#reconciliation-with-additional-data}

Tijdens de afstemmingsfasen (**[!UICONTROL Union]**, **[!UICONTROL Intersection]**, enz. activiteiten) selecteert u de kolommen die u wilt gebruiken voor het afstemmen van gegevens in de extra kolommen. Hiertoe configureert u een afstemming op een selectie van kolommen en geeft u de hoofdset op. Selecteer vervolgens de kolommen in de onderste kolom van het venster, zoals in het volgende voorbeeld wordt getoond:

![](assets/select-column-and-join.png)

Selecteer een expressie en bevestig deze.

![](assets/select-column-and-join-2.png)


### Subsets maken {#create-subsets}

De **[!UICONTROL Split]** Met activiteit kunt u subsets maken op criteria die zijn gedefinieerd via extractiemery&#39;s. Voor elke ondergroep, wanneer u een filtervoorwaarde op de bevolking uitgeeft, zult u tot de standaardvraagactiviteit toegang hebben die u de voorwaarden van de doelsegmentatie laat bepalen.

U kunt een doel in verscheidene subsets verdelen gebruikend slechts extra gegevens als het filtreren voorwaarden, of naast doelgegevens. U kunt ook externe gegevens gebruiken als u de **Federale gegevenstoegang** -optie.

Raadpleeg [deze sectie](#create-subsets-using-the-split-activity) voor meer informatie.

## Segmentgegevens {#segment-data}

### Verschillende doelen combineren (Unie) {#combine-several-targets--union-}

Met de vakbondsactiviteit kunt u het resultaat van verschillende activiteiten in één overgang combineren. Stellen hoeven niet noodzakelijkerwijs homogeen te zijn.

![](assets/union-keys-only.png)

De volgende afstemmingsopties voor gegevens zijn beschikbaar:

* **[!UICONTROL Keys only]**

  Deze optie kan worden gebruikt als de inputpopulaties homogeen zijn.

* **[!UICONTROL All columns in common]**

  Met deze optie kunt u gegevens afstemmen op basis van alle kolommen die de verschillende populaties van het doel gemeen hebben.

  Adobe Campaign geeft kolommen aan op basis van hun naam. Een tolerantiedrempel wordt geaccepteerd: een kolom &#39;E-mail&#39; kan bijvoorbeeld worden herkend als identiek aan een kolom &#39;@email&#39;.

* **[!UICONTROL A selection of columns]**

  Selecteer deze optie om de lijst met kolommen te definiëren waarop de afstemming van gegevens wordt toegepast.

  Begin door de belangrijkste reeks (die bevat de brongegevens) te selecteren, dan de kolommen die voor de verbinding moeten worden gebruikt.

  ![](assets/join-reconciliation-options.png)

  >[!CAUTION]
  >
  >Tijdens de afstemming van gegevens worden populaties niet gededupliceerd.

  U kunt de populatiegrootte tot een bepaald aantal verslagen beperken. Klik hiertoe op de gewenste optie en geef het aantal records op dat u wilt behouden.

  Geef ook de prioriteit van de binnenkomende populaties op: in de onderste sectie van het venster worden de binnenkomende overgangen van de samenvoegactiviteit weergegeven en kunt u deze sorteren met de blauwe pijlen rechts van het venster.

  De gegevens worden eerst overgenomen uit de populatie van de eerste binnenkomende overgang in de lijst. Als het maximum niet is bereikt, worden ze onttrokken aan de populatie van de tweede binnenkomende overgang, enz.

  ![](assets/join_limit_nb_priority.png)

### Verbindingsgegevens extraheren (doorsnede) {#extract-joint-data--intersection-}

![](assets/traitements.png)

Met het snijpunt kunt u alleen de regels herstellen die worden gedeeld door de populaties van binnenkomende overgangen. Deze activiteit moet als vakbondsactiviteit worden gevormd.

Bovendien is het mogelijk om slechts een selectie van kolommen te houden, of slechts de kolommen die door de binnenkomende bevolking worden gedeeld.

De intersectieactiviteit wordt beschreven in de [Intersectie](intersection.md) sectie.

### Een populatie uitsluiten (Uitsluiting) {#exclude-a-population--exclusion-}

Met de uitsluitingsactiviteit kunt u de elementen van een doel uitsluiten van een andere doelpopulatie. De doeldimensie van deze activiteit is die van de hoofdset.

Indien nodig, is het mogelijk om binnenkomende lijsten te manipuleren. Om een doel van een andere dimensie uit te sluiten, moet dit doel worden teruggebracht naar dezelfde doeldimensie als het hoofddoel. Klik op de knop **[!UICONTROL Add]** en geeft u de voorwaarden voor het wijzigen van de afmetingen op.

Afstemming van gegevens vindt plaats via een id, een veranderende as of een samenvoeging.

![](assets/exclusion-add-rule.png)

### Subsets maken met de splitsingsactiviteit {#create-subsets-using-the-split-activity}

De **[!UICONTROL Split]** activiteit is een standaardactiviteit die u zo vele reeksen door één of verscheidene het filtreren dimensies zonodig, evenals het produceren van of één outputovergang per ondergroep of een unieke overgang laat tot stand brengen.

De extra gegevens die door de binnenkomende overgang worden overgebracht kunnen in de het filtreren criteria worden gebruikt.

Om het te vormen, moet u eerst criteria selecteren:

1. Sleep een **[!UICONTROL Split]** activiteit.
1. In de **[!UICONTROL General]** selecteert u de gewenste optie: **[!UICONTROL Use data from the target and additional data]**, **[!UICONTROL Use the additional data only]** of **[!UICONTROL Use external data]**.
1. Als de **[!UICONTROL Use data from the target and additional data]** Als deze optie is geselecteerd, kunt u met de doeldimensie alle gegevens gebruiken die door de binnenkomende overgang worden overgedragen.

   ![](assets/split-general-tab-options.png)

   Wanneer subsets worden gemaakt, worden de eerder vermelde filterparameters gebruikt.

   Als u filtervoorwaarden wilt definiëren, kiest u de **[!UICONTROL Add a filtering condition on the inbound population]** en klik op de knop **[!UICONTROL Edit...]** koppeling. Geef vervolgens de filtervoorwaarden op voor het maken van deze subset.

   ![](assets/split-subset-config-all-data.png)

   Een voorbeeld waarin wordt getoond hoe filtervoorwaarden in het dialoogvenster **[!UICONTROL Split]** de activiteit om het doel in verschillende populaties te segmenteren, wordt beschreven in [deze sectie](cross-channel-delivery-workflow.md).

   De **[!UICONTROL Label]** in dit veld geeft u de nieuwe subset een naam die overeenkomt met de uitgaande overgang.

   U kunt ook een segmentcode aan de subset toewijzen om deze te identificeren en te gebruiken om de populatie te bepalen.

   Indien nodig, kunt u de het richten en het filtreren dimensies individueel voor elke ondergroep veranderen u wilt tot stand brengen. Om dit te doen, geef de het filtreren voorwaarde van de ondergroep uit en controleer **[!UICONTROL Use a specific filtering dimension]** -optie.

   ![](assets/split-subset-config-specific-filtering.png)

1. Als de **[!UICONTROL Use the additional data only]** is geselecteerd, worden alleen aanvullende gegevens voor filteren van subsets aangeboden.

1. Als de **Federale gegevenstoegang** -optie is ingeschakeld, wordt de **[!UICONTROL Use external data]** Hiermee kunt u gegevens verwerken in een externe database die al is geconfigureerd, of een nieuwe verbinding met een database maken.

Vervolgens moeten nieuwe subsets worden toegevoegd:

1. Klik op de knop **[!UICONTROL Add]** en definieert u de filtervoorwaarden.

   ![](assets/wf_split_add_a_tab.png)

1. Definieer de filterdimensie in het dialoogvenster **[!UICONTROL General]** tabblad van de activiteit (zie boven).Deze is standaard van toepassing op alle subsets.

   ![](assets/wf_split_edit_filtering.png)

1. Indien nodig kunt u de filterdimensie voor elke subset afzonderlijk wijzigen. Hiermee kunt u een set maken voor alle houders van een Gold-kaart, één voor alle ontvangers die op de meest recente nieuwsbrief hebben geklikt en een derde voor personen van 18 tot en met 25 jaar die de laatste 30 dagen in de winkel een aankoop hebben gedaan, allemaal met dezelfde gesplitste activiteit. Selecteer de optie **[!UICONTROL Use a specific filtering dimension]** en selecteert u de context voor het filteren van gegevens.

Nadat subsets zijn gemaakt, toont de splitsingsactiviteit standaard evenveel uitvoerovergangen als er subsets zijn:

![](assets/wf_split_multi_outputs.png)

U kunt al deze subsets groeperen in één uitvoerovergang. In dit geval is de koppeling naar de desbetreffende subsets bijvoorbeeld zichtbaar in de segmentcode. Selecteer de optie **[!UICONTROL Generate all subsets in the same table]** -optie.

![](assets/wf_split_single_output.png)

Bijvoorbeeld, kunt u één enkele leveringsactiviteit plaatsen en de leveringsinhoud personaliseren die op de segmentcode van elke ontvankelijke reeks wordt gebaseerd.


Subsets kunnen ook worden gemaakt met de opdracht **[!UICONTROL Cells]** activiteit. Raadpleeg voor meer informatie de [Cellen](cells.md) sectie.

### Doelgegevens gebruiken {#using-targeted-data}

Zodra de gegevens zijn geïdentificeerd en opgesteld, kunnen ze in de volgende context worden gebruikt:

* U kunt de gegevens in de database bijwerken na gegevensmanipulatie in de verschillende werkstroomfasen.

  Voor meer informatie hierover: [Gegevens bijwerken](update-data.md).

* U kunt ook de inhoud van bestaande lijsten vernieuwen.

  Raadpleeg voor meer informatie hierover [Lijstupdate](list-update.md).

* U kunt leveringen rechtstreeks voorbereiden of starten in de workflow.

  Raadpleeg voor meer informatie hierover [Aflevering](delivery.md), [Afleveringscontrole](delivery-control.md) en [Doorlopende levering](continuous-delivery.md).

## Data management {#data-management}

In Adobe Campaign combineert het gegevensbeheer een reeks activiteiten om complexe doelgerichte problemen op te lossen door efficiëntere en flexibelere hulpmiddelen aan te bieden. Dit laat u verenigbaar beheer van alle communicatie met een contact uitvoeren gebruikend informatie met betrekking tot hun contracten, abonnementen, reactiviteit aan leveringen, enz. Met data management kunt u de levenscyclus van data bijhouden tijdens segmentatiebewerkingen, met name:

* Het vereenvoudigen en optimaliseren van targetingprocessen, door data op te nemen die niet in de datamart worden gemodelleerd (het maken van nieuwe tabellen: lokale extensie voor elke targetingworkflow afhankelijk van de configuratie).
* Het bijhouden en overbrengen van bufferberekeningen, vooral tijdens fasen voor de opbouw van doelen of voor databasebeheer.
* Het openen van externe databases (optioneel): heterogene databases waarmee tijdens het targetingproces rekening wordt gehouden.

Voor de uitvoering van deze transacties biedt Adobe Campaign:

* Gegevensverzameling: [Bestandsoverdracht](file-transfer.md), [Gegevens laden (bestand)](data-loading-file.md), [Gegevens laden (RDBMS)](data-loading-rdbms.md), [Gegevens bijwerken](update-data.md). In deze eerste stap voor het verzamelen van gegevens worden de gegevens voorbereid, zodat ze in andere activiteiten kunnen worden verwerkt. Verschillende parameters moeten worden gecontroleerd om ervoor te zorgen dat de workflow correct wordt uitgevoerd en de verwachte resultaten oplevert. Wanneer u bijvoorbeeld gegevens importeert, moet de primaire sleutel (sleutel) voor deze gegevens uniek zijn voor elke record.
* Doelactiviteiten zijn verrijkt met opties voor gegevensbeheer: [Query](query.md), [Unie](union.md), [Intersectie](intersection.md), [Splitsen](split.md). Zo kunt u een samenvoeging of een doorsnede configureren tussen gegevens van verschillende doeldimensies, zolang de gegevens met elkaar in overeenstemming kunnen worden gebracht.
* Transformatie van gegevens: [Verrijking](enrichment.md), [Dimensie wijzigen](change-dimension.md).

>[!CAUTION]
>
>Wanneer twee workflows zijn gekoppeld, betekent het verwijderen van een brontabelelement niet dat alle gegevens die eraan zijn gekoppeld, worden verwijderd.
>  
>Als u bijvoorbeeld een ontvanger verwijdert via een workflow, wordt niet alle leveringsgeschiedenis van de ontvanger verwijderd. Als u echter een ontvanger rechtstreeks in de map &#39;Ontvangers&#39; verwijdert, worden alle gegevens die aan deze ontvanger zijn gekoppeld, ook verwijderd.

### Gegevens verrijken en wijzigen {#enrich-and-modify-data}

Naast het richten afmeting, laat de het filtreren afmeting u de aard van de verzamelde gegevens specificeren. Zie [deze sectie](targeting-workflows.md#targeting-and-filtering-dimensions).

De geïdentificeerde en verzamelde gegevens kunnen worden verrijkt, geaggregeerd en gemanipuleerd om de doelconstructie te optimaliseren. Hiervoor geldt, naast de in [deze sectie](#segmen-data)en gebruikt u het volgende:

* De **[!UICONTROL Enrichment]** Met activiteit kunt u tijdelijk kolommen aan een schema toevoegen en informatie aan bepaalde elementen toevoegen. Het wordt in het [Verrijking](enrichment.md) van de gegevensbank van activiteiten.
* De **[!UICONTROL Edit schema]** Met activiteit kunt u de structuur van een schema wijzigen. Het wordt in het [Schema bewerken](edit-schema.md) van de gegevensbank van activiteiten.
* De **[!UICONTROL Change dimension]** Met activiteit kunt u de doeldimensie tijdens de ontwerpcyclus wijzigen. Het wordt in het [Dimensie wijzigen](change-dimension.md) sectie.
