---
title: Best practices voor het gegevensmodel
description: Meer informatie over tips en trucs voor extensies van Campagne-gegevensmodellen
feature: Data Model
role: User, Developer
level: Beginner, Intermediate
exl-id: bdd5e993-0ce9-49a8-a618-ab0ff3796d49
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '2740'
ht-degree: 4%

---

# Best practices voor het gegevensmodel {#data-model-best-practices}

Dit document bevat belangrijke aanbevelingen bij het ontwerpen van uw Adobe Campaign-gegevensmodel.

Het Adobe Campaign-systeem is zeer flexibel en kan verder worden uitgebreid dan de eerste implementatie. Hoewel de mogelijkheden oneindig zijn, is het echter van essentieel belang om verstandige beslissingen te nemen en sterke fundamenten te leggen voor het ontwerpen van uw gegevensmodel.

Voor een beter begrip van de ingebouwde lijsten van de Campagne en hoe zij met elkaar betrekking hebben, verwijs naar [ deze sectie ](datamodel.md).

Lees uit [ deze sectie ](schemas.md) om met de schema&#39;s van de Campagne begonnen te worden.

Leer hoe te om uitbreidingsschema&#39;s te vormen om het conceptuele gegevensmodel van het gegevensbestand van Adobe Campaign in [ uit te breiden deze pagina ](extend-schema.md).

## Gegevensmodelarchitectuur {#data-model-architecture}

Adobe Campaign is een krachtig campagnebeheersysteem voor meerdere kanalen waarmee u uw online- en offlinestrategieën kunt uitlijnen en persoonlijke ervaringen voor klanten kunt creëren.

### klantgerichte benadering {#customer-centric-approach}

Hoewel de meeste e-mailserviceproviders via een lijstgerichte aanpak communiceren met klanten, vertrouwt Adobe Campaign op een relationele database om een bredere visie op de klanten en hun kenmerken te kunnen gebruiken.

Ga naar **[!UICONTROL Admin > Configuration > Data schemas]** om de beschrijving van elke tabel te openen, selecteer een bron in de lijst en klik op de tab **[!UICONTROL Documentation]** .


