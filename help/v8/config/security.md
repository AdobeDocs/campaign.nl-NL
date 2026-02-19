---
title: Tips en trucs voor beveiliging
description: Ga aan de slag met best practices voor Campagne-beveiliging
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: da2274cfd19bb067fcc1e990360093f161d5638a
workflow-type: tm+mt
source-wordcount: '2810'
ht-degree: 52%

---

# Tips en trucs voor beveiliging {#ac-security}

In Adobe nemen we de veiligheid van je digitale ervaring zeer serieus. Beveiligingspraktijken zijn diep verankerd in onze interne processen en tools voor softwareontwikkeling en -bewerkingen en worden rigoureus gevolgd door onze interfunctionele teams om incidenten op een snelle manier te voorkomen, op te sporen en erop te reageren.

Bovendien helpen ons samenwerkingswerk met partners, toonaangevende onderzoekers, veiligheidsonderzoeksinstellingen en andere brancheorganisaties ons bij het up-to-date houden met de nieuwste dreigingen en kwetsbaarheden en wij nemen regelmatig geavanceerde veiligheidstechnieken op in de producten en diensten die wij aanbieden.

>[!NOTE]
>
>**Campagne v8 Beheerde de Diensten van de Wolk:** de Infrastructuur (netwerk, server, TLS, het patching) wordt beheerd door Adobe. Deze pagina concentreert zich op huurder en toepassing-vlakke configuratie die u controleert: toegangsbeheer, authentificatie, instantiemontages, gegevensbescherming, codering, en operationele praktijken.

## Beveiligingschecklist {#security-checklist}

Gebruik deze controlelijst om uw configuratie met geadviseerde veilige gebreken te richten:

