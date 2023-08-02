---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 758d542b353a2d784407954089586e761825d740
workflow-type: tm+mt
source-wordcount: '1466'
ht-degree: 16%

---

# Nieuwste release{#latest-release}

Adobe Campaign wordt regelmatig bijgewerkt. Deze regelmatige frequentie van updates is bedoeld om u het nieuwste en beste in handen te geven, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Adobe raadt alle klanten ten zeerste aan een upgrade uit te voeren naar de nieuwste versie.

Als Beheerde gebruiker van Cloud Services, wordt uw instantie bevorderd door Adobe met elke nieuwe versie. Adobe zal contact met u opnemen en uw omgeving upgraden. Campagne-clientconsole **moet worden geüpgraded naar dezelfde versie** als Campagneservers. Lees op deze [pagina](../start/connect.md#upgrade-ac-console) hoe u uw Client Console kunt upgraden.

Als klant moet u er bovendien voor zorgen dat u de meest recente ondersteunde versies van de systemen gebruikt die in de [Compatibiliteitsmatrix](compatibility-matrix.md).

## Release 8.5.2 {#release-8-5-2}

_2 aug. 2023_

Oplossing voor een beveiligingsprobleem dat kon optreden bij de upgrade naar 8.5.1. (NEO-64767)

## Release 8.5.1 {#release-8-5}

_30 juni 2023_


**Enhanced Push Notification Service**

Campagne v8.5.1 introduceert onze nieuwste Push-meldingsservice, aangedreven door een robuust raamwerk dat is gebaseerd op een moderne, geavanceerde technologie. Deze service is ontworpen om nieuwe schaalbaarheidsniveaus te ontgrendelen, zodat uw meldingen een groter publiek met naadloze efficiëntie kunnen bereiken. Met onze verbeterde infrastructuur en geoptimaliseerde processen kunt u een hogere schaal en betrouwbaarheid verwachten, zodat u uw mobiele App-gebruikers net als nooit tevoren kunt gebruiken en er verbinding mee kunt maken. Deze mogelijkheid is alleen beschikbaar voor een geselecteerde groep klanten (beperkte beschikbaarheid).

Raadpleeg de [gedetailleerde documentatie](../send/push-data-collection.md) voor meer informatie.


**Verhoogde doorvoer van mobiele kanalen**

<!--
The newly introduced Push notification service showcases significant improvements in throughput for both Push Android and Push iOS compared to our previous version (v8.4). Users will experience notably enhanced performance with the upgraded service in the latest version (v8.5).

* Push Notifications (Android): up to **5x** faster
* Push Notifications (iOS): up to **2.2x** faster

SMS throughput has undergone substantial enhancements through a series of optimizations, resulting in notable improvements in speed and efficiency for SMS communication. These upgrades have led to increased throughput from the previous version (v8.4) to the latest version (v8.5), encompassing both sending and feedback updates. Users can now experience the benefits of this enhanced SMS service.</p>

* SMS throughput: up to **5x** faster

These max throughput performances have been measured by Adobe testing teams, in lab conditions.
-->

<table style="table-layout:fixed" text-align="bottom"><tr style="border: 0;">
<td>
<br/><img alt="Verbeteringen van de doorvoer" src="../start/assets/do-not-localize/improvements.jpeg">
<p>
</td>
<td>
<div>

<p>De nieuwe Push-meldingsservice laat zien dat de doorvoer voor zowel Push Android als Push iOS aanzienlijk is verbeterd ten opzichte van onze vorige versie (v8.4). De gebruikers zullen met name verbeterde prestaties met de verbeterde dienst in de recentste versie (v8.5) ervaren. </p>
<ul>
<li>Pushmeldingen (Android): tot <strong>5x</strong> sneller </li>
<li>Pushmeldingen (iOS): maximaal <strong>2,2 x</strong> sneller</li>
</ul>
<p>De productie van SMS heeft aanzienlijke verhogingen door een reeks optimalisaties ondergaan, resulterend in opmerkelijke verbeteringen in snelheid en efficiency voor de mededeling van SMS. Deze upgrades hebben geleid tot een hogere doorvoer van de vorige versie (v8.4) naar de nieuwste versie (v8.5), die zowel updates voor verzenden als feedback omvat. Gebruikers kunnen nu profiteren van de voordelen van deze verbeterde SMS-service.</p>
<ul>
<li>SMS-doorvoer: maximaal <strong>5x</strong> sneller</li>
</ul>
<p><em>Deze maximumproductieprestaties zijn gemeten door Adobe testende teams, in laboratoriumomstandigheden.</em></p>
</div>
<p></p>
</td>
</tr></table>


**Algemene verbeteringen**

* U kunt nu Adobe Experience Platform Destination-verbinding gebruiken om profielkenmerken, zoals gegevens voor niet-toegang, te synchroniseren tussen Adobe Experience Platform en de v8-database voor Campagne.
* De voorbereiding van de levering is op alle kanalen geoptimaliseerd.
* Er is een nieuwe op sleutels gebaseerde verificatieoptie toegevoegd voor de externe SFTP-account, naast de bestaande verificatiemethode voor gebruikers/wachtwoorden. Gebruikers kunnen nu veilig verifiëren met een persoonlijke sleutel, waardoor de beveiliging wordt verbeterd en een alternatief verificatiemechanisme voor SFTP-toegang wordt geboden. Meer informatie in [deze sectie](../config/external-accounts.md).

**Verbeterde beveiliging**

* Vanaf Campagne v8.5.1 is het verificatieproces naar Campagne v8 verbeterd. Technische operatoren moeten gebruikmaken van Adobe Identity Management System (IMS) om verbinding te maken met Campagne. Leer hoe u uw bestaande technische account(s) kunt migreren in [dit technote](../../technotes/upgrades/ims-migration.md).
* U kunt geen operatoren meer maken vanuit de Campagne Client Console. De gebruikersinterface is dienovereenkomstig bijgewerkt. Nu moet je Adobe Admin Console gebruiken. [Meer informatie](../start/gs-permissions.md).
* Verschillende hulpmiddelen van derden zijn bijgewerkt om de beveiliging te optimaliseren.

**Compatibiliteitsupdates**

* De 32-bits versie van de clientconsole is nu vervangen. Vanaf 8.6 is de Client Console alleen beschikbaar in 64 bits. De upgrade naar de 64-bits versie van de clientconsole is naadloos. Raadpleeg voor meer informatie over het upgraden van uw besturingssysteem [technote](../../technotes/upgrades/console.md).
* U kunt nu uw Campagne v8 instantie met uw Azure synapse externe gegevensbestand verbinden. Deze verbinding wordt beheerd via een nieuw extern account. Meer informatie in [Matrixcompatibiliteitsmatrix voor campagnes](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda).


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
* Adobe Analytics-connector exporteert nu de metriek met het juiste kanaaltype. Deze was voorheen altijd ingesteld als &#39;email&#39;-kanaal. (NEO-26340)
* Probleem verholpen dat tot fouten kon leiden wanneer de Big Query-aansluiting met datetime-velden werd gebruikt. (NEO-49768)


## Release 8.4.5 {#release-8-4-5}

_3 april 2023_

**Patches**

* Probleem verholpen die tot een fout met betrekking tot een dubbele sleutel kon leiden als meerdere goedkeuringswerkstromen op hetzelfde schema werden ingesteld. (NEO-48968)
* Oplossing voor een regressieprobleem dat werd geïntroduceerd door NEO-54474 (8.4.4). Hierdoor werd het stijlkenmerk van de body-tag gewijzigd tijdens het uploaden van een afbeelding in de Digital Content Editor (DCE). (NEO-57697)
* Probleem verholpen dat tot een fout kon leiden wanneer het uitvoeren van gegevens gebruikend een schakelaar van CRM als de tijdelijke lijst een primaire sleutel had die lang in plaats van uuid wordt bepaald. (NEO-54153)
* Oplossing voor een regressieprobleem dat in 8.4.1 werd geïntroduceerd en dat tot fouten in pakketexport, FDA boven HTTP en rapportage kon leiden. (NEO-57731)
* Oplossing voor een regressieprobleem dat in 8.3.8 werd geïntroduceerd en waardoor de leveringsstatus niet correct kon worden bijgewerkt voor leveringen met negatieve id&#39;s. (NEO-54675)
* Probleem verholpen met Booleaanse velden bij het importeren van gegevens via de Big Query-connector (NEO-49181)


## Release 8.4.4 {#release-8-4-4}

_8 maart 2023_

**Beveiligingsverbetering**

* Tomcat is bijgewerkt van versie 8.5.81 naar 8.5.85 om de beveiliging te verbeteren. (NEO-50530)

**Patches**

* Probleem verholpen waardoor scrollen soms niet mogelijk was in het tabblad **Bewerken** van de Digital Content Editor (DCE). (NEO-54474)
* Probleem verholpen tijdens replicatie die tot een crash van een webserver kan leiden. (NEO-53670)


## Release 8.4.3 {#release-8-4-3}


_27 januari 2023_

**Verbeteringen**

* Probleem met synchronisatie van een leveringsindicator tussen de marketingserver en de server voor midsourcing is opgelost. (NEO-50724) <!--OKKKK-->
* Probleem verholpen dat tot een fout kon leiden bij het exporteren van een workflow. (NEO-50555) <!--OKKKK-->
* Probleem verholpen bij het uitbreiden van een schema dat eerder was uitgebreid. (NEO-49118) <!--OKKKK-->
* Probleem verholpen bij het gebruik van twee verrijkingsactiviteiten met dezelfde id in de koppelingsdefinitie. (NEO-48851)
* Oplossing voor twee problemen met de voorbereiding van de levering. De voorbereiding van de levering zou kunnen mislukken wanneer het aantal potentiële aanbiedingen dat wordt gemanipuleerd te hoog was. De tweede kwestie kwam voor wanneer beeld URLs als URLs werd gedefinieerd om in een levering van het tekstformaat te volgen. (NEO-48807) <!--OKKKK-->
* Probleem verholpen dat tot een workflowfout kon leiden waarbij een workflow de opslagnaam zou overschrijven die in de externe account voor niet-FFDA-accounts is gedefinieerd. (NEO-43209) <!--OKKKK-->
* Verbeterde beveiliging van webtoepassingen om DoS-aanvallen te voorkomen. (NEO-50757) <!--OKKKK-->
* Het beheer van geconsolideerde volggegevens is verbeterd in de **[!UICONTROL Consolidated tracking]** (nms:trackingStats) FFDA-tabel om dubbele gegevens te voorkomen. (NEO-46409)
* Probleem met een logische operator verholpen bij workflowquery&#39;s bij gebruik van een `enableIf` in een logische operatorvoorwaarde. De vorige logische voorwaarde is overschreven. (NEO-45815)  <!--OKKKK-->
* Het genereren van actieve profielen is geoptimaliseerd in de factureringsworkflow om de prestaties te verbeteren. (NEO-47658) <!--OKKKK-->
* Er is een probleem verholpen met het importeren van HTML-bestanden wanneer afbeeldingsnodes (img) URL&#39;s met personalisatievelden bevatten. (NEO-48396)
* Probleem verholpen met Snowflake (alle implementaties) bij gebruik van de sorteerparameter in een **Splitsen** workflowactiviteit. (NEO-45899) <!--OKKKK-->
* Er is een probleem verholpen dat tot een fout leidde wanneer een gebruiker met leestoegangsrechten voor de map nmsDeliveryMapping probeerde een campagne of workflow uit te voeren. (NEO-48230)
* Er is een probleem verholpen in het HTML-tabblad van een bezorging dat kon optreden voor grootschalige HTML-code. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Probleem verholpen waardoor gebruikers de **Geselecteerde lijnen samenvoegen** workflowoptie. (NEO-48488)
* Probleem verholpen met de Snowflake FDA-connector, die ertoe leidde dat records werden verwijderd bij gebruik van de optie &quot;0 of 1 cardinaliteit eenvoudige verbinding&quot; tijdens verrijking. (NEO-48737)
* De resterende verwijzingen naar de bibliotheek log4j zijn verwijderd uit de installatie van Campaign in Windows. (NEO-44851)
* Er is een probleem verholpen dat tot een fout kon leiden bij het toevoegen van de indicator **Ontvangers die hebben geopend** (estimatedRecipientOpen) in de aanvullende gegevens van een **Query**-workflowactiviteit. (NEO-46665)
* Het beheer van URL&#39;s bijhouden is verbeterd in workflows met meerdere leveringen om de prestaties te verbeteren. (NEO-50894) <!--OKKKK-->
* Probleem verholpen waarbij de replicatie van schema&#39;s die Xtkfolder gebruiken kon mislukken. (NEO-46787) <!--OKKKK-->
* Probleemoplossing die ervoor zorgde dat de aangepaste kolom &quot;lastModified&quot; in de tabel NmsSubscription zou worden verwijderd. (NEO-48402)


