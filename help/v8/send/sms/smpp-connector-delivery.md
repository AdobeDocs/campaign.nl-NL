---
title: SMPP-connector in leveringseigenschappen
description: Informatie over de instellingen van de SMPP-connector in leveringen
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="Beperkte beschikbaarheid" type="Informative"
exl-id: 704e151a-b863-46d0-b8a1-fca86abd88b9
source-git-commit: 30babc4bec802f61d3bd28a7ebcf0c15e22b2284
workflow-type: tm+mt
source-wordcount: '1326'
ht-degree: 1%

---

# Beschrijving van SMPP-aansluiting {#smpp-connector-desc}

>[!IMPORTANT]
>
>Dit geldt voor Adobe Campaign v8.7.2 en hoger.
>
>Voor oudere versies, verwijs naar de [ documentatie van Campaign Classic v7 ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Gegevensstroom SMS-connector {#sms-data-flow}

Deze sectie beschrijft hoe het proces van SMS gegevens behandelt.

Hier is een blokdiagram op hoog niveau dat samenvat hoe het proces van SMS met zijn milieu interactie aangaat.

![](assets/smsv2_highlevel.png){zoomable="yes"}

Het proces van SMS gastheren 2 belangrijke componenten: de schakelaar SMPP zelf die communicatie met de leverancier SMPP behandelt, en een achtergrondtaak voor verenigbaarheid SR.

### Gegevensstroom voor SMPP-accounts {#sms-data-flow-smpp-accounts}

Het proces van SMS opiniepeilt nms:extAccount en paagt nieuwe verbindingen in zijn schakelaar SMPP, die montages van elke rekening overgaat. De opiniepeilingsfrequentie kan in serverConf, in het *configRefreshMillis* plaatsen worden aangepast.

Voor elke actieve rekening SMPP, probeert de schakelaar SMPP om verbindingen actief te houden de hele tijd. De verbinding wordt opnieuw verbonden als de verbinding wordt verloren.

### Gegevensstroom tijdens verzenden van berichten {#sms-data-flow-sending-msg}

* Het proces van SMS selecteert actieve leveringen door nms te scannen:levering. Een levering is actief wanneer:
   * Zijn staat impliceert dat de berichten kunnen worden verzonden
   * De geldigheidsperiode is niet verstreken
   * Het is in feite een levering (het is bijvoorbeeld geen sjabloon, het wordt niet verwijderd)
   * De SMPP-connector kan ten minste één verbinding openen voor de externe account die is gekoppeld aan de levering
* Voor elke levering, laadt het proces van SMS leveringsdelen. Als het leveringsgedeelte gedeeltelijk werd verzonden, controleert het proces van SMS welke berichten reeds werden verzonden door het brede logboek te controleren.
* Het proces van SMS breidt het malplaatje met verpersoonlijkingsgegevens van het leveringsgedeelte uit.
* De schakelaar SMPP produceert MT (SUBMIT_SM PDU) aanpassing van de inhoud en andere montages.
* De schakelaar SMPP verzendt MT door een zender (of zendontvanger) verbinding.
* De provider retourneert een id voor deze MT. Het wordt ingevoegd in nms:providerMsgId.
* Het proces van SMS werkt het brede logboek aan de verzonden status bij.
* In het geval van definitieve fout, werkt het proces van SMS het brede logboek dienovereenkomstig bij, en kan tot een nieuw soort fout in nms:wideLogMsg leiden.

### Gegevensstroom bij ontvangst van SR {#sms-data-flow-sr}

* De schakelaar SMPP ontvangt en decodeert SR (DELIVER_SM PDU). Het gebruikt regexes die in de externe rekening worden bepaald om bericht identiteitskaart en status te krijgen.
* Bericht-id en status worden ingevoegd in nms:providerMsgStatus
* Nadat wordt opgenomen, beantwoordt de schakelaar SMPP met een PDU DELIVER_SM_RESP.
* Als om het even wat tijdens het proces verkeerd ging, verzendt de schakelaar SMPP negatief DELIVER_SM_RESP PDU en registreert een bericht.

### Gegevensstroom bij ontvangst van een MO {#sms-data-flow-mo}

* De schakelaar SMPP ontvangt en decodeert MO (DELIVER_SM PDU).
* Het trefwoord wordt uit het bericht geëxtraheerd. Als de waarde overeenkomt met een gedeclareerd trefwoord, worden de bijbehorende handelingen uitgevoerd. Het kan aan nms:adres schrijven om quarantaine bij te werken.
* Als aangepaste TLV wordt gedeclareerd, worden deze gedecodeerd volgens de desbetreffende instellingen.
* De volledig gedecodeerde en verwerkte MO wordt opgenomen in de nms:inSms-tabel.
* De schakelaar SMPP antwoordt met een PDU DELIVER_SM_RESP. Als er een fout is aangetroffen, wordt er een foutcode geretourneerd aan de provider.

### Gegevensstroom bij het in overeenstemming brengen van MT en SR {#sms-reconciling-mt-sr}

* De component SR-aansluiting leest periodiek nms:providerMsgId en nms:providerMsgStatus. Gegevens uit beide tabellen worden samengevoegd.
* Voor alle berichten die een ingang in beide lijsten hebben, wordt de passende nms:wideLog ingang bijgewerkt.
* De tabel nms:wideLogMsg kan tijdens het proces worden bijgewerkt als er een nieuwe fout wordt gedetecteerd, of om tellers bij te werken voor fouten die niet handmatig zijn gemarkeerd.

## Overeenkomende MT-, SR- en Broadlog-vermeldingen {#sms-matching-entries}

Hier volgt een diagram waarin het hele proces wordt beschreven:

![](assets/message_processing.png){zoomable="yes"}

**Fase 1**

* Het bericht wordt gescand, geformatteerd dan overgebracht naar de schakelaar SMPP.
* De schakelaar SMPP formatteert het als SUBMIT_SM MT PDU.
* De MT wordt naar de leverancier SMPP verzonden.
* De leverancier antwoordt met SUBMIT_SM_RESP. SUBMIT_SM en SUBMIT_SM_RESP worden aangepast door hun sequence_number.
* SUBMIT_SM_RESP verstrekt een identiteitskaart die van de leverancier komt. Deze id wordt samen met brede logboekidentiteitskaart in de nms:providerMsgId- lijst opgenomen.

**Fase 2**

* De leverancier verzendt een PDU DELIVER_SM SR.
* De SR wordt geparseerd om providerid, status en foutcode te extraheren. In deze stap worden extractieregexes gebruikt.
* De provider-id en de bijbehorende status worden ingevoegd in nms:providerMsgStatus.
* Wanneer alle gegevens veilig in het gegevensbestand worden opgenomen, beantwoordt de schakelaar SMPP met DELIVER_SM_RESP. DELIVER_SM en DELIVER_SM_RESP worden aangepast door hun sequence_number.

**Fase 3**

* De SR-afstemmingscomponent van het SMS-proces controleert periodiek zowel nms:providerMsgId als nms:providerMsgStatus.
* Als een rij overeenkomende provider-id&#39;s in beide tabellen bevat, worden de twee items bij elkaar gevoegd. Dit staat aanpassing van brede logboekidentiteitskaart (die in providerMsgId wordt opgeslagen) met de status (die in providerMsgStatus wordt opgeslagen) toe
* Het brede logboek wordt bijgewerkt met de overeenkomstige status.

## Partnerschappen en de toegewijde procesconnector {#sms-affinities}

Affinities worden genegeerd door de toegewijde procesconnector, alleen binnen het SMS-proces.

## serverConf-opties {#sms-serverconf-options}

Sommige instellingen kunnen worden ingesteld in serverConf.xml. Net als andere instellingen in dit bestand moet het bestand worden opgegeven in het bestand config-instance.xml. Alle instellingen bevinden zich in het element &lt; mta2 >.

In deze tabel staan alle instellingen vermeld. De min/max-waarden geven een globaal beeld van het bereik dat u in de meeste gevallen moet overwegen. De waarde voor foutopsporing is de waarde die u moet kiezen wanneer u problemen zoekt die geen verband houden met de prestaties.

| Instelling | Beschrijving | Standaard | Minimale zinvolle waarde | Maximale zinvolle waarde | Waarde van foutopsporing |
|:-:|:-:|:-:|:-:|:-:|:-:|
| batchUpdateSize | Grootte van updatemicrobatches | 5000 | 100: Zeer lage latentie | maxWaitingMessages/updateThreads: boven deze waarde gaan is nutteloos omdat maxWaitingMessages toch het bufferen zal beperken | 1: microbatchverwerking uitschakelen, berichten een voor een bijwerken |
| configRefreshMillis | Periode voor het opnieuw laden van de configuratie in milliseconden | 10000 | pollPeriodMillis: Lage latentie | 600000: Niet te snel opnieuw laden om bronnen te besparen | 500: met lage latentie kunt u sneller nieuwe instellingen proberen |
| deliveryPartRetryCount | Maximale aantal keren dat een deliveryPart opnieuw wordt geprobeerd of uitgesteld. Let op: als u het verzendingsproces opnieuw start, telt u mogelijk opnieuw mee dat crashes worden beschouwd als een poging om het proces opnieuw te starten. | 20 | 1: Opnieuw proberen uitschakelen | 50: Maak berichten standvastiger om rond instabiele leveranciers te werken | 1: Opnieuw proberen uitschakelen. 1000: Voorkom dat mislukte berichten worden gespoeld. |
| deliveryPartRetryDelaySeconds | Minimale vertraging voordat een deliveryPart opnieuw wordt geprobeerd. Dit is cross-process en cross-container. Vertraging is in seconden. | 60 | 0: Onmiddellijk opnieuw proberen | 3600: zeer trage pogingen (1 uur tussen elke poging) | 1: Hiermee kunt u gemakkelijk opnieuw proberen in drukke logboeken. |
| logOutput | Bewaking en profilering van gegevens verzenden bij uitvoer hoofdlogboek. | true | false: kan de doorvoer een beetje verhogen. Ontmoedigd. | true: logbestand inschakelen. | true |
| maxWaitingMessages | Maximumaantal berichten dat op elk moment wordt verwerkt | 50000 | 256: Voldoende voor één leveringDeel | 200000: beperkt door SQL-querylengte (64k) | 1: Verwerk de berichten een voor een |
| pollPeriodMillis | De opiniepeilingsfrequentie van het gegevensbestand (in milliseconden) om nieuwe berichten te controleren | 2000 | 500: Zeer lage latentie | 10000: grotere batches | 500: Met lage latentie kunt u eenvoudig fouten opsporen. |
| prepareThreads | Aantal draden voor berichtvoorbereiding | 3 | 1: één schroefdraad | Aantal CPU&#39;s Wees voorzichtig met het gebruik van RAM. Bij een toename boven 6 is mogelijk een verhoging van maxSMSMemoryMb, maxProcessMemoryAlertMb en maxProcessMemoryWarningMb vereist | 1: Single threaded levert schonere logbestanden op. |
| profDeliveryState | Verschillende geaggregeerde statistieken over interne gegevens van het SMS-proces registreren | true | false: kan de doorvoer een beetje verhogen. Ontmoedigd. | true: log met lage breedtegraad | true |
| profLogPerMessage | Logboek elke verwerkingsstap voor elk bericht | false | false: Beperk de logdiepte. | true: zeer uitgebreid log. **Gebruik slechts wanneer absoluut noodzakelijk**. Grote invloed op de prestaties. **gelieve dit het plaatsen onbruikbaar te maken zodra genoeg gegevens** zijn verzameld. | true |
| providerIdScanPeriod | Periode in seconden tussen scans voor nieuwe leveranciershulpmiddelen om te verzoenen | 10 | 1: Lage latentie | 60: Grotere batches voor meer doorvoer | 1: Lage latentie helpt foutopsporingsberichten te verwerken. |
| providerIdThreads | Aantal draden voor leverancier identiteitskaart het in overeenstemming brengen. 1 draad per instantie is genoeg. Ingesteld op 0 om uit te schakelen op deze container. | 1 | 0: Uitschakelen op deze container | 1 | 1 |
| sendingThreads | Aantal het verzenden van draden | 1 | 1: één schroefdraad | Aantal CPU&#39;s Te veel threads hebben meestal nadelige gevolgen voor de prestaties. | 1: Single threaded levert schonere logbestanden op. |
| updateThreads | Aantal draden voor het bijwerken van database | 1 | 1: één schroefdraad | Aantal CPU&#39;s Elke thread maakt een eigen DB-verbinding. | 1: Single threaded levert schonere logbestanden op. |
| verifyMode | Het verzenden van berichten simuleren. Berichten worden niet daadwerkelijk verzonden. Nuttig voor foutopsporing | false | false | true | false: voer het systeem normaal uit. true: Alleen toegang tot testdatabase en voorbereiding van berichten. |
