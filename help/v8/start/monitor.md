---
title: Overzicht van de bewaking van campagnes
description: Leer hoe u leveringen, workflows en uw Campagne-instantie kunt controleren
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 2%

---

# Overzicht van de bewaking van campagnes {#monitor-campaign}

Adobe Campaign biedt een uitgebreide reeks mogelijkheden om uw processen, leveringen en omgeving te controleren om optimale prestaties te garanderen en problemen proactief op te lossen.

>[!NOTE]
>
>Als beheerder van de Campagne, kunt u [ Controlebord van de Campagne ](#control-panel) ook gebruiken om uw instanties te controleren, prestaties te beheren, en montages met zelfbediening mogelijkheden te vormen.

## Uw leveringen controleren {#monitor-deliveries}

Het controleren van uw leveringen nadat deze zijn verzonden, is een belangrijke stap om ervoor te zorgen dat uw marketingcampagnes efficiënt zijn en uw klanten bereiken. Na het verzenden van een levering, kunt u zijn status controleren en zeer belangrijke metriek in het leveringsdashboard volgen. Het dashboard verleent toegang tot leveringslogboeken, uitsluitingslogboeken, het volgen logboeken, en andere controlemogelijkheden om u te helpen uw leveringsprestaties over alle kanalen analyseren.

**E-mailleveringen** - de status van de e-maillevering van de monitor, spoorzeer belangrijke metriek, en toegang gedetailleerde logboeken. Leer meer over [ controleleveringen in Campagne UI ](../send/delivery-dashboard.md), [ leveringsstatussen ](../send/delivery-statuses.md) en [ e-mailleveringscontrole ](../send/send.md#email-monitoring).

{de leveringen van 0} SMS **- de leveringsstatus van het Sms van het Spoor en controleren zeer belangrijke metriek in het de leveringsdashboard van SMS.** Leer meer over [ controle van SMS ](../send/sms/sms-monitor.md).

**duw berichten** - de levering van het pushbericht van de Monitor om ervoor te zorgen zij uw mobiele app gebruikers effectief bereiken. Leer meer over [ duw- bericht controle ](../send/push.md#push-test).

**Transactionele berichten** - voor berichten die door gebeurtenissen worden teweeggebracht, de status van de gebeurtenisverwerking, berichtuitvoering en leveringsstatus controleren. Leer meer over [ transactiebericht controle ](../send/delivery-execution.md#monitor-messages).

**mislukkingen van de Levering** - Begrijpend waarom een mislukte levering kritiek is om een schoon gegevensbestand te handhaven en goede leverbaarheidstarieven te verzekeren. Leveringsfouten worden geclassificeerd in harde stuiteringen, zachte stuiteringen en genegeerde berichten. Leer meer over [ leveringsmislukkingen en quarantines ](../send/delivery-failures.md).

## Te leveren items bewaken {#monitor-deliverability}

Dankzij de bewaking van de aflevering kunt u ervoor zorgen dat uw berichten de inboxes van de ontvangers bereiken en spamfilters voorkomen. Adobe Campaign biedt verschillende ingebouwde tools voor het bewaken en verbeteren van de leverbaarbaarheid, waaronder leveringsrapporten, inbox-rendering, SpamAssassin-tests en uitzendstatistieken. De volgende best practices op het gebied van leverbaarheid, zoals het bijhouden van een schone e-maillijst, het controleren van de reputatie van de afzender en het verifiëren van verzendende domeinen, zijn van essentieel belang voor het handhaven van goede leveringspercentages.

Leer meer over [ de controlehulpmiddelen van de leverbaarheid ](../send/monitoring-deliverability.md) en [ best practices van de leverbaarheid ](../send/about-deliverability.md).

## Workflows bewaken {#monitor-workflows}

Workflows zijn essentieel om uw marketingcampagnes en gegevensverwerking te automatiseren. De uitvoering van de workflow controleren helpt u:

* Workflows voltooien
* Fouten opsporen en problemen oplossen
* Workflowprestaties optimaliseren

### Functies voor workflowbewaking {#workflow-monitoring}

**controleert de volgende werkschemaelementen:**

**de uitvoeringsstatus van het Werkschema** - spoor of de werkschema&#39;s lopen, gepauzeerd, ontbroken, of voltooid zijn. [ Leer meer over werkschemauitvoering ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

**de uitvoeringslogboeken van de Activiteit** - toegang gedetailleerde logboeken voor elke werkschemaactiviteit om kwesties problemen op te lossen en prestaties te optimaliseren.

**hitmap van het Werkschema** - visualiseer de patronen van de werkschemauitvoering, identificeer knelpunten, en controleer gezamenlijke werkschema&#39;s. De workflow HeatMap is beschikbaar voor campagnebeheerders. [ Leer meer over werkschemaritmap ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html){target="_blank"}

**geschiedenis van het Werkschema** - spoor alle werkschemauitvoeringen en wijzigingen in tijd om werkschemagedrag en prestaties te begrijpen.

## Uw instantie controleren {#monitor-instance}

Met Instance Monitoring kunt u de gezondheid en prestaties van uw Adobe Campaign-omgeving garanderen.

### Audit trail {#audit-trail}

Met de zelfbedieningsinterface van het audittrail kunt u de wijzigingen in uw Adobe Campaign-instantie controleren. Het spoor van de controle vangt, in real time, een uitvoerige lijst van acties en gebeurtenissen die binnen uw instantie voorkomen.

**spoor van de Controle van het Gebruik aan:**

* **de componentenveranderingen van het Spoor**: Monitor wat met uw werkschema&#39;s, schema&#39;s, opties, en andere componenten gebeurde
* **identificeer wie veranderingen** aanbracht: Zie wie het laatst een specifiek element bijwerkte en wanneer
* **Begrijp gebruikersacties**: Herzie wat de gebruikers in de instantie voor het oplossen van problemen of controle deden
* **handhaaf naleving**: Houd alle configuratieveranderingen voor naleving en veiligheidsdoeleinden

Het spoor van de Controle is toegankelijk door de de cliëntconsole van de Campagne en verstrekt gedetailleerde informatie over acties die door gebruikers worden uitgevoerd.

Leer meer over [ spoor van de Controle ](../reporting/audit-trail.md)

### Prestatiebewaking {#performance-monitoring}

Campagne v8 biedt verschillende controlemogelijkheden om de prestaties van uw instantie te volgen en een optimale werking te garanderen:

**controle van het Gegevensbestand** - het gegevensbestandgebruik en de capaciteit van de Monitor door Controlebord om optimale prestaties en opslagbeheer te verzekeren. [ Leer meer over gegevensbestand controle ](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Actieve profielen die** controleren - spoor actief profielgebruik tegen uw contractuele grenzen om naleving te handhaven en middeltoewijzing te optimaliseren. [ leer meer over actieve profielen ](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}

**controle van het Werkschema** - de status van de werkschemauitvoering van de monitor om langdurige werkschema&#39;s te identificeren en alle technische werkschema&#39;s te verzekeren correct lopen. [ leer meer over technische werkschema&#39;s ](#technical-workflows)

**Productie en latentie van de levering** - de leveringproductie van het spoor (berichten die per uur worden verzonden) en latentie voor transactionele mededelingen door Controlebord. [ leer meer over productie controle ](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>Voor Campagne v8 Managed Cloud Services wordt de serverinfrastructuur (CPU, geheugen, schijf) gecontroleerd en beheerd door Adobe.

### Technische workflows {#technical-workflows}

Technische workflows zijn essentiële processen die op de achtergrond worden uitgevoerd om uw instantie Campagne te onderhouden.

**Monitor dat de technische werkschema&#39;s zijn:**

* Uitvoeren volgens schema
* Voltooien zonder fouten
* Gegevens correct verwerken

**Zeer belangrijke technische werkschema&#39;s om te controleren:**

| Workflow | Doel |
|----------|---------|
| **Tracking** | Verwerkt trackinggegevens van e-mailleveringen |
| **Opschonen** | Verwijdert oude gegevens en logboeken om databaseprestaties te behouden |
| **de update van de Leverbaarheid** | Werkt leverbaarbaarheidsregels en spamfilterpatronen bij |
| **Opschonen van het Gegevensbestand** | Oude bezorgings- en trackinglogboeken worden gewist |

Leer meer over [ technische werkschema&#39;s ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

### Campaign-configuratiescherm {#control-panel}

Het Controlebord van de campagne voorziet beheerders van zelfbediening mogelijkheden om de instanties van de Campagne te controleren en te beheren.

| Type controle | Mogelijkheden |
|-----------------|--------------|
| **Prestaties** | Actief profielgebruik bijhouden, databasegebruik en -capaciteit controleren, status van workflowuitvoering weergeven, doorvoerdoorvoer controleren en latentie |
| **Infrastructuur** | SFTP-opslagcapaciteit bewaken, subdomeinconfiguratie volgen, verlopen van SSL-certificaten controleren, lijst met IP-adressen beheren |
| **Instantie** | Builversie en geïnstalleerde pakketten weergeven, systeemconfiguratie controleren, geautoriseerde externe domeinen beheren |

Leer meer over [ Controle ](../config/self-service.md) en [ de prestaties van het Controlebord controle ](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=nl){target="_blank"}

>[!NOTE]
>
>Adobe bewaakt en beheert voor Campagne v8 Managed Cloud Services de serverinfrastructuur, het besturingssysteem en de toepassingslaag. U kunt de controlemogelijkheden gebruiken die in deze pagina en het Controlebord worden beschreven om uw instantieprestaties, werkschema&#39;s, en leveringen te controleren.

## Tracering en rapportage {#tracking-reporting}

### Berichten tracken {#message-tracking}

Houd het gedrag van ontvangers bij en meet de doeltreffendheid van uw campagnes:

* **opent**: Spoor wanneer de ontvangers uw e-mail openen
* **klikt**: Monitor die ontvangers verbindt klikt
* **Unsubscribes**: De verzoeken van de spooropt-out
* **spiegel paginameningen**: Zie hoeveel ontvangers uw e-mail in browser bekijken

Leer meer over [ bericht het volgen ](../send/tracking.md)

### Leveringsrapporten {#delivery-reports}

Adobe Campaign biedt een uitgebreide reeks rapporten om uw prestaties van de levering te analyseren:

* **Overzicht van de Levering**: Overzicht van verzendt, leveringen, en mislukkingen
* **het Volgen indicatoren**: Opent, klikt, en klik-door tarieven
* **URLs en klik stromen**: De populairste verbindingen in uw leveringen
* **Het klikt**: Visuele vertegenwoordiging van waar de ontvangers in uw e-mail klikte

Leer meer over [ leveringsrapporten ](../reporting/delivery-reports.md)

### Algemene rapporten {#global-reports}

Toegang tot algemene rapporten om de prestaties in alle campagnes en leveringen te analyseren:

* **Productie van de levering**: De berichten die in tijd worden verzonden
* **niet-te leveren items en stuitingen**: Analyse van ontbroken leveringen
* **de activiteiten van de Gebruiker**: Opent, klikt, en unsubscript over alle campagnes

Leer meer over [ globale rapporten ](../reporting/global-reports.md)

## Verwante onderwerpen {#related-topics}

* [Best practices voor leveringen](delivery-best-practices.md)
* [Quarantainebeheer](../send/quarantines.md)
* [Leveringen configureren en verzenden](../send/configure-and-send.md)
* [Aan de slag met rapportage](../reporting/gs-reporting.md)