>[!NOTE]
>
>Adobe Campaign staat toe om a [ douane ontvankelijke lijst ](custom-recipient.md) te bouwen. Nochtans, in de meeste gevallen, wordt het geadviseerd om de ingebouwde [ Ontvanger lijst ](datamodel.md#ootb-profiles) te hefboomwerking die reeds extra lijsten en eigenschappen heeft vooraf gebouwd.

### Gegevens voor Adobe Campaign {#data-for-campaign}

Welke gegevens moeten naar Adobe Campaign worden verzonden? Het is van essentieel belang om de gegevens te bepalen die nodig zijn voor uw marketingactiviteiten.

>[!NOTE]
>
>Adobe Campaign is geen data-entrepot of rapportageinstrument. Probeer daarom niet alle mogelijke klanten en hun bijbehorende informatie in Adobe Campaign in te voeren, of gegevens in te voeren die slechts zullen worden gebruikt om rapporten te bouwen.

Om te beslissen of een attribuut al dan niet nodig zou zijn in Adobe Campaign, vraag uzelf of het onder één van deze categorieën zou vallen:

* Attribuut dat voor **wordt gebruikt segmentatie**
* Attribuut dat voor **wordt gebruikt gegevensbeheerprocessen** (gezamenlijke berekening bijvoorbeeld)
* Attribuut dat voor **wordt gebruikt verpersoonlijking**

Als er niet in een van deze elementen valt, hebt u deze eigenschap waarschijnlijk niet nodig in Adobe Campaign.

### Keuze van gegevenstypen {#data-types}

Volg de onderstaande aanbevolen procedures om gegevens in te stellen in Adobe Campaign om een goede architectuur en prestaties van uw systeem te garanderen.

* In de grote tabel kunt u tekenreeks- of numerieke velden invoegen en koppelingen toevoegen naar referentietabellen (wanneer u werkt met een lijst met waarden).
* Het **expr** attribuut staat toe om een schemaattribuut als berekend gebied eerder dan een fysieke vastgestelde waarde in een lijst te bepalen. Hierdoor kan toegang tot de informatie in een ander formaat mogelijk zijn (bijvoorbeeld voor leeftijd en geboortedatum) zonder dat beide waarden moeten worden opgeslagen. Dit is een goede manier om te voorkomen dat velden worden gekopieerd. De tabel Ontvanger gebruikt bijvoorbeeld een expressie voor het domein, die al aanwezig is in het e-mailveld.
* Nochtans, wanneer de uitdrukkingsberekening complex is, wordt het niet geadviseerd om het **expr** attribuut te gebruiken aangezien de berekening ter plaatse de prestaties van uw vragen kan beïnvloeden.
* Het **type van XML** is een goede manier te vermijden creërend teveel gebieden. Maar het neemt ook schijfruimte op aangezien het een kolom CLOB in het gegevensbestand gebruikt. Het kan ook tot complexe SQL vragen leiden en prestaties kunnen beïnvloeden.
* De lengte voor a **koord** gebied zou altijd met de kolom moeten worden bepaald. Standaard is de maximumlengte in Adobe Campaign 16K, maar Adobe raadt u aan het veld korter te houden als u al weet dat de grootte een kortere lengte niet overschrijdt.
* Het is acceptabel om in Adobe Campaign een veld te hebben dat korter is dan in het bronsysteem als u er zeker van bent dat de grootte in het bronsysteem is overschat en niet zou worden bereikt. Dit kan een kortere tekenreeks of een kleiner geheel getal in Adobe Campaign betekenen.

### Keuze van velden {#choice-of-fields}

Een veld moet in een tabel worden opgeslagen als het een doel of een doel voor personalisatie heeft. Met andere woorden, als een gebied niet wordt gebruikt om een gepersonaliseerde e-mail te verzenden of als criterium in een vraag wordt gebruikt, zal het onnodig schijfruimte opnemen.

### Keuze van sleutels {#choice-of-keys}

Naast **autoUtouuid** en **automatisch** die door gebrek in de meeste lijsten wordt bepaald, zou u moeten overwegen één of andere logische of bedrijfssleutels (rekeningsaantal, cliëntaantal, etc.) toe te voegen. Het kan later worden gebruikt voor invoer/verzoening of gegevenspakketten. Voor meer op dit, zie [ Herkenningstekens ](#identifiers).

Efficiënte toetsen zijn essentieel voor de prestaties. Met Snowflake kunt u numerieke of op tekenreeks gebaseerde gegevenstypen invoegen als sleutels voor tabellen.

>[!NOTE]
>
>Het **autouuid** attribuut is slechts op [ de plaatsingen van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md) van toepassing.

## Id&#39;s {#identifiers}

Adobe Campaign-bronnen hebben drie id&#39;s en u kunt een extra id toevoegen.

In de volgende tabel worden deze id&#39;s en hun doel beschreven.

| Id | Beschrijving | Best practices |
|--- |--- |--- |
| Id | <ul><li>De id is de fysieke primaire sleutel van een Adobe Campaign-tabel. Voor ingebouwde tabellen is dit een universeel unieke id (UUID)</li><li>Deze id moet uniek zijn. </li><li>Een UUID kan in een schemadefinitie zichtbaar zijn.</li></ul> | <ul><li>Automatisch gegenereerde id&#39;s mogen niet worden gebruikt als een referentie in een workflow of in een pakketdefinitie.</li><li>De id in een tabel is een UUID en dit type mag niet worden gewijzigd.</li></ul> |
| Naam (of interne naam) | <ul><li>Deze informatie is een unieke id van een record in een tabel. Deze waarde kan handmatig worden bijgewerkt, meestal met een gegenereerde naam.</li><li>Deze id behoudt zijn waarde wanneer deze wordt geïmplementeerd in een andere instantie van Adobe Campaign en mag niet leeg zijn.</li></ul> | <ul><li>Wijzig de naam van de record die wordt gegenereerd door Adobe Campaign als het object moet worden geïmplementeerd vanuit een omgeving naar een andere.</li><li>Wanneer een voorwerp een namespace attribuut (*schema* bijvoorbeeld) heeft, zal dit gemeenschappelijke namespace over alle gecreeerde douanevoorwerpen leveraged worden. Sommige gereserveerde namespaces zouden niet moeten worden gebruikt: *nms*, *xtk*, enz.  Sommige naamruimten zijn alleen intern. [Meer informatie](schemas.md#reserved-namespaces).</li><li>Wanneer een voorwerp geen namespace (*werkschema* of *levering* bijvoorbeeld) heeft, zou dit namespace begrip als prefix van een intern naamobject worden toegevoegd: *namespaceMyObjectName*.</li><li>Gebruik geen speciale tekens zoals spatie &quot;&quot;, puntkolom &quot;:&quot; of afbreekstreepje &quot;-&quot;. Al deze tekens worden vervangen door een onderstrepingsteken &quot;_&quot; (toegestaan teken). &quot;abc-def&quot; en &quot;abc:def&quot; worden bijvoorbeeld opgeslagen als &quot;abc_def&quot; en worden elkaar overschreven.</li></ul> |
| Label | <ul><li>Het label is de bedrijfsidentificatie van een object of record in Adobe Campaign.</li><li>Voor dit object zijn spaties en speciale tekens toegestaan.</li><li>Het garandeert niet dat een record uniek is.</li></ul> | <ul><li>Het wordt aanbevolen een structuur voor de objectlabels te bepalen.</li><li>Dit is de meest gebruikersvriendelijke oplossing om een record of object voor een Adobe Campaign-gebruiker te identificeren.</li></ul> |

In de context van een [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), is de primaire sleutel van Adobe Campaign auto-geproduceerde UUID voor alle ingebouwde lijsten. Een UUID kan ook worden gebruikt voor aangepaste tabellen. [Meer informatie](../architecture/keys.md)

Zelfs als het aantal id&#39;s oneindig is, moet u de grootte van uw database in acht nemen om optimale prestaties te garanderen. Om problemen te voorkomen, moet u de instellingen voor het opschonen van de instantie aanpassen. Zie [deze sectie](#data-retention)voor meer informatie.


## Aangepaste interne sleutels {#custom-internal-keys}

Voor elke tabel die in Adobe Campaign wordt gemaakt, zijn primaire sleutels vereist.

De meeste organisaties voeren verslagen van externe systemen in. Terwijl de fysieke sleutel van de Ontvangerlijst het &quot;id&quot;attribuut is, is het mogelijk om een douanetoets extra te bepalen.

Deze aangepaste sleutel is de werkelijke primaire sleutel van de record in het externe systeem dat Adobe Campaign voedt.

Bij het maken van een aangepaste tabel hebt u twee opties:
* Een combinatie van automatisch gegenereerde sleutel (id) en interne sleutel (aangepast). Deze optie is interessant als uw systeemsleutel een samengestelde sleutel of niet een geheel is. Met Snowflake kunnen gehele getallen of tekenreekssleutels hogere prestaties leveren in grote tabellen en kunnen ze worden gecombineerd met andere tabellen.
* De primaire sleutel gebruiken als de primaire sleutel van het externe systeem. Deze oplossing heeft doorgaans de voorkeur, omdat deze de aanpak van het importeren en exporteren van gegevens vereenvoudigt, met een consistente sleutel tussen verschillende systemen. **Autouuid** zou moeten worden onbruikbaar gemaakt als de sleutel &quot;identiteitskaart&quot;genoemd wordt en verwacht om met externe waarden (niet auto-geproduceerd) te worden gevuld.

>[!CAUTION]
>
>* Een autoID zou niet als verwijzing in werkschema&#39;s moeten worden gebruikt.
> * Het **autouuid** attribuut is slechts op [ de plaatsingen van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md) van toepassing.
>

## Koppelingen en kardinaliteit {#links-and-cardinality}

### Koppelingen {#links}

Let op de &#39;eigen&#39; integriteit voor grote tabellen. Het schrappen van verslagen die grote lijsten in &quot;eigen&quot;integriteit hebben kan de instantie potentieel tegenhouden. De tabel is vergrendeld en de verwijderingen worden een voor een gemaakt. Het is dus beter om &quot;neutrale&quot;integriteit op kindlijsten te gebruiken die grote volumes hebben.

Het declareren van een koppeling als externe verbinding is niet geschikt voor de prestaties. De nul-id verslag emuleert de externe aansluit zich aan bij functionaliteit. In de context van een [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), is het niet noodzakelijk om externe te verklaren toetreedt als de verbinding **autouuid** gebruikt.

Hoewel het mogelijk is om zich aan te sluiten bij een tabel in een workflow, raadt Adobe aan om gemeenschappelijke koppelingen tussen bronnen rechtstreeks in de definitie van de gegevensstructuur te definiëren.

De verbinding zou in groepering met de daadwerkelijke gegevens in uw lijsten moeten worden bepaald. Een verkeerde definitie kan van invloed zijn op gegevens die via koppelingen zijn opgehaald, bijvoorbeeld gegevens die onverwacht worden gedupliceerd.

Geef de koppeling een naam die consistent is met de tabelnaam: de naam van de koppeling moet u helpen begrijpen wat de verafgelegen tabel is.

Geef een koppeling met &quot;id&quot; geen naam als achtervoegsel. Geef de naam bijvoorbeeld &quot;transactie&quot; en niet &quot;transactie-id&quot;.

Adobe Campaign maakt standaard een koppeling met de primaire sleutel van de externe tabel. Voor meer duidelijkheid, is het verkieslijk om uitdrukkelijk te bepalen toetreedt in de verbindingsdefinitie.

### Kardinaal {#cardinality}

Wanneer u een verbinding ontwerpt, zorg ervoor dat het doelverslag uniek is wanneer een 1-1 verhouding is verklaard. Anders kan verbinden veelvoudige verslagen terugkeren wanneer slechts één wordt verwacht. Dit resulteert in fouten tijdens leveringsvoorbereiding wanneer de vraag meer rijen dan verwacht terugkeert. Stel de naam van de koppeling in op dezelfde naam als het doelschema.

Definieer een koppeling met een kardinaliteit (1-N) in het schema aan de (N) zijde. De relatie Ontvanger (1) - (N) Transactie moet bijvoorbeeld in het transactieschema worden gedefinieerd.

Een omgekeerde kardinaliteit van een koppeling is standaard (N). Het is mogelijk om een verbinding (1-1) te bepalen door de attributen revCardinality=&#39;single&quot;aan de verbindingsdefinitie toe te voegen.

Als de omgekeerde verbinding niet aan de gebruiker zichtbaar zou moeten zijn, kunt u het met de verbindingsdefinitie revLink= &quot;_GEEN_&quot;verbergen. Een goed gebruiksgeval voor dit is een verbinding van ontvanger aan de laatste uitgevoerde transactie te bepalen bijvoorbeeld. U hoeft alleen de koppeling van de ontvanger naar de laatste transactie te zien en er is geen omgekeerde koppeling vereist om zichtbaar te zijn vanuit de transactietabel.

Koppelingen die een externe verbinding (1-0..1) uitvoeren, moeten met de nodige voorzichtigheid worden gebruikt omdat dit van invloed is op de systeemprestaties.

## Gegevensretentie {#data-retention}

Adobe Campaign is geen data-entrepot of rapportageinstrument. Om goede prestaties van de oplossing van Adobe Campaign te verzekeren, zou de gegevensbestandgroei daarom onder controle moeten blijven. Om dit te bereiken, kan het volgen van een aantal van de onderstaande beste praktijken helpen.

Voor retentie bevatten de ingebouwde logtabellen in Campaign vooraf ingestelde retentieperioden, waarbij de gegevensopslag over het algemeen is beperkt tot zes maanden of korter.

Hieronder volgen de standaardwaarden voor retentie in de ingebouwde tabellen. Houd er rekening mee dat de retentieconfiguratie tijdens de implementatie door technische beheerders van Adobe wordt ingesteld, en dat de waarden per implementatie kunnen verschillen op basis van de vereisten van de klant.

* **Geconsolideerde tracking**: 1 jaar
* **Verzendingslogs**: 6 maanden
* **Trackinglogs**: 1 jaar
* **Verwijderde verzendingen**: 1 week
* **Geweigerde importacties**: 6 maanden
* **Bezoekersprofielen**: 1 maand
* **Aanbiedingsvoorstellen**: 1 jaar
* **Gebeurtenissen**: 1 maand
* **Statistieken van gebeurtenisverwerking**: 1 jaar
* **Gearchiveerde gebeurtenissen**: 1 jaar
* **Genegeerde pijplijngebeurtenissen**: 1 maand

>[!CAUTION]
>
>Aangepaste tabellen worden niet gewist met het standaardopschoonproces. Hoewel dit niet op dag één vereist zou kunnen zijn, vergeet niet om een zuiveringsproces voor uw douanetabellen te bouwen aangezien dit tot prestatiesuitdagingen zou kunnen leiden.

Er zijn een paar oplossingen om de behoefte aan verslagen in Adobe Campaign te minimaliseren:
* Exporteer de gegevens in een gegevensopslagruimte buiten Adobe Campaign.
* Genereer geaggregeerde waarden die minder ruimte gebruiken en toch voldoende zijn voor uw marketingactiviteiten. U hebt bijvoorbeeld niet de volledige transactiegeschiedenis van klanten in Adobe Campaign nodig om de laatste aankopen bij te houden.

U kunt het kenmerk &quot;deleteStatus&quot; in een schema declareren. Het is efficiënter om het verslag te merken zoals geschrapt, dan de schrapping in de schoonmaakbeurttaak uit te stellen.

Als gebruiker van de Beheerde Cloud van de Diensten, contacteer aan de consultants van Adobe of technische beheerders om meer over behoud te leren of als u behoud voor douanetabellen moet plaatsen.

## Prestaties {#performance}

Volg onderstaande aanbevolen procedures om te zorgen voor betere prestaties op elk moment.

### Algemene aanbevelingen {#general-recommendations}

* Gebruik geen bewerkingen zoals &quot;CONTAINS&quot; in query&#39;s. Als u weet waarvoor wordt verwacht en waarvoor wordt gefilterd, past u dezelfde voorwaarde toe met een &quot;GELIJK AAN&quot; of andere specifieke filteroperatoren.
* Probeer en zorg ervoor de processen zoals de invoer en de uitvoer van bedrijfsuren gebeuren.
* Zorg ervoor dat er een schema is voor alle dagelijkse activiteiten en houd zich aan het schema.
* Als een of weinig van de dagelijkse processen mislukken en als het verplicht is om het op die zelfde dag in werking te stellen, zorg ervoor er geen conflicterende processen lopen wanneer het handproces wordt opgeheven aangezien dit de systeemprestaties zou kunnen beïnvloeden.
* Zorg ervoor dat de dagelijkse campagne niet wordt uitgevoerd tijdens het importproces of wanneer een handmatig proces wordt uitgevoerd.
* Gebruik een of meer referentietabellen in plaats van een veld in elke rij te dupliceren. Wanneer u sleutel-/waardeparen gebruikt, verdient het de voorkeur een numerieke sleutel te kiezen.
* Een korte tekenreeks blijft acceptabel. Als referentietabellen al in een extern systeem zijn geïnstalleerd, wordt de gegevensintegratie met Adobe Campaign vergemakkelijkt door dit systeem opnieuw te gebruiken.

### Een-op-veel relaties {#one-to-many-relationships}

* Gegevensontwerp beïnvloedt bruikbaarheid en functionaliteit. Als u uw gegevensmodel met vele één-aan-vele verhoudingen ontwerpt, maakt het voor gebruikers moeilijker om zinvolle logica in de toepassing te construeren. Een-op-veel filterlogica kan voor niet-technische marketers moeilijk zijn om correct te construeren en te begrijpen.
* Het is goed om alle essentiële gebieden in één lijst te hebben omdat het het voor gebruikers gemakkelijker maakt om vragen te bouwen. Soms is het ook handig om bepaalde velden te dupliceren naar andere tabellen als u samenvoeging kunt voorkomen.
* Bepaalde ingebouwde functies kunnen niet verwijzen naar een-op-een-relatie, zoals de formule en levering van de Afweging van aanbiedingen.

## Grote tabellen {#large-tables}

Adobe Campaign is afhankelijk van externe databasemotoren. Afhankelijk van de leverancier, kan het optimaliseren van prestaties voor grotere lijsten een specifiek ontwerp vereisen.

Hieronder vindt u een aantal veelvoorkomende aanbevolen procedures die moeten worden gevolgd bij het ontwerpen van uw gegevensmodel met behulp van grote tabellen en complexe verbindingen.

* Wanneer het gebruiken van extra douane ontvankelijke lijsten, zorg ervoor u een specifieke logboeklijst voor elke leveringsafbeelding hebt.
* Verminder het aantal kolommen, met name door de kolommen te identificeren die niet worden gebruikt.
* Optimaliseer de relaties van het gegevensmodel door complexe verbindingen, zoals verbindingen op verschillende voorwaarden en/of meerdere kolommen te vermijden.
* Voor verbindingssleutels, kunt u numerieke of op koord-gebaseerde waarden gebruiken.
* Verminder zoveel u de diepte van logboekbehoud kunt. Als u een diepere geschiedenis nodig hebt, kunt u berekeningen samenvoegen en/of aangepaste logboektabellen verwerken om de grotere historie op te slaan.

### Grootte van tabellen {#size-of-tables}

De tabelgrootte is een combinatie van het aantal records en het aantal kolommen per record. Beide kunnen de prestaties van vragen beïnvloeden.

* A **klein-grootte** lijst is gelijkaardig aan de lijst van de Levering.
* A **middelgroot grootte** lijst is het zelfde als de grootte van de Ontvankelijke lijst. Het heeft één verslag per klant.
* A **groot-grootte** lijst is gelijkaardig aan de Grote logboeklijst. Het heeft vele verslagen per klant.
Bijvoorbeeld, als uw gegevensbestand 10 miljoen ontvangers bevat, bevat de Brede logboeklijst ongeveer 100 tot 200 miljoen berichten, en de lijst van de Levering bevat een paar duizend verslagen.

Het aantal rijen heeft ook invloed op de prestaties. De Adobe Campaign-database is niet bedoeld voor het opslaan van historische gegevens die niet actief worden gebruikt voor het maken van doelen of het maken van persoonlijke gegevens. Dit is een operationele database.

Om prestatieskwestie te verhinderen met betrekking tot het hoge aantal rijen, slechts de noodzakelijke verslagen in het gegevensbestand houden. Alle andere records moeten worden geëxporteerd naar een gegevenspakhuis van derden en uit de operationele Adobe Campaign-database worden verwijderd.

Hier volgen enkele tips en trucs voor de grootte van tabellen:

* Ontwerp grote tabellen met minder velden en meer numerieke gegevens.
* Gebruik geen groot aantal kolomtypen om kleine getallen op te slaan, zoals booleaanse waarden.
* Verwijder niet-gebruikte kolommen uit de tabeldefinitie.
* Bewaar historische of inactieve gegevens niet in uw Adobe Campaign-database (exporteren en opschonen).
