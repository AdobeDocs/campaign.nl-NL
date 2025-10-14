---
title: Opmerkingen bij de release Campagne v8 2022
description: Lijst met functies en verbeteringen die worden geleverd bij de 2022-campagne v8-releases
feature: Release Notes
exl-id: 76473fa5-48ba-42cf-8664-0dd197833a86
source-git-commit: b3ca222fb28c1a5d35190e41cfbbe463c5d1bcad
workflow-type: tm+mt
source-wordcount: '1943'
ht-degree: 13%

---

# Opmerkingen bij de release 2022{#2022-rn}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met **2022 de Versies van de Campagne v8** komen.

>[!BEGINSHADEBOX]

**In deze pagina**

* Campagne v8.4 - [&#x200B; Versie 8.4.1 &#x200B;](#release-8-4-1) | [&#x200B; Versie 8.4.2 &#x200B;](#release-8-4-2)
* Campagne v8.3 - [&#x200B; Versie 8.3.8 &#x200B;](#release-8-3-8) | [&#x200B; Versie 8.3.9 &#x200B;](#release-8-3-9)
* Campagne v8.2 - [&#x200B; Versie 8.2.10 &#x200B;](#release-8-2-10)

>[!ENDSHADEBOX]



## Release 8.4.2 {#release-8-4-2}

_zaterdag 28 oktober 2022_

**Bevestigingen**

* Probleem verholpen waardoor de leverindicator voor succes niet correct kon worden bijgewerkt bij gebruik van Adobe Campaign Enhanced MTA. (NEO-50462)

## Release 8.4.1 {#release-8-4-1}

_zaterdag 30 september 2022_

**Nieuwe functies**

<table> 
<thead>
<tr> 
<th> <strong> de integratie van Adobe Campaign met Adobe Experience Platform </strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Er zijn nu nieuwe bestemmings- en bronconnectors beschikbaar voor naadloze integratie tussen Adobe Campaign en Adobe Experience Platform:</p>
<ul><li>Gebruik de Adobe Campaign Managed Cloud Services-doelconnector om Experience Platform-segmenten naar Adobe Campaign te sturen voor activering.</li>
<li>Gebruik de Adobe Campaign Managed Cloud Service-bronconnector om Adobe Campaign-leverings- en trackinglogboeken naar Adobe Experience Platform te verzenden.</li>
</ul>
<p>Raadpleeg de <a href="../connect/ac-aep.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong> X (vroeger gekend als Twitter) kanaalbeschikbaarheid </strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Het <a href="../send/twitter.md"> sociale kanaal van X </a> is nu beschikbaar met Campagne v8. U kunt:</p>
<ul> 
<li><p>Verzend berichten op X (voorheen bekend als Twitter): met Adobe Campaign kunt u berichten rechtstreeks naar uw X-account plaatsen. U kunt ook directe berichten verzenden naar al uw volgers.
</p></li>
<li><p>Verzamel nieuwe contacten: Adobe Campaign kan de profielgegevens automatisch terugkrijgen, die u toelaat om het richten campagnes uit te voeren en kanaalstrategieën uit te voeren.
</p></li>
</ul>
<p>Leer hoe te om Campagne en X in de <a href="../connect/ac-tw.md"> gedetailleerde documentatie </a> aan te sluiten.</p>
<p>Leer hoe te om posten tot stand te brengen en directe berichten met Campagne in <a href="../connect/ac-tw.md"> te verzenden deze pagina </a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Beveiligingsverbetering**

Om de beveiliging te optimaliseren, zijn beveiligingstokens verwijderd uit URL&#39;s die zijn gegenereerd door Campagne:

* Deze wijziging geldt alleen voor GET-URL&#39;s. Dit heeft geen invloed op andere typen, zoals POST-URL&#39;s.
* Als u aangepaste code gebruikt, worden beveiligingstokens niet meer opgehaald uit de beveiligingstoken-parameter voor GET URL. U moet een nieuw veiligheidstoken produceren gebruikend de volgende code JSSP:

  ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

  U kunt ook de API voor aanmelding gebruiken om beveiligingstokens op te halen.
* Er is geen verandering in het beheer van het zittingstoken.

**Verbeteringen**

* Na het eind van leven van Microsoft Internet Explorer 11, gebruikt de HTML die motor in de console teruggeeft nu **Chromium van Microsoft Edge**. Bovendien, wordt de installatie van **Microsoft Edge WebView 2** runtime nu vereist voor om het even welke installatie van de Console van de Cliënt.
* Verbeterde workflowuitvoering met een hoge beschikbaarheid van de workflow waardoor u gelijktijdige workflows kunt uitvoeren over verschillende containers om te voorkomen dat de workflowservice verloren gaat en gerelateerde uitvoeringsfouten te voorkomen. **Nota**: Dit nieuwe vermogen wordt vrijgegeven in Beperkte Beschikbaarheid aan een reeks slechts klanten.
* De verzoeken van de privacy worden nu uitgevoerd in partij voor een bepaalde privacy namespace. Deze verbetering verhoogt de uitvoeringstijd voor aanvragen voor GDPR/privacy-verwijdering.

**Compatibiliteitsupdates**

* Campaign v8 SDK biedt nu ondersteuning voor iOS 16 voor pushberichten.

Raadpleeg de [Campaign-compatibiliteitsmatrix](compatibility-matrix.md).

**Bevestigingen**

* Probleem verholpen dat invloed had op de statusupdates van het leveringslogboek voor de MID-instantie toen de optie FeatureFlag_GZIP_Compression was ingeschakeld. (NEO-49183)
* Oplossing een kwestie die leveringen kon leiden om in **Hangende** status te blijven zelfs als de contactdatum werd bereikt. (NEO-48079)
* Vaste een kwestie in werkschema&#39;s die dossiers konden verhinderen op server worden bijgewerkt wanneer het gebruiken van de **Gegevens ladende (dossier)** activiteit. Het proces is gestopt bij 100%, maar is nooit beëindigd. (NEO-47269)
* Probleem verholpen tijdens naupgrade op japanse omgevingen. (NEO-46640)
* Probleem verholpen dat zich kon voordoen als een levering een exacte grootte bereikte tijdens het MTA-proces. (NEO-46097)
* Probleem verholpen waarbij het bijhouden van logbestanden gegevens met betrekking tot de browser van de ontvanger niet kon retourneren. (NEO-46612)
* Probleem verholpen dat tot personalisatieproblemen leidde bij het verzenden van SMS-berichten via een externe leveringsmodus. (NEO-46415)
* Probleem verholpen waarbij duplicaten konden worden gegenereerd in trackinglogboeken. (NEO-46409)
* Probleem verholpen waarbij de technische workflow van **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) werd verhinderd om te stoppen, zelfs als er een fout is opgetreden tijdens de uitvoering. (NEO-46280)
* Om vertraging te verhinderen wanneer het verzenden van bewijs naar zaadadressen, worden alle opeenvolgende replicaties van zaadleden nu gegroepeerd aan één replicatieverzoek. (NEO-44844)
* Probleem verholpen waarbij een fout werd weergegeven tijdens een voorvertoning van een levering in een gearchiveerde gebeurtenis in het Message Center. (NEO-43620)
* Vaste een kwestie toen het injecteren van gegevens in het wolkengegevensbestand van Snowflake met een 1&rbrace; activiteit van de Vraag van de Campagne **en de activiteit van de Gegevens van de a** Verandering Source **: het proces faalde wanneer een backslash karakter in de gegevens aanwezig is.** De brontekenreeks is niet gevonden en gegevens zijn niet correct verwerkt op Snowflake. (NEO-45549)
* Vaste een kwestie wanneer het gebruiken van de **activiteit van de Vraag** en het filtreren van een lijst. Wanneer een kolomnaam het woord &quot;Update&quot;bevatte, kwam een compilatiefout met een ongeldige herkenningsteken en het volgende bericht voor: &quot;aantal rijen bijgewerkt&quot;. (NEO-46485)
* De **schoonmaakbeurt van het Gegevensbestand** technische werkschema behandelt nu ook douanegraferingsschema&#39;s. (NEO-48974)
* Probleem verholpen dat de leveringanalyse zou kunnen vertragen, tijdens de uitsluitingsfase van op de lijst met ongewenste personen staan ontvangers, wanneer grote aantallen ontvangers als doelgroep zouden worden genomen. (NEO-48019)
* Verbeterde stabiliteit bij het verwerken van ongeldige XML-tekenreeksen tijdens SOAP-aanroepen. (NEO-48027)
* Probleem opgelost dat leidde tot het maken van onnodige DeliveryParts wanneer de levering de kalender- en splitsingsmodi gebruikte. (NEO-48634)
* Probleem opgelost met prestaties bij gebruik van op kalender gebaseerde golven. (NEO-48451)
* Probleem verholpen die tot een foutbericht in het scherm met de leveringslijst kon leiden nadat een nieuwe doeltoewijzing op een aangepast schema was gemaakt. (NEO-49237)
* Probleem verholpen waarbij gegevensverlies kan optreden als de testworkflow fout was en de bewaarperiode volledig is verstreken. (NEO-48975)

## Release 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> De upgrade van Client Console is verplicht. Lees op deze [pagina](../start/connect.md#download-ac-console) hoe u uw Client Console kunt upgraden.

_zaterdag 7 oktober 2022_

**Bevestigingen**

* Probleem verholpen dat invloed had op de statusupdates van het leveringslogboek voor de MID-instantie toen de optie FeatureFlag_GZIP_Compression was ingeschakeld. (NEO-49183)
* De **schoonmaakbeurt van het Gegevensbestand** technische werkschema behandelt nu ook douanegraferingsschema&#39;s. (NEO-48974)
* Oplossing een kwestie die leveringen kon leiden om in **In afwachting van** status te blijven zelfs als de contactdatum werd bereikt. (NEO-48079, NEO-48251)
* Verbeterde stabiliteit bij het verwerken van ongeldige XML-tekenreeksen tijdens SOAP-aanroepen. (NEO-48027)
* Probleem verholpen dat de leveringanalyse zou kunnen vertragen, tijdens de uitsluitingsfase van op de lijst met ongewenste personen staan ontvangers, wanneer grote aantallen ontvangers als doelgroep zouden worden genomen. (NEO-48019)
* Om vertraging te verhinderen wanneer het verzenden van bewijs naar zaadadressen, worden alle opeenvolgende replicaties van zaadleden nu gegroepeerd in één replicatieverzoek. (NEO-44844)
* Probleem verholpen dat tot personalisatieproblemen leidde bij het verzenden van SMS-berichten via een externe leveringsmodus. (NEO-46415)
* Probleem verholpen waarbij een fout werd weergegeven tijdens een voorvertoning van een levering in een gearchiveerde gebeurtenis in het Message Center. (NEO-43620)
* Vaste een kwestie in werkschema&#39;s die dossiers konden verhinderen op server worden bijgewerkt wanneer het gebruiken van de **Gegevens ladende (dossier)** activiteit. Het proces is gestopt bij 100%, maar is nooit beëindigd. (NEO-47269)
* Probleem opgelost dat leidde tot het maken van onnodige DeliveryParts wanneer de levering de kalender- en splitsingsmodi gebruikte. (NEO-48634)
* Probleem opgelost met prestaties bij gebruik van op kalender gebaseerde golven. (NEO-48451)
* Probleem verholpen die tot een foutbericht in het scherm met de leveringslijst kon leiden nadat een nieuwe doeltoewijzing op een aangepast schema was gemaakt. (NEO-49237)
* Probleem verholpen dat zich kon voordoen als een levering een specifieke grootte bereikte tijdens het MTA-proces. (NEO-46097)
* Probleem verholpen waarbij het bijhouden van logbestanden gegevens met betrekking tot de browser van de ontvanger niet kon retourneren. (NEO-46612)
* Probleem verholpen tijdens postupgrade op Japanse omgevingen. (NEO-46640)
* Vaste een kwestie wanneer het gebruiken van de **activiteit van de Vraag** en het filtreren van een lijst. Wanneer een kolomnaam het woord &quot;Update&quot; bevatte, is een compilatiefout opgetreden met een ongeldige id en het volgende bericht: &quot;number of rows updated&quot;. (NEO-46485)
* Probleem verholpen waarbij de technische workflow van **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) werd verhinderd om te stoppen, zelfs als er een fout is opgetreden tijdens de uitvoering. (NEO-46280)
* Probleem verholpen waarbij gegevensverlies kan optreden als de testworkflow fout was en de bewaarperiode volledig is verstreken. (NEO-48975)
* Vaste een kwestie toen het injecteren van gegevens in het wolkengegevensbestand van Snowflake met een 1&rbrace; activiteit van de Vraag van de Campagne **en de activiteit van de Gegevens van de a** Verandering Source **: het proces faalde wanneer een backslash karakter in de gegevens aanwezig is.** De brontekenreeks is niet gevonden en gegevens zijn niet correct verwerkt op Snowflake. (NEO-45549)

## Release 8.3.8 {#release-8-3-8}

_Mei 18, 2022_

**Nieuwe functies**

<table> 
<thead>
<tr> 
<th> <strong>Tijdgevoelige meldingen</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Met iOS 15 heeft Apple een concept van gevoelige meldingen toegevoegd dat de ontwikkelaar van de app de mogelijkheid geeft om de modus Focus te omzeilen wanneer een melding als gevoelig wordt beschouwd en de gebruiker in real time moet bereiken.</p>
<p>Raadpleeg de <a href="../send/push.md#send-notifications-on-ios">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong> Integratie van de Kern Privacy Service </strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campagne v8 kan nu worden geïntegreerd met Adobe Privacy Core Service. Verzoeken om toegang tot persoonsgegevens die van de Privacy-kernservice naar alle Experience Cloud-oplossingen worden gepusht, worden door Campaign automatisch behandeld via een speciale workflow.</p>
<p>Raadpleeg de <a href="privacy.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>

<table>
<thead>
<tr>
<th><strong>Responsbeheer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Met het beheer van de campagne-respons kunt u het succes en het rendement van uw marketingcampagnes meten of voorstellen aanbieden op alle kanalen: e-mail, mobiel, direct mail, enz.</p>
<p>Raadpleeg de <a href="../start/campaigns.md#response-manager-add-on">gedetailleerde documentatie</a> voor meer informatie.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Gedistribueerde marketing</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Met de campagne Distributed Marketing kunt u samenwerkingscampagnes opzetten tussen centrale entiteiten (hoofdkantoor, marketingafdelingen, enz.) en lokale entiteiten (verkooppunten, regionale agentschappen, enz.). Via een gedeelde werkruimte (campagne-pakketten) kunt u campagnemalplaatjes maken en deze aan uw lokale entiteiten voorstellen.</p>
<p>Raadpleeg de <a href="../start/campaigns.md#distributed-marketing-add-on">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>

**Compatibiliteitsupdates**

* Campaign v8 SDK biedt nu ondersteuning voor Android 12 en iOS 15 voor pushberichten.
* Campagne v8 is nu compatibel met Windows 11.

Raadpleeg de [Campaign-compatibiliteitsmatrix](compatibility-matrix.md).

**Verbeteringen**

* Microsoft Exchange Online OAuth 2.0-verificatie voor POP3 wordt nu ondersteund in Campaign. [Meer informatie](../config/external-accounts.md#bounce-mails-external-account)
* Er zijn kritieke correcties toegepast voor de webAPI van de Microsoft Dynamics-connector.
* De nieuwe operator en het groepsschema schrijven (operatorWrite) naar rechts is toegevoegd om gebruikers toe te staan operatorschema&#39;s (xtk:operator) en groepen operatoren (xtk:group) in te voegen, bij te werken en te verwijderen.
  <!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
  <!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* De veelvoudige actieve rekeningen van de LIJN kunnen nu op één enkele midsourcing worden gevormd.
* Het aantal standaardverbindingen voor het webproces is verhoogd van 50 naar 150.
* Campagne wordt geleverd met een set nieuwe instructies om te voorkomen dat gedupliceerde sleutels worden ingevoegd in de Snowflake-database. [Meer informatie](../architecture/keys.md)

**Bevestigingen**

* Probleem verholpen dat optrad bij het gebruik van zaden en controlegroepen in dezelfde terugkerende levering. (NEO-41197)
* Probleem met FFDA verholpen waarbij het verzenden van e-mail werd geblokkeerd voor alle ontvangers die tot dezelfde bezorging behoren tijdens het verzendproces (maximaal 256) wanneer personaliseringsblokken een van de volgende tekens bevatten: `' & < > "` . Deze tekens worden nu ondersteund in blokken voor personalisatie (bijvoorbeeld: firstname=&quot;Brian O&#39;Neil&quot;). (NEO-43184)
* Probleem verholpen waardoor de workflow voor bijhouden kon mislukken wanneer een aangepast schema als doeltoewijzing werd gebruikt. Wij zorgen nu ervoor dat het type van de buitenlandse verbinding aan een douane gericht schema correct is wanneer het produceren van schema wideLog via de tovenaar van de doelafbeelding. (NEO-43506)
* Probleem opgelost waarbij de implementatieworkflows van de FFDA zouden kunnen mislukken voor andere talen dan het Engels. (NEO-44561)

## Release 8.2.10 {#release-8-2-10}

_donderdag 2 februari 2022_

**Bevestigingen**

* Probleem opgelost waarbij de voorbereiding van de levering mislukte als het maximum aantal berichten, dat in de typologieregel is gedefinieerd, is bereikt.
* Probleem verholpen tijdens de configuratie van de Adobe Analytics-connector toen het e-mailadres een &#39;s&#39;-teken bevatte.
* Probleem verholpen tijdens postupgrade die ertoe kon leiden dat de tabel deliveryMapping gegevens uit een aangepaste leveringstoewijzing verliest.
* Probleem verholpen waarbij ontvangers hetzelfde bericht meerdere keren kregen voor dezelfde levering wanneer het e-mailadres één aanhalingsteken (&#39;) bevatte. Dit teken is nu beschermd. (NEO-41198)
* Probleem met genereren van id verholpen bij het verzenden van proefdrukken met zaden of substitutieadressen. (NEO-42637)
* Probleem verholpen waardoor proofs niet meer kunnen worden verzonden door middel van de methode Adres. (NEO-40417)
* Probleem verholpen waardoor u het LINE-pakket niet kon installeren. (NEO-42503)
