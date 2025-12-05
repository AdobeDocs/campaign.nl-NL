---
title: Naar de nieuwe SMS-connector v2
description: Leer hoe u naar de nieuwe SMS-connector v2 gaat
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 30ab5a10f17baddfc455dc406a4f31f058ea05ba
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Naar de nieuwe SMS-connector v2

Adobe Campaign v8 introduceert een nieuwe **specifieke het processchakelaar van SMS** (v2), die betere prestaties en betrouwbaarheid in vergelijking met de erfenis op MTA-Gebaseerde schakelaar van SMS aanbiedt.

## Waarom schakelen naar de v2-connector

Het specifieke proces van SMS introduceert steun voor de wijze van de zendontvanger SMPP, verminderend verbindentelling en verbeterend middelefficiency, terwijl nog het steunen van zender/ontvangermontages indien nodig. Het biedt beduidend grotere stabiliteit, met snellere terugwinning van fouten, blijvende verbindingen, en geen afhankelijkheid van lokale dossiers of interprocess mededeling. De prestaties zijn ook verbeterd, met lagere latentie, hogere productie, en intelligente microbatching om snelheid en betrouwbaarheid in evenwicht te brengen. Bovendien, vereenvoudigt de isolatie van het proces van SMS het oplossen van problemen en minimaliseert dwars-kanaalgevolgen. Deze verbeteringen maken van de specifieke schakelaar een robuustere en scalable oplossing voor levering van SMS.

## Configuratie

Met Adobe Campaign Managed Cloud Services worden de serverconfiguratie en de migratie van sms-connectors beheerd door Adobe. Deze technische procedure vereist directe toegang tot de dossiers van de serverconfiguratie en gegevensbestandverrichtingen.

Als u naar de nieuwe SMS-connector v2 moet migreren, neemt u contact op met uw Adobe-vertegenwoordiger of de klantenservice van Adobe. Zij zullen de noodzakelijke updates voor uw instantie plannen en uitvoeren.

Voor meer informatie over het kanaal van SMS in Campagne v8, verwijs naar de [&#x200B; documentatie van SMS &#x200B;](../../v8/send/sms/sms.md).
