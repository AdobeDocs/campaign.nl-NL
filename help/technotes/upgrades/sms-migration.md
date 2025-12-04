---
title: Naar de nieuwe SMS-connector v2
description: Leer hoe u naar de nieuwe SMS-connector v2 gaat
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: ed9e784c1610a6f042b99223ac0d4cc0cf312b09
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Naar de nieuwe SMS-connector v2

Dit document schetst de procedure en de belangrijkste overwegingen wanneer het migreren van de MTA-Gebaseerde schakelaar van SMS aan de nieuwe **specifieke het processchakelaar van SMS** in Adobe Campaign v8.

## Waarom schakelen naar de v2-connector

Het specifieke proces van SMS introduceert steun voor de wijze van de zendontvanger SMPP, verminderend verbindentelling en verbeterend middelefficiency, terwijl nog het steunen van zender/ontvangermontages indien nodig. Het biedt beduidend grotere stabiliteit, met snellere terugwinning van fouten, blijvende verbindingen, en geen afhankelijkheid van lokale dossiers of interprocess mededeling. De prestaties zijn ook verbeterd, met lagere latentie, hogere productie, en intelligente microbatching om snelheid en betrouwbaarheid in evenwicht te brengen. Bovendien, vereenvoudigt de isolatie van het proces van SMS het oplossen van problemen en minimaliseert dwars-kanaalgevolgen. Deze verbeteringen maken van de specifieke schakelaar een robuustere en scalable oplossing voor levering van SMS.

## Verschillen tussen v1- en v2-connectors

De speciale SMS-connector in Adobe Campaign v8 introduceert verschillende architecturale wijzigingen in vergelijking met de MTA-connector. Één zeer belangrijk verschil is het standaardgebruik van de zendontvangerwijze van SMPP, die het aantal verbindingen vermindert door te combineren verzend en ontvangt functies. Als de leverancier deze wijze niet steunt, is het nog mogelijk om afzonderlijke zender en ontvangerverbindingen te gebruiken. In tegenstelling tot de schakelaar MTA, heeft het toelaten van automatische antwoorden geen effect op verbindentelling, en alle ontvangerverbindingen kunnen om het even welk type van inkomend bericht behandelen.

Het aantal verbindingen wordt nu berekend met een andere formule:

```
Total connections = SMS sending threads * Number of MTA child connections. 
```

De sendingThreads parameter, die in serverConf wordt gedefinieerd, is standaard 1 en moet over het algemeen ongewijzigd blijven, tenzij deze specifiek wordt geoptimaliseerd voor hoge prestaties. Omdat één enkel proces al verkeer van SMS behandelt, wordt het beheren van parallellisme door deze parameters kritiek om systeemlading en gedrag te controleren.

Het verzendende venster gedraagt zich gelijkaardig aan de schakelaar MTA maar heeft een nog grotere invloed op prestaties op de specifieke wijze. Grotere verzendende vensters reduceren de IOPS van de database en verbeteren de doorvoer. De campagne kan vensters van meer dan 1000 berichten efficiënt behandelen, op voorwaarde dat de leverancier dit steunt en het gebruiksgeval voor een kleine marge van berichtverlies of duplicatie in het geval van verbindingskwesties toestaat. Aan de aanbodzijde kan het vormen van een groter SR verzendend venster ook de productie van het leveringsrapport aanzienlijk verbeteren.

Tot slot, terwijl MO (Mobiel voortgekomen) bericht behandeling functioneel onveranderd blijft, is de onderliggende code bijgewerkt. De productie per verbinding is nog beperkt de zelfde manier, maar de specifieke schakelaar laat veel sneller burst het verzenden toe. Nochtans, zonder productielimieten, kan de hoge snelheid het verzenden leverancier of systeemmiddelen overweldigen, die het raadzaam maken om expliciete MT productiekapitalen in de externe rekeningsconfiguratie te plaatsen.

## Omschakelingsprocedure

Om een vlotte schakelaar aan het specifieke proces van SMS te verzekeren, is het best om de verrichting tijdens laag of geen verkeer van SMS uit te voeren. Sommige gebufferde berichten kunnen in een ongeldige staat worden verloren of worden verlaten als de buffers MTA niet volledig worden gespoeld. Het is ook normaal om sommige SRs tot een week na de schakelaar te missen, toe te schrijven aan onvoorspelbare timing SR. Het niet volgen van deze voorzorgsmaatregelen kan tot berichtverlies of dubbel leiden, ondanks ingebouwde waarborgen.

Beide schakelaars van SMS gebruiken verschillende formaten voor de verwerking van SR (het Rapport van de Status). Hoewel beide toepassingen afhankelijk zijn van de tabel `NmsProviderMsgId` , hebben ze een andere interactie. Daarom vereist de omschakelingsschakelaars het ontruimen van de volledige lijst om conflicten of weesfoto&#39;s te verhinderen. Er zijn verschillende manieren om deze opschoning uit te voeren. Hieronder vindt u de SQL-query&#39;s die u kunt gebruiken:

```
TRUNCATE TABLE NmsProviderMsgId;
TRUNCATE TABLE NmsProviderMsgStatus;
```

### Stappen

1. Reviseer `serverConf` instellingen (`sms > mta2`).
1. Workflow voor het voorbereiden van berichten in realtime pauzeren (indien van toepassing).
1. Pauze alle SMS-leveringen.
1. Schakel de externe SMS-account uit.
1. Stop en herstart de MTA- en SMS-processen.
1. Zorg ervoor dat er geen SMPP-verbindingen actief zijn. Indien aanwezig, zorg ervoor alle leveringen worden gepauzeerd.
1. Wis de inhoud van de tabellen `NmsProviderMsgId` en `NmsProviderMsgStatus` in de database.
1. Op de externe rekening:
   * Selectievakje &quot;Speciaal proces&quot; inschakelen
   * Andere instellingen aanpassen: MTA-onderliggende verbindingen, MT-doorvoer, venster verzenden
1. Schakel de externe account opnieuw in en sla deze op.
1. SMS-leveringen hervatten.
1. Controleer of SMS-services normaal werken.

>[!NOTE]
>
>Houd SMS, MTA en MTA-onderliggende logboeken bij voor fouten of problemen.
>
>Vorige instellingen voor externe account opslaan voor terugdraaidoeleinden.

### Terugkeerprocedure

Terugdraaien naar de schakelaar MTA is mogelijk door de zelfde stappen te volgen die tijdens de aanvankelijke schakelaar, in de zelfde orde worden gebruikt. Dit omvat het stoppen of pauzeren van alle leveringen van SMS en het herstellen van de originele externe rekeningsconfiguratie.

1. Als de instantie leveringen in real time gebruikt, onderbreek het technische werkschema verantwoordelijk voor het voorbereiden van die berichten.
1. Pauze alle SMS-leveringen.
1. Schakel de externe SMS-account uit.
1. Stop en herstart zowel de MTA- als de SMS-processen.
1. Zorg ervoor dat geen verbindingen SMPP actief blijven; als zij, verifieer dat alle leveringen behoorlijk worden gepauzeerd.
1. Wis de tabellen `NmsProviderMsgId` en `NmsProviderMsgStatus` in de database.
1. Op de externe rekening:
   * Schakel de optie &quot;toegewezen proces&quot; in de externe account uit.
   * Alle vorige instellingen voor externe accounts herstellen: MTA-onderliggende verbindingen, MT-doorvoer, venster Verzenden
1. Schakel de externe account opnieuw in en sla deze op.
1. Hervat alle SMS-leveringen.
1. Ten slotte, bevestig dat de diensten van SMS normaal functioneren.
