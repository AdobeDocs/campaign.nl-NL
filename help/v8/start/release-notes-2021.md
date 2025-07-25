---
title: Opmerkingen bij de release Campagne v8 2021
description: Lijst met functies en verbeteringen die worden geleverd bij de 2021-campagne v8-releases
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 5ac6bda9-86c8-4200-b285-6fee2a29039d
source-git-commit: e4f6c70ecdcf7414b5f49a43933cfd1c967a0905
workflow-type: tm+mt
source-wordcount: '1581'
ht-degree: 37%

---

# Opmerkingen bij de release 2021{#2021-release}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met **2021 de Versies van de Campagne v8** komen.

## Release 8.2.8 {#release-8-2-8}

_vrijdag 28 oktober 2021_

<table>
<thead>
<tr>
<th><strong>Binnenkomende interactie</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Interactiebeheer in real time is nu beschikbaar voor binnenkomende kanalen. De module van de Interactie van de Campagne van het gebruik binnenkomende om de beste aanbieding aan uw klanten voor te stellen aangezien zij uw website bezoeken of uit naar uw vraagcentrum bereiken. Dit vermogen komt met Campagne v8 als optie en vereist specifieke configuratie op uw instantie. Vraag uw Adobe-medewerker om toegang tot de module Binnenkomende interactie.</p>
<p>Raadpleeg de <a href="../interaction/interaction-architecture.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong> Optimalisering van de Campagne </strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>De module Campagne optimaliseren is nu beschikbaar. Met deze module kunt u het verzenden van leveringen beheren, filteren en controleren. Om conflicten tussen campagnes te vermijden kan Adobe Campaign diverse combinaties testen door specifieke beperkingsregels toe te passen. Dit garandeert dat de verzonden berichten voldoen aan de behoeften en verwachtingen van klanten en het communicatiebeleid van het bedrijf.</p>
<p>Raadpleeg de <a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=nl-NL#campaign-optimization">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong> de Dienst van de Uniciteit </strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service is een nieuwe Cloud Database Manager-component. Hiermee kunnen gebruikers de integriteit van unieke sleutelbeperkingen in Cloud Database-tabellen behouden en controleren. Hierdoor kunt u het risico van het invoegen van dubbele toetsen verkleinen.
<p>Aangezien het Gegevensbestand van de Wolk uniciteitsbeperkingen niet afdwingt, introduceert de Dienst van de Uniciteit op toepassingsniveau, <b> een reeks nieuwe gidsen </b> het risico verminderen om duplicaten op te nemen wanneer het beheren van de gegevens met Adobe Campaign.</p> 
<p>De Dienst van de toxiciteit stelt een nieuw ingebouwd werkschema genoemd <b> ffdaUnicity </b> in werking om uniciteitsbeperkingen en alarm te controleren wanneer de duplicaten worden ontdekt.</p>
<p>Raadpleeg de <a href="../architecture/keys.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> </tr> 
</tbody> 
</table>


**Verbeteringen**

* De Snowflake-aansluiting is verbeterd op het gebied van prestaties.
* Voor controle- en testdoeleinden bevatten de auditlogs van de **[!UICONTROL Replicate Staging data]** -workflow nu het aantal records dat naar de FFDA-database (Full Federated Data Access) is verzonden.
* Met de SQL-codeactiviteit kunt u nu kiezen in welke database het SQL-script wordt opgeslagen: de standaardgegevensbron of een gekozen actieve externe FDA-account.
* Er is nu een set vooraf gedefinieerde entrepots beschikbaar die kan worden gebruikt om verschillende query&#39;s parallel uit te voeren, zoals segmentatie, ETL of pieken. [Meer informatie](../config/workflows.md)

**Andere wijzigingen**

* Het veld **[!UICONTROL Encrypted identifier]** is toegevoegd aan het bezoekersschema (`nms:visitor`). Dit veld wordt berekend en moet worden gebruikt voor webtoepassingen.
* Probleem verholpen dat ertoe leidde dat de leveringsanalyse mislukte wanneer sommige IP affiniteiten in sommige middelsourcingcontainers bestonden, maar niet in alle. Nu worden de IP affiniteiten allen opgeslagen in het gegevensbestand, zodat om het even welke container tot de affiniteiten kan toegang hebben die in alle andere containers aanwezig zijn. (NEO-37564)
* U kunt nu een pakket importeren met meerdere schema&#39;s en knooppunten van de navigatiestructuur.

**Patches**

