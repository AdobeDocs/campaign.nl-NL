---
title: Best practices voor verzending
description: Leer de beste werkwijzen bij het ontwerpen en verzenden van leveringen met Adobe Campaign
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
source-git-commit: b4fad76b43a77909a4ea2c0877527af80027681a
workflow-type: tm+mt
source-wordcount: '2869'
ht-degree: 1%

---

# Best practices voor verzending {#delivery-best-practices}

Lees de beste praktijken met de leveringsmogelijkheden van de Campagne.

## Levering optimaliseren {#optimize-delivery}

Voordat u zelfs begint met het maken van leveringen, kunt u verschillende acties uitvoeren om het verzendingsproces te beveiligen en te optimaliseren. In de volgende sectie worden aanbevolen procedures en aanbevolen procedures voor de optimale configuratie van Adobe Campaign beschreven.

### Platformprestaties

Verschillende factoren kunnen rechtstreeks van invloed zijn op de prestaties van de server en uw Campagneplatform vertragen:

* Het aantal en het type van [ verpersoonlijking ](../send/personalize.md) elementen: verpersoonlijking in e-mail trekt gegevens uit het gegevensbestand voor elke ontvanger. in het geval van veel personalisatie - elementen is de hoeveelheid gegevens die nodig is om de levering voor te bereiden hoger . Dit kan uw platform vertragen. Leer meer over verpersoonlijkingsbegeleiding in [ deze sectie ](../send/personalize.md#perso-guardrails).

* De server wordt geladen: wanneer de marketingserver meerdere taken tegelijk uitvoert, kunnen de prestaties afnemen. De marketingserver moet alle inkomende en uitgaande gegevens voor alle leveringen coördineren om ervoor te zorgen dat de gegevens correct en op tijd zijn.
Om dit te vermijden, coördineer de planning van leveringen met de andere leden van uw team om de beste prestaties te verzekeren.

* De workflowuitvoering: het controleren van uw workflows is essentieel om problemen met de prestaties van het platform te voorkomen. Volg de vermelde richtlijnen [ in dit document ](../../automation/workflow/workflow-best-practices.md#execution-and-performance).

* Verbind met uw [ mogelijkheden van het Controlebord van de Campagne ](https://experienceleague.adobe.com/en/docs/control-panel/using/discover-control-panel/key-features) {target="_blank"} om uw platform te controleren, gebruikend [ prestaties controlerend ](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring) {target="_blank"} functies.

#### Quarantainebeheer {#quarantine-management}

Het is in uw belang om goede processen van het quarantainebeheer te handhaven.

Wanneer u e-mailberichten op een nieuw platform gaat verzenden, kunt u een lijst met adressen gebruiken die niet volledig zijn gekwalificeerd. Als u naar ongeldige adressen of naar honeypot-adressen (brievenbussen slechts die aan truc spammers worden gecreeerd) verzendt, zal dit de reputatie van uw platform beginnen te verminderen. Goede quarantainebeheerprocessen helpen: de adreskwaliteit handhaven, lijst van gewezen personen door internettoegangsproviders vermijden, en uw foutenpercentage verminderen, leveringen en productie versnellen.


Leer meer hoe te om een nieuw platform in de [ Gids van de Beste praktijken van de Levering van de Adobe te beginnen ](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform) {target="_blank"}.

De technische aanbevelingen worden vermeld in [ deze sectie ](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations) {target="_blank"}.


**Uiteinden**

* Als u een lijst met ongeldige adressen hebt, kunt u het beste deze naar de quarantainetabel importeren via **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** > **[!UICONTROL Non deliverables and addresses]** .

* De ontvangers de waarvan adressen in quarantined zijn uitgesloten door gebrek tijdens de leveringsanalyse: zij worden niet gericht. Dit versnelt leveringen, aangezien het foutenpercentage een significant effect op leveringssnelheid heeft. Een e-mailadres kan in quarantaine worden geplaatst bijvoorbeeld wanneer inbox volledig is of als het adres niet bestaat.
Adobe Campaign beheert onjuiste adressen op basis van het type geretourneerde fout. [ leer meer over quarantines ](../send/quarantines.md)

* Sommige providers van internettoegang beschouwen e-mails automatisch als spam als de snelheid van ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat deze providers aan de lijst van gewezen personen worden toegevoegd.


### Dubbele opt-in-regeling {#double-opt-in}

Om te voorkomen dat berichten naar ongeldige adressen worden verzonden, onjuiste communicatie wordt beperkt en de reputatie van de afzender wordt verbeterd, raadt de Adobe aan een dubbele opt-in-mechanisme in te voeren voor bevestiging na abonnementen. Zo weet u zeker dat een ontvanger met opzet is geabonneerd.

## Sjablonen gebruiken {#use-templates}

De malplaatjes van de levering staan voor verhoogde efficiency toe door kant-en-klare scenario&#39;s voor de meeste gemeenschappelijke soorten activiteiten te verstrekken. Met malplaatjes, kunnen de marketers nieuwe campagnes met minimale aanpassing in een kortere hoeveelheid tijd opstellen. [ Leer meer over leveringsmalplaatjes ](../send/create-templates.md).

### Branding

Wanneer u meerdere merken beheert in Adobe Campaign, raadt Adobe aan één subdomein per merk te hebben. Een bank kan bijvoorbeeld verschillende subdomeinen hebben die overeenkomen met elk van haar regionale agentschappen. Als een bank eigenaar is van het bluebank.com-domein, kunnen de subdomeinen @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com enzovoort zijn. Als u één leveringssjabloon per subdomein hebt, kunt u altijd de juiste vooraf geconfigureerde parameters voor elk merk gebruiken. Hierdoor worden fouten voorkomen en bespaart u tijd. Leer meer over subdomain branding in de [ documentatie van het Controlebord van de Campagne ](https://experienceleague.adobe.com/en/docs/control-panel/using/subdomains-and-certificates/subdomains-branding) {target="_blank"}.

### Adressen configureren

Pas de volgende richtlijnen toe:

* Het adres van de afzender is verplicht om het verzenden van een e-mail toe te staan. Sommige ISPs (de Dienstverleners van Internet) controleren de geldigheid van het afzenderadres alvorens berichten goed te keuren.
* Een slecht geformuleerd adres kan ertoe leiden dat het door de ontvangende server wordt verworpen. U moet ervoor zorgen een correct adres wordt gegeven.
* Het adres moet de afzender uitdrukkelijk identificeren. Het domein moet eigendom zijn van en geregistreerd zijn bij de afzender.
* Adobe raadt u aan e-mailaccounts te maken die overeenkomen met de adressen die zijn opgegeven voor leveringen en antwoorden. Vraag de beheerder van het berichtensysteem om advies.

Voer de onderstaande stappen uit om adressen in de Campagne-interface te configureren:

1. In het [ leveringsmalplaatje ](../send/create-templates.md), klik de **[!UICONTROL From]** verbinding. Voer in het **[!UICONTROL Email header parameters]** -venster de instellingen in.

1. Controleer in het veld **[!UICONTROL Sender address]** of het adresdomein hetzelfde is als het subdomein dat u aan de Adobe hebt gedelegeerd. U kunt het deel vóór &#39;@&#39; maar niet het domeinadres wijzigen.

1. Gebruik in het veld **[!UICONTROL From]** een naam die gemakkelijk kan worden herkend door de ontvangers, zoals de naam van uw merk, om de openingsfrequentie van uw leveringen te verhogen. Om de ervaring van de ontvanger verder te verbeteren, kunt u de naam van een persoon toevoegen, bijvoorbeeld &quot;Emma van Megastore&quot;.

1. In de velden **[!UICONTROL Reply address text]** wordt standaard het adres van de afzender gebruikt voor antwoorden. Adobe raadt echter aan een bestaand reëel adres te gebruiken, zoals de klantenservice van uw merk. In dit geval, als een ontvanger een antwoord verzendt, zal de klantenzorg het kunnen behandelen.

### Een controlegroep instellen

Nadat de levering is verzonden, kunt u het gedrag van de uitgesloten ontvangers vergelijken met de ontvangers die de levering wel hebben ontvangen. Vervolgens kunt u de efficiëntie van uw campagnes meten. Leer meer over controlegroepen [ deze sectie ](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Typologieën gebruiken om filters of controleregels toe te passen

Een typologie bevat controleregels die tijdens de analysefase worden toegepast, alvorens om het even welk bericht te verzenden.

Wijzig de standaardtypologie naar wens op het tabblad **[!UICONTROL Typology]** van de sjablooneigenschappen.

Bijvoorbeeld, om het uitgaande verkeer beter te controleren, kunt u bepalen welke IP adressen kunnen worden gebruikt door één affiniteit per subdomein te bepalen en één typologie per affiniteit te creëren. De affiniteiten worden gedefinieerd in het configuratiebestand van de instantie. Neem contact op met uw Adobe Campaign-beheerder.

Voor meer op typologieën, verwijs naar [ deze sectie ](../../automation/campaign-opt/campaign-typologies.md).

## Uw inhoud optimaliseren {#optimize-content}

### Gepersonaliseerde content maken {#perso-content}

Om uw berichten aan te passen, kunt u de gegevens gebruiken van ontvangers die in het gegevensbestand worden opgeslagen, of door het volgen, het landen pagina&#39;s, abonnementen, enz. worden verzameld. De grondbeginselen van Personalization worden voorgesteld in [ deze sectie ](../send/personalize.md).

Zorg ervoor dat de inhoud van uw bericht correct is ontworpen om fouten te voorkomen die gerelateerd kunnen zijn aan personalisatie. Een Adobe Campaign-personalisatiemarkering heeft altijd de volgende vorm: `<%=table.field%>`. Het onjuiste gebruik van parameters in verpersoonlijkingsblokken kan een kwestie zijn. Variabelen in JavaScript moeten bijvoorbeeld als volgt worden gebruikt:

``
<%
var brand = "xxx"
%>
``

Voor meer op verpersoonlijkingsblokken, verwijs naar [ deze sectie ](../send/personalization-blocks.md).

U kunt aanpassingsgegevens voorbereiden in een workflow om de voorbereiding van de levering te verbeteren. Dit moet speciaal worden gebruikt als de personalisatiegegevens afkomstig zijn van een externe tabel via Federated Data Access (FDA). Deze optie wordt beschreven in dit [ deze sectie ](../send/personalization-data.md#optimize-personalization)

### Geoptimaliseerde inhoud maken {#build-optimized-content}

Houd bij het maken van uw e-mails rekening met de onderstaande algemene tips:

* Ontwerp eenvoudig houden

* Houd mobiele gebruikers in gedachten

* Vermijd volledig op afbeeldingen gebaseerde e-mails

* E-mailveilige lettertypen gebruiken

* Speciale tekens coderen

### Onderwerpregel

Het werk op de [ onderwerpregel ](../send/personalization-fields.md#personalization-fields-uc) om open tarieven te verbeteren:

* Vermijd personen die te lang zijn. Maximaal 50 tekens gebruiken

* Vermijd het gebruik van herhalende woorden zoals &quot;gratis&quot; of &quot;aanbieding&quot;, die als spam kunnen worden beschouwd

* Vermijd hoofdletters en speciale tekens zoals &quot;!&quot;, &quot;£&quot;, &quot;€&quot;, &quot;$&quot;

### Pagina spiegelen

Neem altijd een koppeling naar een spiegelpagina op. De voorkeurspositie boven aan het e-mailbericht. Leer meer over de spiegelpagina in [ deze pagina ](../send/mirror-page.md)

### Koppeling met abonnement opheffen

De koppeling om uw abonnement op te zeggen is essentieel. Het formulier moet zichtbaar en geldig zijn en moet functioneel zijn. Door gebrek, wanneer het bericht wordt geanalyseerd, controleert een ingebouwde **[!UICONTROL Unsubscription link approval]** [ typologieregel ](../../automation/campaign-opt/control-rules.md) of een opt-out verbinding is omvat en produceert een waarschuwing als het mist.

**Uiteinde**: Omdat de menselijke fout altijd mogelijk is, controleer dat de opt-out verbinding correct vóór elke keer werkt u verzendt. Wanneer u bijvoorbeeld de proefdruk verzendt, controleert u of de koppeling geldig is, of het formulier online is en of het veld `No longer contact this recipient ` is gewijzigd in `Yes` .

Leer hoe te om een opt-out verbinding [ in deze sectie ](personalization-blocks.md#personalization-blocks-example) op te nemen.

### E-mailformaat

Om prestaties of leveringsproblemen te vermijden, is de geadviseerde maximumgrootte van een e-mail ongeveer **35KB**. Als u de berichtgrootte wilt controleren, bladert u naar de tab **[!UICONTROL Preview]** en kiest u een testprofiel. Zodra geproduceerd, wordt de berichtgrootte getoond in de hoogste juiste hoek.

Houd rekening met het volgende om uw e-mailadres onder de limiet te houden:

* Overbodige of ongebruikte stijlen verwijderen

* Een deel van de e-mailinhoud naar een openingspagina verplaatsen

* Miniatuur uw code

Zorg ervoor om het even welke veranderingen vóór de definitieve verzending te testen.

### Sms-lengte

Standaard voldoet het aantal tekens in een SMS aan de GSM-standaarden (Global System for Mobile Communications). Sms-berichten met gsm-codering mogen maximaal 160 tekens bevatten of 153 tekens per sms voor berichten die in meerdere delen worden verzonden.

Vertaling bestaat erin een teken van een SMS door een ander te vervangen wanneer dat teken niet in aanmerking wordt genomen door de GSM-standaard. Als u personalisatievelden in de inhoud van uw SMS-bericht invoegt, kunnen er tekens worden ingevoerd waarmee de GSM-codering geen rekening houdt. U kunt tekentransliteratie autoriseren door het corresponderende vak te selecteren op het tabblad met SMPP-kanaalinstellingen van het corresponderende **[!UICONTROL External account]** .

**Uiteinden**

* Als u alle tekens in uw SMS-berichten wilt behouden, bijvoorbeeld als u eigennamen niet wilt wijzigen, moet u transliteratie niet inschakelen.

* Als uw SMS-berichten echter veel tekens bevatten waarmee de GSM-standaard geen rekening houdt, kunt u met transliteratie de verzendkosten van uw berichten beperken.

Leer meer [ in deze sectie ](../send/sms/smpp-external-account.md#smpp-transliteration).

### Bijlagen voorkomen

Bijlagen blijven een van de meest voorkomende vectoren voor de proliferatie van malware, vooral wanneer ze bulksgewijs worden verzonden. Neem een beveiligde koppeling naar het document op in plaats van deze te koppelen. Dit verzekert een extra laag van veiligheid om onbedoelde herdistributie te verhinderen, en vermindert enorm de kansen dat het bericht bij binnenkomende e-mailgateways voor berichtgrootte of veiligheidsredenen zal worden verworpen.

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).-->


## Afbeeldingen beheren {#manage-images}

Hier volgen enkele specifieke richtlijnen voor het optimaliseren van afbeeldingen voor uw marketingcampagne voor e-mail.

### Afbeeldingen blokkeren voorkomen

Sommige e-mailclients blokkeren afbeeldingen standaard en sommige gebruikers wijzigen hun instellingen om afbeeldingen te blokkeren zodat ze op gegevensgebruik kunnen worden opgeslagen. Als afbeeldingen niet worden gedownload, kan het hele bericht verloren gaan. Om dit te voorkomen:

* Verdeel uw inhoud met afbeelding en tekst. Vermijd e-mails die volledig op afbeeldingen zijn gebaseerd.

* Als er tekst in een afbeelding moet staan, gebruikt u de alt- en titeltekst om ervoor te zorgen dat uw bericht overloopt. Maak de alt-/titeltekst op om de weergave te verbeteren.

* Vermijd het gebruik van achtergrondafbeeldingen, omdat deze niet door sommige e-mailclients worden ondersteund.

### Afbeeldingen responsief maken

Probeer afbeeldingen responsief te maken en de grootte ervan te wijzigen. Merk op dat dit een kosteneffect kan hebben aangezien het langer duurt om te bouwen.

### Absolute verwijzingen naar afbeeldingen gebruiken

Om van buitenaf toegankelijk te zijn, moeten de beelden die in e-mail en openbare middelen verbonden aan campagnes worden gebruikt op een extern toegankelijke server aanwezig zijn.

* Vanuit de bezorgingsassistent kunt u een HTML-pagina met afbeeldingen importeren of rechtstreeks afbeeldingen invoegen met de HTML-editor via het pictogram **[!UICONTROL Image]** .

* Als afbeeldingen niet worden weergegeven, controleert u of de afbeeldingen beschikbaar zijn op de server. Om dit te doen, doorblader aan het **Source** lusje van uw levering. Zoek uw afbeeldingen en kopieer en plak de URL van elke afbeelding in een webbrowser. Als de afbeeldingen niet worden weergegeven, neemt u contact op met uw IT-beheerder of de externe leverancier die uw leveringsinhoud levert.

### Een voorbeeld van uw bericht bekijken en uw bericht testen {#preview-msg}

Adobe raadt u aan een voorbeeld van uw bericht te bekijken om na te gaan hoe de inhoud van het bericht wordt aangepast en hoe de ontvangers de levering zien.

In de bezorgingsassistent kunt u op het subtabblad **[!UICONTROL Preview]** de rendering van elke inhoud voor een ontvanger weergeven. De verpersoonlijkingsgebieden en de voorwaardelijke elementen van inhoud worden vervangen met de overeenkomstige informatie voor het geselecteerde profiel. [Meer informatie](../send/preview-and-proof.md).


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## De juiste doelgroep definiëren {#define-the-right-audience}

De doelgroep is belangrijk: maak uw lijsten zorgvuldig, test uw e-mails op populaire e-mailclients en mobiele apparaten en controleer of uw e-maillijsten up-to-date zijn (zonder onbekende of verouderde adressen). U kunt ook proefdrukken verzenden waarmee u een volledige validatiecyclus kunt instellen. Leer meer over publiek in [ deze sectie ](../audiences/gs-audiences.md).

### Doelgroep {#target-the-right-audience}

Wanneer u uw inhoud klaar hebt, moet u zorgvuldig bepalen wie uw bericht zal ontvangen.

Om uw levering succesvol te maken, wilt u de meest relevante gepersonaliseerde inhoud naar de juiste ontvangers verzenden. Met Adobe Campaign kunt u het meest nauwkeurige doel maken: u kunt ontvangers selecteren op basis van hun leeftijd, lokalisatie, wat ze hebben gekocht, als ze op een koppeling in een vorige levering klikken, enzovoort. Met Adobe Campaign kunt u ook testprofielen, controlegroepen en zaadadressen definiëren om te controleren of het doel correct is.

### Doeltoewijzingen {#target-mappings}

In Campagne, door gebrek, richten de leveringsmalplaatjes **Ontvangers**. Adobe Campaign biedt andere doeltoewijzingen voor uw leveringen die u op basis van uw behoeften kunt wijzigen. U kunt bijvoorbeeld leveren aan bezoekers van wie de profielen via sociale netwerken zijn verzameld of aan bezoekers die zijn geabonneerd op een informatieservice.

Deze afbeeldingen worden voorgesteld [ in deze sectie ](../audiences/target-mappings.md).

### Externe ontvangers {#external-recipients}

U kunt leveren aan ontvangers die in een extern dossier eerder dan opgeslagen in het gegevensbestand worden opgeslagen. Leer meer [ in deze sectie ](create-message.md#select-external-recipients-selecting-external-recipients).

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### Ontvangers testen {#test-recipients-seed-addresses}

Om uw levering te testen, gebruik proef alvorens naar het belangrijkste doel te verzenden.

Zorg ervoor dat u de juiste ontvangers voor het bewijs selecteert, omdat deze het formulier en de inhoud van het bericht valideren. De stappen voor het bepalen van de proefontvangers worden voorgesteld [ in deze sectie ](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target).


### Gedupliceerde adressen {#deduplicate-addresses}

Het is belangrijk om dubbele e-mailadressen te vermijden, omdat dit van invloed kan zijn op uw doel:

* Hetzelfde bericht kan meerdere keren worden verzonden wanneer een doel wordt gesplitst.

* Als een ontvanger zich afmeldt na het ontvangen van een bericht, zal hun dubbele profiel nog toekomstige berichten ontvangen.

Deduplicating adressen beschermt uw verzendende reputatie en verzekert goed quarantainebeheer.

**Verwante onderwerpen:**

* [ de activiteit van de Deduplicatie ](../../automation/workflow/deduplication.md).
* [ het geval van het Gebruik: Gebruikend de samenvoegfunctionaliteit van de activiteit van de Deduplicatie ](../../automation/workflow/deduplication-merge.md).


## Alle controles uitvoeren voordat ze worden verzonden {#perform-all-checks}

Zodra uw bericht klaar is, zorg ervoor zijn inhoud correct, op alle apparaten wordt getoond, en bevat geen fouten zoals verkeerde verpersoonlijking of gebroken verbindingen. Alvorens uw bericht te verzenden, zorg ook dat de parameters en de configuratie met de levering verenigbaar zijn.

De stappen voor het bevestigen van een levering worden voorgesteld [ in deze sectie ](../send/preview-and-proof.md).

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### Proefberichten {#proof-messages}

Door proefdrukken te verzenden, kunt u de koppeling om te weigeren controleren, de pagina spiegelen en andere koppelingen controleren, het bericht valideren, controleren of afbeeldingen worden weergegeven, mogelijke fouten opsporen, enz. Mogelijk wilt u ook uw ontwerp en rendering op verschillende apparaten controleren.

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### Controleer of je bericht is bezorgd {#make-sure-your-message-is-delivered}

Als laatste stap maximaliseert u uw kansen en gebruikt u de kracht van Adobe Campaign om ervoor te zorgen dat uw bericht ook daadwerkelijk aan de relevante ontvangers wordt bezorgd.

#### Een validatieproces doorlopen

U kunt een volledig validatieproces definiëren, waarbij Adobe Campaign-operatoren en -groepen betrokken zijn, om zowel de inhoud van het doel als het bericht te valideren. Dit zal zorgen voor volledig toezicht en controle op de verschillende processen van de campagne: gericht op, inhoud, begroting, extractie en het verzenden van bewijzen. Afhankelijk van hun machtigingen zullen gebruikers op de hoogte worden gesteld, proefdrukken ontvangen en het bericht kunnen valideren of afwijzen. Leer meer [ in deze sectie ](../../automation/campaigns/marketing-campaign-approval.md).

#### Golven gebruiken

U kunt het verzonden volume progressief verhogen gebruikend golven. Zo voorkomt u dat uw berichten als spam worden gemarkeerd of dat u het aantal berichten per dag wilt beperken. Met golven kunt u leveringen in verschillende batches verdelen in plaats van tegelijkertijd grote volumes berichten te verzenden. Leer meer [ in deze sectie ](../send/configure-and-send.mdsending-using-multiple-waves).

#### Prioriteitsberichten

U kunt de verzendende orde voor uw leveringen plaatsen door het prioritaire niveau te verklaren. Dit doet u als volgt:

1. Bewerk de leveringseigenschappen en selecteer de tab **[!UICONTROL Delivery]** .

1. Definieer het prioriteitsniveau voor de levering op een schaal van **[!UICONTROL Very low]** tot **[!UICONTROL Very high]** .

>[!NOTE]
>
>Het is niet mogelijk om de volgorde te bepalen waarin berichten worden verzonden vanuit een levering.

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### Typologieën gebruiken

U kunt typologische regels gebruiken om een deel van het doel uit te sluiten op basis van specifieke criteria. Dit garandeert dat de verzonden berichten het best aan de behoeften en de verwachtingen van klanten voldoen, in overeenstemming met het beleid van het bedrijfs communicatie. U kunt bijvoorbeeld de ontvangers die jonger zijn, filteren van het doel van de nieuwsbrief. Leer meer [ in dit voorbeeld ](../../automation/campaign-opt/filtering-rules.md).


## Track en monitor {#track-and-monitor}

U klikte **verzendt** knoop? Laten we eens kijken wat er gebeurt. Zodra de levering wordt verzonden, laat Adobe Campaign u toe om spoor van de verzonden berichten te houden en te ontdekken hoe uw ontvangers op uw levering reageren. Op deze manier kunt u uw volgende campagnes beter verzenden en optimaliseren.

## Leveringen controleren {#monitoring-deliveries}

Om uw campagnes te controleren, moet u ervoor zorgen dat het bericht inderdaad aan uw ontvangers is geleverd.

Van het dashboard van de levering van de Campagne, kunt u de verwerkte berichten en de logboeken van de leveringscontrole controleren. U kunt de status van de berichten in de leveringslogboeken ook controleren.

[ leer meer over levering controle in Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html) {target="_blank"}


## Traceergedrag {#track-behaviour}

Als u het gedrag van de ontvangers beter wilt weten, kunt u bijhouden hoe zij op een levering reageren: ontvangst, openen, klikken op koppelingen, abonnementen, enz. In Campagne, wordt deze informatie getoond in het **Volgen** lusje van de ontvangers die door de levering en in het Volgen lusje van de levering worden gericht.

**Uiteinde**: Het volgen van het bericht wordt toegelaten door gebrek. Om URLs te vormen, selecteer de optie van de Vertoning URLs in de lagere sectie van de leveringsmedewerker. Voor elke URL van het bericht kunt u kiezen of u reeksspatiëring wilt activeren.


[ leer meer over het volgen mogelijkheden in Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html#sending-messages) {target="_blank"}

