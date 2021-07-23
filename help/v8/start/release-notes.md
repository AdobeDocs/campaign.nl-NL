---
product: Adobe Campaign
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Overzicht
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 9e745f7fb8fd20f35025c06ff621a9da5002190e
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 4%

---

# Laatste release{#latest-release}

Deze pagina bevat nieuwe mogelijkheden, verbeteringen en oplossingen die worden geleverd met de **nieuwste versie van Campagne v8 Release**.

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
<td> <p>Het lijnkanaal is nu beschikbaar met Campagne v8. De volgende verbeteringen zijn aangebracht bij het gebruik van LIJN met Berichtencentrum:
</p>
<ul> 
<li><p>Probleem verholpen waardoor bezoekers zich niet konden richten op een lijnlevering. 
</p></li>
<li><p>Probleem verholpen waarbij fouten konden optreden bij het ophalen van bezoekers van de uitvoeringsinstantie naar de marketinginstantie.
</p></li>
<li><p>Oplossing voor problemen tijdens de verwerking van real-time gebeurtenissen in de context van lijnleveringen met behulp van Message Center.</p></li>
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
