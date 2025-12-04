---
product: campaign
title: Leverbaarheid in Adobe Campaign bewaken
description: Meer informatie over gereedschappen en richtlijnen voor het controleren van de prestaties in Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# Controleer uw prestaties{#monitoring-deliverability}

Hieronder vindt u meer informatie over de verschillende bewakingstools van Adobe Campaign en enkele aanvullende richtlijnen voor het benutten van de functies die Adobe Campaign aanbiedt om de prestaties van uw platform te controleren.

## Monitoringinstrumenten {#monitoring-tools}

Adobe Campaign biedt u toegang tot de hieronder vermelde hulpmiddelen voor het leveren van producten.

### Inboxrendering {#inbox-rendering-tool}

Het [ Inbox teruggevend rapport ](inbox-rendering.md) laat u toe om uw berichten op belangrijke e-mailcliënten voor te vertonen om inhoud en reputatie af te tasten.

### Leveringsdoorvoer {#throughput-reports}

Het **[!UICONTROL Delivery throughput]** -rapport geeft u een overzicht van de doorvoer van het gehele platform gedurende een bepaalde periode. Zie [deze sectie](../reporting/global-reports.md#delivery-throughput)voor meer informatie.

### Uitzendstatistieken {#broadcast-statistics}

Elke levering produceert een rapport van uitzendingsstatistieken voor de verschillende dienstverleners van Internet (ISPs). Het toont sommige gegevenskwaliteit en reputatie metriek die uw leverbaarheid, met inbegrip van de volgende aantallen kunnen beïnvloeden:

**[!UICONTROL Hard bounces]** geeft de gegevenskwaliteit aan. Dit getal moet lager zijn dan 2%.

**[!UICONTROL Soft bounces]** geeft reputatie aan. Dit aantal zou niet hoger moeten zijn dan 10% voor om het even welke bepaalde ISP.

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### Leveringsdashboard {#delivery-dashboard-monitoring}

Meer over het algemeen, geeft het [ leveringsdashboard ](delivery-dashboard.md) u toegang tot:

De leveringssamenvatting, die de details van het verzenden en het aantal berichten toont om te verzenden, te verwerken en met succes te verzenden.

De leveringslogboeken en de geschiedenis, die tonen welk doel is uitgesloten en waarom.

De volgende logboeken, die het volgen informatie zoals opent tonen en klikt.

### SpamAssassin testen {#spam-testing}

Gebruik [ SpamAssassin ](spamassassin.md) om uw e-mailinhoud te testen en het te scoren om te bepalen of een bericht het risico loopt om als spam door de anti-anti-spamhulpmiddelen worden beschouwd die op ontvangstbewijs worden gebruikt.

### Configuratiescherm  {#control-panel-monitoring}

>[!NOTE]
>
>Het Configuratiescherm is beschikbaar voor gebruikers van beheerde Cloud Services voor campagne v8. Leer meer over [ Controlebord ](../config/self-service.md).

Het Comité van de Controle van de campagne [ ](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl){target="_blank"} verstrekt controlemogelijkheden voor levering, met inbegrip van subdomein en certificaatbeheer, actieve profielen die, en leveringsproductie en latentiemetriek controleren.

## Controlerichtlijnen {#monitoring-guidelines}

Hier volgen enkele aanvullende richtlijnen voor het controleren van de leverbaarheid:

### Bewaking van de platformafvoer

Controleer regelmatig de [ leveringsproductie ](../reporting/global-reports.md#delivery-throughput) voor het volledige platform om te verifiëren of het met de originele opstelling verenigbaar is.

### Configuratie opnieuw proberen

Controle dat [ opnieuw probeert ](delivery-failures.md#retries) opstelling correct (30 minuten voor herbeproefperiode en meer dan 20 herpogingen) in leveringsmalplaatjes is.

### Verificatie van postvak stuiteren

Verifieer regelmatig dat de [ stuiteren ](delivery-failures.md#bounce-mail-qualification) brievenbus toegankelijk is en dat de rekening niet op het punt staat te verlopen.

### Controles van de leveringsprestaties

Controleer elke leveringsproductie, die van het [ leveringsdashboard ](delivery-dashboard.md) toegankelijk is, om ervoor te zorgen dat het met de geldigheid van de leveringsinhoud verenigbaar is (b.v. &quot;flitsverkoop&quot;zou in notulen, niet dagen moeten worden geleverd).

### Validatie van golflengte

Wanneer het gebruiken van [ golven ](configure-and-send.md#sending-using-multiple-waves), verifieer dat elke golf genoeg tijd heeft om te beëindigen alvorens volgende wordt teweeggebracht.

### Quarantaine-controle

Controleer dat het aantal fouten en nieuwe [ quarantines ](quarantines.md) met andere leveringen verenigbaar zijn.

### Analyse van het leveringslogboek

Raadpleeg zorgvuldig de [ leveringslogboeken ](delivery-dashboard.md#delivery-logs-and-history) in detail om het soort fouten te controleren die worden benadrukt (lijsten van gewezen personen, DNS kwesties, anti-spamregels, enz.).

## Verwante onderwerpen

{de Gids van de Beste praktijken van de Levering van Adobe 1} verstrekt uitvoerige begeleiding op leveringsstrategie, definitie, metriek, en beste praktijken.[](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}

[ wat leverbaarheid ](about-deliverability.md) is introduceert zeer belangrijke leveringsconcepten en hoe te om uw leverbaarheidstarief in Campagne te verbeteren.

[ de mislukkingen en de stuitingen van de Levering ](delivery-failures.md) beschrijft de verschillende types van leveringsmislukkingen, hoe de Campagne hen behandelt, en omvat het oplossen van problemenbegeleiding voor gemeenschappelijke kwesties.

[ het beheer van de Quarantaine ](quarantines.md) verklaart hoe de Campagne quarantined adressen beheert om uw verzendende reputatie te beschermen.

[ het berichtinhoud van de Controle ](control-message-content.md) verstrekt begeleiding op hoe te om uw inhoud te verzekeren voor leverability wordt geoptimaliseerd.
