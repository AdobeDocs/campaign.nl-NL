---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 55711ea42b9cc0be70e875e1544780b6983af98b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Nieuwste release{#latest-release}

Deze pagina bevat nieuwe mogelijkheden, verbeteringen en oplossingen die worden geleverd met de **nieuwste versie van Campaign v8**.

## Release 8.4.4 {#release-8-4-4}

>[!CAUTION]
>
> De upgrade van Client Console is verplicht. Lees op deze [pagina](../start/connect.md#download-ac-console) hoe u uw Client Console kunt upgraden.

_8 maart 2023_

**Beveiligingsverbetering**

* Tomcat is bijgewerkt van versie 8.5.81 naar 8.5.85 om de beveiliging te verbeteren. (NEO-50530)

**Patches**

* Probleem verholpen waardoor u niet in het dialoogvenster **Bewerken** tabblad van de Digital Content Editor (DCE). (NEO-54474)
* Probleem verholpen tijdens replicatie die tot een crash van een webserver kan leiden. (NEO-53670)

## Release 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> De upgrade van Client Console is verplicht. Lees op deze [pagina](../start/connect.md#download-ac-console) hoe u uw Client Console kunt upgraden.

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
