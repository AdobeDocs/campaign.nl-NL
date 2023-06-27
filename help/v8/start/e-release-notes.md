---
title: Opmerkingen bij de release Vroege campagne v8
description: release van Early Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 9736ebb3d2a60bfe23b135318b899acb657a580c
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 7%

---

# Vroege aanvullende informatie {#e-new-release}

Op deze pagina vindt u een beschrijving van de verbeteringen en correcties die zijn opgenomen in de volgende versie van Campagne v8. Deze inhoud kan tot de releasedatum zonder voorafgaande kennisgeving worden gewijzigd. De officiële opmerkingen bij de release staan in dit [page](../start/release-notes.md).

## Release 8.5 {#release-8-5}

_30 juni 2023_

**Nieuwe functies**

<table> 
<thead>
<tr> 
<th> <strong>Enhanced Push Notification Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campagne 8.5 introduceert onze nieuwste pushmeldingenservice op v8, aangedreven door een robuust raamwerk dat is gebaseerd op een moderne, geavanceerde technologie. Deze service is ontworpen om nieuwe schaalbaarheidsniveaus te ontgrendelen, zodat uw meldingen een groter publiek met naadloze efficiëntie kunnen bereiken. Met onze verbeterde infrastructuur en geoptimaliseerde processen kunt u een hogere schaal en betrouwbaarheid verwachten, zodat u uw mobiele App-gebruikers net als nooit tevoren kunt gebruiken en er verbinding mee kunt maken. Deze mogelijkheid is alleen beschikbaar voor een geselecteerde groep klanten (beperkte beschikbaarheid).</p>
</td> 
</tr> 
</tbody> 
</table>

**Compatibiliteitsupdates**

* De 32-bits versie van de clientconsole is nu vervangen. Vanaf 8.6 is de Client Console alleen beschikbaar in 64 bits. De upgrade naar de 64-bits versie van de clientconsole is naadloos. Raadpleeg voor meer informatie over het upgraden van uw besturingssysteem [technote](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html).
* U kunt nu uw Campagne v8 instantie met uw Azure synapse externe gegevensbestand verbinden. Deze verbinding wordt beheerd via een nieuw extern account.

**Verbeteringen**

* De productie van SMS is beduidend verbeterd door een waaier van optimalisaties uit te voeren, resulterend in betere snelheid en efficiency voor de mededeling van SMS.
* Vanaf Campagne v8.5 is het verificatieproces naar Campagne v8 verbeterd. Technische operatoren moeten gebruikmaken van Adobe Identity Management System (IMS) om verbinding te maken met Campagne.
* U kunt nu Bestemming- en Bronverbindingen gebruiken om profielkenmerken, zoals uitschakelgegevens, te synchroniseren tussen de Adobe Experience Platform- en Campagne v8-database
* De voorbereiding van de levering is geoptimaliseerd.
* Er is een nieuwe op sleutels gebaseerde verificatieoptie toegevoegd voor de externe SFTP-account, naast de bestaande verificatiemethode voor gebruikers/wachtwoorden. Gebruikers kunnen nu veilig verifiëren met een persoonlijke sleutel, waardoor de beveiliging wordt verbeterd en een alternatief verificatiemechanisme voor SFTP-toegang wordt geboden.

**Verbeterde beveiliging**

* U kunt geen operatoren meer maken via de clientconsole. U moet nu de Admin Console gebruiken. [Meer informatie](../start/gs-permissions.md).
* Verschillende hulpmiddelen van derden zijn bijgewerkt om de beveiliging te optimaliseren.

**Patches**

* Probleem verholpen waarbij speciale tekens in de HTML-inhoud van een levering onjuist werden gecodeerd in verschillende browsers. (NEO-60081)
* Probleem verholpen waardoor u geen rapport kon opslaan over een FFDA-implementatie (Campaign v8 Enterprise). (NEO-56836)
* Probleem verholpen bij het invoegen of bijwerken van gegevens in een aangepast FFDA-schema via de workflowactiviteit Gegevens bijwerken. (NEO-54708)
* Probleem verholpen waardoor de workflow voor het opschonen van databases geen adressen kon verwijderen in de tabel nms:address in FFDA. (NEO-54460)
* Probleem met de factureringsworkflow verholpen waarbij een fout met het compilatiegeheugen is opgetreden. (NEO-51137)
* Probleem opgelost waarbij de GPG-decodering niet correct werkte in de werkstroomactiviteit voor het laden van gegevens (bestand). (NEO-50257)
* Er is een probleem verholpen waardoor de functie `JSPContext.sqlExecWithOneParam` niet werkte. (NEO-50066)
* Probleem verholpen dat tot leveringsfouten leidde bij het gebruik van niet-afdrukbare tekens in personalisatievelden. (NEO-48588)
* Probleem verholpen waarbij leveringsfouten kunnen optreden bij het invoegen van dynamische Adobe Target-afbeeldingen. (NEO-62689)
* Probleem verholpen waarbij browsers geen extra spaties konden toevoegen wanneer voorwaardelijke inhoud in een levering werd gebruikt. (NEO-62132)
* Probleem verholpen waarbij een pop-upvenster werd geopend wanneer werd geklikt op een afbeelding in de e-mailinhoudeditor. (NEO-60752)
* Probleem verholpen dat tot een fout kon leiden en ertoe kon leiden dat u niet kon schuiven wanneer u de inhoud van een levering bewerkt. (NEO-61364)