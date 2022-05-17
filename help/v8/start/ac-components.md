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

Adobe Campaign is een oplossing voor kanaalmarketing die e-mail, mobiele, sociale en offlinecampagnes automatiseert. Adobe Campaign provides a central place to access your customer data and profiles. Met Adobe Campaign kunt u consistente ervaringen voor uw klanten ordenen, ontwerpen, uitvoeren en uw marketing aanpassen via verschillende kanalen, terwijl de ervaringen van klanten op elk apparaat en aanraakpunt worden verbeterd. Met Adobe Campaign kunt u meerdere gegevensbronnen beheren, uw publiekssegmenten definiëren en meerstapscampagnes voor meerdere kanalen plannen en uitvoeren via een visuele workflowinterface voor slepen en neerzetten.

Meer informatie over de belangrijkste mogelijkheden van de Campagne in [deze pagina](../start/get-started.md).

## Campagneonderdelen {#ac-components}

Adobe Campaign-componenten en algemene architectuur worden hieronder beschreven.

![](assets/ac-components.png)

### Presentation layer{#presentation-layer}

U kunt toegang krijgen tot Adobe Campaign via een rijke client, een dunne client of API-integratie.

* Rich client

   Campaign Rich client is a native application which communicates with the Adobe Campaign application server, through standard internet protocols, such as SOAP and HTTP.

   Campaign Client console centralizes all capabilities and settings, and requires minimal bandwidth as it relies on a local cache. De Campagne Client Console is ontworpen voor eenvoudige implementatie en kan worden geïmplementeerd vanuit een internetbrowser, automatisch worden bijgewerkt. Hiervoor is geen specifieke netwerkconfiguratie nodig omdat alleen HTTP(S)-verkeer wordt gegenereerd.

   ![](../assets/do-not-localize/glass.png) [Learn more about Campaign Client Console](../start/connect.md).

* Dunne client

   Met Adobe Campaign-mogelijkheden voor webtoegang hebt u via een gebruikersinterface toegang tot een subset van Campagnefuncties via een webbrowser. Gebruik deze webinterface om rapporten te openen, berichten te besturen en te valideren, toegang te krijgen tot controledashboards en nog veel meer.

   ![](../assets/do-not-localize/glass.png) [Meer informatie over Campagne Web Access](../start/connect.md).

* Externe toepassingen met API&#39;s

   In bepaalde gevallen, kan het systeem van externe toepassingen worden geroepen gebruikend de Diensten APIs van het Web die via het protocol van de ZEEP worden blootgesteld.

   ![](../assets/do-not-localize/glass.png) [Meer informatie over campagne-API&#39;s](../dev/api.md).

### Persistentielaag{#persistance-layer}

De gegevensbestanden van de campagne worden gebruikt als persistentielagen, en bevatten bijna alle informatie en gegevens die door Adobe Campaign worden beheerd. This includes: functional data, such as profiles, subscriptions, content; technical data, such as delivery jobs and logs, tracking logs; and work data (purchases, leads).

The reliability of the database is of utmost importance because the majority of Adobe Campaign components require access to the database in order to perform their tasks (with the exception of the redirection module).

### Logische toepassingslaag{#logical-app-layer}

De logische toepassingslaag van de campagne is gemakkelijk configureerbaar om aan complexe bedrijfsbehoeften te voldoen. U kunt Campagne als één enkel platform met verschillende toepassingen gebruiken die combineren om een open en scalable architectuur tot stand te brengen. Each Campaign intance is a collection of processes in the application layer, some of which are shared and some of which are dedicated.

## Campagne Managed Services{#ac-managed-services}

Adobe Campaign v8 is as a Managed Service geïmplementeerd: alle componenten van Adobe Campaign, inclusief de gebruikersinterface, de uitvoeringsbeheerengine en Campagne-databases, worden volledig door Adobe gehost, inclusief e-mailuitvoering, spiegelpagina&#39;s, traceringsserver en extern opvallende webcomponenten, zoals pagina-/voorkeurscentrum voor afmelden en bestemmingspagina&#39;s.

## Campagneprocessen

De server van het Web van de campagne controleert de toegang tot de processen van het Web van de Campagne. Javascript is the server-side language used for core product features and customization. Tomcat is the back-end engine and is embedded in the Campaign product as part of the Web process. Javascript wordt bijvoorbeeld gebruikt in JSP- of JSSP-pagina&#39;s om dynamische inhoud te renderen.

![](assets/ac-processes.png)

De console van de Cliënt van de campagne verbindt met de server van het Web gebruikend XML van de ZEEP over HTTP. De server van het Web verstrekt de veiligheidslaag, gaat de verzoeken tot de laag van de Toepassing over gebruikend Javascript en de interne processen van de Campagne toegang tot het gegevensbestand gebruikend SQL.

The overall communication between Campaign processes are described in the following standalone deployment diagram: all Campaign components are installed in the same machine.

![](assets/ac-standalone.png)

The user connects to the Campaign application server using the HTTP. Alle gegevens en informatie worden beheerd in het gegevensbestand van de Campagne. If a Campaign developer performs any configuration changes, it is captured in the database. Als een markeerteken een nieuwe campagne maakt, worden alle informatie en gegevens met betrekking tot deze nieuwe campagne ook beheerd in de database. When a marketer executes a campaign, email deliveries are sent to profiles from the Campaign server through the SMTP server. As profiles interact with email deliveries, such as opening the email, that tracking data is sent back to the tracking server.

![](../assets/do-not-localize/glass.png) [Meer informatie over campagneprocessen](../dev/general-architecture.md#dev-env).
