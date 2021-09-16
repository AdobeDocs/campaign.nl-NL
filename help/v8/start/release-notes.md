---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 4%

---

# Laatste release{#latest-release}

Deze pagina bevat nieuwe mogelijkheden, verbeteringen en oplossingen die worden geleverd met de **nieuwste versie van Campagne v8 Release**.

## Release 8.1.20 {#release-8-1-20}

_7 september 2021_

**Verbeterde beveiliging**

* Oplossing voor een beveiligingsprobleem ter versterking van de bescherming tegen aanvallen via directory traversal. (NEO-28547)

**Verbeteringen**

* Na zijn levenseinde is Flash verwijderd uit alle verwante campagnefuncties en -componenten en vervangen door HTML5. Het diagramtype **Gage** is verwijderd. (NEO-30330) [Meer informatie](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html)
* Wanneer u de clientconsole in Windows installeert, controleert het installatieprogramma nu of er een bovenliggend registerknooppunt is en wordt er een gemaakt als dit knooppunt ontbreekt. Hiermee voorkomt u potentiële problemen wanneer u de console start. (NEO-34854)
* De functie Handtekening bijhouden is verbeterd om fouten te voorkomen die samenhangen met de manier waarop hulpmiddelen van derden (e-mailclients, internetbrowsers, enz.) speciale tekens gebruiken. URL-parameters zijn nu gecodeerd.

**Andere wijzigingen**

* Eerder vervangen de schakelaars van Microsoft CRM (Bureau 365 en On-premise plaatsingen) zijn verwijderd uit de interface. [Meer informatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html#configure-acc-for-microsoft)
* Na de migratie aan Tomcat 8, is het IIS opstellingsmanuscript bijgewerkt om IIS integratiekwesties te bevestigen. (NEO-31019)
* Er is een hulplijn toegevoegd waarmee alleen de technische workflow [factureren](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html#billing-report) op de marketinginstantie kan worden uitgevoerd.
* De identificatie van de gegevensbron is verbeterd op de tabbladen voor gegevens en schema&#39;s van het venster **Volgpopulatie weergeven**.
* Ontbrekende database-indexen zijn toegevoegd aan de volgende schema&#39;s om problemen met databaseupdates te voorkomen: xtk:rights, nms:dlvExclusion, nms:zaadMember, nms:trackingUrl

**Patches**

* Probleem verholpen waardoor het **Hot clicks**-rapport niet werkte wanneer aanbiedingen aan de levering waren gekoppeld. (NEO-26295)
* Probleem verholpen met de **Sub-worklow** activiteit toen de uitvoering geen outputlijst produceerde. (NEO-36242)
* Verschillende problemen verholpen bij het exporteren van het **rapport Beschrijvende analyse** naar PDF. (NEO-25847)
* Probleem verholpen waarbij leveringen mislukten wanneer een externe postbestelling werd gebruikt. (NEO-37435)
* Probleem verholpen wanneer verbinding werd gemaakt met Microsoft CRM via web-API. Het foutbericht is verwijderd omdat dit geen invloed had op de functies.
* Probleem met logdeduplicatie bijhouden verholpen waarbij de medio-server werd ingesteld als een relais tussen tracking- en marketingservers. (NEO-36285)
* Oplossing voor een regressie waardoor Vault niet kon worden gebruikt als een specifieke codeopslag.
* Probleem verholpen waarbij u geen variabelen kon gebruiken in een **Verrijking**-workflowactiviteit toen de inkomende overgang afkomstig was van een FDA-gegevensbron.
* Probleem met FFDA verholpen waarbij een correcte replicatie van groepen en rechten van exploitanten werd voorkomen.
* Probleem verholpen waarbij een onjuiste koppeling voor het opzeggen van een abonnement via de levering kon worden verzonden.
* Oplossing voor een probleem in replicatiebeheer dat invloed had op de duur van de postupgrade.
* Probleem verholpen waardoor **Hot click** niet kan worden weergegeven.
* Probleem verholpen dat tot verbroken URL&#39;s in e-mailberichten kon leiden.

## Release 8.1.14 {#release-8-1-14}

_23 juli 2021_

**Nieuwe functies**

<table>
<thead>
<tr>
<th><strong>Nieuwe workflowactiviteit: Gegevensbron wijzigen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Met de nieuwe <b>Gegevensbron wijzigen</b>-workflowactiviteit kunt u de gegevensbron van de werktabel van een workflow wijzigen. Dit biedt meer flexibiliteit bij het beheer van gegevens over verschillende gegevensbronnen (FDA, FFDA en lokale database).</p>
<p>In Adobe Campaign-workflows worden de gegevens beheerd met behulp van tijdelijke (of werkende) tabellen. Tijdens het uitvoeren van de workflow delen werktabellen gegevens over de verschillende workflowactiviteiten. Door gebrek, worden het werken lijsten gecreeerd op het zelfde gegevensbestand zoals de bron van de gegevens wij waarvragen.</p>
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
<td> <p>Het <a href="../send/line.md">LINE kanaal</a> is nu beschikbaar met Campagne v8, met inbegrip van de volgende verhogingen wanneer gecombineerd met <a href="../send/transactional.md">transactional overseinen</a> module:
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

* Probleem verholpen waardoor **Hot clicks** niet kan worden weergegeven voor specifieke leveringen.
* Probleem verholpen met de **Deduplicatie**-workflowactiviteit die kan leiden tot een onjuiste dubbele telling.
* Probleem verholpen bij het gebruik van een workflowquery met het filter &#39;ID is niet leeg&#39;, wat ertoe kan leiden dat een leeg item wordt weergegeven in de overgangspopulatie.
* Probleem verholpen waarbij werd voorkomen dat aanvullende velden werden gemaakt in een nieuwe doeltoewijzing.
