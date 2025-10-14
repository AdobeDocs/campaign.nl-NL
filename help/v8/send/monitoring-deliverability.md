---
product: campaign
title: Leverbaarheid in Adobe Campaign bewaken
description: Meer informatie over gereedschappen en richtlijnen voor het controleren van de prestaties in Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 2%

---

# Controleer uw prestaties{#monitoring-deliverability}

Hieronder vindt u meer informatie over de verschillende bewakingstools van Adobe Campaign en enkele aanvullende richtlijnen voor het benutten van de functies die Adobe Campaign aanbiedt om de prestaties van uw platform te controleren.

## Monitoringinstrumenten {#monitoring-tools}

Adobe Campaign biedt u toegang tot alle hieronder vermelde hulpmiddelen voor het leveren van producten.

* Het [&#x200B; Inbox teruggevend rapport &#x200B;](inbox-rendering.md) laat u toe om uw berichten op belangrijke e-mailcliënten voor te vertonen om inhoud en reputatie af te tasten.

* Het **[!UICONTROL Delivery throughput]** -rapport geeft u een overzicht van de doorvoer van het gehele platform gedurende een bepaalde periode. Zie [deze sectie](../reporting/global-reports.md#delivery-throughput)voor meer informatie.
* Elke levering produceert een rapport van uitzendingsstatistieken voor de verschillende dienstverleners van Internet (ISPs). Het toont sommige gegevenskwaliteit en reputatie metriek die uw leverbaarheid, met inbegrip van de volgende aantallen kunnen beïnvloeden:
   * **[!UICONTROL Hard bounces]** geeft de gegevenskwaliteit aan. Dit getal moet lager zijn dan 2%.
   * **[!UICONTROL Soft bounces]** geeft reputatie aan. Dit aantal zou niet hoger moeten zijn dan 10% voor om het even welke bepaalde ISP.

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* Meer over het algemeen, geeft het [&#x200B; leveringsdashboard &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=nl-NL#sending-messages){target="_blank"} u toegang tot:
   * de leveringssamenvatting, waarin de bijzonderheden van de verzending en het aantal berichten dat met succes moet worden verzonden, verwerkt en verzonden, worden vermeld;
   * de leveringslogboeken en de geschiedenis waaruit blijkt welk doel is uitgesloten en waarom;
   * de volgende logboeken, die het volgen informatie zoals opent tonen en klikt.

## Controlerichtlijnen {#monitoring-guidelines}

Hier volgen enkele aanvullende richtlijnen voor het controleren van de leverbaarheid:

* Controleer regelmatig de [&#x200B; leveringsproductie &#x200B;](../reporting/global-reports.md#delivery-throughput) voor het volledige platform om te verifiëren of het met de originele opstelling verenigbaar is.
* Controle dat [&#x200B; opnieuw probeert &#x200B;](delivery-failures.md#retries) opstelling correct (30 minuten voor herbeproefperiode en meer dan 20 herpogingen) in leveringsmalplaatjes is.
* Verifieer regelmatig dat de [&#x200B; stuiteren &#x200B;](delivery-failures.md#bounce-mail-qualification) brievenbus toegankelijk is en dat de rekening niet op het punt staat te verlopen.
* Controleer elke leveringsproductie, die van het [&#x200B; leveringsdashboard &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=nl-NL#sending-messages){target="_blank"} toegankelijk is, om ervoor te zorgen dat het met de geldigheid van de leveringsinhoud verenigbaar is (b.v. &quot;flitsverkoop&quot;zou in notulen, niet dagen moeten worden geleverd). is een belangrijk hulpmiddel om uw leveringen en potentiële problemen tijdens het verzenden van berichten te controleren.
* Wanneer het gebruiken van [&#x200B; golven &#x200B;](configure-and-send.md#sending-using-multiple-waves), verifieer dat elke golf genoeg tijd heeft om te beëindigen alvorens volgende wordt teweeggebracht.
* Controleer dat het aantal fouten en nieuwe [&#x200B; quarantines &#x200B;](quarantines.md) met andere leveringen verenigbaar zijn.
* Raadpleeg zorgvuldig de [&#x200B; leveringslogboeken &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=nl-NL#delivery-logs-and-history){target="_blank"} in detail om het soort fouten te controleren die worden benadrukt (lijsten van gewezen personen, DNS kwesties, anti-spamregels, enz.).