* Nadat een gebruiker in een gegevensschema het kenmerk `<autoStg>` uit een tabeldefinitieelement had verwijderd of de waarde van `true` in `false` had gewijzigd, is de gerelateerde testtabel niet verwijderd. Dit probleem is opgelost.
* Probleem verholpen dat een fout veroorzaakte bij het maken van records met een toegewezen formulier vanwege Id-beheer met een FFDA-gegevensbron.
* Probleem verholpen waarbij voorstellen niet in een levering konden worden ingevoegd als de aanbiedingen in een workflow werden beheerd door een verrijkingsactiviteit.
* Probleem verholpen waarbij het importeren van pakketten trager kon worden.
* Probleem opgelost waarbij e-mailleveringen met zaadadressen niet konden worden verzonden.
* Probleem verholpen waardoor voorstellen niet konden worden opgeslagen in de tabel met aanbiedingsvoorstellen.
* Er is een probleem opgelost waarbij netwerktime-outproblemen ten onrechte werden vastgelegd als scriptonderbrekingsproblemen in plaats van netwerkfouten. Dit probleem is opgetreden in het geval van HTTP-aanvragen die in JavaScript-activiteiten zijn opgenomen.
* Probleem opgelost waarbij aanbiedingen niet konden worden gerepliceerd naar de live aanbiedingsomgeving op Snowflake.
* Probleem opgelost waarbij het kenmerk &#39;autoStg&#39; voor niet-uitgebreide ingebouwde schema&#39;s werd genegeerd.
* Probleem verholpen waardoor gebruikers de koppeling **[!UICONTROL Country/Region]** niet konden selecteren bij het voorvertonen van een profiel.
* Probleem verholpen waarbij de datepicker in aangepaste rapporten tot een scriptfout leidde. (NEO-36345)
* Er is een probleem opgelost waardoor het systeem crashte bij het opnieuw genereren van de configuratie in geval van beschadigde configuratiebestanden.
* Probleem verholpen waardoor de upgrade van de marketing- en besturingsinstanties niet kon worden voltooid.
* Er is een probleem opgelost waardoor de factureringsworkflow kon crashen op marketinginstanties.
* Probleem verholpen dat tot dubbele sleutels in FFDA Snowflake buiten-de-doos lijsten kon leiden. (NEO-38583)
* Probleem verholpen waarbij tijdelijke workflowschema&#39;s verloren zouden kunnen gaan wanneer twee deduplicatieactiviteiten achterelkaar werden bewerkt. (NEO-34063)
* Er is een probleem opgelost dat onjuiste resultaten opleverde bij het uitvoeren van de Amazon Redshift HoursDiff- en MinutesDiff-functies tijdens het extraheren van de tijdcomponent.(NEO-31673)
* Probleem verholpen waardoor gebruikers zich niet konden aanmelden bij de console vanwege een probleem met de proxyconfiguratie. (NEO-38388)
* Er is een regressieprobleem opgelost waardoor de functie **Map opschonen** niet correct werkte. (NEO-37459)
* Er is een probleem opgelost waardoor u geen voorbeeld van mobiele leveringen kon bekijken die aan een workflow waren gekoppeld.
* Er is een probleem opgelost waardoor de werkstroomactiviteit **Leeslijst** niet werkte wanneer de lijst in de database werd geïdentificeerd met een negatieve ID. (NEO-39607)

## Release 8.1.20 {#release-8-1-20}

_7 september 2021_

**Verbeterde beveiliging**

* Oplossing voor een beveiligingsprobleem ter versterking van de bescherming tegen aanvallen via directory traversal. (NEO-28547)

**Verbeteringen**

* Na het eind van zijn gebruiksduur is Flash verwijderd uit alle verwante Campaign-functies en onderdelen, en vervangen door HTML5. Het diagramtype **Gauge** is verwijderd. (NEO-30330) [Meer informatie](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=nl-NL)
* Wanneer u de clientconsole in Windows installeert, controleert het installatieprogramma nu of er een bovenliggend registerknooppunt is en wordt er een gemaakt als dit knooppunt ontbreekt. Hiermee voorkomt u potentiële problemen wanneer u de console start. (NEO-34854)
* De functie voor het bijhouden van handtekeningen is verbeterd om fouten te voorkomen met de manier waarop tools van derden (klant-e-mail, internetbrowsers, enz.) speciale tekens verwerken. URL-parameters zijn nu gecodeerd.

**Andere wijzigingen**

