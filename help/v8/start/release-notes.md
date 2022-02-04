---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: b7db9597aa6b4ca4fb2e1e13f8b7b718f4840031
workflow-type: tm+mt
source-wordcount: '1714'
ht-degree: 36%

---

# Nieuwste release{#latest-release}

Deze pagina bevat nieuwe mogelijkheden, verbeteringen en oplossingen die worden geleverd met de **nieuwste versie van Campaign v8**.

## Release 8.2.10 {#release-8-2-10}

_2 februari 2022_

**Patches**

* Probleem opgelost waarbij de voorbereiding van de levering mislukte als het maximum aantal berichten, dat in de typologieregel is gedefinieerd, is bereikt.
* Probleem verholpen tijdens de configuratie van de Adobe Analytics-connector toen het e-mailadres een &#39;s&#39;-teken bevatte.
* Probleem verholpen tijdens postupgrade die ertoe kon leiden dat de tabel deliveryMapping gegevens uit een aangepaste leveringstoewijzing verliest.
* Probleem verholpen waarbij ontvangers hetzelfde bericht meerdere keren kregen voor dezelfde levering wanneer het e-mailadres één aanhalingsteken (&#39;) bevatte. Dit teken is nu beschermd. (NEO-41198)
* Probleem met genereren van id verholpen bij het verzenden van proefdrukken met zaden of substitutieadressen. (NEO-42637)
* Probleem verholpen waardoor proofs niet meer kunnen worden verzonden door middel van de methode Adres. (NEO-40417)
* Probleem verholpen waardoor u het LINE-pakket niet kon installeren. (NEO-42503)

## Release 8.2.8 {#release-8-2-8}

_28 oktober 2021_

<table>
<thead>
<tr>
<th><strong>Binnenkomende interactie</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Interactiebeheer in real time is nu beschikbaar voor binnenkomende kanalen. De module van de Interactie van de Campagne van het gebruik binnenkomende om de beste aanbieding aan uw klanten voor te stellen aangezien zij uw website bezoeken of uit naar uw vraagcentrum bereiken. Dit vermogen komt met Campagne v8 als optie en vereist specifieke configuratie op uw instantie. Bereid uit aan uw vertegenwoordiger van de Adobe om toegang tot de Binnenkomende module van de Interactie te hebben.</p>
<p>Raadpleeg de <a href="../send/interaction-architecture.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Campagnes optimaliseren</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>De module Campagne optimaliseren is nu beschikbaar. Met deze module kunt u het verzenden van leveringen beheren, filteren en controleren. Om conflicten tussen campagnes te vermijden kan Adobe Campaign diverse combinaties testen door specifieke beperkingsregels toe te passen. Dit garandeert dat de verzonden berichten voldoen aan de behoeften en verwachtingen van klanten en het communicatiebeleid van het bedrijf.</p>
<p>Raadpleeg de verwante bronnen voor meer informatie <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html">Campaign Classic v7-documentatie</a>.</p>
</td> 
</tr> 
</tbody> 
</table>
<table> 
<thead>
<tr> 
<th> <strong>Uniciteitsservice</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service is een nieuwe Cloud Database Manager-component. Hiermee kunnen gebruikers de integriteit van unieke sleutelbeperkingen in Cloud Database-tabellen behouden en controleren. Hierdoor kunt u het risico van het invoegen van dubbele toetsen verkleinen.
<p>Aangezien de Gegevensbestand van de Wolk uniciteitsbeperkingen niet afdwingt, introduceert de Dienst van de Uniciteit op toepassingsniveau, <b>een reeks nieuwe instructies</b> bij het beheer van de gegevens met Adobe Campaign het risico op het invoegen van duplicaten verminderen.</p> 
<p>De Dienst van Unicity stelt een nieuwe ingebouwde werkschema in werking genoemd <b>ffdaUnicity</b> om uniciteitsbeperkingen en alarm te controleren wanneer de duplicaten worden ontdekt.</p></td> </tr> 
</tbody> 
</table>

**Verbeteringen**

* De Snowflake-aansluiting is verbeterd op het gebied van prestaties.
* Voor toezicht- en testdoeleinden worden de auditlogboeken van de **[!UICONTROL Replicate Staging data]** De workflow bevat nu het aantal records dat naar de FFDA-database (Full Federated Data Access) is verzonden.
* Met de SQL-codeactiviteit kunt u nu kiezen in welke database het SQL-script wordt opgeslagen: de standaardgegevensbron of een gekozen actieve externe FDA-rekening.
* Er is nu een set vooraf gedefinieerde entrepots beschikbaar die kan worden gebruikt om verschillende query&#39;s parallel uit te voeren, zoals segmentatie, ETL of pieken. [Meer informatie](../config/workflows.md)

**Andere wijzigingen**

* De **[!UICONTROL Encrypted identifier]** veld is toegevoegd aan het bezoekersschema (`nms:visitor`). Dit veld wordt berekend en moet worden gebruikt voor webtoepassingen.
* Probleem verholpen dat ertoe leidde dat de leveringsanalyse mislukte wanneer sommige IP affiniteiten in sommige middelsourcingcontainers bestonden, maar niet in alle. Nu worden de IP affiniteiten allen opgeslagen in het gegevensbestand, zodat om het even welke container tot de affiniteiten kan toegang hebben die in alle andere containers aanwezig zijn. (NEO-37564)
* U kunt nu een pakket importeren met meerdere schema&#39;s en knooppunten van de navigatiestructuur.

**Patches**

* Nadat een gebruiker in een gegevensschema had verwijderd, `<autoStg>` kenmerk van een tabeldefinitieelement, of de waarde ervan wijzigen vanuit `true` tot `false`, is de bijbehorende testtabel niet verwijderd. Dit probleem is opgelost.
* Probleem verholpen dat een fout veroorzaakte bij het maken van records met een toegewezen formulier vanwege Id-beheer met een FFDA-gegevensbron.
* Probleem verholpen waarbij voorstellen niet in een levering konden worden ingevoegd als de aanbiedingen in een workflow werden beheerd door een verrijkingsactiviteit.
* Probleem verholpen waarbij het importeren van pakketten trager kon worden.
* Probleem opgelost waarbij e-mailleveringen met zaadadressen niet konden worden verzonden.
* Probleem verholpen waardoor voorstellen niet konden worden opgeslagen in de tabel met aanbiedingsvoorstellen.
* Er is een probleem opgelost waarbij netwerktime-outproblemen ten onrechte werden vastgelegd als scriptonderbrekingsproblemen in plaats van netwerkfouten. Dit probleem deed zich voor in het geval van HTTP-verzoeken die waren opgenomen in JavaScript-activiteiten.
* Probleem verholpen waarbij aanbiedingen niet konden worden gerepliceerd naar de live aanbiedingsomgeving op Snowflake.
* Probleem verholpen waarbij het kenmerk &#39;autoStg&#39; voor niet-uitgebreide ingebouwde schema&#39;s werd genegeerd.
* Probleem verholpen waardoor gebruikers niet de **[!UICONTROL Country/Region]** koppelen bij voorvertonen van een profiel.
* Probleem verholpen waarbij de datepicker in aangepaste rapporten tot een scriptfout leidde. (NEO-36345)
* Probleem verholpen waarbij het systeem vastliep bij het opnieuw genereren van configuratie in geval van slechte configuratiebestanden.
* Probleem verholpen waardoor de upgrade van de marketing- en besturingsinstanties is mislukt.
* Er is een probleem opgelost waardoor de factureringsworkflow kon crashen op marketinginstanties.
* Probleem verholpen dat tot dubbele sleutels in FFDA Snowflake out-of-the-box lijsten kon leiden. (NEO-38583)
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

* Na het eind van zijn gebruiksduur is Flash verwijderd uit alle verwante Campaign-functies en onderdelen, en vervangen door HTML5. Het diagramtype **Gauge** is verwijderd. (NEO-30330) [Meer informatie](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html)
* Wanneer u de clientconsole in Windows installeert, controleert het installatieprogramma nu of er een bovenliggend registerknooppunt is, en zo niet, dan wordt er een gemaakt. Hiermee voorkomt u potentiële problemen wanneer u de console start. (NEO-34854)
* De functie voor het bijhouden van handtekeningen is verbeterd om fouten te voorkomen die gekoppeld zijn aan tools van derden (klant-e-mail, internetbrowsers, enz.) speciale tekens gebruiken. URL-parameters zijn nu gecodeerd.

**Andere wijzigingen**

* Eerder vervangen connectoren van Microsoft CRM (Bureau 365 en On-premise-implementaties) zijn uit de interface verwijderd. [Meer informatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html#configure-acc-for-microsoft)
* Na de migratie aan Tomcat 8 is het IIS-instellingenscript bijgewerkt om IIS-integratiekwesties te bevestigen. (NEO-31019)
* Er is een veiligheidsbarrière toegevoegd waarmee alleen de [technische workflow voor facturering](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html#billing-report) op de marketingversie kan worden uitgevoerd.
* De identificatie van de databron is verbeterd in de gegevens- en schematabbladen van het venster **Populatie weergeven** van de workflowtransities.
* Ontbrekende database-indexen zijn toegevoegd aan de volgende schema&#39;s om problemen met database-updates te voorkomen: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Patches**

* Het probleem dat de **Hot kliks** rapport van het werk toen de aanbiedingen met de levering verbonden waren. (NEO-26295)
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
* Het probleem dat de **Hot click** van weergave.
* Probleem verholpen dat kon leiden tot verbroken URL&#39;s in e-mailberichten.

## Release 8.1.14 {#release-8-1-14}

_23 juli 2021_

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
<th> <strong>Beschikbaarheid van lijnkanalen</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>De <a href="../send/line.md">LINE-kanaal</a> is nu beschikbaar met Campagne v8, inclusief de volgende verbeteringen in combinatie met de <a href="../send/transactional.md">transactieberichten</a> module:
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

* Het probleem dat de **Hot kliks** rapporteren van het weergeven voor specifieke leveringen.
* Probleem verholpen met de **Deduplicatie** workflowactiviteit die kan leiden tot een onjuiste dubbele telling.
* Probleem verholpen bij het gebruik van een workflowquery met het filter &#39;ID is niet leeg&#39;, wat ertoe kan leiden dat een leeg item wordt weergegeven in de overgangspopulatie.
* Probleem verholpen waarbij werd voorkomen dat aanvullende velden werden gemaakt in een nieuwe doeltoewijzing.
