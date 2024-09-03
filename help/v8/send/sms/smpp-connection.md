---
title: Een SMPP-verbinding valideren
description: Leer hoe u een SMPP-verbinding valideert
feature: SMS
role: User
level: Intermediate
badge: label="Beperkte beschikbaarheid" type="Informative"
source-git-commit: dde669980493b996c80baacc8726db87353585ad
workflow-type: tm+mt
source-wordcount: '4439'
ht-degree: 0%

---


# Een SMPP-verbinding valideren {#validate-smpp-connection}

Hier volgen enkele controles om te controleren of de SMPP-verbinding OK is.

## Te controleren dingen voordat je live gaat {#check-go-live}

Voordat u live gaat, moet u controleren of uw SMPP-installatie OK is met de onderstaande lijst met controles.

>[!IMPORTANT]
>
>Deze controlelijst is niet limitatief. Hoe meer controles je doet, hoe beter.

>[!NOTE]
>
>Laat uitgebreide sporen SMPP tijdens controles toe, zal het u en het steunteam helpen om de problemen te begrijpen huisvesten.

### Controleren op conflicten met externe accounts {#sms-external-accounts-check}

Controleer of je geen externe SMS-accounts hebt. Verwijder de testaccounts om mogelijke conflicten te voorkomen.

Controleer of geen enkele andere instantie verbinding maakt met de externe account. Controleer met name of de voorproefomgeving geen verbinding maakt met de externe account van de voorruit.

Als u veelvoudige rekeningen op de zelfde instantie van de Campagne moet hebben die met de zelfde leverancier verbinden, contacteer de leverancier om ervoor te zorgen dat zij eigenlijk verbindingen tussen deze rekeningen onderscheiden. Voor meerdere accounts met dezelfde aanmelding is een extra configuratie vereist.

Controleer of alle ingeschakelde externe SMS-accounts de toegewezen procesinstelling hebben ingeschakeld. U kunt de twee typen accounts (met en zonder toegewezen proces) niet op hetzelfde exemplaar mengen.

### Een echte test uitvoeren {#real-test}

Probeer een paar sms&#39;jes te sturen op verschillende mobiele telefoons.

**verzend SMS met allerlei karakters**

Als u SMS met niet-GSM of niet-ASCII karakters moet verzenden, probeer verzendend sommige berichten met de meest diverse karakters mogelijk. Als u opstelling een lijst van de douanetoewijzing van het douaneteken, verzendt minstens één SMS voor alle mogelijke data_coding waarden.

**Controle dat SR behoorlijk wordt verwerkt**

Het SMS moet worden gemarkeerd als ontvangen in het leveringslogboek. Het leveringslogboek zou succesvol moeten zijn en als dit kijken: &quot;*SR yourProvider stat=DELIVRD err=000|#MESSAGE#*&quot;.

Controle dat u behoorlijk het &quot;*SMSC Naam van de Implementatie*&quot;gebied plaatst: het leveringslogboek moet nooit &quot;*Generische Sr*&quot;op productiemilieu&#39;s bevatten.

**Controle dat MO wordt verwerkt**

Verzend een paar SMS voor alle automatische antwoordsleutelwoorden en controleer dat het antwoord snel (niet meer dan een paar seconden) is.

Controleer dat MOs in het *nms wordt opgenomen:inSms* gegevensbestand. Als u aangepaste TLV&#39;s hebt, moet u ervoor zorgen dat deze ook correct en correct zijn opgemaakt.

Controle in het logboek dat de Campagne met succesvol *DELIVER_SM_RESP (command_status=0)* antwoordt.

**doe een ladingstest**

Dit is vooral belangrijk als u veel berichten verzendt of als u overseinen in real time gebruikt.

Doe een test die de verbinding bij 100% voor minstens 5 seconden zal laden. U moet echte berichten verzenden als de provider geen manier heeft om verbinding te maken met een nepaccount voor tests. Een manier om dat te bereiken is de eerste grote genoeg levering met uitgebreide toegelaten SMPP berichten nauwlettend te controleren.

Het minimumaantal te verzenden berichten zou als volgt kunnen worden berekend:

*Max MT productie * Totaal aantal zenders/zendieververbindingen * 5*

Nadat de levering wordt gebeëindigd, controleer de volgende dingen:

