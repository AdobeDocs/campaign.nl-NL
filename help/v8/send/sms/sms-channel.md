---
title: Kenmerken van SMS-kanalen
description: Leer de kenmerken van het kanaal van SMS
feature: SMS
role: User
level: Intermediate
exl-id: abab6f15-43ea-42fc-817b-8dbd88df82f7
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 0%

---

# Kenmerken van SMS-kanalen {#sms-channel}

>[!IMPORTANT]
>
>Deze documentatie is van toepassing op Adobe Campaign v8.7.2 en hoger. Om van erfenis aan de nieuwe schakelaar van SMS over te schakelen, verwijs naar dit [ technote ](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Voor oudere versies, gelieve de [ documentatie van Campaign Classic v7 ](https://experienceleague.adobe.com/nl/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"} te lezen.

## Typen SMS {#sms-types}

Wanneer u SMS verzendt via een SMS-provider, hebt u te maken met drie verschillende typen SMS:

* **MT van SMS (Beëindigde Mobiele)**: Dit is een SMS dat door Adobe Campaign naar mobiele telefoons door de leverancier SMPP wordt uitgegeven.
* **MO van SMS (Mobiel voortgekomen)**: Dit is een SMS dat door een mobiel naar Adobe Campaign door de leverancier SMPP wordt verzonden.
* **SMS SR (het Rapport van de Status) of DR. of DLR (Ontvangstbewijs)**: Dit is een terugkeerontvangstbewijs dat door mobiel naar Adobe Campaign door de leverancier wordt verzonden SMPP erop wijst die dat SMS met succes is ontvangen. Adobe Campaign kan ook SR ontvangen om aan te geven dat het bericht niet kan worden verzonden, vaak met een beschrijving van de fout.

U moet tussen erkenning (RESP PDU, een deel van het protocol SMPP) en SR onderscheid maken. Een SR is een soort SMS dat door het netwerk van begin tot eind wordt verzonden, terwijl een erkenning slechts een bevestiging is dat één overdracht succesvol is geweest.

Zowel erkenningen als SR kunnen fouten teweegbrengen, die tussen beide het oplossen van problemen helpen.

### Informatie die via een SMS wordt verzonden  {#sms-info}

Een SMS bevat meer informatie dan tekst. Hier een lijst van wat u in SMS kunt verwachten te vinden:

* De tekst, die is beperkt tot 140 bytes, wat betekent tussen 70 en 160 karakters afhankelijk van de codering. Zie [ tekst het coderen van SMS ](#sms-text-encoding) hieronder voor details en beperkingen.
* Een ontvankelijk adres, soms genoemd ADC of MSISDN (de technische naam voor &quot;telefoonaantal&quot;). Dat is het nummer van de mobiele telefoon die het SMS zal ontvangen.
* Een afzenderadres, dat oADC of soms afzenderidentiteitskaart kan worden genoemd. Dat kan een telefoonaantal (in dagelijks gebruik), een korte code (wanneer verzonden door een leverancier) of een naam (dit is een facultatieve eigenschap, in dat geval kunt u niet op SMS antwoorden) zijn.
* Een vlag om erop te wijzen of het bericht een flitsbericht is (een flitsbericht is een pop-up die niet in geheugen wordt opgeslagen)
* Een vlag die aangeeft of een SR wordt verwacht of niet.
* Een geldigheidsdatum, waarna geen netwerkmateriaal wordt toegestaan om opnieuw te proberen (niet altijd aanwezig of gerespecteerd).
* A data_coding field, which indicates the encoding of the text.

## SMS-tekstcodering {#sms-text-encoding}

>[!IMPORTANT]
>
>Het coderen van SMS is een enorm, complex onderwerp met vele vallen en niet in overeenstemming zijnde implementaties!

De eerste regel is **altijd contacteer de leverancier SMPP in het geval van het coderen problemen**. Alleen zij beschikken over nauwkeurige kennis van de codering die zij ondersteunen en speciale regels die van toepassing kunnen zijn vanwege beperkingen in hun technische platform. Laat ze controleren wat je ze stuurt en wat ze je terugsturen, het is de enige weg naar een succesvolle en stabiele verbinding.

SMS-berichten gebruiken een speciale 7-bits codering, vaak de GSM7-codering genoemd.  Wikipedia heeft [ een goed artikel over het (GSM 03.38 in het Engels) ](https://en.wikipedia.org/wiki/GSM_03.38).

In het protocol SMPP, zal de tekst GSM7 tot 8 beetjes per karakter voor het gemakkelijkere oplossen van problemen worden uitgebreid. Het SMSC zal het in 7 beetjes per karakter verpakken alvorens het naar mobiel wordt verzonden. Dit betekent dat het short_message gebied van SMS tot 160 bytes lang in het kader kan zijn SMPP terwijl het tot 140 bytes wanneer verzonden op het mobiele netwerk (het meest significante beetje wordt eenvoudig verworpen) beperkt is.

In het geval van coderingsproblemen moet u een aantal belangrijke zaken controleren:
* Controleer eerst welke tekens bij de codering horen. GSM7 is berucht voor zijn gedeeltelijke steun aan diakritische tekens (accenten). Vooral in het Frans, waar é en è deel uitmaken van GSM7, maar ê, â of ï niet. Hetzelfde geldt voor het Spaans.
* De C met cedilla (ç) is alleen in hoofdletters aanwezig in het GSM7-alfabet, maar sommige telefoons geven het in kleine letters of &quot;slimme&quot; gevallen weer: de algemene aanbeveling is om het volledig te vermijden en de cedilla (die in het Frans nog steeds zeer leesbaar is) of de overschakeling op UCS-2 te verwijderen.
* **gebruik geen ASCII in SMS!** tenzij uitdrukkelijk gevraagd door de leverancier SMPP: Deze codering verspilt ruimte omdat het karakters met 8 bits en minder dekking dan GSM7 heeft. Deze codering kan vereist zijn voor CDMA-netwerken (gebruikt in Noord-Amerika).
* Latin-1 wordt niet altijd ondersteund. Controleer de compatibiliteit met uw SMPP-provider voordat u Latin-1 gaat gebruiken.
* Tabellen voor nationale taalverschuiving worden niet ondersteund door de Adobe Campaign-connector. In plaats hiervan moet u UCS-2 of andere data_coding gebruiken.
* UCS-2 en UTF-16 worden vaak gemengd door telefoons. Dit is een probleem voor mensen die emojis en andere zelden gebruikte karakters verzenden die niet in UCS-2 aanwezig zijn.
* Enige oudere telefoons hebben doopvontglyphs niet voor alle karakters UCS-2. De nieuwste smartphones zijn vaak vrij gemakkelijk om zeldzame tekens weer te geven, oudere smartphones hebben vaak veel emoties en zeer oude functietelefoons hebben over het algemeen slechts ondersteuning die nuttig is in de moedertaal van het land waarin ze zijn gekocht. Als u emoji of ASCII-kunst van één of andere soort wilt gebruiken, test het op een grote verscheidenheid van telefoons alvorens te verzenden. In de voorvertoning van de campagne worden ontbrekende glyphs niet gesimuleerd en worden alle symbolen weergegeven die beschikbaar zijn in de webbrowser waarin de voorvertoning wordt weergegeven.

Het *data_coding* gebied vertelt welke het coderen wordt gebruikt. Een belangrijk probleem is dat waarde 0 *standaardSMSC het coderen* in de specificatie betekent, over het algemeen betekent het GSM7, maar dat is niet altijd het geval. Vraag de leverancier SMPP welke codering is gekoppeld aan data_coding = 0. Andere data_coding waarden neigen om de specificatie te volgen, maar de enige manier om zeker te zijn is met de leverancier te controleren SMPP.

De maximumgrootte van een bericht hangt van zijn codering af. In deze tabel worden alle relevante gegevens samengevat:

| Codering | Gebruikelijke gegevens_codering | Berichtgrootte (tekens) | Onderdeelformaat voor SMS met meerdere onderdelen | Beschikbare tekens |
|:-:|:-:|:-:|:-:|:-:|  
| GSM7 | 0 | 160 | 152 | GSM7 basis tekenset + extensie (uitgebreide tekens nemen 2 tekens in beslag) |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (varieert van telefoon tot telefoon) |

## Multipart SMS (lang SMS) {#multipart-sms}

Multipart SMS (vaak lange SMS genoemd) is SMS die in veelvoudige delen wordt verzonden. Vanwege technische beperkingen in het mobiele netwerkprotocol kan een SMS niet groter zijn dan 140 bytes (zie de sectie voor tekstcodering van SMS hieronder voor het aantal tekens dat in een SMS kan passen), zodat langere berichten moeten worden gesplitst.

Elk deel van een lang bericht is een individueel SMS. Deze onderdelen reizen onafhankelijk op het netwerk en worden door de ontvangende mobiele telefoon gemonteerd. Om pogingen en connectiviteitsproblemen netjes te behandelen, verzendt de Campagne onderdelen in omgekeerde orde en vraagt om een SR slechts op het eerste deel van het bericht (die laatst wordt verzonden); aangezien de mobiele telefoon slechts een bericht toont wanneer het zijn eerste deel ontving, zullen de pogingen op extra delen geen duplicaten op de mobiele telefoon veroorzaken.

Het maximumaantal SMS per bericht kan per levering worden geplaatst gebruikend het Maximum aantal SMS per bericht dat in het leveringsmalplaatje plaatst. Berichten die deze limiet overschrijden, mislukken tijdens het verzenden met een te lange reden voor SMS-fout.

Er zijn twee manieren om lange SMS te verzenden:

* UDH
* message_payload

UDH is de standaard en aanbevolen manier om lange berichten te verzenden. Op deze wijze splitst de schakelaar het bericht in veelvoudige SUBMIT_SM PDUs met UDH informatie in hen. Dit protocol is het protocol dat door mobiele telefoons zelf wordt gebruikt, betekenend dat de Campagne de meeste controle over de berichtgeneratie heeft, die het maakt om precies te berekenen hoeveel delen werden verzonden en hoe zij werden verdeeld.

*message_payload* is een manier om het gehele lange bericht in één enkele PDU te verzenden SUBMIT_SM. De leverancier moet het splitsen, wat betekent dat het voor Campaign onmogelijk is om precies te weten hoeveel onderdelen zijn verzonden. Sommige leveranciers vereisen deze wijze, slechts gebruik het als zij UDH niet steunen.

Zie de beschrijving van esm_class, short_message en message_payload gebieden van SUBMIT_SM PDU hierboven voor meer details over het protocol en formaten.

>[!NOTE]
>
>Hoewel Adobe Campaign zowel UDH als message_payload voor verzending ondersteunt, wordt alleen message_payload ondersteund voor binnenkomende SMS (MO).