* Eerder vervangen Microsoft CRM-connectors (Office 365 en on-premise implementaties) zijn verwijderd uit de interface. [Meer informatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-ms-dynamics.html?lang=nl-NL#configure-acc-for-microsoft)

* Na de migratie aan Tomcat 8 is het IIS-instellingenscript bijgewerkt om IIS-integratiekwesties te bevestigen. (NEO-31019)
* Er is een veiligheidsbarrière toegevoegd waarmee alleen de [technische workflow voor facturering](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=nl-NL#billing-report) op de marketingversie kan worden uitgevoerd.
* De identificatie van de databron is verbeterd in de gegevens- en schematabbladen van het venster **Populatie weergeven** van de workflowtransities.
* Ontbrekende database-indexen zijn toegevoegd aan de volgende schema&#39;s om problemen met database-updates te voorkomen: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Patches**

* Oplossing een kwestie die **Hete kliks** rapport verhinderde te werken wanneer de aanbiedingen met de levering werden verbonden. (NEO-26295)
* Probleem verholpen met de activiteit **Sub-worklow** waarbij de uitvoering geen outputtabel produceerde. (NEO-36242)
* Verschillende problemen verholpen bij het exporteren van het rapport **Beschrijvende analyse** naar PDF. (NEO-25847)
* Probleem verholpen waarbij leveringen soms mislukten wanneer een externe maillevering werd gebruikt. (NEO-37435)
* Probleem verholpen bij de verbinding met Microsoft CRM via web-API. Het foutbericht is verwijderd omdat dit geen invloed had op de functies.
* Probleem met logdeduplicatietracking verholpen waarbij de middenserver was ingesteld als een relais tussen tracking- en marketingservers. (NEO-36285)
* Oplossing voor een regressie waardoor Vault niet als een specifieke codeopslag kon worden gebruikt.
* Probleem verholpen waardoor u geen variabelen kon gebruiken in een workflowactiviteit **Verrijkings** als de binnenkomende transitie afkomstig was van een FDA-databron.
* Probleem met FFDA verholpen waarbij een correcte replicatie van groepen en rechten van exploitanten werd voorkomen.
* Probleem verholpen waarbij een onjuiste koppeling voor het opzeggen van een abonnement via de levering kon worden verzonden.
* Oplossing voor een probleem in replicatiebeheer dat invloed had op de duur van de postupgrade.
* Vaste een kwestie die **Hete klik** kon verhinderen te tonen.
* Probleem verholpen dat kon leiden tot verbroken URL&#39;s in e-mailberichten.

## Release 8.1.14 {#release-8-1-14}

_zaterdag 23 juli 2021_

**Nieuwe functies**

<table>
<thead>
<tr>
<th><strong>Nieuwe workflowactiviteit: Databron wijzigen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Met de nieuwe workflowactiviteit <b>Databron wijzigen</b> kunt u de databron van de werktabel van een workflow wijzigen. Dit biedt meer flexibiliteit bij het beheer van gegevens over verschillende gegevensbronnen (FDA, FFDA en lokale database).</p>
<p>In Adobe Campaign-workflows worden gegevens beheerd met behulp van werkende (of tijdelijke) tabellen. Tijdens het uitvoeren van de workflow delen werktabellen gegevens over de verschillende workflowactiviteiten. Standaard worden werktabellen gemaakt in dezelfde database als de bron van de gegevens waarop we query's uitvoeren.</p>
<p>Met Campagne v8 wordt de tabel met hoofdprofielen rechtstreeks opgeslagen in de cloud-database. Als u dus de tabel Profielen opvraagt, wordt er ook een werktabel voor de cloud-database gemaakt. In bepaalde gevallen kan het zinvol zijn de werktabel naar een andere gegevensbron te verplaatsen om specifieke bewerkingen uit te voeren.</p>
<p>Raadpleeg de <a href="../config/workflows.md#change-data-source-activity">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong> de kanaalbeschikbaarheid van de LIJN </strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Het <a href="../send/line.md"> kanaal van de LIJN </a> is nu beschikbaar met Campagne v8, met inbegrip van de volgende verhogingen wanneer gecombineerd met de <a href="../send/transactional.md"> transactionele overseinen </a> module:
<ul> 
<li><p>Probleem verholpen waardoor bezoekers zich niet konden richten op een lijnlevering. 
</p></li>
<li><p>Probleem verholpen waarbij fouten konden optreden bij het ophalen van bezoekers van de uitvoeringsinstantie naar de marketinginstantie.
</p></li>
<li><p>Problemen verholpen tijdens het verwerken van real-time gebeurtenissen.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>


**Overige verbeteringen**

* Vaste een kwestie die **Hete kliks** rapport van het tonen voor specifieke leveringen kon verhinderen.
* Vaste een kwestie met de **Deduplicatie** werkschemaactiviteit die in een onnauwkeurige dubbele telling kon resulteren.
* Probleem verholpen bij het gebruik van een workflowquery met het filter &#39;ID is niet leeg&#39;, wat ertoe kan leiden dat een leeg item wordt weergegeven in de overgangspopulatie.
* Probleem verholpen waarbij werd voorkomen dat aanvullende velden werden gemaakt in een nieuwe doeltoewijzing.