* [&#x200B; Toegangsbeheer &#x200B;](#access-management): Creeer veiligheidsgroepen, wijs aangewezen rechten toe, beperk admin gebruik, één exploitant per gebruiker, overzicht periodiek
* [&#x200B; Authentificatie en zitting &#x200B;](#authentication-and-session): Gebruik Adobe IMS, sterk identiteitsbeleid, zittingsonderbreking
* [&#x200B; Instantie en netwerkveiligheid &#x200B;](#instance-and-network-security): IP lijst van gewenste personen, toestemmingen URL, sleutels GPG via Controlebord
* [&#x200B; Gegevens en bescherming PII &#x200B;](#data-and-pii-protection): HTTPS, PII meningsbeperking, beperkte wachtwoorden, beschermt gevoelige pagina&#39;s
* [&#x200B; Coderende richtlijnen &#x200B;](#coding-guidelines): Geen hard-gecodeerde geheimen, bevestigt input, parameterized SQL, captchas
* [&#x200B; Beperking van Gegevens &#x200B;](#data-restriction): Beperk toegang tot wachtwoord en geheime gebieden in externe rekeningen
* [&#x200B; Operationeel en naleving &#x200B;](#operational-and-compliance): Ben met deze basislijn periodiek vergelijkbaar, gebruiks controletraject

## Privacy

Werk binnen de wetgeving die geldt voor de regio(’s) waar u actief bent om privacy en persoonsgegevens correct te behandelen en te beheren. De mogelijkheden van Adobe Campaign helpen u aan de verordeningen voldoen die in [&#x200B; worden vermeld deze pagina &#x200B;](../start/privacy.md)

### Adobe Experience Cloud-privacy {#experience-cloud-privacy}

Adobe Campaign maakt deel uit van de Adobe Experience Cloud-oplossingen. De manier waarop in Campaign met privacy wordt omgegaan, volgt de algemene Experience Cloud-beginselen:

* **Welke informatie wanneer wordt verzameld bij het gebruik van Adobe Experience Cloud**

  Als bedrijf dat Adobe Experience Cloud-oplossingen gebruikt, bepaalt u welke gegevens u verzamelt en naar uw Adobe Experience Cloud-account verzendt. Voorbeelden van soorten informatie die mogelijk worden verzameld, zijn webbrowseractiviteiten, IP-adressen, locatiegegevens van mobiele apparaten, succespercentages van campagnes, items die zijn aangeschaft of in een winkelwagentje zijn geplaatst, enz.

  >[!NOTE]
  >
  >Net als alle andere Adobe-producten verzamelt Campaign informatie over gebruikers van apps en websites. Zie het [Adobe-privacybeleid](https://www.adobe.com/nl/privacy/policy.html) voor meer informatie.

* **Hoe Adobe Experience Cloud wordt gebruikt om informatie te verzamelen**

   * Adobe Experience Cloud-oplossingen gebruiken cookies en vergelijkbare technologieën zoals webbakens (ook wel tags of pixels genoemd), waarmee u informatie kunt verzamelen. Zie [deze sectie](#tracking-capabilities) voor meer informatie over cookies en trackingmogelijkheden met Adobe Campaign.
   * U kunt in uw mobiele apps ook Adobe Experience Cloud-technologieën gebruiken. Voor meer bij het verzenden van mobiele leveringen met Campagne, zie [&#x200B; het kanaal van SMS &#x200B;](../send/sms/sms-channel.md) en Mobiel app kanaal.

* **De privacyopties van uw gebruikers voor uw gebruik van Adobe Experience Cloud**

  Adobe vraagt u om uw klanten een privacybeleid te verstrekken waarin het volgende wordt beschreven:

   * Uw privacymethoden in verband met Adobe Experience Cloud
   * Hoe gebruikers hun voorkeuren kunnen instellen voor het verzamelen of gebruiken van hun gegevens in verband met Adobe Experience Cloud

  >[!NOTE]
  >
  >Net als bij alle Adobe-producten kunnen Campaign-gebruikers weigeren om verzamelde informatie over hen te delen via apps en websites. Raadpleeg de [Veelgestelde vragen over Adobe Experience Cloud-gebruiksgegevens](https://www.adobe.com/nl/privacy/experience-cloud-usage-info-faq.html) voor meer informatie daarover.

Zie [deze pagina](https://www.adobe.com/nl/privacy/marketing-cloud.html) voor meer informatie over de Adobe Experience Cloud-privacy.

## Persoonsgegevens en persona&#39;s {#personal-data}

Bij privacybeheer is het belangrijk om te bepalen welke gegevens met zorg moeten worden behandeld en door wie.
* **Persoonsgegevens** omvatten informatie aan de hand waarvan een levende persoon direct of indirect kan worden geïdentificeerd.
* **Gevoelige persoonsgegevens** zijn gegevens over etnische afkomst, politieke opvattingen, godsdienstige overtuiging, criminele achtergrond, genetische informatie, gezondheidsgegevens, seksuele voorkeur, biometrische informatie en lidmaatschap van een vakbond.

Wanneer het integreren van Campagne met andere oplossingen van Experience Cloud waar het publiek van één systeem aan een andere, zoals [&#x200B; Adobe Analytics &#x200B;](../connect/ac-aa.md) kan worden overgebracht, [&#x200B; het Soorten van Experience Cloud &#x200B;](../start/shared-audiences.md), Campaign Standard, of met andere oplossingen door [&#x200B; Schakelaar van CRM &#x200B;](../../automation/workflow/crm-connector.md), moet u extra zorg aan persoonlijke gegevensbescherming betalen.

De [belangrijkste verordeningen](#privacy-regulations) betreffen de verschillende entiteiten die gegevens als volgt beheren:

* Een **gegevenscontroller** is de instantie die de middelen en het doel van het verzamelen, gebruiken en delen van persoonsgegevens bepaalt.

* Een **gegevensprocessor** is een persoon of partij die persoonsgegevens verzamelt, gebruikt of deelt op de manier die door de gegevenscontroller wordt aangegeven.

* Een **betrokkene** is een levende persoon wiens persoonsgegevens worden verzameld, gebruikt of gedeeld en die aan de hand van deze persoonsgegevens direct of indirect kan worden geïdentificeerd.

Als bedrijf dat persoonsgegevens verzamelt en deelt, bent u dus de gegevenscontroller, zijn uw klanten de betrokkenen en fungeert Adobe Campaign als gegevensprocessor bij het verwerken van deze persoonsgegevens op uw aanwijzingen. Als gegevenscontroller bent u verantwoordelijk voor de relatie met de betrokkenen, bijvoorbeeld bij het beheren van [verzoeken om toegang tot persoonsgegevens](#privacy-requests).

### Gebruiksscenario {#use-case-scenario}

Hier is een voorbeeld van een AVG-gebruiksscenario van hoog niveau om te laten zien hoe verschillende persona’s interactie met elkaar hebben.

In dit voorbeeld is de klant van Adobe Campaign een luchtvaartmaatschappij. Dit bedrijf is de **Gegevenscontroller** en alle klanten van de luchtvaartmaatschappij zijn **Betrokkenen**. Laura is in dit specifieke geval een klant van de luchtvaartmaatschappij.

Dit zijn de verschillende persona’s die in dit voorbeeld worden gebruikt:

* **Laura** is de **Betrokkene**. Zij is de ontvanger die berichten van de luchtvaartmaatschappij krijgt. Laura vliegt misschien wel vaak (Frequent Flyer), maar ze zou op een gegeven moment kunnen besluiten dat ze geen gepersonaliseerde reclame- of marketingberichten van de luchtvaartmaatschappij meer wil. Ze zal de luchtvaartmaatschappij (volgens hun procedure) vragen haar Frequent-Flyernummer te verwijderen.

* **Anne** is **Gegevenscontroller** bij de luchtvaartmaatschappij. Ze ontvangt het verzoek van Laura, haalt nuttige id&#39;s op die gevraagd zijn om het onderwerp te identificeren en verzendt het verzoek in Adobe Campaign.

* **Adobe Campaign** is de **Gegevensprocessor**.

![](assets/privacy-gdpr-flow.png)

Hier volgt de algemene workflow voor dit gebruiksscenario:

1. De **Betrokkene** (Laura) stuurt een AVG-verzoek naar de **Gegevenscontroller** via e-mail, de Klantenservice of een webportal.

1. De **Gegevenscontroller** (Anne) stuurt het AVG-verzoek naar Campaign via de interface of met een API.

1. Zodra de **Gegevensprocessor** (Adobe Campaign) de informatie heeft ontvangen, onderneemt deze actie voor het AVG-verzoek en stuurt een reactie of een bevestiging naar de **Gegevenscontroller** (Anne).

1. De **Gegevenscontroller** (Anne) bekijkt vervolgens de informatie en stuurt deze terug naar de **Betrokkene** (Laura).

## Gegevensacquisitie {#data-acquisition}

Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en gevoelige informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

* Zorg ervoor dat ontvangers altijd toestemming geven voor het ontvangen van communicatie. Daarvoor moet u opt-outverzoeken altijd zo snel mogelijk verwerken en moet u toestemming controleren via een dubbele opt-inprocedure. Zie [Een lidmaatschapsformulier maken met dubbele opt-in](https://experienceleague.adobe.com/en/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank} voor meer informatie.
* Importeer geen frauduleuze lijsten en gebruik seedadressen om te controleren of uw clientbestand niet onrechtmatig wordt gebruikt. Zie [Seedadressen](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank} voor meer informatie.
* Via toestemmings- en rechtenbeheer kunt u de voorkeuren van uw ontvangers bijhouden en beheren wie binnen uw organisatie toegang heeft tot welke gegevens. Zie [deze sectie](#consent)voor meer informatie.
* Faciliteer en beheer de verzoeken om toegang tot persoonsgegevens van uw ontvangers. Zie [deze sectie](#privacy-requests)voor meer informatie.

## Privacybeheer {#privacy-management}

Het beheer van de privacy verwijst naar alle processen en hulpmiddelen die u kunnen helpen aan de verordeningen van de Privacy (GDPR, CCPA, enz.) voldoen.

Adobe Campaign biedt u verschillende functiesets voor privacybeheer:
* toestemmingsbeheer, dataretentie en gebruikersrollen. Zie [deze sectie](#consent).
* Verzoeken om toegang tot persoonsgegevens (toegangsrecht en recht om te worden vergeten). Zie [deze sectie](#privacy-requests).
* Opt-out voor de Verkoop van Persoonlijke Informatie (specifiek CCPA).

De belangrijkste privacymogelijkheden in Campaign en een voorbeeld van de betrokken persona’s worden weergegeven in [deze sectie](https://helpx.adobe.com/nl/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).

### Toestemming, retentie en rollen {#consent}

Oorspronkelijk biedt Adobe Campaign belangrijke functies die essentieel zijn voor privacy:

* **Toestemmingsbeheer**: via de procedure van abonnementsbeheer kunt u de voorkeuren van uw ontvangers beheren en bijhouden welke ontvangers zich hebben aangemeld voor welke soorten abonnementen. Zie [Lidmaatschappen](../../automation/workflow/subscription-services.md) voor meer informatie hierover.
* **Dataretentie**: alle ingebouwde standaard logtabellen bevatten vooraf ingestelde retentieperioden, waarbij de gegevensopslag over het algemeen is beperkt tot 6 maanden of korter. Er kunnen extra retentieperioden worden ingesteld met workflows. Neem hiervoor contact op met de adviseurs van Adobe of met technische beheerders.
* **Rights Management**: Adobe Campaign biedt u de mogelijkheid om via verschillende standaard of aangepaste rollen de rechten te beheren die aan de verschillende Campaign-operators zijn toegewezen. Hierdoor kunt u bepalen wie binnen uw bedrijf toegang heeft tot verschillende typen gegevens en deze kan wijzigen of exporteren. Zie [Toegangscontrole](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank} voor meer informatie.

### Privacyverzoeken {#privacy-requests}

Adobe Campaign biedt extra mogelijkheden om uw taak als gegevenscontroller voor bepaalde verzoeken om toegang tot persoonsgegevens te vergemakkelijken:

* Het **toegangsrecht** is het recht van de betrokkene om van de gegevenscontroller bevestiging te krijgen of er persoonsgegevens van de betrokkene worden verwerkt, waar en voor welk doel.

* Het **recht om te worden vergeten** (verwijderingsverzoek) geeft de betrokkene het recht om zijn of haar persoonsgegevens door de gegevensbeheerder te laten wissen.

De verzoeken **Toegang** en **Verwijderen** worden weergegeven in [deze sectie](../start/privacy.md).

De implementatiestappen voor het maken van deze verzoeken worden uiteengezet in [deze sectie](../start/privacy.md).

## Trackingmogelijkheden {#tracking-capabilities}

### Cookies {#cookies}

Dankzij de trackingfuncties van Adobe Campaign kunt u bijhouden hoe verzendingsontvangers bladeren met behulp van drie typen cookies: een sessiecookie en twee permanente cookies.

* Een **sessiecookie**: de **nlid**-cookie bevat de id van de e-mail die is verzonden naar de contactpersoon (**broadlogId**) en de id van de berichtsjabloon (**deliveryId**). Deze wordt toegevoegd wanneer de contactpersoon op een URL klikt die is opgenomen in een e-mail die door Adobe Campaign wordt verzonden. Hiermee kunt u het gedrag van de contactpersoon op het web volgen. Deze sessiecookie wordt automatisch gewist wanneer de browser wordt gesloten. De contactpersoon kan zijn browser configureren om cookies te weigeren.

* Twee **permanente** cookies:
   * Het **UUID**-cookie (Universal Unique IDentifier) wordt gedeeld tussen Adobe Experience Cloud-oplossingen. Dit wordt één keer ingesteld totdat het verdwijnt uit de clientbrowser wanneer een nieuwe waarde wordt gegenereerd. Met dit cookie kunt u de gebruikers identificeren die met de Experience Cloud-oplossingen werken wanneer ze een website bezoeken. Het kan worden geplaatst door een introductiepagina (om onbekende klantenactiviteiten aan een ontvanger te koppelen) of door een verzending. De beschrijving van dit cookie is beschikbaar op [deze pagina](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html#ec-cookies).
   * Het **nllastdelid**-cookie (geïntroduceerd in Campaign Classic 20.3) is een permanente cookie die de **deliveryId** bevat van de laatste verzending waarvan de gebruiker op de koppeling heeft geklikt. Deze cookie wordt gebruikt wanneer de sessiecookie ontbreekt om te identificeren welke trackingtabel moet worden gebruikt.

In verordeningen zoals de Algemene verordening gegevensbescherming (AVG) wordt bepaald dat bedrijven de toestemming van webgebruikers nodig hebben voordat ze cookies mogen installeren.

* Pop-upvensters moeten worden vermeden omdat ze vaak worden geblokkeerd door browsers.

### Berichten tracken {#message-tracking}

Met Adobe Campaign kunt u de verzonden e-mails en het gedrag van de ontvangers van de verzending bijhouden: het openen, het klikken op koppelingen, afmeldingen, enzovoort. Voor meer op dit, zie [&#x200B; Ongeveer berichten &#x200B;](../start/gs-message.md).

Om dit te doen, voeg bijgehouden verbindingen aan uw berichten toe om het effect van uw levering en ontvankelijk gedrag op het Te volgen lusje van het leveringsdashboard te meten. Trackinggegevens worden geïnterpreteerd in het rapport Tracking-indicatoren. Meer over het volgen leren, verwijs naar [&#x200B; deze pagina &#x200B;](../send/tracking.md).

### Webtracking {#web-tracking}

>[!AVAILABILITY]
>
>Webtracering is niet beschikbaar in Campagne v8. Leer meer over niet beschikbare eigenschappen in [&#x200B; deze pagina &#x200B;](../start/v7-to-v8.md#gs-unavailable-features).

## Beveiliging van gegevens en BI&#39;s {#data-and-pii-protection}

De configuratie van de privacy en het verharden is een zeer belangrijk element van veiligheidsoptimalisering. Volg deze aanbevolen procedures:

* **HTTPS van het Gebruik voor alle eindpunten** - verzeker alle eindpunten die door Campagne (het volgen, spiegelpagina, Webtoepassingen, APIs) worden gebruikt worden gediend over HTTPS.
* **Beperk PII mening** - gebruik [&#x200B; PII meningsbeperking &#x200B;](../dev/restrict-pi-view.md) zodat slechts de erkende exploitanten gevoelige gebieden (b.v. e-mail, telefoon) in schema&#39;s en de schermen kunnen zien.
* **Beperk toegang tot gecodeerde wachtwoorden** - Beperk toegang tot wachtwoord en geheime gebieden in externe rekeningen en andere schema&#39;s zodat slechts kunnen de beheerders of een minimale reeks exploitanten hen bekijken. Zie {de beperking van 0} Gegevens [&#x200B; hieronder.](#data-restriction)
* **beschermt gevoelige pagina&#39;s** - Beperk toegang tot spiegelpagina&#39;s, Webtoepassingen, en landende pagina&#39;s die tonen of PII verzamelen; gebruikexploitant en omslagtoestemmingen en, waar relevant, titels en toestemming.

>[!NOTE]
>
>Als gebruiker van Managed Cloud Services werkt Adobe samen met u om deze configuraties in uw omgeving te implementeren.

## Toegangsbeheer {#access-management}

Toegangsbeheer is een belangrijk onderdeel van de beveiliging. Hier volgen de belangrijkste aanbevolen procedures:

* **creeer genoeg veiligheidsgroepen** - bepaal exploitantgroepen die rollen aanpassen en slechts de rechten toewijzen elke rolbehoeften.
* **Controle dat elke exploitant de aangewezen toegangsrechten** heeft - pas het beginsel van minste voorrecht toe; vermijd het verlenen van BEHEER of andere brede rechten door gebrek.
* **vermijd gebruikend de adminexploitant en vermijd het hebben van teveel exploitanten in de admingroep** - deel niet de ingebouwde adminrekening; creeer één exploitant per fysieke gebruiker voor verantwoordingsplicht en controle.
* **Één exploitant per fysieke gebruiker** - deel geen rekeningen. Maak één Campagneoperator (Adobe ID) per persoon, zodat audittrails en logboeken kunnen worden toegewezen.
* **de grens hoog-voorrecht genoemde rechten** - het BEHEER van de Verlening **&#x200B;**, **UITVOERING VAN HET PROGRAMMA** (createProcess), en **SQL** slechts aan een klein aantal vertrouwde op exploitanten; document dat hen en waarom heeft.
* **toegang van het Overzicht periodiek** - herziet Periodiek Operatoren, de groepen van de Exploitant, en omslagtoestemmingen; verwijder of verminder toegang wanneer de rollen veranderen of de mensen verlaten.
* **de productprofielen van het Gebruik constant** - verkies het toewijzen van gebruikers aan productprofielen (exploitantgroepen) in Admin Console; houd het noemen verenigbaar (b.v. `campaign - <instance> - <group>`). Zie [&#x200B; begonnen worden met toestemmingen &#x200B;](../start/gs-permissions.md).
* **toegang van het Controlebord** - in Campagne v8, productprofielen of genoemde rechten de waarvan naam &quot;admin&quot;bevat kan toegang tot het Controlebord van de Campagne verlenen. Vermijd het gebruik van &quot;admin&quot; in profiel- of groepsnamen, tenzij deze gebruikers toegang moeten hebben tot het Configuratiescherm.

Leer meer over toestemmingen in [&#x200B; deze sectie &#x200B;](../start/gs-permissions.md).

## Verificatie en sessie {#authentication-and-session}

* **Gebruik Adobe IMS** - alle gebruikers zouden binnen met hun Adobe ID (IMS) moeten ondertekenen; baseer zich niet op erfenislogin/wachtwoord voor dagelijkse exploitanten.
* **Vertrouw op sterk identiteit en wachtwoordbeleid** - gebruik Admin Console of uw identiteitsleverancier voor MFA en wachtwoordbeleid; zorg ervoor slechts de erkende gebruikers aan de profielen van het het productproduct van de Campagne worden toegewezen.
* **vorm zittingsonderbreking** - waar configureerbaar (b.v. cliëntconsole), plaats een redelijke zittingsonderbreking en sluit het scherm wanneer het verlaten van het werkstation.

## Instantie- en netwerkbeveiliging {#instance-and-network-security}

Als het productbeheerder van de Campagne v8, gebruik [&#x200B; Controlebord van de Campagne &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl){target="_blank"} om instantie-vlakke veiligheid te beheren:

* **IP lijst van gewenste personen** - beheer de IP lijst van gewenste personen voor instantietoegang; beperk tot bekende netwerken (b.v. bureau, VPN) en vermijd overdreven brede waaiers waar mogelijk.
* **toestemmingen URL** - Beperk de toestemmingen URL tot de domeinen uw instantie (APIs, het volgen, de externe diensten) moet roepen om het risico van server-zijverzoekmisbruik te verminderen.
* **GPG sleutels** - als u encryptie voor dossieroverdrachten of andere gebruiksgevallen gebruikt, de sleutels van GPG via Controlebord beheren en hen roteren volgens uw veiligheidsbeleid.

## Codeerrichtlijnen {#coding-guidelines}

Volg bij het ontwikkelen in Adobe Campaign (workflows, Javascript, JSSP, enz.) altijd de volgende richtlijnen:

* **Scripting** - probeer om ruwe SQL te vermijden; gebruik geparameterialiseerde functies in plaats van koordaaneenschakeling. Vermijd SQL-injectie door alleen de SQL-functies toe te voegen die u aan de lijst van gewenste personen nodig hebt.
* **Beveilig het gegevensmodel** - Gebruik genoemde rechten om exploitantacties te beperken en systeemfilters (sysFilter) toe te voegen.
* **voegt kapitalen in Webtoepassingen** toe - voeg kapitalen aan openbare het landen pagina&#39;s en abonnementspagina&#39;s toe.
* **niet hardcode geheimen** - gebruik geen hardcode wachtwoorden, API sleutels, of tekenen in werkschema&#39;s, JavaScript, of JSSP; gebruik externe rekeningen of veilige configuratie.
* **bevestigt en ontsmet input** - Valideer en ontsmet gebruikersinput in Webtoepassingen en werkschemaparameters om injectie en risico&#39;s te verminderen XSS.
* **Gebruik de lijst van gewenste personen voor SQL** - wanneer SQL of manuscriptuitvoering wordt vereist, gebruik de lijst van gewenste personen voor toegelaten SQL functies en vermijd bouwend vragen van gebruikersinput via koordaaneenschakeling.

Leer meer in [&#x200B; Adobe Campaign Classic v7 documentatie &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}.


## Personalisatie

Wanneer u persoonlijke koppelingen toevoegt aan uw inhoud, moet u altijd geen persoonlijke instellingen opgeven in het gedeelte hostnaam van de URL om mogelijke beveiligingsproblemen te voorkomen. De volgende voorbeelden mogen nooit in alle URL-kenmerken &lt;`a href="">` of `<img src="">` worden gebruikt:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Gegevensbeperking {#data-restriction}

U moet ervoor zorgen dat de gecodeerde wachtwoorden niet toegankelijk zijn voor gebruikers met lage bevoegdheden. Hiervoor zijn er twee manieren: de toegang tot alleen wachtwoordvelden of tot de gehele entiteit beperken.

Met deze beperking kunt u wachtwoordvelden verwijderen, maar de externe account blijft toegankelijk vanuit de interface voor alle gebruikers. Meer informatie vindt u [op deze pagina](../dev/restrict-pi-view.md).

1. Ga in **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]** .

1. Maak een nieuwe **[!UICONTROL Extension of a schema]** .

1. Kies **[!UICONTROL External Account]** (extAccount).

1. In het laatste scherm, kunt u uw nieuw srcSchema uitgeven om toegang tot alle wachtwoordgebieden te beperken:

   U kunt het hoofdelement (`<element name="extAccount" ... >`) vervangen door:

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   Zo kan uw uitgebreide srcSchema als kijken:

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >U kunt `$(loginId) = 0 or $(login) = 'admin'` vervangen door `hasNamedRight('admin')` zodat alle gebruikers met de juiste beheerdersrechten deze wachtwoorden kunnen zien.

## Operationeel en conform {#operational-and-compliance}

* **vergelijkt om basislijn** te beveiligen - vergelijk periodiek uw exploitantgroepen, genoemde rechten, en omslagtoestemmingen aan de aanbevelingen in deze pagina (en, indien van toepassing, [&#x200B; Verbeterde veiligheid toe:voegen-op &#x200B;](enhanced-security.md)) om met geadviseerde veilige gebreken te richten.
* **gebruik het controletraject** - Rust op het de controlespoor van de Campagne voor belangrijke veranderingen (b.v. werkschema&#39;s, leveringen, zeer belangrijke configuratie); behoud en herzie logboeken zoals vereist door uw naleving en behoudbeleid.
