---
title: Veelgestelde vragen over campagne v8
description: Geniet van antwoorden op algemene Adobe Campaign v8-vragen over setup, configuratie, berichten, workflows en meer
feature: Overview
role: User
level: Beginner
keywords: Veelgestelde vragen, campagne v8, vragen, antwoorden, Help, ondersteuning, problemen oplossen
version: Campaign v8
hide: true
hidefromtoc: true
source-git-commit: 64d2b6a6ddba8b2de2e27ab8286584c99ef39583
workflow-type: tm+mt
source-wordcount: '10162'
ht-degree: 4%

---

# Veelgestelde vragen {#faq}

Geniet van snelle antwoorden op de meest voorkomende vragen over Adobe Campaign v8. Of u enkel begonnen bent of het zoeken naar geavanceerde configuratiehulp, zult u antwoorden vinden die door onderwerp hieronder worden georganiseerd.

**Nieuw aan Campagne?** Begin met [ Begonnen ](#getting-started) om de essentiële elementen te leren.\
**Heb hulp met versies nodig?** Controle [ Verbeteringen ](#upgrades) voor versieinformatie en verbeteringsprocessen.\
**migrerend van v7 of Standaard?** zie [ Campagne v8 vs Vorige Versies ](#v7-differences) voor verschillen en overgangsbegeleiding.\
**technische hulp nodig?** Controle [ Ontwikkelaars ](#developers) en [ de Montages van de Campagne ](#settings).\
**Kan uw antwoord niet vinden?** Bezoek onze [ Communautaire Forums ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} of [ contactsteun ](#get-help).

**Uiteinde:** Gebruik Ctrl+F (Cmd+F op Mac) om naar specifieke sleutelwoorden op deze pagina te zoeken. Klik op een vraag om het antwoord uit te vouwen.


## Aan de slag {#getting-started}

Leer de basisbeginselen om met Adobe Campaign v8 te gaan werken, van installatie en verbinding tot het maken van uw eerste campagnes.

+++ Wat is Adobe Campaign v8?

Adobe Campaign v8 is een krachtig platform voor kanaalmarketingautomatisering waarmee u persoonlijke campagnes kunt maken, coördineren en leveren via e-mail, mobiele, sociale en offlinekanalen. Het combineert een robuuste marketing gegevensbestand, de motor van de campagneorchestratie, en interactiemogelijkheden in real time om klanten tijdens hun reis in dienst te nemen.

**Zeer belangrijke mogelijkheden:** Multikanaal campagnebeheer, publiekssegmentatie en het richten, werkschemaautomatisering, verpersoonlijking bij schaal, bericht in real time en partijoverseinen, rapportering en analyse, integratie met Adobe Experience Cloud.

**wat tot v8 uniek maakt:** de inheemse architectuur van de Wolk (Beheerde Diensten van de Wolk slechts), prestaties op bedrijfsniveau aangedreven door het gegevensbestand van Snowflake, automatische verbeteringen, verbeterde veiligheid, en bidirectionele integratie met Adobe Experience Platform.

**Ideaal voor:** Onderneming marketing teams die complexe, hoog-volumecampagnes over veelvoudige kanalen en klantenaanraakpunten beheren.

**Verwante onderwerpen:**

[ Campagne v8 productbeschrijving ](https://helpx.adobe.com/nl/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"} | [ nieuw in v8 ](whats-new.md) | [ krijgen begonnen gids ](get-started.md)

+++

+++ Hoe kan ik campagne downloaden?

U kunt het installatieprogramma en de clientconsole ophalen vanuit Adobe Download Center.

Als Admin gebruiker, heb toegang tot de Distributie van de Software van Adobe [ ](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"} om Adobe Campaign te downloaden.

Leer meer over het Centrum van de Distributie [ op deze pagina ](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html){target="_blank"}.

+++

+++ Hoe kan ik verbinding maken met Campaign v8?

U moet de clientconsole van Campagne downloaden en installeren om verbinding te maken met Adobe Campaign. [Meer informatie](connect.md).

De aanvang van de Versie van Campagne v8.6, hebt u toegang tot het **de gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud. Experience Cloud is een geïntegreerde Adobe-reeks met digitale marketingtoepassingen, producten en services.

Leer hoe te met Adobe Experience Cloud te verbinden, en tot de interface van het Web van Adobe Campaign [ in deze pagina ](campaign-ui.md#ac-web-ui) toegang te hebben. Leer meer in de [ gebruikersinterfacedocumentatie van het Web van Adobe Campaign ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Verwante onderwerpen:**

[ installeer de cliëntconsole ](connect.md) | [ Campagne gebruikersinterface ](campaign-ui.md) | [ de toestemmingen van de Gebruiker ](gs-permissions.md)

+++

+++ Kan ik verbinding maken met Campaign v8 met een Adobe ID?

Ja! Dankzij de integratie met de IMS (Adobe Identity Management System) maken gebruikers via hun Adobe ID verbinding met de Adobe Campaign-console. Deze integratie biedt de volgende voordelen:

* Dezelfde id kan voor alle Experience Cloud-oplossingen worden gebruikt.
* De verbinding wordt onthouden bij het gebruik van Adobe Campaign met verschillende integraties.
* Veiliger beleid voor wachtwoordbeheer.
* Gebruik van Federated ID-accounts (externe id-provider).

[ leer meer ](connect.md) over de toegang tot van Campagne v8 met een Adobe ID.

+++

+++ Wat zijn de concepten van het gebruikersinterface van de Campagne ik zou moeten weten?

Verwijs naar [ deze sectie ](campaign-ui.md) om meer over de grondbeginselen van het gebruikersinterface van Adobe Campaign te leren.

Beginnende Versie van Campagne v8.6, hebt u ook toegang tot het nieuwe **de gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud.

[ leer meer in de gebruikersinterfacedocumentatie van het Web van Adobe Campaign ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Hoe kan ik gebruikersmachtigingen instellen?

Als Campaign-beheerder kunt u machtigingen instellen voor gebruikers van uw organisatie.

Dit zijn een reeks rechten en beperkingen waarbij wordt toegestaan of geweigerd om:

* Toegang tot bepaalde functies
* Toegang tot bepaalde gegevens
* Gegevens maken, wijzigen en/of verwijderen

**Verwante onderwerpen:**

[ krijgen begonnen met toestemmingen ](gs-permissions.md) | [ leiden gebruikerstoestemmingen ](manage-permissions.md) | [ voeg toestemmingen op omslagen ](folder-permissions.md) toe

+++

+++ Hoe kan ik het publiek van mijn berichten selecteren?

De campagne biedt veelvoudige het richten methodes aan om het juiste publiek voor uw berichten te selecteren:

**het richten methodes:**

* **redacteur van de Vraag** - Bouw publiek gebruikend visuele filters op ontvankelijke attributen, gedrag, of demografie
* **Lijsten** - Gebruik vooraf bepaalde statische of dynamische ontvankelijke lijsten
* **de invoer van het Dossier** - upload externe ontvankelijke dossiers voor éénmalige campagnes
* **Werkschema&#39;s** - creeer complexe het richten logica met vraag, spleet, en verrijkingsactiviteiten
* **vooraf bepaalde filters** - pas gebruiksklare filters (actieve klanten, abonnees, VIPs) toe
* **Segmenten van Adobe Experience Platform** - hefboomwerking verenigde profielen en segmenten in real time

U kunt meerdere criteria (locatie, aankoopgeschiedenis, betrokkenheid) combineren en uitsluitingen, snijpunten of samenvoegingen gebruiken om uw publiek te verfijnen.

**Verwante onderwerpen:**

[ bepalen publiek in Campagne v8 ](../audiences/gs-audiences.md) | [ redacteur van de Vraag ](query-editor.md) | [ de afbeeldingen van het Doel ](../audiences/target-mappings.md)

+++

+++ Hoe maak en verzend een eerste e-mail?

Het is eenvoudig om uw eerste e-mailbericht te maken in Campagne v8. U begint met een sjabloon, selecteert het doelpubliek, ontwerpt de inhoud met personalisatie, test deze met proefdrukken en verzendt de inhoud vervolgens. De campagne biedt twee interfaces voor e-mailverwezenlijking aan: de volledig-gekenmerkte **console van de Cliënt** voor gevorderde gebruikers en moderne **UI van het Web van de Campagne** voor sneller, intuïtiever e-mailgebouw.

**5 zeer belangrijke stappen:**

1. **creeer levering** - Begin van een e-mailmalplaatje of creeer van kras
2. **bepaalt publiek** - selecteer ontvangers die vragen, lijsten, of werkschema&#39;s gebruiken
3. **inhoud van het Ontwerp** - gebruik de e-mailontwerper om uw bericht met verpersoonlijkingsgebieden tot stand te brengen
4. **verzendt testproefdrukken** - bevestigt het teruggeven en inhoud over apparaten en e-mailcliënten
5. **analyseert en verzendt** - de leveringsanalyse van de Looppas om fouten te controleren, dan uw e-mail te verzenden

**Verwante onderwerpen:**

[ E-mailontwerp en bevestiging ](../send/email.md) | [ creeer eerste levering ](create-message.md) | [ de malplaatjes van de Levering ](../send/create-templates.md) | [ Personaliseer inhoud ](../send/personalize.md)

+++

+++ Hoe kan ik een foutbericht vertalen?

Een foutbericht wordt weergegeven in een vreemde taal? Alle foutberichten en de vertaling ervan worden weergegeven op [deze pagina](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=nl){target="_blank"}.

+++

+++ Hoe kan ik een probleem registreren?

Om de Steun van de Klant van Adobe te contacteren, verbind met [ Adobe Admin Console ](https://adminconsole.adobe.com/overview){target="_blank"} om een geval tot stand te brengen of een praatjezitting te beginnen.

Vereist afzonderlijke accounts met de juiste machtigingen. Als u zich niet kunt aanmelden, kunt u toegang aanvragen via Experience League. [Meer informatie](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Alternatief, sluit zich aan bij [ Gemeenschap van de Campagne ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} aan onderzoek naar antwoorden of vraag deskundigen.

+++

+++ Met welke systemen en componenten is Campagne v8 compatibel?

U kunt de lijst van alle systemen en componenten krijgen die voor de recentste bouw van Campagne in [ de matrijs van de Verenigbaarheid van Adobe Campaign ](compatibility-matrix.md) worden gesteund.

+++

+++ Kan ik Campaign v8 gebruiken met andere Adobe-oplossingen?

Ja. Campagne v8 kan naadloos worden geïntegreerd met Adobe Experience Cloud-oplossingen voor een uniform ecosysteem voor marketing.

**Zeer belangrijke integratie:** Adobe Experience Platform (verenigde profielen, gegevens in real time), Adobe Analytics (prestatiesmeting), Adobe Target (verpersoonlijking), Adobe Experience Manager (inhoudsbeheer), Adobe Audience Manager (publiekssegmenten).

**Opstelling:** vereist de authentificatie van Adobe IMS, automatisch gevormd voor Campagne v8 Beheerde Diensten van de Wolk.

**Verwante onderwerpen:**

[ de integraties van Adobe Campaign ](../connect/integration.md) | [ verbind met Adobe ID ](connect.md)

+++

+++ Wat zijn de beperkingen van Campaign v8?

Campagne v8 levert aanzienlijke prestatieverbeteringen op, maar heeft enkele architectuurverschillen ten opzichte van Campaign Classic v7, met name in FFDA-implementaties.

**Zeer belangrijke overwegingen:**

* **architectuur FFDA** - gebruikt wolkengegevensbestand (Snowflake) met verschillende patronen van de gegevenstoegang
* **de updates van Gegevens** - zou in werkschema&#39;s, niet via directe gegevensbestandtoegang moeten worden gedaan
* **batch-geoptimaliseerde** - geoptimaliseerd voor partijverrichtingen eerder dan high-frequency individuele updates
* **niet beschikbaar in FFDA** - Enquêtes, het Beheer van het Middel van de Marketing (MRM), sommige specifieke schakelaars

**Effect van de Migratie:** de code van de Douane die het directe gegevensbestand gebruikt schrijft behoeften refactoring; API de integraties kunnen aanpassing voor partijverwerking vereisen.

Deze beperkingen veranderen naarmate Adobe versie 8 verbetert. Raadpleeg de nieuwste documentatie voor de huidige status.

**Verwante onderwerpen:**

[ Campagne v7 aan v8 migratie ](../start/v7-to-v8.md#limitations) | [ architectuur FFDA ](../architecture/enterprise-deployment.md)

+++

+++ Mag ik als Campaign Classic v7-gebruiker migreren naar Campaign v8?

Geautomatiseerde migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.

Campagne v8 is **slechts** beschikbaar als Beheerde Cloud Service, en kan niet op een op-gebouw of hybride milieu&#39;s worden opgesteld.

Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie over het migratieproces.

Leer meer in de [ Campagne v8 vs Vorige versies ](#v7-differences) sectie.

+++


## Upgrades {#upgrades}

Leer hoe u uw versie van de Campagne controleert, het verbeteringsproces begrijpt, en over nieuwe versies op de hoogte blijft. Met Campagne v8 Managed Cloud Services worden upgrades automatisch afgehandeld met minimale onderbreking.

+++ Wat is mijn versie van Campaign?

Controleer uw [versie en buildnummer](upgrades.md#version) in het menu **Help > Info...** van de Campaign-clientconsole.

+++

+++ Hoe kan ik campagne upgraden naar de nieuwste versie?

Adobe Campaign wordt regelmatig bijgewerkt. Kleine versies worden elk jaar uitgebracht met nieuwe functies, verbeteringen en oplossingen. Bovendien brengen wij periodiek versies uit met uitsluitend cumulatieve oplossingen.

Deze regelmatige frequentie van updates is bedoeld om de nieuwste en beste in uw handen te krijgen, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Daarom vinden wij het van essentieel belang dat u de meest recente versie van Adobe Campaign uitvoert.

**Nota:** als Beheerde gebruiker van de Diensten van de Wolk, wordt uw instantie bevorderd door Adobe met nieuwe versies.

Leer meer over [ versies en verbeteringen van de Campagne ](upgrades.md).

+++

+++ Hoe kan ik op de hoogte worden gesteld van de vrijgave van een nieuwe versie?

Houd via de volgende kanalen op de hoogte van nieuwe campagnereleases:

* **vertegenwoordiger van Adobe** - Contacteert u direct wanneer een nieuwe versie beschikbaar is
* **de Nota&#39;s van de Versie** - Alle versies en veranderingen die in [ worden gedocumenteerd de Nota&#39;s van de Versie van de Campagne ](release-notes.md)
* **Updates van het Product van de Prioriteit van Adobe** - [ Abonneren ](https://www.adobe.com/nl/subscription/priority-product-update.html){target="_blank"} voor e-mailberichten
* **Gemeenschap van de Campagne** - sluit zich aan bij [ besprekingen ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} voor vroege updates

Als gebruiker van Managed Cloud Services handelt Adobe upgrades en coördineert de timing met u.

**Verwante onderwerpen:**

[ de Nota&#39;s van de Versie ](release-notes.md) | [ wat nieuw is ](whats-new.md) | [ de versies en verbeteringen van de Campagne ](upgrades.md)

+++

+++ Waarom heeft mijn organisatie een upgrade nodig?

Het upgraden naar de nieuwste versie van Campagne is van essentieel belang voor de beveiliging, de prestaties en de ondersteuningskwaliteit.

**Zeer belangrijke voordelen:**

* **Verbeterde veiligheid** - Bescherming tegen kwetsbaarheid, recentste flarden, verbeterde gegevensbescherming
* **Betere steun** - snellere probleemresolutie, toegang tot insectenmoeilijke situaties, prioritaire steun op recente versies
* **Verbeterde prestaties** - Gegevensbestand en werkschemaoptimalisering, betere scalability, betrouwbaardere verrichtingen
* **Nieuwe mogelijkheden** - de recentste eigenschappen, verbeterde integratie van Adobe Experience Cloud, moderne verhogingen UI

Adobe raadt u ten zeerste aan de meest recente versie uit te voeren. Als klant van Managed Cloud Services worden upgrades uitgevoerd door Adobe met minimale onderbreking.

**Verwante onderwerpen:**

[ de versies en verbeteringen van de Campagne ](upgrades.md) | [ wat nieuw is ](whats-new.md) | [ de matrijs van de Verenigbaarheid ](compatibility-matrix.md)

+++

+++ Wat is het proces en de chronologie voor een verbetering?

Als klant van Managed Cloud Services beheert Adobe het volledige upgradeproces met minimale gevolgen voor uw activiteiten.

**Proces:**

1. **Bericht** - Adobe brengt u weken vooraf op de hoogte
2. **Planning** - de verbetering van het Programma in optimale tijd met uw vertegenwoordiger van Adobe
3. **Voorbereiding** - Adobe bereidt milieu voor en bevestigt
4. **Uitvoering** - de upgrades van Adobe infrastructuur met minimale onderbreking
5. **Bevestiging** - post-verbeterings het testen door Adobe
6. **de consoleverbetering van de Cliënt** - U bevordert uw cliëntconsoles om serverversie aan te passen

**Uw verantwoordelijkheden:**

* Coördinatie van interne belanghebbenden voor timing
* [ de cliëntconsoles van de Verbetering ](connect.md#upgrade-ac-console) aan de nieuwe versie
* Campagnes en workflows testen na upgrade
* Problemen met Adobe-ondersteuning melden

Adobe voert de infrastructuurupgrade uit. U hoeft geen technische handelingen uit te voeren op servers.

**Verwante onderwerpen:**

[ de versies en verbeteringen van de Campagne ](upgrades.md) | [ de cliëntconsole van de Verbetering ](connect.md#upgrade-ac-console) | [ de Nota&#39;s van de Versie ](release-notes.md)

+++


## Campagne v8 versus vorige versies {#v7-differences}

Begrijp de belangrijkste verschillen tussen Campagne v8 en vorige versies (Klassieke v7 en Standaard), met inbegrip van architectuur, plaatsing, migratiewegen, en eigenschapveranderingen. Of je nu uit Campaign Classic v7 of Campaign Standard komt, leer wat nieuw is en hoe je vloeiend kunt overstappen.


+++ Wat zijn de belangrijkste verschillen tussen Campagne v8 en vorige versies?

Campagne v8 is gebaseerd op een moderne cloudnative architectuur met aanzienlijke verbeteringen:

* **Beheerde de Diensten van de Wolk slechts** - volledig die door Adobe (geen op-gebouw/hybride opties) wordt ontvangen
* **Superieure prestaties** - tot 20 miljoen verrichtingen/uur, met de Volledige architectuur van de Toegang van Gegevens Federated (FFDA)
* **Nieuwe UI van het Web van de Campagne** - Moderne, intuïtieve interface naast de klassieke console
* **Automatische verbeteringen** - altijd op de recentste versie met nul onderbreking
* **Verbeterde eigenschappen** - de Medewerker van AI, rijke dupberichten, bevorderd SMS, verbeterde integratie met Adobe Experience Cloud

**voor de gebruikers van Campaign Classic v7:** Leer over [ overgaand van v7 aan v8 ](v7-to-v8.md) met inbegrip van architectuurveranderingen, onbeschikbare eigenschappen, en migratieoverwegingen.

**voor de gebruikers van Campaign Standard:** ontdekt de [ overgangspad aan v8 ](acs-to-v8.md) en [ de migratiegids van Campaign Standard ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

**Verwante onderwerpen:**

[ de belangrijkste mogelijkheden van de Campagne v8 ](whats-new.md) | [ Campagne v8 architectuur ](../architecture/architecture.md) | [ matrijs van de Mogelijkheid ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [ Grafieken en beperkingen ](ac-guardrails.md)

+++

+++ Moet ik migreren van Campaign Classic v7 of Campaign Standard naar v8?

Campagne v8 is een strategisch Adobe-platform dat ideaal is voor organisaties die grootschalige campagnes nodig hebben (20M-bewerkingen per uur), moderne webinterface, cloudnative voordelen en ondersteuning op lange termijn. Eerdere versies zullen de komende jaren het einde van de ondersteuning bereiken.

**Zeer belangrijke voordelen:**

* **voor de gebruikers van Campaign Standard** - het Vertrouwde Web UI, eigenschappariteit (Dynamische Rapportering, REST APIs, het Bestaan van Pagina&#39;s), vlotte gegevensmigratie
* **voor Campaign Classic v7 gebruikers** - Dubbele interface (console + Web UI), betere prestaties, automatische verbeteringen, verbeterde architectuur FFDA

**overweegt migrerend als u:**

* Grote gegevensvolumes verwerken of prestatieproblemen ervaren
* Wil IT-overhead en infrastructuurbeheer verminderen
* Integratie met Adobe Experience Cloud/Platform vereist
* Kies voor toekomstbestendige technologie met automatische updates

**Volgende stappen:** Contacteer uw vertegenwoordiger van Adobe om migratiebereidheid en toegangsmigratiehulpmiddelen te beoordelen.

**Verwante onderwerpen:**

[ van Campaign Classic v7 aan v8 ](v7-to-v8.md) | [ de overgangsgids van Campaign Standard ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [ matrijs van de Mogelijkheid ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

+++

+++ Kan Campagne v8 worden geïnstalleerd op een bedrijfs- of hybride omgeving?

Nee. De campagne v8 is exclusief beschikbaar als a **Beheerde Cloud Service**, volledig die door Adobe wordt ontvangen.

**Zeer belangrijke voordelen van de Beheerde Diensten van de Wolk:**

* Superieure prestaties en schaalbaarheid
* Automatische upgrades - altijd met de nieuwste versie
* Verbeterde beveiliging met continue bewaking
* Geen infrastructuurbeheer of IT-overhead
* Ingebouwde hoge beschikbaarheid en noodherstel

Leer meer over [ de architectuur van de Campagne v8 ](../architecture/architecture.md) en [ verschillen tussen Campagne v8 en Klassieke v7 ](../start/v7-to-v8.md).

+++

+++ Hoe migreer ik mijn Campaign Classic v7 On-Premise of Hybride omgeving naar Adobe Managed Services?

Migratie naar Adobe Managed Services biedt een strategisch pad van &#39;on-premise/hybride&#39; v7 naar de cloud, met verbeterde schaalbaarheid, beveiliging en lagere IT-overhead. Het is vaak een springplank voor de overgang naar Campaign v8.

**Zeer belangrijke punten:**

* Geen geautomatiseerd migratiehulpmiddel beschikbaar - handmatige planning en uitvoering vereist
* Adobe Professional Services-ondersteuning wordt sterk aanbevolen
* Tot de voordelen behoren cloudinfrastructuur, automatische beveiligingspatches, ondersteuning door experts en een eenvoudiger pad naar v8
* De migratie omvat zorgvuldigheid, milieucontrole, gegevenszuivering, werkgebiedmigratie en productiedruk

**Begonnen het worden:** contacteer uw vertegenwoordiger van Adobe om uw milieu te beoordelen en een gedetailleerd migratieplan met Adobe Professional Services te ontwikkelen.

Leer meer over [ migrerend aan Managed Services ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"} met inbegrip van uitdagingen, beste praktijken, en gedetailleerde migratie roadmap.

+++

+++ Wat zijn de belangrijkste terminologie en eigenschapverschillen in Campaign v8?

Campagne v8 biedt de meeste v7/Standard-mogelijkheden met verbeteringen, maar sommige terminologie en functies verschillen. Hieronder vindt u een overzicht van de belangrijkste wijzigingen.

**Zeer belangrijke terminologieveranderingen (Campaign Standard → v8):**

* De middelen van de douane → **Schemas** | Berichten → **Leveringen** | De gebruikers van het product → **Exploitanten**
* De groepen van de veiligheid → **groepen van de Exploitant** | Organisatorische eenheden → **Toestemmingen van de Omslag**

**updates van het Web UI van de Campagne:**

* Ontvangers → **Profielen** | Zaadadressen → **de profielen van de Test** | Leveringsanalyse → **Voorbereiding van de Levering**
* Lijsten → **Soorten publiek** | E-mailvoorproef → **simuleert inhoud**

**niet beschikbaar in v8:**

* On-premise/hybride implementaties (alleen Managed Cloud Services)
* Directe databasetoegang (gebruik-API&#39;s)
* Handmatig infrastructuurbeheer (Adobe beheerd)

**Nieuwe eigenschappen voor de gebruikers van Campaign Standard:**

* Dynamische rapportage, gecentraliseerde branding, REST API&#39;s, verbeteringen in bestemmingspagina&#39;s, visuele fragmenten

**Verwante onderwerpen:**

[ matrijs van de Mogelijkheid ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [ v7 aan v8 overgangsgids ](v7-to-v8.md) | [ Campaign Standard aan v8 overgang ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## Profielen en doelgroepen {#audiences}

Vind antwoorden op vragen over het beheren van profielen, het creëren van publiek, het invoeren van gegevens, en het richten van ontvangers voor uw campagnes.

+++ Hoe te om ontvangers tot stand te brengen?

Handmatig ontvangers maken in de clientconsole voor afzonderlijke profielen, importeren uit bestanden (CSV/TXT) voor bulktoevoegingen, webformulieren gebruiken voor zelfregistratie of integreren via API&#39;s van externe systemen. Gebruik workflows voor importeren voor het terugkeren van gegevens.

**Verwante onderwerpen:**

[ creeer manueel profielen ](../audiences/create-profiles.md) | [ de profielen van de Invoer van een dossier ](../audiences/import-profiles.md) | [ verzamel profielen met Webvormen ](../audiences/collect-profiles.md)

+++

+++ Hoe kan ik profielen importeren?

Campagne biedt meerdere importmethoden: eenvoudige bestandsimporten met de wizard Importeren, op workflow gebaseerde import voor complexe transformaties, terugkerende import met geplande workflows uit SFTP en API-import voor programmatische integratie.

Bereid voor het importeren van bestanden uw gegevensbestand voor (CSV/TXT, UTF-8-codering), gebruik de wizard of workflow voor importeren, wijs kolommen toe aan Campagnevelden, definieer de regels voor bijwerken/invoegen en test eerst met een klein voorbeeld. Gebruik workflows voor terugkerende importbewerkingen en pas deduplicatieregels toe.

**Verwante onderwerpen:**

[ de gegevensgids van de Invoer ](../start/import.md) | [ Terugkerend de invoerwerkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [ het laden van Gegevens activiteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}

+++

+++ Hoe maak ik testprofielen voor mijn leveringen?

De profielen van de test (zaadadressen) laten u ontvangers richten die niet bepaalde het richten criteria aanpassen, toestaand u om uw levering te testen alvorens naar uw belangrijkste publiek te verzenden. Voeg ze via **[!UICONTROL Seed addresses]** toe in de leveringseigenschappen of gebruik de map **[!UICONTROL Seed addresses]** .

Leer meer over [ testprofielen ](../audiences/test-profiles.md).

+++

+++ Hoe kan ik de doelpopulatie van een marketingcampagne definiëren?

De campagne biedt veelvoudige het richten methodes aan: bouwt vragen met visuele criteria, richt bestaande lijsten of segmenten, invoerontvangers uit externe dossiers (CSV, TXT), of pas vooraf bepaalde filters toe. U kunt criteria met logica combineren AND/OR, specifieke populaties uitsluiten, controlegroepen gebruiken, en voor het testen A/B verdelen. Geef altijd een voorvertoning weer van de grootte van de doelpopulatie voordat u deze verzendt.

**Verwante onderwerpen:**

[ bepalen campagnedoelstellingen ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html){target="_blank"} | [ de activiteit van de Vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [ creeer publiek ](../audiences/create-audiences.md)

+++

+++ Hoe kan ik een lijst met profielen maken?

Een lijst is een statische reeks ontvangers die u in leveringen en hergebruik over campagnes kunt richten.

**Drie creatiemethodes:**

* **Handmatige verwezenlijking:** navigeer aan **[!UICONTROL Profiles and Targets > Lists]** en klik **[!UICONTROL Create]**. Voeg ontvangers van een vraag, door individuele selectie, of van een omslag toe.

* **automatisering van het Werkschema:** gebruik de **[!UICONTROL List update]** activiteit om lijsten automatisch van vraagresultaten of ingevoerde gegevens tot stand te brengen en te handhaven.

* **tijdens de invoer:** creeer een lijst wanneer het invoeren van profielen om hen als herbruikbare groep te bewaren.

**Uiteinde:** werkschema&#39;s van het gebruik voor lijsten die regelmatige updates, en handverwezenlijking voor éénmalige segmentatie vereisen.

**Verwante onderwerpen:**

[ creeer publiek ](../audiences/create-audiences.md) | [ de updateactiviteit van de Lijst ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ Hoe kan ik een populatie dedupliceren voordat ik een bericht verstuurt?

Gebruik de **[!UICONTROL Deduplication]** -activiteit in een werkstroom om dubbele ontvangers te verwijderen vóór levering. Plaats de locatie tussen uw **[!UICONTROL Query]** - en **[!UICONTROL Delivery]** -activiteiten en kies vervolgens de deduplicatiecriteria (doorgaans het e-mailadres of de id van de ontvanger) en de record die u wilt bijhouden.

**Uiteinde:** dedupliceer altijd alvorens te verzenden om ervoor te zorgen elke persoon uw bericht slechts eenmaal ontvangt.

Leer meer over de [ activiteit van de Deduplicatie ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}

+++

+++ Hoe te om abonnees aan een nieuwsbrief te identificeren en te richten?

De campagne volgt automatisch nieuwsbrieven abonnementen door informatiediensten. Abonnees activeren:

* Gebruik een **[!UICONTROL Query]** activiteit en filter op **[!UICONTROL Subscriptions]** > om uw nieuwsbrief service te selecteren
* Kies **[!UICONTROL To > Subscribers of an information service]** als u direct vanaf uw levering abonnees wilt activeren
* Abonnementenlijsten samenstellen met de **[!UICONTROL Subscription Services]** -workflowactiviteit

De campagne volgt abonnement/unsubscription geschiedenis en beheert automatisch opt-in/opt-out.

**Verwante onderwerpen:**

[ beheert abonnementen ](../start/subscriptions.md) | [ de activiteit van de Vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ Wat is de beste praktijk om profielen uit te sluiten van een doelpopulatie?

Gebruik de activiteit **[!UICONTROL Exclusion]** in een werkstroom om ongewenste profielen uit uw doel te verwijderen. Plaats het na uw gerichte activiteiten en bepaal welke populatie om uit te sluiten.

Leer meer over de [ activiteit van de Uitsluiting ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Kan ik externe profielen gebruiken zonder deze te importeren in Campagne?

Ja, met Campagne v8 kunt u werken met externe profielen die zijn opgeslagen in een externe database zonder deze te laden in Adobe Campaign. [Meer informatie](../audiences/external-profiles.md).

+++

## Berichtontwerp {#design}

Leer hoe u effectieve marketingberichten kunt ontwerpen in Campaign v8, inclusief e-mailsjablonen, personalisatietechnieken en meertalige inhoud. Ontwerp uw berichten in de cliëntconsole of gebruik moderne **E-mail Designer** in het Web UI van de Campagne voor verbeterde visuele het uitgeven ervaring.

+++ Wat zijn de beste werkwijzen voor het ontwerpen van e-mails in Campagne?

Belangrijke richtlijnen: zorg voor een ontwerp dat reageert op mobiele apparaten, gebruik HTML 4.0/XHTML-compatibele code met inline CSS, optimaliseer afbeeldingen (onder 100 KB) met alternatieve tekst, gebruik velden voor het samenvoegen van personalisatie, test voor alle e-mailclients voordat u het verzendt en voeg een gewone tekstversie toe. Doel voor totale e-mailgrootte van minder dan 500 kB voor optimale prestaties.

[ het ontwerpgids van de E-mail ](../send/email.md) | [ Beste praktijken van de Levering ](delivery-best-practices.md)

+++

+++ Wat is een leveringssjabloon?

Een leveringsmalplaatje is een pre-gevormde levering die alle montages en parameters voor hergebruik over veelvoudige campagnes bewaart. De malplaatjes omvatten doelregels, inhoudsontwerp, verpersoonlijking, technische montages (afzender, antwoord-aan), en typologieregels. Creëer eens en hergebruik om consistentie te behouden en het creëren van campagnes te versnellen.

Leer hoe te [ leveringsmalplaatjes ](../send/create-templates.md) creëren

+++

+++ Kan ik eenvoudig een bestaande HTML importeren om een e-mailbericht te maken in Campagne?

Ja. Importeer HTML-inhoud via directe kopiëren/plakken in de inhoudeditor, upload het bestand vanaf uw computer of laad de inhoud via een URL. Zorg ervoor dat uw HTML e-mailcompatibele code (HTML 4.0/XHTML) met inline CSS gebruikt en dat u afbeeldingen host op een openbare server. De campagne voegt automatisch personalisatie en het volgen aan ingevoerde HTML toe.

**Uiteinde:** voor de beste ervaring van het e-mailontwerp, gebruik **E-mail Designer** in het Web UI van de Campagne, die moderne belemmering-en-dalingsmogelijkheden en ingebouwde ontvankelijke malplaatjes, eerder dan het invoeren van ruwe HTML aanbiedt.

Leer hoe te [ de inhoud van HTML van de Invoer ](../send/defining-the-email-content.md)

+++

+++ Hoe kan ik een nieuwsbrief op abonnementsbasis in Campaign tot stand brengen?

Ja. Gebruik de informatieservices van Campagne om nieuwsbrieven te beheren. De belangrijkste mogelijkheden omvatten automatische opt-in/opt-out behandeling, abonnement volgen, nalevingsbeheer (GDPR, CAN-SPAM), multi-nieuwsbrief steun, Webintegratie voor sign-up vormen, en gerichte levering aan abonnees.

Leer hoe te [ abonnementen ](../start/subscriptions.md) beheren

+++

+++ Hoe kan ik berichten personaliseren?

De campagne biedt verpersoonlijkingsmogelijkheden aan om relevante, gerichte berichten tot stand te brengen die op ontvankelijke gegevens, gedrag, en voorkeur worden gebaseerd.

**de opties van Personalization:**

* **de gebieden van de Personalisatie** - neem ontvankelijke gegevens (b.v., `"Hello {{firstName}}")` op
* **de blokken van de Personalisatie** - Gebruik vooraf bepaalde of blokken van de douaneinhoud
* **Voorwaardelijke inhoud** - de verschillende inhoud van de vertoning die op ontvankelijke criteria wordt gebaseerd
* **gedragsgegevens** - het doorbladeren van hefboomwerkingen geschiedenis, aankooppatronen, of betrokkenheidsmetriek

Test personalisatie alvorens te verzenden om fusievelden en voorwaardelijke logica te verifiëren correct werken.

**Verwante onderwerpen:**

[ de gids van Personalization ](../send/personalize.md) | [ de gebieden van de Personalisatie ](../send/personalization-fields.md) | [ Voorwaardelijke inhoud ](../send/conditions.md)

+++

+++ Hoe kan ik de onderwerpregel van e-mail personaliseren?

Gepersonaliseerde onderwerpreeksen verhogen de openstaande tarieven aanzienlijk. Met campagnes kunt u op dynamische wijze ontvangende gegevens invoegen, voorwaardelijke logica toepassen en variaties testen om betrokkenheid te optimaliseren.

**technieken van Personalization:**

* **Basisgebieden** - Tussenvoegsel eerste naam, lastname, plaats: `"<%@ firstName %>, exclusive offer for you"`
* **Voorwaardelijke inhoud** - Verschillende onderwerpen door segment: `"<% if (recipient.gender == 'F') { %>Special offer just for you<% } else { %>Exclusive deal inside<% } %>"`
* **Dynamische gegevens** - omvat aankoopgeschiedenis, loyaliteitspunten, of rekeningsinfo
* **Emojis** - voeg visueel beroep (test over e-mailcliënten eerst) toe

**Beste praktijken:** houd onder 50 karakters, test verpersoonlijkingstkens alvorens te verzenden, gebruik A/B het testen om te optimaliseren, spamtrekkerwoorden te vermijden, waardevoorstel of urgentie te omvatten.

**Verwante onderwerpen:**

[ de gebieden van de Personalisatie ](../send/personalization-fields.md) | [ Voorwaardelijke inhoud ](../send/conditions.md) | [ het testen A/B ](../send/a-b-testing.md)

+++

+++ Kan ik meertalige berichten versturen?

Ja. De campagne v8 biedt meertalige mogelijkheden, met het **Web UI van de Campagne** die de gemakkelijkste benadering verstrekt. Het Web UI biedt inheemse meertalige levering met taalvarianten-voegt taalvarianten aan uw levering toe, en de Campagne verzendt automatisch de aangewezen die versie op de aangewezen taal van de ontvanger wordt gebaseerd. Beschikbaar voor e-mail-, push-berichten, SMS- en transactieberichten.

Belangrijkste functies: automatische duplicatie van inhoud, automatisch verzenden op basis van taal, standaardtalenfallback en eenvoudig beheer van varianten.

De clientconsole ondersteunt ook meertalige inhoud met behulp van voorwaardelijke inhoud en workflows, maar vereist meer handmatige configuratie.

**Verwante onderwerpen:**

[ Meertalige leveringen (Web UI) ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [ Voorwaardelijke inhoud (de console van de Cliënt) ](../send/conditions.md)

+++

+++ Kan ik een webformulier lokaliseren?

Ja. Campagne voor webtoepassingen ondersteunt meertalige lokalisatie. Definieer vertalingen voor alle formulierelementen (labels, knoppen, berichten, fouttekst) met automatische taaldetectie op basis van het profiel van de ontvanger of de browserinstellingen. Meerdere taalversies worden ondersteund in één webtoepassing, waarbij zo nodig een standaardtaal wordt gebruikt.

Leer meer over [ de toepassingslocalisatie van het Web ](../dev/webapps.md)

+++

+++ Kan ik door AI aangedreven inhoud in mijn e-mails gebruiken?

Ja, maar **slechts door het Web UI van de Campagne**. AI Assistant, aangedreven door Microsoft Azure OpenAI en Adobe Firefly, helpt professionele, merkconsistente inhoud te maken voor e-mail-, SMS- en pushberichten.

**Zeer belangrijke mogelijkheden:**

* Tekst genereren (e-mailkopie, onderwerpregel, SMS/push-inhoud) en afbeeldingen met een merknaam genereren
* Inhoudsvariaties maken die zijn geoptimaliseerd voor verschillende soorten publiek
* Inhoud verfijnen (uitwerken, samenvatten, herformuleren, vereenvoudigen)
* Brontage-elementen uploaden en scoring van branduitlijning ophalen
* Bestaande inhoud gebruiken als verwijzing en stijlreferentieafbeeldingen uploaden

**Nota:** De Medewerker AI is beschikbaar uitsluitend in het Web UI van de Campagne en steunt momenteel slechts Engels. Gebruikers hebben de juiste machtigingen nodig en moeten akkoord gaan met een gebruikersovereenkomst.

**Verwante onderwerpen:**

[ AI Hulpoverzicht ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [ AI Hulpgevallen van het gebruiksgeval ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [ Merk groepering ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Berichten testen en verzenden {#send}

Leer beste praktijken voor het testen, het bevestigen, het verzenden van, en het volgen van uw marketing berichten om succesvolle campagnelevering te verzekeren.

+++ Hoe kan ik de e-mailleverbaarheid verbeteren?

E-maillevering, een essentieel onderdeel van het succes van het marketingprogramma van elke afzender, wordt gekenmerkt door voortdurend veranderende criteria en regels. Voor een effectieve navigatie in deze digitale wereld is een regelmatige afstemming van uw e-mailstrategie vereist, waarbij rekening wordt gehouden met belangrijke ontwikkelingen op het gebied van de leverbaarheid, zodat uw publiek het beste kan bereiken.

Verwijs naar deze gids om [ Aanbevolen Praktijken van de Levering te leren ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}

Leer hoe te om leverbaarheid in Campagne [ in deze gids uit te voeren ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html){target="_blank"}

**Verwante onderwerpen:**

[ worden begonnen met bevrediging ](../send/about-deliverability.md) | [ het berichtinhoud van de Controle ](../send/control-message-content.md) | [ de leverbaarheid van de Monitor ](../send/monitoring-deliverability.md) | [ SpamAssassin ](../send/spamassassin.md)

+++

+++ Hoe kan ik ervoor zorgen dat mijn levering zonder fouten wordt verzonden?

**alvorens te verzenden:** de leveringsanalyse van de Looppas, verzendt testproeven, herziet waarschuwingen, verifieer doeltelling.

**tijdens/na het verzenden:** de leveringsdashboard van de Monitor (verzonden, geleverd, stuiters, fouten), controleleveringslogboeken, spoorsucces/stuittarieven, overzicht quarantined adressen.

**Beste praktijken:** Het alarm van de opstelling, gebruikgolven voor grote volumes, test met kleine volumes eerst, schoon ontvankelijk gegevensbestand regelmatig, de reputatie van de monitor.

**Verwante onderwerpen:**

[ leveringen van de Monitor ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html){target="_blank"} | [ Beste praktijken van de Levering ](delivery-best-practices.md)

+++

+++ Wat is de leveringanalyse?

De analyse van de levering is een looppas van de de bevestigingsfase Campagne alvorens te verzenden. Het berekent de doelpopulatie, valideert inhoud, controleert fouten, past typologische regels toe, en schat leveringsvolume.

Campagne genereert logboeken met waarschuwingen en fouten. Fouten bij blokoplevering en moeten worden gecorrigeerd. Waarschuwingen zijn een advies. Analyselogs altijd controleren voordat ze worden verzonden.

Leer meer in de [ de analysegids van de Levering ](../send/delivery-analysis.md)

+++

+++ Waarom zou ik proefdrukken maken?

Proofs zijn testberichten die uw levering bevestigen alvorens naar uw belangrijkste publiek te verzenden. Gebruik proefdrukken om de personalisatie te controleren, de weergave van inhoud voor verschillende e-mailclients te testen, koppelingen te bevestigen en het werk te volgen, afbeeldingen en bijlagen te controleren en de reactiesnelheid van mobiele apparaten te valideren.

Proefdrukken helpen fouten af te vangen voordat ze duizenden ontvangers bereiken, maken goedkeuring van belanghebbenden en plaatsing van inbox testen mogelijk. Verzend proef naar veelvoudige e-mailcliënten en apparaten, en verkrijg altijd goedkeuring alvorens de productie verzendt.

Leer meer in de [ Proefdrukken en voorproefgids ](../send/preview-and-proof.md)

+++

+++ Hoe te om zaadadressen in Adobe Campaign te gebruiken?

Zaadadressen zijn speciale ontvangers die automatisch aan elke levering voor het testen, de kwaliteitsborging, en controle-zonder het aanpassen van uw doelcriteria worden toegevoegd. Nuttig voor doorlopende bewaking, plaatsingstests in de postbus, directe-mailvalidatie en zichtbaarheid van belanghebbenden.

**Zeer belangrijke verschillen van proeven:**

* **zaadadressen** - die aan productieleveringen automatisch worden toegevoegd, tellen naar verzendt volume
* **Proefdrukken** - de Test verzendt vóór productie, telt niet naar volume, dat voor bevestiging wordt gebruikt

Zaadadressen beheren in **[!UICONTROL Resources > Campaign management > Seed addresses]** . Houd lijsten klein om te voorkomen dat de leveringswaarden worden beïnvloed.

Leer meer in de [ Zaad adresgids ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ Hoe kan ik opstelling een goedkeuringsproces alvorens berichten te verzenden?

De campagne verstrekt goedkeuringswerkschema&#39;s om ervoor te zorgen dat de berichten aan kwaliteitsnormen alvorens verzenden voldoen. Configureer goedkeuringen voor inhoud, doel, extractie (direct mail) en budget op campagne- of leveringsniveau.

**Opstelling:**

Maak in **[!UICONTROL Administration > Access management > Operator groups]** groepen met operatoren en wijs vervolgens goedkeuringsgroepen toe in campagne- of leveringseigenschappen. Tijdens de campagne worden e-mailberichten verzonden naar revisoren die wijzigingen kunnen goedkeuren, afwijzen of aanvragen.

**voor standalone leveringen (niet in een campagne):**

Gebruik **proeven als uw goedkeuringsproces**. Verzend proefdrukken naar uw goedkeuringsgroep voor validatie en verzend altijd een nieuwe proefdruk nadat u wijzigingen hebt aangebracht om ervoor te zorgen dat belanghebbenden de nieuwste versie controleren.

**Verwante onderwerpen:**

[ Bevestiging van de Levering ](../send/preview-and-proof.md) | [ Goedkeuringen van de Campagne ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html){target="_blank"}

+++

+++ Kan ik A/B tests op mijn leveringen in werking stellen?

Ja! Met Campagne kunt u A/B-tests (ook wel gesplitste tests genoemd) uitvoeren om de onderwerpregel, de inhoud, de namen van de afzender te optimaliseren, tijden te verzenden en meer door de prestaties van verschillende varianten te vergelijken.

**wat u kunt testen:**

* **Onderwerplijnen** - vergelijk open tarieven over verschillende onderwerpen
* **variaties van de Inhoud** - test verschillende lay-outs, vraag-aan-actie, of beelden
* **de informatie van de afzender** - de naam van de Afzender van de Test of van adreseffect
* **verzend tijd** - identificeer optimale leveringsvensters
* **strategieën van Personalization** - vergelijk gepersonaliseerde versus generische inhoud

**hoe het werkt:**

1. Uw levering maken en testvarianten definiëren (maximaal 3)
2. Splits uw publiek (doorgaans 10-20% voor testsegmenten)
3. De campagne verzendt varianten naar testsegmenten en volgt prestaties
4. De winnende variant verzendt automatisch naar het resterende publiek (of u selecteert manueel winnaar)

**Beschikbaar in:** zowel UI van het Web van de Campagne als cliëntconsole. De gebruikersinterface van het Web biedt eenvoudigere opstelling met visuele vergelijking.

**Verwante onderwerpen:**

[ A/B testende gids ](../send/a-b-testing.md) | [ Leveringsanalyse ](../send/delivery-analysis.md)

+++

+++ Wat is een typologieregel?

De typologische regels zijn geautomatiseerde bedrijfslogica die tijdens leveringsanalyse wordt toegepast om bericht het verzenden te bevestigen en te optimaliseren. Zij verzekeren naleving van marketing beleid, beschermen leverbaarheid, en verhinderen klantenvermoeidheid.

**Belangrijkste regeltypes:**

* **het Filtreren regels** - sluit (gevoegde op lijst van gewenste personen, unsubscribed, quarantined) ontvangers uit
* **Regels van de Druk** - het berichtfrequentie van de Controle om overweldigende ontvangers te vermijden
* **Regels van de Capaciteit** - het berichtvolume van de Grens voor verwerkingscapaciteit of ISP grenzen
* **Regels van de Controle** - de berichtgeldigheid van de controle (onderwerpregel, unsubscribe verbinding, afzenderformaat)

De regels worden gegroepeerd in typologieën en tijdens leveringsanalyse toegepast. De campagne kan ontvangers uitsluiten, de levering blokkeren, of waarschuwingen produceren die op de regels worden gebaseerd.

Leer meer in de [ gids van de Regels van de Typologie ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html){target="_blank"}

+++

+++ Hoe kan ik e-mails sturen in golven?

Ja. Golf die uw levering verdeelt in veelvoudige partijen verzendt die met geplande intervallen worden verzonden. Dit is essentieel voor groot-volumecampagnes om serverlading in evenwicht te brengen, ISP throttling te verhinderen, afzenderreputatie met nieuwe IPs te bouwen, en opt-outs/grenzen tussen golven te beheren.

**Configuratie:**

In uw leveringseigenschappen, laat golf toe die en bepaalt het aantal golven (of partijgrootte) verzendt, interval tussen golven, en golfdistributie (lineaire of douanepercentages). De campagne verdeelt automatisch uw doelbevolking en verzendt elke golf op programma.

Gebruik golven voor grote campagnes, controleer eerste golfprestaties alvorens verder te gaan, en sta voldoende tijd tussen golven toe om schommelingen en opt-outs te verwerken.

Leer hoe te om [ golf te vormen die ](../send/configure-and-send.md#sending-using-multiple-waves) verzendt

+++

+++ Hoe een levering te plannen?

Met campagnes kunt u leveringen plannen voor toekomstig verzending om verzendtijden te optimaliseren en campagnes te coördineren.

**Plannend opties:**

* **de eigenschappen van de Levering** - verzend onmiddellijk, programma voor specifieke datum/tijd, of vertragen door uren/dagen
* **het niveau van de Campagne** - coördineer alle leveringen binnen een campagne
* **activiteit van de Planner van het Werkschema** - voor terugkomende leveringen, complexe patronen, en gebeurtenis-teweeggebrachte campagnes

De campagne steunt ook optimalisering van de contactdatum (het beste verzendt tijd per ontvanger) en aanpassing van de tijdzone (zelfde lokale tijd voor alle ontvangers).

Leer hoe te [ levering van het Programma verzendend ](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Kan ik een bijlage toevoegen aan e-mails?

Ja. De campagne steunt statische gehechtheid (het zelfde dossier voor alle ontvangers) en gepersonaliseerde gehechtheid (verschillende dossiers per ontvanger die op profielgegevens worden gebaseerd). Voeg bijlagen toe in de sectie **[!UICONTROL Attachments]** van de leveringseigenschappen.

**Belangrijke overwegingen:**

* Bijlagen onder 1 MB houden voor optimale prestaties
* Bijlagen kunnen spamfilters activeren; test grondig alvorens te verzenden
* Bestandstypen die vaak door e-mailclients worden geblokkeerd (.exe, .zip, .js), worden voorkomen
* Gebruik voor grote bestanden liever bijgehouden downloadkoppelingen

Gebruik veilige bestandsindelingen (PDF, JPEG, PNG, DOCX) en test met zaadadressen voordat de productie wordt verzonden.

Leer meer in de [ gids van de Bijlagen E-mail ](../send/email.md#attachments)

+++

+++ Hoe kan ik bijgehouden koppelingen in een e-maillevering configureren?

Met Campagne worden alle URL&#39;s in uw e-mail automatisch omgezet in bijgehouden koppelingen om de betrokkenheid van ontvangers te controleren. Open de sectie **[!UICONTROL Tracking]** in uw levering om het volgen montages voor elke verbinding te vormen.

**de opties van de Configuratie:**

* **laat/maakt het volgen** - Controle het volgen per verbinding toe
* **de etiketten van de Verbinding** - voeg beschrijvende namen voor het melden (b.v., &quot;Shop nu CTA&quot;) toe
* **categorieën van de Verbinding** - de verbindingen van de Groep door type voor bijeengevoegde analyse
* **Volgend type** - het Spoor klikt, opent, of allebei

De campagne volgt inhoudsverbindingen, spiegelt paginakoppelingen, unsubscribe verbindingen, en kan een facultatieve volgende pixel voor e-mail omvatten opent. Gebruik duidelijke labels en categorieën om de rapportage te vereenvoudigen en snel hoogwaardige inhoud te identificeren.

**Verwante onderwerpen:**

[ het volgen van de Verbinding gids ](../start/tracking.md) | [ het Volgen beste praktijken ](../send/send.md)

+++

+++ Waar heb ik toegang tot bezorgings- en trackinglogboeken?

De levering van de toegang en het volgen logboeken van de toegang direct van elk leveringsdashboard. Klik in de clientconsole op de tab **[!UICONTROL Delivery]** onderaan. Navigeer in de interface Campagne Web naar de sectie **[!UICONTROL Logs]** .

**Beschikbare logboeken:**

* **Logboeken van de Levering** - Verzonden berichten met ontvankelijke details en status (verzonden, in afwachting, ontbroken)
* **het Volgen logboeken** - Ontvankelijke interactie (opent, klikt) met timestamps
* **Logboeken van de Uitsluiting** - Uitgesloten ontvangers met redenen (quarantaine, typologische regels, duplicaten)
* **Logboeken van de Uitzending** - Volledige verzendende geschiedenis met inbegrip van pogingen en fouten

Gebruik deze logboeken om leveringskwesties problemen op te lossen, betrokkenheid te analyseren, en lijsthygiëne te handhaven.

**Verwante onderwerpen:**

[ Controle van de Levering ](../send/send.md) | [ het Volgen gids ](../start/tracking.md)

+++

+++ Waar kan ik leveringsrapporten krijgen?

Campagne biedt uitgebreide ingebouwde rapporten om de prestaties van de levering, de betrokkenheid van ontvangers en de doeltreffendheid van de campagne te analyseren. Open rapporten op het tabblad **[!UICONTROL Reports]** in elke levering, vanaf het campagnemashboard of vanuit het algemene **[!UICONTROL Reports]** -menu voor cross-campagneanalyse.

**Zeer belangrijke rapporten omvatten:**

* **Overzicht van de Levering** - verzend statistieken, opent, klikt, stuitingen, en unsubscript
* **Hete kliks** - Visuele heatmap van verbindingsprestaties
* **het Volgen indicatoren** - Doorkliktarieven en betrokkenheidsmetriek
* **Niet-te leveren** - de analyse van de Stuiting met mislukkingsredenen

De rapporten zijn beschikbaar in zowel de cliëntconsole als het Web UI van de Campagne met moderne visualisaties.

**Verwante onderwerpen:**

[ Ingebouwde leveringsrapporten ](../reporting/delivery-reports.md) | [ Campagne die ](../reporting/gs-reporting.md) rapporteert

+++

+++ Hoe kwalificeert en beheert Adobe Campaign quarantaineadressen?

De campagne beheert automatisch een quarantainelijst om uw afzenderreputatie te beschermen en leverbaarheid te verbeteren. Gegarandeerde adressen worden automatisch uitgesloten van toekomstige leveringen totdat ze worden gevalideerd of uit quarantaine worden verwijderd.

**waarom de adressen in quarantaine worden geplaatst:**

* **Harde grenzen** - de Permanente mislukkingen van de levering (ongeldig e-mailadres, domein bestaat niet, geschrapt brievenbus)
* **Zachte stuitdrempel** - Herhaalde tijdelijke mislukkingen (brievenbus volledig, server tijdelijk niet beschikbaar) die de foutendrempel overschrijden
* **Spam klachten** - Ontvangers die uw e-mails als spam merken
* **Ongeldige adressen** - Adressen met syntaxisfouten of die bevestiging ontbreken
* **Gevoegd op lijst van gewenste personen** - Ontvangers die verkozen of verzocht om worden uitgesloten

**Hoe quarantaine werkt:**

De campagne volgt leveringsfouten voor elk adres. Wanneer een adres de gevormde foutendrempel bereikt, is het automatisch quarantined en uitgesloten van alle toekomstige leveringen tijdens analyse. Harde grenzen (permanente storingen) worden onmiddellijk in quarantaine geplaatst, terwijl zachte grenzen meerdere storingen vereisen voordat ze in quarantaine worden geplaatst.

**het Leiden quarantined adressen:**

Open quarantainebeheer in **[!UICONTROL Administration > Campaign Management > Non deliverables Management]** . U kunt quarantined adressen bekijken, manueel bevestigde adressen uit quarantaine verwijderen, of automatische schoonmaakbeurtregels vormen.

**Uiteinde:** controleer regelmatig uw quarantainelijst. Het verhogen van quarantainetarieven signaleert vaak de kwaliteitskwesties van gegevens die aandacht nodig hebben alvorens zij afzenderreputatie beïnvloeden.

**Verwante onderwerpen:**

[ het beheersgids van de quarantaine ](../send/quarantines.md) | [ Stuitbeheer ](../send/delivery-failures.md)

+++

## Workflows {#workflows}

Ontdek hoe u workflows kunt gebruiken om processen te automatiseren, gegevens te beheren en complexe marketingcampagnes in Adobe Campaign te organiseren.

+++ Wat is een workflow?

Adobe Campaign bevat workflows om het volledige scala aan processen en taken in de verschillende modules van de applicatieserver te orkestreren. Met deze uitgebreide grafische omgeving kunt u processen ontwerpen, zoals segmentatie, uitvoering van campagnes, bestandsverwerking, menselijke participatie, enzovoort. Deze processen worden uitgevoerd en bijgehouden door de workflowengine.

U kunt bijvoorbeeld een workflow gebruiken om een bestand van een server te downloaden, het te decomprimeren en vervolgens records in de Adobe Campaign-database te importeren.

Een workflow kan ook een of meer operatoren omvatten die op de hoogte moeten worden gebracht of die keuzes kunnen maken en processen kunnen goedkeuren. Op deze manier is het mogelijk om een leveringsactie te maken, een taak toe te wijzen aan een of meer operatoren om aan content te werken, doelen op te geven en proeven goed te keuren voordat de levering wordt gestart.

[ leer meer ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html){target="_blank"} over werkschema&#39;s. U kunt ook [de best practices voor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} lezen.

**Verwante onderwerpen:**

[ worden begonnen met werkschema&#39;s ](../config/workflows.md) | [ bouwt uw eerste werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [ het gebruiksgevallen van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [ de werkschemauitvoering van de Monitor ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

+++ Kan ik de uitvoering van de workflow controleren?

Ja. De campagne biedt meerdere controlemiddelen: werkstroomdashboard (real-time status en fouten), werkstroomlogboeken (gedetailleerde uitvoeringslogboeken), heatmap (activiteiten en knelpunten visualiseren), audittrail (spoorwijzigingen) en waarschuwingen (meldingen voor fouten).

Om te controleren, open het werkschema en klik de **Logboeken** tabel. Mislukte activiteiten worden rood weergegeven.

**Verwante onderwerpen:**

[ de werkschemauitvoering van de Monitor ](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [ Beste praktijken van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

+++

+++ Wat zijn de belangrijkste stappen om een workflow te maken?

Maak workflows om marketingprocessen in de campagne te automatiseren:

1. **creeer een nieuw werkschema** - ga aan **[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]** of **[!UICONTROL Administration > Production > Technical workflows]** en klik **[!UICONTROL Create]**
1. **voegt activiteiten** toe - de activiteiten van de belemmering en van de daling van het palet (richten, debietcontrole, actieactiviteiten)
1. **vorm activiteiten** - klik elke activiteit tweemaal om parameters te plaatsen en logica te bepalen
1. **verbindt activiteiten** - de activiteiten van de verbinding met overgangen om de uitvoeringsstroom te bepalen
1. **Test en bevestigt** - gebruik het werkschemadiagram om logica te controleren, dan test met een kleine dataset
1. **Uitvoeren** - Begin manueel het werkschema of programma het voor automatische uitvoering

Veelvoorkomende workflowpatronen: gegevensimport, publiekssegmentatie, verzending van gegevens, gegevensverrijking en kanaaloverschrijdende orchestratie.

**Verwante onderwerpen:**

[ bouwt een werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [ de activiteiten van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [ Beste praktijken van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [ het gebruiksgevallen van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Hoe kan ik terugkerende campagnes automatiseren?

De werkschema&#39;s van het gebruik met de **Planner** activiteit om campagnes te automatiseren die op regelmatig programma-dagelijks, wekelijks, maandelijks, of douaneintervallen lopen. Ideaal voor welkomstberichten, verjaardagsberichten, nieuwsbrief die wordt verzonden, verlaten winkelwagentjes en regelmatige rapportage.

**patroon van de Opstelling:**

1. **Planner** - bepaal frequentie (b.v., &quot;Elke Maandag bij 9 AM&quot;)
2. **Vraag** - selecteer doelpubliek met dynamische criteria
3. **Verrijking** (facultatief) - voeg verpersoonlijkingsgegevens toe
4. **Levering** - vorm uw bericht (e-mail, SMS, duw)
5. **Eind** - Het werkschema voltooit en wacht op volgende geplande looppas

**Gemeenschappelijke geautomatiseerde campagnes:**

* **Welkome reeksen** - Dagelijkse werkschema om aan boord komende e-mails naar nieuwe abonnees te verzenden
* **Verjaardag e-mails** - Dagelijkse controle voor ontvangers met verjaardagen, verzend gepersonaliseerd bericht
* **re-engagement** - Wekelijks het richten van inactieve gebruikers met win-back aanbiedingen
* **Nieuwsbrieven** - Geplande wekelijkse of maandelijkse inhoudsdistributie
* **Verlaten van de kunst** - Het werkschema van de Uur om karretjes te identificeren en te berichten verlaten

**Uiteinde:** Gebruik **terugkomende levering** type in werkschema&#39;s om elke uitvoering afzonderlijk te volgen en historische rapportering te handhaven.

**Verwante onderwerpen:**

[ de activiteit van de Planner ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html){target="_blank"} | [ Terugkomende leveringen ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/sending-a-birthday-email.html){target="_blank"} | [ automatisering van de Campagne ](https://experienceleague.adobe.com/docs/campaign/automation/home.html){target="_blank"}

+++

+++ Hoe kan ik gegevens importeren in Campagne?

**Methoden:** de tovenaar van de Invoer (eenmalige CSV/TXT), op werkschema-gebaseerde invoer (**[!UICONTROL Data loading (file)]** activiteit voor complexe/terugkomende invoer met transformaties), REST APIs (programmatic/real-time synchronisatie).

**Beste praktijken:** Test met kleine steekproeven, gebruik UTF-8 codering, kaartgebieden correct, pas deduplicatie toe, programma grote invoer buiten piek.

**Verwante onderwerpen:**

[ de beste praktijken van de Invoer ](../start/import.md) | [ het laden van Gegevens activiteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [ Terugkerend de invoerwerkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ Hoe kan ik de kwaliteit van de gegevens tijdens de import garanderen?

Gegevenskwaliteit is essentieel voor een geslaagde uitvoering van de campagne. De slechte gegevens leiden tot leveringsmislukkingen, verspilde middelen, en nalevingsrisico&#39;s. Campagne biedt gereedschappen voor het valideren, opschonen en verrijken van gegevens tijdens het importproces.

**de bevestigingsstappen van Gegevens:**

1. **pre-invoerbevestiging** - verifieer dossierformaat, het coderen (UTF-8), kolomafbeelding, vereiste aanwezige gebieden
2. **Deduplicatie** - Gebruik **[!UICONTROL Deduplication]** activiteit om duplicaten door e-mail, identiteitskaart, of douanetoetsen te identificeren en te behandelen
3. **de verrijking van Gegevens** - Gebruik **[!UICONTROL Enrichment]** activiteit om ontbrekende gegevens van bestaande lijsten van de Campagne toe te voegen
4. **Normalisatie van het Formaat** - normaliseer telefoonaantallen, e-mailadressen, data, landcodes gebruikend JavaScript of verrijking
5. **de regels van de Bevestiging** - pas beperkingen (geldig e-mailformaat, verplichte gebieden, waardewaaiers toe)

**Gemeenschappelijke kwesties en moeilijke situaties:**

* **het coderen van het Karakter fouten** → Gebruik altijd het coderen UTF-8
* **de formaatwanverhoudingen van de Datum** → Standaardiseren aan formaat JJJJ-MM-DD
* **Ongeldige e-mailadressen** → De bevestigingsregels van het Gebruik of JavaScript om te filtreren
* **Dubbele verslagen** → omvat altijd deduplicatieactiviteit alvorens updates
* **Ontbrekende vereiste gebieden** → Plaats standaardwaarden of verwerp onvolledige verslagen

**Beste praktijken:** creeer een herbruikbare het werkschemamalplaatje van de &quot;gegevenskwaliteit&quot;met standaardbevestiging en schoonmaakactiviteiten die u op alle invoer kunt toepassen.

**Verwante onderwerpen:**

[ de kwaliteitsgids van Gegevens ](../start/import.md) | [ Deduplicatieactiviteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"} | [ de activiteit van de Verrijking ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ Wat zijn algemene voorbeelden van workflowgebruik in Campagne?

Workflows automatiseren marketingprocessen, waaronder:

**het beheer van Gegevens:** Invoer/ladingsgegevens, zuiverend, verrijking, lijstbeheer\
**de automatisering van de Campagne:** Welkome reeksen, verjaardagscampagnes, re-engagement, wortelbeëindiging\
**Geavanceerd het richten:** het testen A/B, dynamische segmentatie, lood het scoren, dwars-kanaalorkest\
**Controle:** Werkschema/levering controle, alarm, gegevensbestandonderhoud\
**Integratie:** synchronisatie CRM, API integratie, gebeurtenis-teweeggebrachte werkschema&#39;s

**Verwante onderwerpen:**

[ het gebruikscasebibliotheek van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [ Bouw een werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [ Beste praktijken van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

+++

+++ Hoe kan ik Campagnegegevens bijwerken met een workflow?

Gebruik **[!UICONTROL Update data]** -activiteit voor bulkdatabasebewerkingen: invoegen (nieuwe records toevoegen), bijwerken (bestaande wijzigingen aanbrengen), invoegen of bijwerken (upsert), verwijderen (overeenkomende records verwijderen).

**gemeenschappelijk gebruik:** de profielattributen van de Update, synchroniseren met externe systemen, handhaven lijstlidmaatschap, schone/dedupliceren gegevens, passen bulkstatusveranderingen toe.

Configureer de afstemmingssleutels voor nauwkeurige afstemming en kies updateopties.

**Verwante onderwerpen:**

[ de gegevensactiviteit van de Update ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"} | [ de beheersactiviteiten van Gegevens ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Hoe kan ik mogelijkheden voor gegevensbeheer benutten?

De activiteiten van het gegevensbeheer laten verfijnde verrichtingen toe: Verrijking (voeg gegevens van verwante lijsten toe), Splitsen (segmentpopulaties), Deduplicatie (verwijder duplicaten), Update data (bulkverrichtingen), Veranderingsdimensie (schakelaar richtend dimensies), Intersection/Union/Exclusion (combinatie/filterpopulaties).

**gemeenschappelijk gebruik:** verrijkt met aankoop/gedragsgegevens, segmentpubliek, verwijder duplicaten, integreer externe gegevensbestanden (FDA), creeer complexe multi-table vragen.

**Verwante onderwerpen:**

[ de beheersactiviteiten van Gegevens ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [ de activiteit van de Verrijking ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ Kan ik het verzenden van persoonlijke berichten automatiseren?

Ja. Geautomatiseerde workflows maken: query (doelgroep) → Verrijking (verrijking toevoegen) → Splitsen (optionele segmenten) → Aflevering (gepersonaliseerde berichten) → Planner (terugkerende uitvoering).

**Personalization:** de profielgegevens van het Gebruik, gedragsgegevens, voorwaardelijke inhoud, dynamische waarden. Veelvoorkomende scenario&#39;s: verjaardagscampagnes, het verlaten van het winkelwagentje, loyaliteitsprogramma&#39;s, win-back, gebeurtenisgestuurde berichten.

**Verwante onderwerpen:**

[ de gids van Personalization ](../send/personalize.md) | [ het gebruikscase van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"}

+++

+++ Hoe kan ik een publiek in subsets splitsen met een workflow?

Gebruik **[!UICONTROL Split]** -activiteit om populaties te verdelen: filteromstandigheden (leeftijd, locatie, VIP-status), procentuele distributie (A/B-tests), limietrecords (eerste N, bovenste X%), gegevensgroepering (één subset per waarde).

**gemeenschappelijk gebruik:** het testen A/B, kanaalvoorkeur die, progressieve uitrol, segmentspecifiek overseinen, lading het in evenwicht brengen verplettert. Elke subset stroomt naar een aparte overgang voor verschillende verwerking.

**Verwante onderwerpen:**

[ Gesplitste activiteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"} | [ A/B testende gids ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Hoe kan ik ontvangergegevens bijwerken uit een extern bestand?

Ja. Workflow: gegevens laden (bestand) → Verrijking (optioneel) → Afstemming (sleutels zoals e-mail/id) → Gegevens bijwerken (records bijwerken komen overeen, nieuwe invoegen indien geen overeenkomst is).

**gemeenschappelijk gebruik:** de profielattributen van de Update van CRM, vernieuw abonnementstatussen, synchroniseer loyaliteitspunten, update opt-in/opt-out voorkeur.

**Beste praktijken:** Gebruik unieke herkenningstekens, bevestig eerst gegevens, test met steekproeven, programma regelmatige updates.

**Verwante onderwerpen:**

[ de gegevensgids van de Invoer ](../start/import.md) | [ het laden van Gegevens activiteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [ de gegevensactiviteit van de Update ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

+++

+++ Hoe kan ik nieuwe ontvangers identificeren en richten?

Vraag **[!UICONTROL Created date]** veld om ontvangers te selecteren die binnen specifieke tijdlijn zijn toegevoegd.

**Geautomatiseerde welkomstwerkschema:** Planner (looppas dagelijks) → Vraag (uitgezochte nieuwe ontvangers) → Deduplicatie (facultatief) → Levering (welkomstbericht) → Update gegevens (merk zoals &quot;verwelkomd&quot;).

**Geavanceerd:** gebruik samengevoegde functies om recente toevoegingen dynamisch te identificeren.

**Verwante onderwerpen:**

[ activiteit van de Vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [ Gebruikend aggregaten ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}

+++

+++ Hoe gebruik ik workflowactiviteiten?

Vier activiteitscategorieën:

**gericht:** Vraag, Splitst, Deduplicatie, Verrijking, Intersection, Vereniging, Uitsluiting (bepaal/verfijnen publiek)\
**controle van de Stroom:** de Planner, wacht, Test, vork, EN-sluit zich aan, OF-sluit zich aan, (beheer logica/timing)\
**Actie:** Levering, Gegevens van de Update, het laden/de extractie van Gegevens, de code van JavaScript (voer verrichtingen uit)\
**Gebeurtenis:** Extern signaal, de inzamelaar van het Dossier, de overdracht van HTTP (op trekkers reageert)

Sleep vanuit het palet en dubbelklik om te configureren, verbinding te maken met overgangen.

**Verwante onderwerpen:**

[ het richten activiteiten ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [ controle van de Stroom ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [ de activiteiten van de Actie ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}

+++

+++ Wat zijn best practices voor workflows?

**Ontwerp:** Duidelijke namen, voeg etiketten/beschrijvingen, groep verwante activiteiten toe, onderbreek complexe processen in kleinere werkschema&#39;s\
**Prestaties:** de vraaggrootte van de grens, gebruik tijdelijke lijsten, programma off-peak, vermijd bovenmatige lijnen\
**de behandeling van de Fout:** voeg foutenwegen toe, vorm alarm, test met steekproeven, overzichtslogboeken\
**Onderhoud:** de verouderde werkschema&#39;s van het Archief, versiecontrole, beperk ingewikkeldheid (&lt;20 activiteiten), gebruiksmalplaatjes\
**Veiligheid:** pas toestemmingen toe, schoon tijdelijke gegevens, gebruikvariabelen niet hard - gecodeerde waarden

**Verwante onderwerpen:**

[ de beste praktijken van het Werkschema gids ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [ werkschema&#39;s van de Monitor ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

## Campagne-instellingen {#settings}

Vorm uw instantie van de Campagne met de juiste montages, de integratie, en de configuraties om uw marketing verrichtingen te optimaliseren.

+++ Kan ik de taal van de interface van de Campagne veranderen?

Het hangt van welke interface af u gebruikt. De **taal van de cliëntconsole** is vast, maar het **Web UI van de Campagne** staat individuele gebruikers toe om hun taalvoorkeur te veranderen.

**Console van de Cliënt (de Toepassing van de Desktop):**

* Taal wordt ingesteld wanneer de instantie wordt gemaakt en kan niet worden gewijzigd
* De clientconsole en server moeten dezelfde taal gebruiken
* Elke Campagne-instantie werkt in één taal
* Voor installaties in het Engels kunt u kiezen tussen Engels (Engels) of Engels (Engels) in de VS (notatie voor datum en tijd verschilt)

**UI van het Web van de Campagne:**

* Gebruikers kunnen hun interfacetaal onafhankelijk wijzigen via hun profielvoorkeuren
* Meerdere talen worden ondersteund met landspecifieke notatie voor datums, tijden en getallen
* Uw de taalvoorkeur van het Web UI is onafhankelijk van uw server van de Campagne en de taal van de cliëntconsole


**Verwante onderwerpen:**

[ taal van de Verandering in het Web UI van de Campagne ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [ krijgen begonnen met de cliëntconsole van de Campagne ](connect.md)

+++

+++ Wat is het Controlebord van de Campagne en hoe heb ik tot het toegang?

Het Controlebord van de campagne is een web-based administratieve interface die de beheerders van de Campagne helpt efficiency verhogen door montages te beheren en gebruik over de instanties van de Campagne te controleren. Het biedt mogelijkheden voor zelfbediening voor het beheer van configuraties met kritieke instanties zonder contact op te nemen met de Adobe-ondersteuning.

**Zeer belangrijke mogelijkheden:**

* **Subdomain beheer** - Afgevaardigde en beheer subdomeinen, controleer SSL certificaten
* **Opslag controle** - het gegevensbestandgebruik van het spoor en verhindert opslagkwesties
* **het beheer van SFTP** - de opslag van SFTP van de Monitor, beheert IP lijsten van gewenste personen, en sleutels SSH
* **montages van de Instantie** - Vorm IP lijsten van gewenste personen, beheer de toestemmingen URL, herzie instantiedetails
* **Actieve profielen die** controleren - spoor actief profielgebruik tegen aanspraken
* **Controle van Prestaties** - het gegevensbestand en werkschemaprestaties van de monitor
* **E-mailleverbaarheid** - vorm DMARC, BIMI, en andere authentificatieverslagen

**vereisten van de Toegang:**

* **slechts Admin gebruikers** - het Controlebord is beperkt tot gebruikers met de rechten van de Beheerder
* **de authentificatie van Adobe IMS** - Toegang door Adobe Experience Cloud met uw Adobe ID
* **Campagne v8 Beheerde Diensten van de Wolk** - Beschikbaar voor ontvangen slechts instanties

**Aanvullende middelen:**

[ documentatie van het Controlebord ](https://experienceleague.adobe.com/en/docs/control-panel/using/control-panel-home){target="_blank"} | [ de zelfstudievideo&#39;s van het Comité van de Controle ](https://experienceleague.adobe.com/en/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ Wat is de procedure voor domeindelegatie?

Een subdomein is een divisie van uw domein die kan worden gebruikt om uw merken of diverse traffictypen (transactieberichten, marketinginformatie, enz.) te isoleren.

>[!NOTE]
>
>Neem als gebruiker van Managed Cloud Services contact op met Adobe om uw subdomeinen te delegeren aan Adobe.

+++

+++ Hoe kan ik het volgen mogelijkheden op mijn instantie van de Campagne plaatsen?

Campagne v8 biedt uitgebreide tracering om de interactie tussen ontvangers en uw berichten te controleren. Voor het bijhouden van gegevens zijn een juiste configuratie van de instantie- en berichtinstellingen vereist.

**wat u kunt volgen:**

* **E-mail opent** - Via het volgen van pixel (1x1 transparant beeld)
* **de Verbinding klikt** - Alle URLs automatisch omgezet in gevolgde verbindingen
* **Unsubscribes** - uit verbinding het volgen
* **spiegel paginameningen** - wanneer de ontvangers de Webversie bekijken
* **Parameters van de Douane** - voeg het volgen gegevens aan URLs voor geavanceerde analyse toe

**Zeer belangrijke configuratiestappen:**

1. URL van trackingsserver configureren in uw instantie-instellingen (beheerd door Adobe voor v8)
2. Tekstspatiëring in leveringseigenschappen inschakelen
3. Tekstspatiëring automatisch instellen voor afzonderlijke koppelingen of alle koppelingen
4. Geldigheidsperiode voor bijhouden en logboekbehoud definiëren

**Beste praktijken:** test altijd het volgen met proeven alvorens naar uw belangrijkste publiek te verzenden om het werk van verbindingen te verzekeren correct en het gegeven wordt gevangen.

**Verwante onderwerpen:**

[ Spoor en controleer leveranties ](tracking.md) | [ vorm getraceerde verbindingen ](../send/email.md)

+++

+++ Hoe te om e-mailleverbaarheid te vormen?

De e-mailleverbaarheid is afhankelijk van de technische configuratie, de kwaliteit van de inhoud en de reputatie van de afzender. Campagne v8 biedt gereedschappen en instellingen om plaatsing in het Postvak IN te optimaliseren.

**Essentiële configuratiestappen:**

* **authentificatie van het Domein** - Opstelling SPF, DKIM, en de verslagen van DMARC om uw verzendend domein te verifiëren
* **opwarming IP** - verhoog geleidelijk verzendend volume op nieuwe IPs om reputatie te bouwen
* **de configuratie van de afzender** - Gebruik verenigbare, herkenbare afzenderadressen en namen
* **stuitbeheer** - vorm quarantaineregels om harde en zachte stuiteringen automatisch te behandelen
* **de lijnen van de Terugkoppeling** - de klacht van de opstelling behandelend om spamrapporten te beheren

**Beste praktijken van de Inhoud:**

* E-mails met SpamAssassin testen om de spamscore te controleren
* De juiste verhouding tussen tekst en afbeelding behouden
* Onbewerkte tekst opnemen naast HTML
* Koppeling voor afmelden altijd opgeven
* Vermijd spamtriggerwoorden en buitensporige kapitalisatie

**Controle:** de leverbaarheidsrapporten van de Campagne van het gebruik om stuiterende tarieven, klachtentarieven, en inbox plaatsing te volgen. Voor Campaign v8 biedt Adobe optimalisatie van de prestaties op infrastructuurniveau.

**Verwante onderwerpen:**

[ Ongeveer leverability in Campagne ](../send/about-deliverability.md) | [ Gids van de Beste praktijken van de Levering ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}

+++

+++ Met welke externe databases kan ik een campagne verbinden?

Campagne v8 ondersteunt FDA-verbindingen (Federated Data Access) met grote databasesystemen van ondernemingen (cloud databases, bedrijfsdatabases, data warehouses, big data platforms).

Ondersteunde databaseversies en verbindingsvereisten variëren. Controleer de [ matrijs van de Verenigbaarheid ](compatibility-matrix.md) voor uw versie van de Campagne v8 om steun voor specifieke gegevensbestanden te bevestigen en behoorlijk vergunning te verzekeren voor schakelaars FDA.

Zie [ verbindingen vormen FDA ](../connect/fda.md)

+++

+++ Kan Adobe Campaign integreren met CRM-systemen?

Ja. De campagne verstrekt inheemse schakelaars van CRM voor tweerichtingssynchronisatie met belangrijke systemen van CRM. Hiermee synchroniseert u contactgegevens, leads, accounts, leveringslogbestanden, gegevens voor bijhouden en gegevens over betrokkenheid. Ondersteunt de synchronisatiemodi voor geplande, handmatige en realtime (via API).

De de schakelaarmedewerker van CRM van CRM van het Gebruik van de Campagne aan kaartgebieden, uitgezochte lijsten, en planningssynchronisatie. Controle [ de matrijs van de Verenigbaarheid ](compatibility-matrix.md) voor de gesteunde versies van CRM.

**Verwante onderwerpen:**

[ de schakelaarconfiguratie van CRM ](../connect/crm.md) | [ de activiteiten van CRM van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html){target="_blank"}

+++

+++ Hoe kan ik de cache van de clientconsole wissen?

Als u de cache van de clientconsole wist, worden veel algemene problemen met weergave en functionaliteit opgelost. Het geheime voorgeheugen slaat lokale configuratiedossiers op die soms bedorven of verouderd kunnen worden.

**Wanneer om geheim voorgeheugen te ontruimen:**

* Nieuwe branding-elementen (logo&#39;s, kleuren) worden niet correct weergegeven
* Functies voor exporteren/importeren zijn onverwacht mislukt
* Interface-elementen die niet worden bijgewerkt na configuratiewijzigingen
* Prestatieproblemen of trage reactie op de console
* Na de upgrade naar een nieuwe versie van de clientconsole

**Stappen om geheim voorgeheugen te ontruimen:**

1. De clientconsole van de campagne openen
2. Ga naar het menu **[!UICONTROL File]**
3. Selecteren **[!UICONTROL Clear the local cache...]**
4. De handeling bevestigen wanneer hierom wordt gevraagd
5. De clientconsole opnieuw starten

Leer meer in [ installeer en vorm cliëntconsole ](connect.md)

+++

+++ Kan ik gebruikersinterfacemontages vormen?

Ja. Campagnebeheerders kunnen de gebruikersinterface aanpassen aan de branding van de organisatie en de gebruikerservaring optimaliseren. Configureer instellingen op instantie- of gebruikersniveau.

**wat u kunt aanpassen:**

* **Brandend** - Logo, kleuren, en visuele identiteitselementen
* **Standaardmeningen** - de paginalay-out van het Huis, de zichtbaarheid van de omslagstructuur
* **configuraties van de Lijst** - Standaard kolommen, soortorde, filters in gegevenslijsten
* **Navigatie** - Beschikbare menupunten en kortere weg
* **Regionale montages** - de formaten van de Datum/van de tijd, aantalformaten, tijdstreken
* **Meldingen** - E-mail alarm, in-app berichten, werkschemaleringen

**niveaus van de Configuratie:**

* **Instantie-breed** - is op alle gebruikers van toepassing (vereist beheerderrechten)
* **gebruiker-specifiek** - Individuele voorkeur en persoonlijke montages

**Verwante onderwerpen:**

[ vorm montages UI ](../config/ui-settings.md) | [ de toestemmingen van de Gebruiker ](gs-permissions.md)

+++

+++ Kan ik aangepaste velden en tabellen maken?

Ja. Het flexibele gegevensmodel van de campagne staat u toe om ingebouwde schema&#39;s met douanevelden uit te breiden en volledig nieuwe lijsten te creëren om aan uw specifieke bedrijfsbehoeften te voldoen.

**wat u kunt aanpassen:**

* **voegt gebieden aan bestaande lijsten** toe - breid ontvankelijke lijst met loyaliteitspunten, douanevoorkeur, externe IDs uit
* **creeer nieuwe douanetabellen** - de producten van de opslag, transacties, loyaliteitsrijen, douaneentiteiten
* **bepaalt verhoudingen** - de lijsten van de Verbinding met bestaande lijsten van de Campagne
* **breidt vormen** uit - Update UI aan vertoning en geef douanegebieden uit

**Gemeenschappelijke gebruiksgevallen:**

* Extra profielkenmerken opslaan (levensduur klant, winkel met voorkeur, VIP-status)
* Productcatalogi met aangepaste kenmerken beheren
* Aangepaste gebeurtenissen en interacties bijhouden
* Externe systeem-id&#39;s integreren voor gegevenssynchronisatie
* Bedrijfsspecifieke gegevensmodellen ontwikkelen (detailhandel, financiën, reizen)

**Verwante onderwerpen:**

[ breid gegevensmodel ](../dev/extend-schema.md) uit | [ de structuur van het Schema ](../dev/schemas.md) | [ beste praktijken van het gegevensmodel ](../dev/datamodel-best-practices.md)

+++

## Rapportage {#reporting}

Krijg inzicht in de rapporteringsmogelijkheden van de Campagne, met inbegrip van ingebouwde rapporten, douanerapporten, en hulpmiddelen van de gegevensanalyse zoals kubussen.

+++ Hoe kan ik nieuwe rapporten maken?

De campagne biedt veelvoudige rapporteringsopties afhankelijk van uw behoeften en technische deskundigheid aan: ingebouwde rapporten, beschrijvende analyse, douanerapporten in de cliëntconsole, en kubussen.

**het Melden van opties:**

* **Ingebouwde rapporten** - klaar-aan-gebruiklevering, campagne, en het volgen rapporten toegankelijk van het **[!UICONTROL Reports]** lusje
* **Beschrijvende analyse** - Snelle statistische rapporten over om het even welke gegevens met een tovenaar-gedreven interface
* **de rapporten van de Douane** - Geavanceerde die rapporten door technische gebruikers worden gebouwd gebruikend de rapporteringsredacteur
* **Kubussen** - Multidimensionale gegevensexploratie en de analyse van de spillijst

**Belangrijk:** de Campagne wordt ontworpen voor het op de markt brengen van verrichtingen die, niet als gespecialiseerd bedrijfsintelligentiehulpmiddel melden. Voor complexe analytische behoeften kunt u overwegen om te integreren met Adobe Analytics of specifieke BI-platforms.

**Verwante onderwerpen:**

[ worden begonnen met het melden ](../reporting/gs-reporting.md) | [ rapporten UI van het Web van de Campagne ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ Hoe kan ik statistische rapporten over populaties ontwerpen en delen?

Gebruik het beschrijvende analysehulpmiddel van de Campagne om statistische rapporten over om het even welke bevolkingsgegevens snel te produceren. Deze wizardgestuurde functie helpt u distributies, trends en patronen te analyseren zonder technische expertise.

**wat u kunt analyseren:**

* Ontvangende demografische gegevens en uitsplitsingen naar segmenten
* Datums en responspercentages voor de campagneprestaties
* Distributie van profielkenmerken (pagina, locatie, voorkeuren)
* Leveringsstatistieken en betrokkenheidspatronen
* Eigen veldwaarden en gegevenskwaliteitswaarden

**hoe te creëren:** selecteer om het even welk lijst of vraagresultaat → klik met de rechtermuisknop → **[!UICONTROL Actions > Analyze]** → kies analysetype (kwalitatief of kwantitatief) → vorm vertoningsopties → produceer rapport.

**het Delen:** de rapporten van de Uitvoer aan Excel/PDF of sparen hen aan de **[!UICONTROL Reports]** omslag voor teamtoegang met aangewezen toestemmingen.

Leer meer over [ Beschrijvende analyse ](../reporting/built-in-reports.md)

+++

+++ Hoe kan ik geavanceerde rapporten over mijn gegevens ontwerpen?

Gebruik de cliëntconsole om geavanceerde douanerapporten met complexe analysemogelijkheden tot stand te brengen.

In de clientconsole kunt u:

* Complexe rapporten maken met SQL-query&#39;s en aangepaste berekeningen
* Rapporten met meerdere pagina&#39;s maken met grafieken, tabellen en draaitabellen
* Voorwaardelijke opmaak en dynamische inhoud ontwerpen
* Toegang tot het volledige gegevensmodel van de Campagne en externe gegevensbestanden (FDA)

Leer hoe te om [ douanerapporten (cliëntconsole) te creëren ](../reporting/custom-reports.md)

+++

+++ Wat is een kubus en hoe kan ik deze gebruiken voor rapportage?

De kubussen zijn multidimensionele gegevensstructuren die bedrijfsgebruikers toelaten om de gegevens van de Campagne door spillijsten zonder technische vaardigheden te onderzoeken en te analyseren. Beschouw ze als vooraf geconfigureerde gegevensmodellen die complexe rapportage vereenvoudigen. Dit rapporteringshulpmiddel is beschikbaar in zowel de cliëntconsole als het Web UI van de Campagne.

* De technische gebruikers creëren en vormen kubussen die afmetingen (tijd, aardrijkskunde, kanalen) en maatregelen (opent, klikt, opbrengst) bepalen
* Zakelijke gebruikers selecteren een kubus wanneer ze rapporten maken en dimensies slepen en neerzetten om gegevens te verkennen
* Gegevens worden automatisch samengevoegd en berekend op basis van de kubusconfiguratie
* De resultaten kunnen worden weergegeven als draaitabellen, grafieken of worden geëxporteerd naar Excel

Leer hoe te [ gegevens met kubussen ](../reporting/gs-cubes.md) ontdekken

+++

+++ Kan ik een rapport maken van antwoorden op een online enquête?

Ja! De campagne omvat een module van het Onderzoek die u toestaat om online vragenlijsten tot stand te brengen en ingebouwde rapporten over enquêteantwoorden te produceren.

**Belangrijk:** het beheer van het Onderzoek is niet beschikbaar in de plaatsingen van de Onderneming van de Campagne v8 (FFDA). [Meer informatie](../architecture/enterprise-deployment.md).

**mogelijkheden van het Onderzoek:**

* Onlinevragen maken met meerdere pagina&#39;s en vraagtypen
* Reacties verzamelen in de database of lokale variabelen
* Reacties van enquêtes in real time weergeven
* Genereer speciale rapporten over enquêteantwoorden (indeling naar vraag, algemene statistieken)
* Antwoorden van enquêtes naar Excel, PDF of CSV exporteren voor verdere analyse
* De onderzoeksgegevens van het gebruik in het richten van werkschema&#39;s om campagnes te personaliseren

**Geavanceerde analyse:**

* enquêteantwoorden openen op het tabblad **[!UICONTROL Responses]** en gegevens exporteren
* Gebruik **[!UICONTROL Survey responses]** -activiteit in workflows om ontvangers als doel in te stellen op basis van hun antwoorden
* De onderzoeksgegevens van de combinatie met andere gegevens van de Campagne voor segmentatie en verpersoonlijking
* Aangepaste rapporten en kubussen maken voor multidimensionale enquêteanalyse

**Verwante onderwerpen:**

[ worden begonnen met onderzoeken ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [ de rapporten van het Onderzoek ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Hoe kan ik de toegang tot mijn rapporten delen?

De rapportzichtbaarheid beheren via mapmachtigingen en benoemde rechten in Campagne.

**de controlemethodes van de Toegang:**

* {de toestemmingen van de Omslag 0} **- Plaats rapporten in omslagen met aangewezen toegang voor gebruikersgroepen**
* **Genoemde rechten** - wijs rechten toe om, rapporten te bekijken tot stand te brengen of te wijzigen
* **context van de Vertoning** - bepaal waar de rapporten verschijnen (de omslag van Rapporten, campagnelusjes, leveringsschermen)

**Opstelling:** sparen rapport aan specifieke omslag → vorm omslagtoegang voor exploitantgroepen → bepaal rapporteigenschappen en vertoningscontext.

**Verwante onderwerpen:**

[ de rapporten van de Douane ](../reporting/custom-reports.md) | [ de toestemmingen van de Gebruiker ](gs-permissions.md)

+++

+++ Kan ik rapporten in verschillende formaten uitvoeren?

Ja, steunt de Campagne veelvoudige uitvoerformaten voor zowel cliëntconsole als Web UI rapporten, toelatend gemakkelijk het delen met belanghebbenden en integratie met andere hulpmiddelen.

**Beschikbare uitvoerformaten:**

* **Excel (.xlsx)** - Beste voor gegevensmanipulatie, verdere analyse, en spillijsten
* **PDF** - Ideaal voor presentaties, uitvoerende overzichten, en gedrukte rapporten
* **CSV** - Perfect voor gegevensinvoer in andere systemen en de hulpmiddelen van BI
* **OpenDocument (.ods)** - het formaat van het open-bronspreadsheet
* **XML** - voor systeemintegratie en geautomatiseerde verwerking

**hoe te om uit te voeren:**

* **de console van de Cliënt:** Open rapport → klik **[!UICONTROL Export]** knoop → kies formaat → sparen dossier
* **Web UI:** Open dashboard → klik het uitvoerpictogram → Uitgezochte formaat → Download
* **Geautomatiseerde uitvoer:** Plan regelmatige uitvoer gebruikend werkschema&#39;s met uitvoeractiviteiten

**Beste praktijken:**

* Excel gebruiken voor rapporten die analyse en annotaties van belanghebbenden vereisen
* PDF gebruiken voor statische rapporten die naar managers worden verzonden of gearchiveerd voor naleving
* CSV gebruiken voor integratie met gegevensopslagplaatsen of externe analysehulpmiddelen
* Geëxporteerde rapporten testen om de opmaak en gegevensnauwkeurigheid te controleren

**Verwante onderwerpen:**

[ de rapporten van de Douane ](../reporting/custom-reports.md) | [ rapporten UI van het Web van de Campagne ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Ontwikkelaars {#developers}

Toegang tot technische informatie voor ontwikkelaars, waaronder gegevens over gegevensmodellen, schema&#39;s, API&#39;s en aanpassingsmogelijkheden.

+++ Wat is het gegevensmodel van de Campagne?

Het gegevensmodel van de campagne is een schema-gedreven relationele gegevensbestandstructuur die uit ingebouwde lijsten (ontvangers, leveringen, campagnes) bestaat die voor uw bedrijfsbehoeften kunnen worden uitgebreid.

**Zeer belangrijke concepten:** Schema&#39;s (de definities van XML), ingebouwde lijsten, verbindingen (verhoudingen), opsommingen (waardelijsten), uitbreidingen (douanegebieden/lijsten).

**Belangrijkste schema&#39;s:** Ontvanger (`nms:recipient`), Levering (`nms:delivery`), Werkschema (`xtk:workflow`), Campagne (`nms:operation`), het Volgen logboeken.

Kennis van het gegevensmodel is essentieel voor workflows, query&#39;s, schema-extensies en integratie.

**Verwante onderwerpen:**

[ het gegevensmodel van de Campagne ](../dev/datamodel.md) | [ Beste praktijken van het gegevensmodel ](../dev/datamodel-best-practices.md)

+++

+++ Hoe te met de schema&#39;s van de Campagne werken?

De schema&#39;s bepalen de gegevensstructuur van de Campagne in het formaat van XML, die lijststructuur, gebiedseigenschappen, verhoudingen, indexen, en toegangsbeheer specificeren.

**Werkend met schema&#39;s:**

* **Mening:** Toegang via **[!UICONTROL Administration > Configuration > Data schemas]**
* **breid uit:** creeer uitbreidingsschema&#39;s (b.v., `cus:recipient`) om douanevelden toe te voegen zonder kernschema&#39;s te wijzigen
* **creeer:** bouw nieuwe lijsten voor zaken-specifieke gegevens
* **Update:** pas veranderingen via **[!UICONTROL Tools > Advanced > Update database structure]** toe

**Gemeenschappelijk gebruik:** voeg douanegebieden aan ontvankelijke lijst toe, creeer douanetabellen, bepaal verhoudingen, voer zaken-specifieke modellen uit.

**Belangrijk:** wijzig nooit direct ingebouwde schema&#39;s. Gebruik altijd extensieschema&#39;s voor upgradecompatibiliteit.

**Verwante onderwerpen:**

[ worden begonnen met schema&#39;s ](../dev/schemas.md) | [ breid een schema ](../dev/extend-schema.md) uit

+++

+++ Hoe te om een douane ontvankelijke lijst te gebruiken?

Gebruik een douane ontvankelijke lijst wanneer het richten van B2B rekeningen, afzonderlijke abonneegegevens, externe systemen, of multibrand architecturen in plaats van de standaard ontvankelijke lijst.

**Implementatie:** creeer douaneschema met verplichte gebieden (e-mail, primaire sleutel, uitsluitingen) → Vorm doelafbeeldingen → Update leveringsmalplaatjes → Pas werkschema&#39;s/vragen aan.

**Zeer belangrijke overwegingen:** moet vereiste leveringsgebieden omvatten, hebben de werkschema&#39;s/de vormen aanpassing nodig, het testen kritiek vóór productiemigratie.

**Beste praktijken:** breid eerst de standaard ontvankelijke lijst uit. Gebruik alleen aangepaste tabellen wanneer dit echt nodig is vanwege de toegevoegde complexiteit.

**Verwante onderwerpen:**

[ de ontvankelijke lijst van de Douane ](../dev/custom-recipient.md) | [ de afbeeldingen van het Doel ](../audiences/target-mappings.md)

+++

+++ Wat zijn de beste praktijken om vragen in Campagne te bepalen?

De vraagredacteur van de campagne bouwt visueel gegevensbestandvragen zonder SQL, die in werkschemaactiviteiten, levering het richten, lijsten, rapporten, en filters worden gebruikt.

**Beste praktijken:**

* Eenvoudig starten - stapsgewijs samenstellen, elke stap testen
* Filterdimensies gebruiken - hefboomtabelrelaties
* Prestaties optimaliseren - indexvelden met vragen, complexe berekeningen vermijden
* Vooraf gedefinieerde filters opnieuw gebruiken voor consistentie
* Test eerst met kleine monsters
* Complexe query&#39;s voor documenten

**Gemeenschappelijke patronen:** de leveringsopeners van het Doel, vinden inactieve contacten, segment door gedrag, sluiten vorige ontvangers uit.

**Toegang:** **[!UICONTROL Tools > Generic query editor]** voor ad hoc exploratie.

**Verwante onderwerpen:**

[ redacteur van de Vraag ](../start/query-editor.md) | [ de activiteit van de Vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ Hoe kan ik een gegevenspakket importeren?

Importeer pakketten via **[!UICONTROL Tools > Advanced > Import package]** in de clientconsole. De pakketten bevatten de configuraties van de Campagne (schema&#39;s, werkschema&#39;s, typologieën) en gegevens voor het opstellen tussen instanties.

**de types van Pakket:** het pakket van de Gebruiker (douane vormt), het pakket van het Platform (Adobe-Geleverd), het pakket van Gegevens (daadwerkelijke gegevens).

**Beste praktijken:** Test eerst in dev, file alvorens in te voeren, voer uit zelfde/oudere versie uit.

Leer meer in [ Werk met gegevenspakketten ](../dev/packages.md)

+++

+++ Waar vind ik de lijst met API&#39;s voor Campagne v8?

Campagne v8 biedt SOAP API&#39;s (clientconsolebewerkingen), REST API&#39;s (moderne integratie) en JavaScript API&#39;s (workflowscripting).

**gemeenschappelijk gebruik:** integreer met CRM/ERP, automatiseer campagnes, synchroniseer gegevens, bouw controleoplossingen, creeer externe interfaces.

**Toegang:** [ de documentatie van de Campagne v8 API ](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=nl){target="_blank"}

+++


+++ Hoe kan ik workflows controleren vanuit API?

Met campagne-API&#39;s kunt u workflows programmatisch beheren: starten, pauzeren/hervatten, stoppen, querystatus, logbestanden ophalen, de voortgang van de activiteit controleren.

**API eindpunt:** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Bevelen:** `{"method":"start"}`, `{"method":"pause"}`, `{"method":"resume"}`, `{"method":"stop"}`

**de gevallen van het Gebruik:** bouw controledashboards, voer geautomatiseerde alarm, orkesteren van externe planners uit, creeer gebiedsdelen over instanties, produceer douanerapporten.

**Beste praktijken:** combineer API controle met controlespoor voor uitvoerig bestuur.

Zie [ werkschema&#39;s van de Controle via API ](../dev/api/controlling-a-workflow.md)

+++

+++ Hoe kan ik de databasestructuur bijwerken?

Nadat u schema&#39;s hebt gewijzigd (velden toevoegen, tabellen maken, gegevenstypen wijzigen), werkt u de fysieke databasestructuur via **[!UICONTROL Tools > Advanced > Update database structure]** bij om wijzigingen toe te passen.

**wanneer nodig:** Toevoegend gebieden, creërend/uitbreidend lijsten, wijzigend gebiedseigenschappen, toevoegend/verwijderend verbindingen, creërend indexen.

**Belangrijk:** Steun eerst, test in dev, plan onderbreking voor grote veranderingen, coördineer met de steun van Adobe (Beheerde Diensten van de Wolk), merk op sommige veranderingen gegevensverlies kunnen veroorzaken.


**Verwante onderwerpen:**

[ de gegevensbestandstructuur van de Update ](../dev/update-database-structure.md) | [ breid schema ](../dev/extend-schema.md) uit

+++

## Privacy {#privacy}

Begrijp hoe Adobe Campaign u helpt aan privacyverordeningen zoals GDPR en CCPA te voldoen, en de verzoeken van de gegevenssubject te beheren.

+++ Wat zijn de belangrijkste privacyconcepten in Campagne?

De campagne helpt u aan privacyverordeningen (GDPR, CCPA, PDPA, LGPD) door hulpmiddelen te voldoen om de rechten van de gegevenssubject, toestemming, en gegevensbehoud te beheren. Belangrijke concepten zijn onder andere privacyregels, identificatie van persoonsgegevens, rechten van betrokkenen (toegang, verwijdering, meeneembaarheid), toestemmingsbeheer en beleid inzake gegevensbewaring.

Als Datacontrole, bent u verantwoordelijk voor de behandeling van gegevensonderwerpverzoeken, het handhaven van toestemmingsverslagen, en het verzekeren van transparant gegevensgebruik.

Leer meer over [ het beheer van de Privacy ](../start/privacy.md)

+++

+++ Hoe kan ik ervoor zorgen dat privacy wordt nageleefd in Campaign?

Campagne biedt tools voor privacynaleving, maar u bent wettelijk verantwoordelijk. Werk met juridische adviseurs voor uw privacyprogramma.

**Essentiële acties:**

* Opzetten van processen voor de behandeling van verzoeken van betrokkenen (toegang, verwijdering)
* Goedkeuringsbeheer implementeren met tijdstempels en bereik bijhouden
* Koppelingen voor abonnementen opnemen in alle e-mails voor marketingdoeleinden
* Gegevensbronnen controleren en ongebruikte gegevens verwijderen
* Besturingselementen voor minst-bevoorrechte toegang toepassen

De campagne biedt de integratie van de Kern van de Privacy, toestemming het volgen, geautomatiseerde verwijderingswerkschema&#39;s, en controletrails voor naleving aan.

Leer meer over [ het beheer van de Privacy ](../start/privacy.md)

+++

+++ Hoe verzamel en beheer ik de toestemming van de gebruiker in Campagne?

Geldige toestemming vereist actieve, specifieke, geïnformeerde en herroepbare overeenkomst. Gebruikers moeten expliciete actie ondernemen. Er zijn geen vooraf aangevinkte vakjes of stilte nodig als toestemming. Afzonderlijke toestemmingen voor verschillende doeleinden (ontbundeld), geef duidelijke verklaringen, en handhaaf verslagen met timestamps.

**Beste praktijken:** verstrek korrelige opt-in opties, vernieuw periodiek toestemming, maak voorkeurscentra gemakkelijk tot toegang, en kadertoestemming als bouwend vertrouwen.

**Technische implementatie in Campagne:**

Campagne biedt abonnementsservices, voorkeurscentra, vlaggen voor opt-out en velden voor aangepaste machtigingen voor het bijhouden van toestemming.

* Ontvangersschema voor toestemmingsgebieden uitbreiden (datum, type, bron)
* Abonnementsservices maken voor elk type toestemming
* Webformulieren voor voorkeurscentra samenstellen
* Workflows gebruiken om toestemming af te dwingen voor het maken van doelen
* Controlerrails onderhouden

Raadpleeg de juridische adviseur om ervoor te zorgen dat uw implementatie voldoet aan de wettelijke vereisten.

**Verwante onderwerpen:**

[ de diensten van het Abonnement ](../start/subscriptions.md) | [ Privacy en toestemming ](../start/privacy.md#consent-retention-roles) | [ Het beheer van de Privacy ](../start/privacy.md)

+++

+++ Welke gegevens worden geschrapt wanneer ik een schrappingsverzoek verwerkt?

Met Campagne worden automatisch alle gegevens verwijderd die aan een gegevenssubject zijn gekoppeld: logboek voor het profiel van de ontvanger, de levering en het bijhouden van de gegevens, aangepaste gegevens met eigendomsrelaties, abonnementsgeschiedenis en webvolggegevens.

**hoe het werkt:** de Campagne schrapt alle gegevens waar de verbinding aan de ontvanger `integrity="own"` in de schemadefinitie heeft, die het draperen schrapping over verwante lijsten verzekeren.

U kunt schrappingswerkingsgebied aanpassen door verbindingsintegriteit in schema&#39;s te wijzigen, maar raadpleeg eerst juridische adviseur. Verwijderen is permanent en kan niet ongedaan worden gemaakt.

**Verwante onderwerpen:**

[ het beheer van de Privacy ](../start/privacy.md) | [ de verbindingen van het Schema ](../dev/schemas.md)

+++

+++ Heeft het verwijderen van privacy invloed op mijn leveringsrapporten?

Nee. Campagnerapporten zijn gebaseerd op vooraf berekende geaggregeerde metriek (totaal verzonden, geopend, geklikt), niet live query&#39;s op individuele logboeken. Het schrappen van individuele ontvankelijke gegevens verandert geen historische statistische aggregaten.

De algemene leveringsstatistieken en prestatiesmetriek blijven intact, terwijl de individuele het volgen logboeken en de persoonlijke details worden verwijderd. Op deze manier kunt u marketinganalyses bijhouden met inachtneming van de rechten van de betrokkene.

**Verwante onderwerpen:**

[ het beheer van de Privacy ](../start/privacy.md) | [ Rapporten ](../reporting/gs-reporting.md)

+++

+++ Hoe voorkom ik het opnieuw importeren van verwijderde gegevens?

U moet gegevens van alle bronsystemen, niet alleen Campagne schrappen. De gegevens vloeien vaak voort uit externe systemen (CRM, e-commerce, data-entrepots).

**Vereiste acties:** identificeer alle gegevensbronnen, schrap uit bronsystemen, voeg aan uitsluiting/onderdrukking lijsten toe, werk de invoerwerkschema&#39;s bij om schrappingsvlaggen te respecteren, en documenteer het proces.

Als Data Controller bent u verantwoordelijk voor de volledige verwijdering van gegevens in uw gehele technologie-ecosysteem.

**Verwante onderwerpen:**

[ het beheer van de Privacy ](../start/privacy.md) | [ de werkschema&#39;s van de Invoer ](../config/workflows.md)

+++

+++ Kunnen verwijderde gebruikers zich opnieuw aanmelden?

Ja. Personen met gegevens kunnen na verwijdering opnieuw aanmelden. Met Campagne maakt u een volledig nieuwe ontvanger-record zonder koppeling naar eerder verwijderde gegevens. Het profiel begint met een schone lei.

In het audittrail van Campaign worden zowel de gebeurtenis die werd verwijderd als het creëren van nieuwe profielen vastgelegd, waarmee wordt aangetoond dat de nieuwe opt-in-optie werd nageleefd en die na verwijdering vrij werd gegeven.

**Verwante onderwerpen:**

[ het beheer van de Privacy ](../start/privacy.md) | [ Abonnementen ](../start/subscriptions.md)

+++

## Nog steeds hulp nodig? {#get-help}

Kun je niet vinden wat je zoekt? Hier zijn aanvullende bronnen om u te helpen slagen met Adobe Campaign v8.

### Communautaire steun

Maak contact met andere campagnegebruikers en Adobe-experts om kennis te delen en antwoorden te krijgen.

* **[Gemeenschap van Adobe Campaign ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** - stel vragen, deel oplossingen, en verbind met de gemeenschap van de Campagne
* **[Forums van Experience League ](https://experienceleaguecommunities.adobe.com/){target="_blank"}** - doorblader besprekingen over alle producten van Adobe
* **[de Uren van het Communautair Bureau van de Campagne ](https://experienceleague.adobe.com/){target="_blank"}** - sluit zich aan bij levende zittingen met de deskundigen van Adobe

### Documentatie en leren

Toegang tot uitgebreide handleidingen, zelfstudies en trainingsmateriaal.

* **[](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html){target="_blank"} de Zelfstudies van de Campagne - Step-by-step videogidsen en hands-on leerprogramma&#39;s**
* **[wat](whats-new.md)** nieuw is - de Meest recente eigenschappen en mogelijkheden
* **[Nota&#39;s van de Versie](release-notes.md)** - Huidige en vorige versieinformatie
* **[Versies en Verbeteringen](upgrades.md)** - Leer over de versies van de Campagne, verbeteringen, en hoe te om uw versie te controleren

### Technische bronnen

Zoek gedetailleerde technische documentatie en ontwikkelaarsmiddelen.

* **[Campagne APIs ](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=nl){target="_blank"}** - Volledige API verwijzingsdocumentatie
* **[Matrijs van de Verenigbaarheid](compatibility-matrix.md)** - Ondersteunde systemen en versies
* **[Veelgestelde vragen van Versies en van Verbeteringen Veelgestelde vragen](upgrades.md-faq)** - controleer uw versie en leer over verbeteringen

### Ondersteuning en services

Vraag hulp aan het ondersteuningsteam van Adobe en beheer uw exemplaar.

* **[Adobe Admin Console ](https://adminconsole.adobe.com/){target="_blank"}** - de steungevallen van het logboek en leiden gebruikers
* **[de Zorg van de Klant van Adobe ](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - contacteer het ondersteuningsteam
* **[Controlebord ](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl){target="_blank"}** - beheer uw de instantiemontages van de Campagne
* **[Status van het Systeem ](https://status.adobe.com/){target="_blank"}** - de status van de Diensten van Adobe van de Controle

### Training en certificering

Werk uw vaardigheden verder met officiële Adobe-trainings- en certificeringsprogramma&#39;s.

* **[Hulp van Experience League ](https://experienceleague.adobe.com/en/browse/campaign/campaign-v8){target="_blank"}** - de middelen van de Hulp voor Campagne v8 (Web UI en console CLient)
* **[](https://learning.adobe.com/){target="_blank"} de Digitale Lerende Diensten van Adobe** - Officiële instructeur-geleide en zelf-afgepaste cursussen
* **[de Certificatie van Adobe Campaign ](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - bevestigt uw deskundigheid met professionele certificatie
* **[Experience League Lerende Wegen ](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** - Geleide het leren reizen

### Andere nuttige bronnen

* **[de Documentatie van Campaign Classic v7 ](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=nl){target="_blank"}** - Verwijzing voor Klassieke v7 gebruikers
* **[](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"} de Documentatie van het Web UI van de Campagne - Nieuwe gids van de Webinterface**
* **[Beste praktijken van de Levering ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}** - optimaliseer e-maillevering

