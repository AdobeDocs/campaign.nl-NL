---
title: Campagne-onderdelen en -processen begrijpen
description: Campagne-onderdelen en -processen begrijpen
feature: Overview, Architecture, Configuration
role: User
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: 6926d84576df1810b511ef1a9976593cb99585bb
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---

# Campagne-onderdelen en -processen begrijpen {#components-and-processes}

Adobe Campaign is een oplossing voor kanaalmarketing die e-mail, mobiele, sociale en offlinecampagnes automatiseert. Adobe Campaign biedt een centrale locatie voor toegang tot de gegevens en profielen van uw klanten. Met Adobe Campaign kunt u consistente ervaringen voor uw klanten ordenen, ontwerpen, uitvoeren en uw marketing aanpassen via verschillende kanalen, terwijl de ervaringen van klanten op elk apparaat en aanraakpunt worden verbeterd. Met Adobe Campaign kunt u meerdere gegevensbronnen beheren, uw publiekssegmenten definiëren en meerstapscampagnes voor meerdere kanalen plannen en uitvoeren via een visuele workflowinterface voor slepen en neerzetten.

Leer meer over de belangrijkste mogelijkheden van de Campagne in [ deze pagina ](../start/get-started.md).

## Campagne-onderdelen {#ac-components}

Adobe Campaign-componenten en algemene architectuur worden hieronder beschreven.

![](assets/do-not-localize//ac-components.png)



### Persistentielaag{#persistance-layer}

De gegevensbestanden van de campagne worden gebruikt als persistentielagen, en bevatten bijna alle informatie en gegevens die door Adobe Campaign worden beheerd. Dit omvat: functionele gegevens, zoals profielen, abonnementen, inhoud; technische gegevens, zoals leveringstaken en logbestanden, trackinglogbestanden en werkgegevens (aankopen, leads).

De betrouwbaarheid van de database is van het grootste belang omdat de meeste Adobe Campaign-componenten toegang tot de database vereisen om hun taken uit te voeren (met uitzondering van de omleidingsmodule).

### Logische toepassingslaag{#logical-app-layer}

De logische toepassingslaag van de campagne is gemakkelijk configureerbaar om aan complexe bedrijfsbehoeften te voldoen. U kunt Campagne als één enkel platform met verschillende toepassingen gebruiken die combineren om een open en scalable architectuur tot stand te brengen. Elke Campagneinstantie is een inzameling van processen in de toepassingslaag, waarvan sommige worden gedeeld en wat specifiek zijn.

## Door campagne beheerde Cloud Servicen{#ac-managed-services}

Adobe Campaign v8 is as a Managed Service geïmplementeerd: alle componenten van Adobe Campaign, inclusief de gebruikersinterface, de uitvoeringsbeheerengine en de campagnedatabases, worden volledig gehost via Adobe, waaronder e-mailuitvoering, spiegelpagina&#39;s, trackingserver en extern gerichte webcomponenten, zoals pagina/voorkeurscentrum voor afmelden en bestemmingspagina&#39;s.

## Campagneprocessen

De server van het Web van de campagne controleert de toegang tot de processen van het Web van de Campagne. Javascript is de taal aan de serverzijde die voor kernproducteigenschappen en aanpassing wordt gebruikt. Tomcat is de achterste-eindmotor en is ingebed in het product van de Campagne als deel van het proces van het Web. Javascript wordt bijvoorbeeld gebruikt in JSP- of JSSP-pagina&#39;s om dynamische inhoud te renderen.

![](assets/do-not-localize/ac-processes.png)

De de cliëntconsole van de campagne verbindt met de server van het Web gebruikend SOAP XML over HTTP. De server van het Web verstrekt de veiligheidslaag, gaat de verzoeken tot de laag van de Toepassing over gebruikend Javascript en de interne processen van de Campagne toegang tot het gegevensbestand gebruikend SQL.

<!--The overall communication between Campaign processes are described in the following standalone deployment diagram: all Campaign components are installed in the same machine.

![](assets/do-not-localize//ac-standalone.png) -->

De gebruiker verbindt met de de toepassingsserver van de Campagne gebruikend HTTP. Alle gegevens en informatie worden beheerd in het gegevensbestand van de Campagne. Als een ontwikkelaar van de Campagne om het even welke configuratieveranderingen uitvoert, wordt het gevangen in het gegevensbestand. Als een markeerteken een nieuwe campagne maakt, worden alle informatie en gegevens met betrekking tot deze nieuwe campagne ook beheerd in de database. Wanneer een teller een campagne uitvoert, worden de e-mailleveringen verzonden naar profielen van de server van de Campagne door de server SMTP. Als profielen reageren op e-mailleveringen, zoals het openen van de e-mail, worden deze gegevens teruggestuurd naar de trackingserver.

[ leer meer over de processen van de Campagne ](../architecture/general-architecture.md#dev-env).
