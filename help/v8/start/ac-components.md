---
title: Campagne-processen en onderdelen begrijpen
description: Campagne-processen en onderdelen begrijpen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 0%

---

# Campagne-processen en onderdelen begrijpen {#components-and-processes}

Adobe Campaign is een oplossing voor kanaalmarketing die e-mail, mobiele, sociale en offlinecampagnes automatiseert. Adobe Campaign biedt een centrale locatie voor toegang tot de gegevens en profielen van uw klanten. Met Adobe Campaign kunt u consistente ervaringen voor uw klanten ordenen, ontwerpen, uitvoeren en uw marketing aanpassen via verschillende kanalen, terwijl de ervaringen van klanten op elk apparaat en aanraakpunt worden verbeterd. Met Adobe Campaign kunt u meerdere gegevensbronnen beheren, uw publiekssegmenten definiëren en meerstapscampagnes voor meerdere kanalen plannen en uitvoeren via een visuele workflowinterface voor slepen en neerzetten.

Meer informatie over de belangrijkste mogelijkheden van de Campagne in [deze pagina](../start/get-started.md).

## Campagneonderdelen {#ac-components}

Adobe Campaign-componenten en algemene architectuur worden hieronder beschreven.

![](assets/ac-components.png)

### Presentatielaag{#presentation-layer}

U kunt toegang krijgen tot Adobe Campaign via een rijke client, een dunne client of API-integratie.

* Rijke client

   Campagne Rich-client is een native toepassing die communiceert met de Adobe Campaign-toepassingsserver via standaard internetprotocollen, zoals SOAP en HTTP.

   De console van de Cliënt van de campagne centraliseert alle mogelijkheden en montages, en vereist minimale bandbreedte aangezien het op een lokaal geheime voorgeheugen baseert. De Campagne Client Console is ontworpen voor eenvoudige implementatie en kan worden geïmplementeerd vanuit een internetbrowser, automatisch worden bijgewerkt. Hiervoor is geen specifieke netwerkconfiguratie nodig omdat alleen HTTP(S)-verkeer wordt gegenereerd.

   ![](../assets/do-not-localize/glass.png) [Meer informatie over Campagne Client Console](../start/connect.md).

* Dunne client

   Met Adobe Campaign-mogelijkheden voor webtoegang hebt u via een gebruikersinterface toegang tot een subset van Campagnefuncties via een webbrowser. Gebruik deze webinterface om rapporten te openen, berichten te besturen en te valideren, toegang te krijgen tot controledashboards en nog veel meer.

   ![](../assets/do-not-localize/glass.png) [Meer informatie over Campagne Web Access](../start/connect.md).

* Externe toepassingen met API&#39;s

   In bepaalde gevallen, kan het systeem van externe toepassingen worden geroepen gebruikend de Diensten APIs van het Web die via het protocol van de ZEEP worden blootgesteld.

   ![](../assets/do-not-localize/glass.png) [Meer informatie over campagne-API&#39;s](../dev/api.md).

### Persistentielaag{#persistance-layer}

De gegevensbestanden van de campagne worden gebruikt als persistentielagen, en bevatten bijna alle informatie en gegevens die door Adobe Campaign worden beheerd. Dit omvat: functionele gegevens, zoals profielen, abonnementen, inhoud; technische gegevens, zoals leveringstaken en logboeken, trackingstammen; en werkgegevens (aankopen, leads).

De betrouwbaarheid van de database is van het grootste belang omdat de meeste Adobe Campaign-componenten toegang tot de database vereisen om hun taken uit te voeren (met uitzondering van de omleidingsmodule).

### Logische toepassingslaag{#logical-app-layer}

De logische toepassingslaag van de campagne is gemakkelijk configureerbaar om aan complexe bedrijfsbehoeften te voldoen. U kunt Campagne als één enkel platform met verschillende toepassingen gebruiken die combineren om een open en scalable architectuur tot stand te brengen. Elke Campagneinstantie is een inzameling van processen in de toepassingslaag, waarvan sommige worden gedeeld en wat specifiek zijn.

## Campagne Managed Services{#ac-managed-services}

Adobe Campaign v8 is as a Managed Service geïmplementeerd: alle componenten van Adobe Campaign, inclusief de gebruikersinterface, de uitvoeringsbeheerengine en Campagne-databases, worden volledig door Adobe gehost, inclusief e-mailuitvoering, spiegelpagina&#39;s, traceringsserver en extern opvallende webcomponenten, zoals pagina-/voorkeurscentrum voor afmelden en bestemmingspagina&#39;s.

## Campagneprocessen

De server van het Web van de campagne controleert de toegang tot de processen van het Web van de Campagne. Javascript is de taal aan de serverzijde die voor kernproducteigenschappen en aanpassing wordt gebruikt. Tomcat is de achterste-eindmotor en is ingebed in het product van de Campagne als deel van het proces van het Web. Javascript wordt bijvoorbeeld gebruikt in JSP- of JSSP-pagina&#39;s om dynamische inhoud te renderen.

![](assets/ac-processes.png)

De console van de Cliënt van de campagne verbindt met de server van het Web gebruikend XML van de ZEEP over HTTP. De server van het Web verstrekt de veiligheidslaag, gaat de verzoeken tot de laag van de Toepassing over gebruikend Javascript en de interne processen van de Campagne toegang tot het gegevensbestand gebruikend SQL.

De algemene communicatie tussen de processen van de Campagne wordt beschreven in het volgende standalone plaatsingsdiagram: alle onderdelen van de campagne worden op dezelfde computer geïnstalleerd.

![](assets/ac-standalone.png)

De gebruiker verbindt met de de toepassingsserver van de Campagne gebruikend HTTP. Alle gegevens en informatie worden beheerd in het gegevensbestand van de Campagne. Als een ontwikkelaar van de Campagne om het even welke configuratieveranderingen uitvoert, wordt het gevangen in het gegevensbestand. Als een markeerteken een nieuwe campagne maakt, worden alle informatie en gegevens met betrekking tot deze nieuwe campagne ook beheerd in de database. Wanneer een teller een campagne uitvoert, worden de e-mailleveringen verzonden naar profielen van de server van de Campagne door de server SMTP. Aangezien profielen communiceren met e-mailleveringen, zoals het openen van de e-mail, worden deze gegevens teruggestuurd naar de trackingserver.

![](../assets/do-not-localize/glass.png) [Meer informatie over campagneprocessen](../dev/general-architecture.md#dev-env).