* Controleren of alle berichten zijn verzonden (niet noodzakelijkerwijs ontvangen)
* Er moet absoluut nul PDU met command_status niet 0x00000000 zijn, tenzij dit uitdrukkelijk door de leverancier als normale verrichting wordt verklaard
* De verbindingen moeten absoluut stabiel (geen BIND PDU) tijdens het volledige leveringsproces blijven.
* Controle dat alle berichten een SR hebben en dat het correct (zie [ Controle correct werd verwerkt dat SR behoorlijk ](#real-test) wordt verwerkt). Als een klein percentage fouten bevat, controleert u of dit echte SR-terugkerende fouten zijn, niet fouten tijdens het verzenden of verwerken aan de Campagnezijde.
* Als u niet zeker bent over prestaties, controleer dat latentie redelijk is, vooral tussen een PDU en zijn overeenkomstige RESP, die meer dan 500ms latentie heeft een probleem voor hoge productie kan zijn. Gebruik die latentie om de verzendende vensterformule te controleren (zie het Verzenden venster plaatsen voor meer details)

### PDU&#39;s controleren {#pdu}

Controleer of PDU&#39;s de juiste indeling hebben.

>[!IMPORTANT]
>
>Deze stap wordt sterk geadviseerd wanneer het verbinden met een leverancier die niet eerder met Campagne werd verbonden.

**BIND**

Controleer of PDU&#39;s BIND_* correct zijn verzonden. Het belangrijkste te controleren ding is dat de leverancier altijd succesvolle PDUs BIND_*_RESP (command_status = 0) terugkeert.

Controleer of er niet teveel PDU&#39;s BIND_* zijn. Als er te veel zijn, zou het erop kunnen wijzen dat de verbinding instabiel is. Raadpleeg de onderstaande sectie Problemen met onstabiele verbindingen met probleemoplossing voor meer informatie hierover.

**INQUIRE_LINK**

Controleer of INQUIRE_LINK PDUs regelmatig wordt geruild wanneer de verbinding nutteloos is.

**SUBMIT_SM / DELIVER_SM**

Verzend een bericht, dan onderzoek in de logboeken naar zijn overeenkomstige SUBMIT_SM, SUBMIT_SM_RESP, DELIVER_SM en DELIVER_SM_RESP PDUs.

Met *SUBMIT_SM PDU*:

* Controleer of data_coding correct is (standaard 0).
* Controleer of short_message correct is gecodeerd: probeer het te decoderen met een hexadecimale converter die meerdere coderingen ondersteunt (er zijn enkele online beschikbaar).
* Als u message_payload voor lange berichten gebruikt, controleer dat de inhoud in het facultatieve gebied en niet op het short_message gebied aanwezig is.

Met *SUBMIT_SM_RESP PDU*:

* Controleer of dit gelukt is (command_status = 0).
* Controleer of de hoofdtekst een correct opgemaakte id bevat, gevolgd door de byte &#39;0&#39;.

Met *DELIVER_SM PDU*:

* Decodeer het hexadecimale short_message gebied (er zijn online hulpmiddelen voor dat).
* Controleer met een regex controlehulpmiddel dat regex in de Regex van de Uitwinning van identiteitskaart in SR precies één vangstgroep terugkeert en dat het volledige identiteitskaart in het bericht vangt.
* Controleer of de geëxtraheerde id overeenkomt met de id in SUBMIT_SM_RESP.
* Controleer of de regex die is gedefinieerd in Extraction regex van de status in de SR, de inhoud van het statusveld retourneert.
* Controleer of de regex die is gedefinieerd in Extraction regex van de fout in de SR, de inhoud van het foutveld retourneert.

Met *DELIVER_SM_RESP PDU*:

* Controleer of deze snel is verzonden na ontvangst van de PDU DELIVER_SM (doorgaans minder dan 1 seconde).
* Controleer of dit gelukt is (command_status = 0).

### Live testen met de provider {#sms-live-test}

Een beste manier om live te gaan is om een live test met de provider uit te voeren, waarbij beide zijden de logbestanden tijdens de uitvoering bekijken.

>[!IMPORTANT]
>
>Deze stap wordt sterk geadviseerd wanneer het verbinden met een leverancier die nooit eerder met Campagne werd verbonden.

### Brede SMPP-sporen uitschakelen {#sms-disable-smpp}

Zodra alle controles volledig zijn, is de laatste actie te doen om uitgebreide sporen SMPP onbruikbaar te maken zodat produceert het niet teveel logboeken.

## SMS-probleemoplossing {#sms-troubleshooting}

### Algemene procedure voor probleemoplossing {#sms-general-troubleshooting}

De sms-connector bestaat uit drie entiteiten: de SMPP-provider, de Adobe en u.
De belangrijkste deskundige van SMS is de leverancier SMPP, zodat zouden zij voor alle verkeer-gerelateerde kwesties van SMS (verbindingskwesties, verloren berichten, coderingsproblemen, landspecifieke regels, enz.) moeten worden betrokken.

#### Speciaal proces inschakelen {#sms-dedicated-process}

>[!IMPORTANT]
>
>Controleer of **[!UICONTROL Send messages through a dedicated process]** is ingeschakeld in alle actieve SMS-accounts.

Als u problemen hebt met de oudere (op MTA-Gebaseerde) schakelaar (specifiek proces gehandicapt), zou u het migreren aan de specifieke processchakelaar moeten overwegen. Het presteert veel beter, is stabieler, en verstrekt veel betere terugkoppelen in zijn logboeken.

#### Conflict tussen verschillende externe rekeningen {#sms-conflict-external-accounts}

Als de instantie veelvoudige externe rekeningen van SMS heeft, controleer dat de problemen niet door een conflict tussen rekeningen worden veroorzaakt.

U kunt als volgt de externe account isoleren die problemen veroorzaakt:

1. Alle externe accounts uitschakelen
1. Eén externe account inschakelen
1. Probeer het probleem te reproduceren
1. Als het probleem niet wordt weergegeven bij dat ene account, schakelt u het uit en start u de toepassing opnieuw op stap 2 voor het volgende account. Als u eenmaal elke account afzonderlijk hebt gecontroleerd, zijn er twee mogelijke scenario&#39;s:

**het probleem verscheen op één of verscheidene rekeningen**

In dit geval kunt u op elke account afzonderlijk andere procedures voor het oplossen van problemen toepassen. Het is best om andere rekeningen onbruikbaar te maken terwijl het diagnostiseren van een rekening, om netwerkverkeer en de hoeveelheid logboeken te verminderen.

**het probleem verscheen niet toen slechts één rekening op om het even welk ogenblik actief is**

Er is een conflict tussen accounts. Adobe Campaign behandelt accounts afzonderlijk, maar de provider kan ze als één account behandelen.

*u gebruikt verschillende login/wachtwoordcombinaties tussen al uw rekeningen*
U moet contact opnemen met de provider om mogelijke conflicten aan de zijkant te onderzoeken.

*Sommige externe rekeningen delen de zelfde login/wachtwoordcombinatie*
De leverancier heeft geen manier om te vertellen van welke externe rekening PDU van de BIND komt, zodat behandelen zij alle verbindingen van de veelvoudige rekeningen als één enkele, zodat zij waarschijnlijk MO en SR willekeurig over de 2 rekeningen leiden, veroorzakend schijnbaar willekeurige kwesties.

Als de leverancier veelvoudige korte codes voor de zelfde login/wachtwoordcombinatie steunt, zult u hen moeten vragen waar te om die korte code in BIND PDU te zetten. Merk op dat dit stuk van informatie binnen BIND PDU, en niet in SUBMIT_SM moet worden gezet, omdat BIND PDU de enige plaats is die het verpletteren van MOs correct zal toestaan.

Zie de [ Informatie in elk soort PDU ](#pdu) sectie hierboven om te weten welke gebieden in BIND PDU beschikbaar zijn, over het algemeen zou u de korte code in *address_range* zetten, maar dat vereist speciale steun van de leverancier. Contacteer hen om te weten hoe zij verwachten om veelvoudige korte codes onafhankelijk te leiden.

Adobe Campaign biedt ondersteuning voor het verwerken van meerdere korte codes op dezelfde externe account. Het is dus vaak prima om slechts één account voor al het verkeer te gebruiken.

#### Een externe account werkt niet meer {#sms-external-account-not-working}

Over het algemeen, neigen de verbindingen SMPP in tijd zeer stabiel te zijn, en zodra zij correct worden gevormd zouden zij moeten blijven werken.

* Onderzoek of de schakelaar onlangs is veranderd - en door wie (controleer Externe Rekeningen als groep).
* Onderzoek of het systeem werd bevorderd en wanneer.
* Onderzoek of om het even welke pakketten die SMS beïnvloeden onlangs zou kunnen worden bevorderd.

Als geen van deze controles tot een worteloorzaak leiden, contacteer de leverancier. Soms, wanneer de leveranciers hun platforms bijwerken, gedraagt hun schakelaar zich lichtjes verschillend. Dit zou fijnafgestemde montages kunnen breken en regressies introduceren.

Aanbevolen wordt contact te houden met de provider en vaak belangrijke wijzigingen vooraf door te geven.

#### Probleem met midsourcing (gehost)  {#sms-issue-hosted}

* Als het probleem zich voordoet in een omgeving voor midsourcing, zorgt u ervoor dat de levering en de uitzending op de juiste wijze worden gemaakt en bijgewerkt op de server voor midsourcing. Als dat niet het geval is, is de kwestie geen kwestie van SMS.
* Zorg ervoor dat de naam van de medio-operator strikt in kleine letters is, anders blijft de levering in behandeling.
* Als alles werkt op de server halverwege en SMS correct worden verzonden, maar de marketinginstantie niet correct wordt bijgewerkt, dan hebt u een probleem met de middendaagse synchronisatie.

#### Probleem bij verbinding met de provider {#sms-issue-connection}

* Als BIND PDU een niet-nul *command_status* code terugkeert (betekenis is er een fout), of als er geen BIND_RESP PDU is, vraag de leverancier waarom dit gebeurt.
* Controleer of het netwerk correct is geconfigureerd, zodat de TCP-verbinding tot stand kan worden gebracht met de provider.
* Vraag de leverancier om te controleren dat zij behoorlijk IP adressen van de instantie van Adobe Campaign (de meeste leveranciers vereisen dit) toetoestonden.
* Controleer de instellingen van de externe account. Vraag het de leverancier in geval van twijfel over de waarde van sommige gebieden.
* Als de verbinding succesvol maar onstabiel is, controleer de [ Kwesties met instabiele verbindingen ](#unstable-connections). hieronder.
* Als de verbindingskwesties moeilijk zijn te diagnostiseren, zal een netwerk vangen u veel informatie brengen. Zorg ervoor dat het netwerk vangt gelijktijdig loopt terwijl het probleem verschijnt zodat kan het efficiënt worden geanalyseerd. U zou ook van de nauwkeurige tijd moeten nota nemen waarop het probleem verschijnt zodat is het gemakkelijker om het probleem in netwerkvangt te vinden.

#### Problemen met instabiele verbindingen {#unstable-connections}

**hoe te om instabiele verbindingen te diagnostiseren:**

Een verbinding wordt als instabiel beschouwd als een van deze dingen gebeurt:

* De verbinding duurt minder dan 1 uur.
* Als u het SMS-proces opnieuw start, worden de zaken tijdelijk &quot;gerepareerd&quot;. Het betekent waarschijnlijk dat een onstabiele verbinding throttling teweegbrengt, die het proces van SMS opnieuw begint ontruimt throttling, dan gebeurt het opnieuw tot de worteloorzaak wordt gevonden.
* De leverancier verzendt UNBIND PDUs. De leverancier zou UNBIND PDUs in normale verrichting nooit moeten verzenden.
* *onderzoek_link* tijden uit, of op de kant van de Campagne of op de leverancierskant. In dat geval ziet u INQUIRE_LINK_RESP al dan niet met een foutcode die niet gelijk is aan nul.
* Er zijn veel BIND PDU&#39;s. Er zouden niet meer dan een paar gedurende een dag moeten zijn (het hangt van het aantal verbindingen af). Meer dan 1 BIND PDU per uur en per verbinding zou alarm moeten zijn.

**hoe te om de problemen van de verbindingsstabiliteit te bevestigen:**

* De instabiele verbindingen zijn zelden de worteloorzaak, het is vaak het resultaat van een ander probleem dat op een of andere manier leidt tot het losmaken van verbinding. Het vinden van de worteloorzaak is de prioriteit.
* Brede SMPP-sporen inschakelen. U zult hen nodig hebben om te zien wat gebeurt wanneer de verbinding opnieuw begint.
* Als de leverancier UNBIND PDUs verzendt, doen zij waarschijnlijk iets fout. Vraag hen waarom zij UNBIND verzenden en het zal waarschijnlijk tot de hoofdoorzaak leiden.
* Het vastleggen van een netwerk is soms de enige manier om te zien hoe de verbinding wordt gesloten.
* Als de leverancier de verbindingen sluit (door of TCP FIN of een pakket van TCP RST te verzenden), vraag hen waarom zij dat doen. Dit zou u de worteloorzaak van het probleem moeten vertellen.
* Als de leverancier de verbinding sluit na het verzenden van een schone fout (zoals DELIVER_SM_RESP met een foutencode), moeten zij hun schakelaar bevestigen omdat dat andere soorten berichten verhindert worden overgebracht en MTA throttling zal teweegbrengen. Dit is met name belangrijk in de transceivermodus, waarbij het sluiten van de verbinding invloed heeft op zowel MT als SR.
* Als er onderbrekingen (onderbrekingen van de BIND, onderbrekingen SUBMIT_SM) zijn, kan de Campagne berichten voor die leverancier te snel verzenden. Verlaag de *maximumMT productie* het plaatsen en zie of lost het de kwestie op.

#### Probleem bij het verzenden van een MT (regelmatig naar een eindgebruiker verzonden SMS)

* Controleer of de verbinding stabiel is: een SMPP-verbinding moet ten minste 1 uur ononderbroken blijven. Zie de sectie &quot;Probleem met instabiele verbindingen&quot; hierboven.
* Als het opnieuw beginnen van het proces van SMS het verzenden van MT opnieuw voor een kleine periode maakt, hebt u waarschijnlijk vertraging toe te schrijven aan een instabiele verbinding. Zie de sectie &quot;Probleem met instabiele verbindingen&quot; hierboven.
* Controleer of het brede logboek aanwezig is en in de juiste status met de juiste datums. Als het niet is, is het geen kwestie van SMS maar een leveringskwestie of een kwestie van de leveringsvoorbereiding (dat is buiten het werkingsgebied van dit document).
* Controleer of de SMS-connector daadwerkelijk is gebonden aan de apparatuur van de provider. Vraag de leverancier om feedback om te controleren of alle systemen correct communiceren. Zie BIND_TRANSMITTER en BIND_TRANSCEIVER PDUs voor informatie over bindt proces. Mogelijk moet u SMPP-sporen inschakelen voor het oplossen van problemen.
* Met toegelaten sporen SMPP, controleer dat SUBMIT_SM PDU de juiste informatie bevat (zie de documentatie hierboven).
* Controleer of de provider reageert met een PDU SUBMIT_SM_RESP met de waarde &quot;OK&quot; (code 0). Zorg ervoor dat de PDU met een redelijke vertraging aankomt: iets langer dan 1 seconde is verdacht en moet met de provider worden besproken, het komt meestal binnen 100 ms aan.
* Als al deze stappen werken, kunt u erop vertrouwen dat het probleem aan de leverancierszijde is. Zij zullen het oplossen van problemen op hun platform moeten doen.
* Als het werkt maar de productie inconsequent is, probeer aanpassend het verzendende venster en verminderend de productie MT. U zult met de leverancier moeten werken om dat aan te passen. De campagne kan berichten zeer snel verzenden zodat kunnen de prestatiesproblemen zich op het materiaal van de leverancier voordoen.

#### MT worden gedupliceerd (zelfde SMS wordt verzonden veelvoudige tijden in een rij)

Duplicaten worden vaak veroorzaakt door nieuwe pogingen. Het is normaal om duplicaten te hebben wanneer het opnieuw proberen van berichten, zodat zou u uw inspanningen moeten concentreren op het elimineren van de worteloorzaak van herpogingen.

* Als u duplicaten ziet die precies 60 seconden van elkaar worden verzonden (of om het even welke andere verdacht &quot;regelmatige&quot;periode), is het waarschijnlijk een probleem aan de leverancierskant, verzenden zij niet snel genoeg een SUBMIT_SM_RESP.
* Als u vele BIND/UNBIND ziet, hebt u een instabiele verbinding: zie de [ Kwesties met instabiele verbindingen ](#unstable-connections) sectie voor oplossingen alvorens te proberen om dubbele berichtkwesties op te lossen.
* Controleer of alle PDU&#39;s SUBMIT_SM kort daarna overeenkomen met SUBMIT_SM_RESP. Als zij niet of SUBMIT_SM_RESP te langzaam zijn, is de kwestie op de leverancierskant.

Het verminderen van de hoeveelheid duplicaten wanneer er opnieuw wordt geprobeerd:

* Verlaag *verzendend venster*. Het verzendende venster zou groot genoeg moeten zijn om voor de latentie SUBMIT_SM_RESP te behandelen, maar niet te groot. De waarde ervan vertegenwoordigt het maximum aantal berichten dat kan worden gedupliceerd als een fout optreedt terwijl het venster vol is.

#### Uitgave bij verwerking van SR (ontvangstbewijzen)

* U hebt SMPP-sporen nodig die zijn ingeschakeld voor het uitvoeren van elk type SR-probleemoplossing.
* Controleer dat DELIVER_SM PDU van de leverancier komt en dat het behoorlijk gevormd is.
* Controleer of Campagne tijdig reageert met een geslaagde PDU DELIVER_SM_RESP. Dit waarborgt dat SR in de providerMsgStatus lijst voor uitgestelde verwerking door het proces van SMS is opgenomen.

Als de PDU DELIVER_SM niet met succes wordt erkend, dan moet u een paar dingen controleren:

* Controleer regex met betrekking tot id-extractie en foutafhandeling in de externe account. Mogelijk moet u deze valideren op basis van de inhoud van de PDU DELIVER_SM.
* Controleer of de fouten correct zijn ingesteld in de tabel wideLogMsg (in de documentatie bij Campagne wordt dit in details uitgelegd).

Als de PDU DELIVER_SM door de ACC uitgebreide schakelaar SMPP is erkend maar het wideLog niet behoorlijk wordt bijgewerkt, controleer het proces van de verzoening van identiteitskaart dat in de sectie het Matching MT, SR en uitzendingangen hierboven wordt beschreven.

Als u alles hebt gecorrigeerd, maar sommige ongeldige SR nog steeds in de buffers van de provider staan, kunt u deze overslaan met de optie &quot;Ongeldige id bevestigt telling&quot;. Dit dient met voorzichtigheid te worden gebruikt en zo snel mogelijk na het schoonmaken van de buffers op 0 te worden ingesteld.

Als SR-verwerking traag is, probeert u de meest voorkomende statusberichten in de tabel BroadLogMsg te kwalificeren.

Als slechts sommige SR maar niet allen worden ontvangen, controleer dat geen ander systeem met de rekening van uw leverancier, zoals een testsysteem verbindt. SR kan op om het even welke verbinding worden verpletterd, zodat kunnen sommige van hen aan dit andere systeem worden verpletterd. De provider kan u helpen zoeken waar dit andere systeem verbinding maakt met de account.

#### Probleem bij verwerking MO (en quarantaine/automatisch antwoord)

* SMPP-sporen inschakelen tijdens tests. Als u TLS niet toelaat, is het altijd beter om een netwerk te doen vangen wanneer het oplossen van problemen MO om te controleren dat PDUs de correcte informatie bevatten en behoorlijk geformatteerd zijn.
* Wanneer het vangen van netwerkverkeer of het analyseren van sporen SMPP, ben zeker om het volledige gesprek met MO en zijn antwoord MT (als een antwoord wordt gevormd) te vangen.
* Als de MO (DELIVER_SM PDU) niet in de sporen verschijnt, kunt u zeker zijn dat het probleem op de leverancierskant is. Zij zullen het oplossen van problemen op hun platform moeten doen.
* Als DELIVER_SM PDU verschijnt, controleer dat het door Campagne met succesvolle PDU DELIVER_SM_RESP (code 0) wordt erkend. Deze RESP garandeert dat alle verwerkingslogica is toegepast door Campagne (automatische reactie en quarantaine). Als het niet het geval is, zoek naar een foutenmelding in de het proceslogboeken van SMS.
* Als de automatische antwoorden worden toegelaten, controleer dat SUBMIT_SM is verzonden naar de leverancier. Als niet, is het gegarandeerd om een foutenmelding in de het proceslogboeken van SMS te vinden.
* Als SUBMIT_SM MT PDU die het antwoord bevat in het spoor wordt gevonden maar SMS niet aan de mobiele telefoon aankomt, zult u voor hulp bij het oplossen van problemen moeten contacteren omdat het probleem waarschijnlijk aan hun kant is.

#### Uitgave tijdens de voorbereiding van de levering, exclusief in quarantaine geplaatste ontvangers (in quarantaine geplaatst door de functie voor automatisch antwoord)

* Controleer dat het formaat van het telefoonaantal precies het zelfde in de quarantainelijst en in het leveringslogboek is. Als het niet is, zie &quot;verzend volledig telefoonaantal&quot;hierboven plaatsen als u kwesties met het plus prefix van het internationale telefoonnummerformaat hebt.
* Korte codes controleren: er treden uitsluitingen op als de korte code van de ontvanger gelijk is aan de code die in de externe account is gedefinieerd of als deze leeg is (leeg = enige snelcode). Als slechts één korte code voor de volledige instantie van de Campagne wordt gebruikt, is het gemakkelijker om alle gebieden van de &quot;korte code&quot;leeg te verlaten.

#### Coderingsproblemen  {#sms-encoding-issues}

Coderingsproblemen treden vaak op in SMS. Hier volgen enkele basisstappen.

**Stap 1: Krijg in contact met de leverancier**

De leverancier is de deskundige die weet hoe SMS werkt. Neem contact op met hen en zie wat er mis is. Ze moeten je kunnen vertellen of het probleem zich aan hun kant of in Campagne bevindt. Als het probleem zich in Campaign voordoet, moeten ze u precies kunnen vertellen welk veld onjuist is, wat enorm helpt.

**Stap 2: Weet wat in uw bericht** is

Je moet weten wat er in je bericht staat. Die zin klinkt misschien makkelijk, maar dat is het niet. Unicode staat zoveel varianten voor blik-gelijke karakters toe dat de Campagne hen niet allen kan behandelen.

De meest voorkomende bron van problemen is het kopiëren-plakken van een tekstverwerker, waarbij gebruikelijke tekens worden gewijzigd in typografisch correcte versies: spaties veranderen in vaste spaties, dubbele aanhalingstekens veranderen in open en sluitende aanhalingstekens, min tekens gewijzigd in verschillende soorten afbreekstreepjes ...

Kopieer uw bericht niet en plak het tijdens het testen altijd rechtstreeks in de interface.

**wordt niet geïntimideerd door hexadecimale**. Hexadecimaal ziet er vreemd en onnatuurlijk uit, maar de kwaliteit is duidelijk: je kunt het verschil zien tussen vergelijkbare tekens. Een L in kleine letters, een I in hoofdletters, O, 0, alle verschillende typen aanhalingstekens, niet-Latijnse coderingen of zelfs verschillende typen spaties kunnen er allemaal hetzelfde uitzien (of zelfs helemaal niet worden weergegeven). Hexadecimaal toont alles en helpt dingen vergelijken.

U kunt online gereedschappen gebruiken om unicode om te zetten in hexadecimaal.

**wanneer het openen van kaartjes** over het coderen problemen, of met de leverancier of de steun van de Campagne, **omvat een hexadecimale** versie van wat u typt en wat u ziet.

**Stap 3: Weet wat u** zou moeten verzenden

Bepaal de codering die u wilt gebruiken en zoek online naar de bijbehorende tekentabel. Controleer of de tekens die u wilt verzenden, daadwerkelijk beschikbaar zijn op de doelcodepagina. Controleer of het veld data_coding correct is en overeenkomt met wat u en de provider verwachten.

**Stap 4: Weet wat u eigenlijk verzonden**

U zult zuivert output van de schakelaar nodig hebben om precies te zien welke bytes u naar de leverancier verzendt. Coderingsproblemen verschijnen in PDUs SUBMIT_SM, zodat ben zeker om hen te vangen. Verzend zeer duidelijke berichten die gemakkelijk in het logboek zijn te vinden.

Wacht niet om verschillende soorten speciale tekens te verzenden tijdens het testen. GSM7-codering bevat bijvoorbeeld uitgebreide tekens die sterk van elkaar verschillen in hun hexadecimale vorm, zodat ze gemakkelijk te vinden zijn omdat ze niet in andere codering voorkomen.

#### Prestatieproblemen {#sms-performance-issues}

>[!NOTE]
>
>Prestaties zijn een zeer breed onderwerp. Deze sectie bevat een aantal basiscontroles die u moet uitvoeren voordat u probeert andere grote projecten te schalen of uit te voeren.

**de kwesties van Prestaties terwijl het verzenden van MT**

* Controleer of alle instellingen in het gedeelte Doorvoer en vertragingen van de externe account correct zijn en of deze overeenkomen met de instellingen die door de provider zijn toegestaan.
* Controleer of er geen nieuwe pogingen zijn.
* Controleer of de infrastructuur van de provider niet verzadigd is. Controleren op RMSGQFUL- of RTHROTTLED-fouten in RESP PDU&#39;s.
* Controleer de serverConf-instellingen. Begin met standaardwaarden en verhoog de parameters langzaam en één voor één.
* Controleer of het SMS-proces niet alle keren opnieuw wordt gestart als het wordt geladen. Als het doet, kunt u *maxSMSMemoryMb* moeten verhogen, *maxProcessMemoryAlertMb* en *maxProcessMemoryWarningMb* in het serverConf- dossier.

**de kwesties van Prestaties terwijl het ontvangen van SR**

Als de leverancier over bufferoverbelasting op hun kant klaagt, kan dit zijn omdat de Campagne geen SR snel genoeg ontvangt.

* Controleer of de instantiedatabase niet overbelast is. SR-verwerking is sterk afhankelijk van databaseprestaties.
* Vraag de leverancier om het verzendende venster voor DELIVER_SM op hun kant te verhogen. Ideaal gezien zou het zo groot moeten zijn zoals *batchUpdateSize* het plaatsen in serverConf.

### Elementen die moeten worden opgenomen bij communicatie over een SMS-probleem

Wanneer u om hulp over een kwestie van SMS (of het een steunkaartje aan Adobe Campaign, aan de leverancier van SMS, of om het even welk soort mededeling over de kwestie opent), zult u minstens de volgende informatie moeten omvatten om ervoor te zorgen dat het behoorlijk zal worden gekwalificeerd. Goed gekwalificeerde kwesties zijn essentieel om problemen sneller op te lossen, dus het nemen van wat meer tijd om te proberen de situatie te begrijpen en betekenisvolle informatie te geven zal leiden tot een enorme sprong in efficiëntie.

* Schakel uitgebreide SMPP-berichten in tijdens de periode waarin het probleem optreedt. De meeste SMS-problemen zijn vrijwel onmogelijk op te lossen zonder dit.
* Als het probleem met het verkeer van SMS verwant is, contacteer eerst de leverancier. Zij zijn het meest deskundig en hun platform is gewoonlijk geschikt voor efficiënte diagnose van de verkeersproblemen van SMS in echt - tijd.
* Neem een korte, maar feitelijke beschrijving van het probleem op.
* Een beschrijving van het verwachte resultaat opnemen.
* Alle feedback van de provider opnemen.
* Inclusief relevante logboeken en/of netwerkvastleggingen. Zorg er tijdens het vastleggen voor dat het probleem tijdens het vastleggen wordt gereproduceerd, anders heeft het geen zin.
* Als u logboeken, sporen of vangen omvat, wijs de nauwkeurige plaats in het dossier wanneer het probleem verschijnt, evenals de nauwkeurige plaats van een werkend voorbeeld als er om het even welk is. Vastleggen of sporen kunnen groot en vervelend zijn om te bekijken, zodat alles wat helpt om informatie in hen te vinden nuttig is.
* Als u berichten, PDUs of logboeken van verwijzingen voorziet, duidelijk hun timestamp zodat zijn zij gemakkelijk te vinden door andere mensen.
* Probeer het probleem op een testomgeving te reproduceren. Als u niet zeker bent over een instelling, probeert u deze in de testomgeving en controleert u het resultaat met de SMPP-sporen. Meestal is het beter om problemen te rapporteren die in testomgevingen worden gerepliceerd dan problemen rechtstreeks te melden in productieomgevingen.
* Neem alle wijzigingen of bijstellingen op het platform op: zelfs een kleine wijziging kan enorme gevolgen hebben. Neem ook alle wijzigingen op die de provider aan hun zijde heeft aangebracht.

#### Wanneer is een netwerk vangst nuttig?

Een netwerk vangt is niet altijd nodig. Heel vaak zijn uitgebreide SMPP-berichten genoeg. Hier zijn sommige richtlijnen die u zullen helpen bepalen als een netwerk vangt de inspanning waard is:

* De kwesties van de verbinding, maar de verbose berichten tonen geen BIND_RESP PDU.
* Onverklaarbare verbreken zonder foutenmelding (dat is het gedrag van de schakelaar wanneer het een laag niveau protocolfout ontdekt).
* De leverancier klaagt over het unbind/disconnection proces.
* Er zijn coderingsproblemen in optionele TLV-velden.
* Vermoedelijk wordt verkeer gemengd tussen verschillende verbindingen.

In alle andere situaties, probeer om verbose SMPP- berichten eerst te analyseren en een netwerk te verzoeken vangt slechts als het duidelijk is dat de informatie in de breedtelogboeken mist.

#### Wanneer is een netwerk vangt nutteloos?

In sommige gevallen is het vastleggen van netwerkverkeer nutteloos of gewoon tijdverspilling. Hier volgen de meest voorkomende situaties:

* TLS ingeschakeld: TLS-verkeer wordt per definitie gecodeerd zodat het niet kan worden vastgelegd.
* Prestatieproblemen: logboeken bevatten alle benodigde informatie om prestatieproblemen op te sporen.
* Timingproblemen (timing opnieuw proberen, periode onderzoeken_koppelen, doorvoerlimiet, ...)
* SR parseren en verwerken: uitgebreide logboeken geven veel meer context en een betere presentatie.
* MO-verwerking (automatische antwoorden, quarantaine).
* Fouten waarbij geen daadwerkelijk SMPP-verkeer is betrokken: voorbereiding van levering, API-problemen voor berichtencentra, workflowproblemen, ...
