---
title: Sms-connectoren
description: Meer informatie over SMS-connectors in Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
source-git-commit: e349e9f236c3eeb28ffe96bcc5ec72ab64c4c127
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%

---

# Informatie over typen SMS-connectors {#sms-connectors}

Adobe Campaign ondersteunt twee SMS-connectors die worden gebruikt voor het verzenden van SMS-berichten naar uw klanten:

* **Verouderde schakelaar van SMS**: Eerste versie van de schakelaar die in Campagne v7 en vroegere versies van Campagne v8 wordt gebruikt. [Meer informatie](#legacy-sms-connector)
* **schakelaar v2 van SMS**: Beschikbaar in GA beginnende Campagne v8.9.1, is deze v2 specifieke schakelaar van SMS gemoderniseerd om betere prestaties en betrouwbaarheid aan te bieden. [Meer informatie](#sms-connector-v2)

## Verouderde SMS-aansluiting {#legacy-sms-connector}

De verouderde sms-aansluiting is de MTA-gebaseerde sms-aansluiting die in eerdere versies van Adobe Campaign wordt gebruikt. Deze connector wordt nog steeds ondersteund voor bestaande implementaties, maar Adobe raadt u ten zeerste aan om de upgrade naar versie 8.9.1 of hoger uit te voeren om te profiteren van de verbeterde prestaties en betrouwbaarheid van de v2-connector.

Leren hoe te om van de v2 schakelaar te profiteren, verwijs naar de [ sectie van de Activering ](#activation).

Voor gedetailleerde informatie over de de schakelaarconfiguratie en het gebruik van erfenisSMS, verwijs naar de [ documentatie van Campaign Classic ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## SMS-connector v2 {#sms-connector-v2}

De v2-connector is beschikbaar in GA vanaf v8.9.1 en biedt SMPP-verbindingen in de transceivermodus, permanente SMPP-verbindingen en betere compatibiliteit. Er is een speciale externe SMS-account beschikbaar voor alle SMS-implementaties die de v2-connector gebruiken.

De v2-connector is standaard ingeschakeld voor nieuwe installaties. Als u een upgrade hebt uitgevoerd vanaf een vorige versie met behulp van de verouderde connector, moet u contact opnemen met uw Adobe-vertegenwoordiger om over te schakelen op de v2-connector. Zie de [ sectie van de Activering ](#activation).

Leren hoe te om schakelaar v2 van SMS in Campagne v8 te gebruiken, verwijs naar de [ documentatie van SMS ](sms.md).

>[!NOTE]
>
>De v2-connector is ook beschikbaar in de volgende builds met enkele beperkingen:
>* 8.8.1: release voor alle FDA-omgevingen voor campagnes. Niet beschikbaar voor campagnes voor FFDA-implementaties.
>* 8.8.2: release voor alle implementatietypen, inclusief FFDA. Uitgegeven in Beperkte Beschikbaarheid (LA).

## Activering {#activation}

### Waarom schakelen naar de v2-connector {#why-switch-v2}

Het specifieke proces van SMS introduceert steun voor de wijze van de zendontvanger SMPP, verminderend verbindentelling en verbeterend middelefficiency, terwijl nog het steunen van zender/ontvangermontages indien nodig. Het biedt beduidend grotere stabiliteit, met snellere terugwinning van fouten, blijvende verbindingen, en geen afhankelijkheid van lokale dossiers of interprocess mededeling. De prestaties zijn ook verbeterd, met lagere latentie, hogere productie, en intelligente microbatching om snelheid en betrouwbaarheid in evenwicht te brengen. Bovendien, vereenvoudigt de isolatie van het proces van SMS het oplossen van problemen en minimaliseert dwars-kanaalgevolgen. Deze verbeteringen maken van de specifieke schakelaar een robuustere en scalable oplossing voor levering van SMS.

### Configuratie {#configuration}

Met Adobe Campaign Managed Cloud Services worden de serverconfiguratie en de migratie van sms-connectors beheerd door Adobe. Deze technische procedure vereist directe toegang tot de dossiers van de serverconfiguratie en gegevensbestandverrichtingen.

Als u de SMS-connector v2 wilt activeren en gebruiken, moet u eerst een upgrade uitvoeren naar v8.9.1 of hoger. Neem contact op met uw Adobe-vertegenwoordiger of de klantenservice van Adobe. Zij zullen de noodzakelijke updates voor uw instantie plannen en uitvoeren.