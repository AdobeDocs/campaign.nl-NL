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
source-git-commit: ceab90331fab0725962a2a98f338ac3dc31a2588
workflow-type: tm+mt
source-wordcount: '13482'
ht-degree: 4%

---

# Veelgestelde vragen {#faq}

Geniet van snelle antwoorden op de meest voorkomende vragen over Adobe Campaign v8. Of u enkel begonnen bent of het zoeken naar geavanceerde configuratiehulp, zult u antwoorden vinden die door onderwerp hieronder worden georganiseerd.

**Nieuw aan Campagne?** Begin met [&#x200B; Algemene Vragen &#x200B;](#general) en [&#x200B; Zeer belangrijke Concepten &#x200B;](#key-concepts).\
**technische hulp nodig?** Controle [&#x200B; Ontwikkelaars &#x200B;](#developers) en [&#x200B; de Montages van de Campagne &#x200B;](#settings).\
**Kan uw antwoord niet vinden?** Bezoek onze [&#x200B; Communautaire Forums &#x200B;](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} of [&#x200B; contactsteun &#x200B;](#get-help).

**Uiteinde:** Gebruik Ctrl+F (Cmd+F op Mac) om naar specifieke sleutelwoorden op deze pagina te zoeken. Klik op een vraag om het antwoord uit te vouwen.


## Algemene vragen {#general}

Beantwoord de meest voorkomende vragen over Adobe Campaign v8, zoals hoe u verbinding kunt maken, een upgrade kunt uitvoeren en ondersteuning kunt krijgen.

+++ Hoe kan ik verbinding maken met Campaign v8?

U moet de clientconsole van Campagne downloaden en installeren om verbinding te maken met Adobe Campaign. [Meer informatie](connect.md).

De aanvang van de Versie van Campagne v8.6, hebt u toegang tot het **de gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud. Experience Cloud is een geïntegreerde Adobe-reeks met digitale marketingtoepassingen, producten en services.

Leer hoe te met Adobe Experience Cloud te verbinden, en tot de interface van het Web van Adobe Campaign [&#x200B; in deze pagina &#x200B;](campaign-ui.md#ac-web-ui) toegang te hebben. Leer meer in de [&#x200B; gebruikersinterfacedocumentatie van het Web van Adobe Campaign &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Verwante onderwerpen:**

[&#x200B; installeer de cliëntconsole &#x200B;](connect.md) | [&#x200B; Campagne gebruikersinterface &#x200B;](campaign-ui.md) | [&#x200B; de toestemmingen van de Gebruiker &#x200B;](gs-permissions.md)

+++

+++ Hoe kan ik de e-mailleverbaarheid verbeteren?

E-maillevering, een essentieel onderdeel van het succes van het marketingprogramma van elke afzender, wordt gekenmerkt door voortdurend veranderende criteria en regels. Voor een effectieve navigatie in deze digitale wereld is een regelmatige afstemming van uw e-mailstrategie vereist, waarbij rekening wordt gehouden met belangrijke ontwikkelingen op het gebied van de leverbaarheid, zodat uw publiek het beste kan bereiken.

Verwijs naar deze gids om [&#x200B; Aanbevolen Praktijken van de Levering te leren &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}

Leer hoe te om leverbaarheid in Campagne [&#x200B; in deze gids uit te voeren &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=nl-NL){target="_blank"}

**Verwante onderwerpen:**

[&#x200B; worden begonnen met bevrediging &#x200B;](../send/about-deliverability.md) | [&#x200B; het berichtinhoud van de Controle &#x200B;](../send/control-message-content.md) | [&#x200B; de leverbaarheid van de Monitor &#x200B;](../send/monitoring-deliverability.md) | [&#x200B; SpamAssassin &#x200B;](../send/spamassassin.md)

+++

+++ Hoe kan ik ervoor zorgen dat mijn levering zonder fouten wordt verzonden?

Voer de volgende stappen uit om ervoor te zorgen dat de levering succesvol is:

**alvorens te verzenden:**

* Leveringsanalyse uitvoeren om fouten te detecteren (personalisatie ontbreekt, ontvangers zijn ongeldig, problemen met inhoud)
* Testproefdrukken verzenden om rendering en personalisatie te verifiëren
* Waarschuwingen tijdens voorbereiding bekijken
* Aantal doelpopulatie controleren

**tijdens en na het verzenden:**

* Controleer het leveringsdashboard voor statistieken in real time (verzonden, geleverd, grenzen, fouten)
* Leveringslogs controleren op status op berichtniveau
* Traceersuccespercentage, stuitsnelheid en foutberichten
* In quarantaine geplaatste adressen controleren

**Beste praktijken:**

* Waarschuwingen voor foutdrempels instellen
* Golven gebruiken (batchverzending) voor grote volumes
* Test eerst met kleine volumes
* Beheer regelmatig uw database voor ontvangers
* De reputatie van de afzender van de monitor

Leer meer over [&#x200B; controlerende leveringen &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=nl-NL){target="_blank"} en [&#x200B; levering beste praktijken &#x200B;](delivery-best-practices.md).

+++

+++ Kan ik de uitvoering van de workflow controleren?

Ja. De campagne biedt verschillende gereedschappen om de uitvoering van de workflow te controleren:

* **[dashboard van het Werkschema &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}** - de status van de Mening in real time, vooruitgang, en fouten voor elke werkschemaactiviteit
* **[Logboeken van het Werkschema &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** - toegang gedetailleerde uitvoeringslogboeken om kwesties problemen op te lossen
* **[Heatmap &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** - visualiseer werkschemaactiviteit en identificeer prestatiesknelpunten
* **[spoor van de Controle](../reporting/audit-trail.md)** - spoor alle wijzigingen die aan werkschema&#39;s worden aangebracht
* **[Alarm &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** - de berichten van de opstelling voor werkschemamislukkingen of vertragingen

Om een werkschema te controleren, open het en klik de **Logboeken** tabel. Mislukte activiteiten worden rood gemarkeerd en u kunt de foutgegevens weergeven door erop te klikken.

Leer meer over [&#x200B; controle werkschemauitvoering &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} en [&#x200B; werkschemabeste praktijken &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=nl-NL){target="_blank"}.

+++

+++ Hoe kan ik campagne downloaden?

U kunt het installatieprogramma en de clientconsole ophalen vanuit Adobe Download Center.

Als Admin gebruiker, heb toegang tot de Distributie van de Software van Adobe [&#x200B; &#x200B;](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"} om Adobe Campaign te downloaden.

Leer meer over het Centrum van de Distributie [&#x200B; op deze pagina &#x200B;](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=nl-NL){target="_blank"}.

+++

+++ Wat is de procedure voor domeindelegatie?

Een subdomein is een divisie van uw domein die kan worden gebruikt om uw merken of diverse traffictypen (transactieberichten, marketinginformatie, enz.) te isoleren.

>[!NOTE]
>
>Neem als gebruiker van Managed Cloud Services contact op met Adobe om uw subdomeinen te delegeren aan Adobe.

+++

+++ Hoe kan ik een probleem registreren?

U kunt een ticket maken om contact op te nemen met de Adobe-klantenondersteuning voor problemen die u ondervindt in Adobe-producten. In de Adobe Admin Console kunt u chatten met de Adobe-klantenondersteuning om uw problemen op te lossen.

Als u een probleem wilt melden of een chatsessie wilt starten in dat nieuwe systeem, maakt u verbinding met de [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}.

Dit systeem vereist individuele rekeningen voor elke gebruiker, met correcte toestemmingen. Als u zich niet kunt aanmelden met uw Adobe ID, kunt u om toegang vragen via de Experience League. Het klantenserviceteam helpt u dan zo snel mogelijk. [Meer informatie](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Deelnemen aan de Campagne-gemeenschap: zoeken naar antwoorden in bestaande vragen of de experts raadplegen. [Deelnemen aan het gesprek](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

+++

+++ Met welke systemen en componenten is Campagne v8 compatibel?

U kunt de lijst van alle systemen en componenten krijgen die voor de recentste bouw van Campagne in [&#x200B; de matrijs van de Verenigbaarheid van Adobe Campaign &#x200B;](compatibility-matrix.md) worden gesteund.

+++

+++ Kan ik Campaign v8 gebruiken met andere Adobe-oplossingen?

Ja. Campagne v8 kan naadloos worden geïntegreerd met Adobe Experience Cloud-oplossingen om een krachtig, uniform marketingecosysteem te creëren. Als beheerde Cloud Service is v8 ontworpen voor systeemeigen integratie met Adobe-bedrijfstoepassingen.

**Belangrijke beschikbare integratie:**

* **Adobe Experience Platform** - Leverage verenigde klantenprofielen en gegevens in real time
* **Adobe Analytics** - de campagneprestaties en klantengedrag van de maatregel over kanalen
* **Adobe Target** - Personaliseer inhoud die op klantensegmenten en gedrag wordt gebaseerd
* **Adobe Experience Manager** - centraliseer inhoudsverwezenlijking en activabeheer
* **Adobe Audience Manager** - bouw en activeer publiekssegmenten over platforms

**Voordelen:** Verenigde klantengegevens, verenigbare gebruikerservaringen, gestroomlijnde werkschema&#39;s, en verbeterde verpersoonlijkingsmogelijkheden.

**Opstelling:** de integratie met de oplossingen van Adobe vereist de authentificatie van het Systeem van Adobe Identity Management (IMS), automatisch gevormd voor Campagne v8 Beheerde Diensten van de Wolk.

**Verwante onderwerpen:**

[&#x200B; de integraties van Adobe Campaign &#x200B;](../connect/integration.md) | [&#x200B; verbind met Adobe ID &#x200B;](connect.md)

+++

+++ Wat zijn de beperkingen van Campaign v8?

Campagne v8 introduceert architectuurveranderingen (met name in implementaties van FFDA) die significante prestatieverbeteringen maar ook enkele verschillen van Campaign Classic v7 brengen. Als u deze opties begrijpt, kunt u migraties plannen en de juiste verwachtingen instellen.

**Belangrijkste v8 overwegingen:**

* **architectuur FFDA** - de plaatsingen van de Onderneming gebruiken wolkengegevensbestand (Snowflake) met verschillende patronen van de gegevenstoegang
* **de updates van de Eenheid** - de updates van Gegevens zouden in werkschema&#39;s, niet door APIs of directe gegevensbestandtoegang moeten worden gedaan
* **In real time schrijft** - Geoptimaliseerd voor partijverrichtingen eerder dan high-frequency individuele updates
* **Model van Gegevens** - sommige schemaaanpassingen vereisen verschillende benaderingen
* **Externe gegevensbestandtoegang** - FDA (Federated Data Access) configuratie verschilt van v7

**Eigenschappen niet beschikbaar in plaatsingen FFDA:**

* Enquêtes (beschikbaar in standaard v8-implementaties)
* Marketing Resource Management (MRM)
* Bepaalde specifieke verbindingsconfiguraties

**Overwegingen van de Migratie:**

* De code van de douane die het directe gegevensbestand gebruikt schrijft behoeften refactoring
* Voor API-integratie is mogelijk aanpassing voor batchverwerking vereist
* Workflows moeten de beste praktijken van de FFDA voor gegevensbewerkingen volgen
* Testen is essentieel voor het valideren van aangepaste ontwikkelingen

**Belangrijk:** Deze beperkingen evolueren aangezien Adobe v8 blijft verbeteren. Raadpleeg de nieuwste documentatie voor de huidige status en routekaart.

**Verwante onderwerpen:**

[&#x200B; Campagne v7 aan v8 migratie &#x200B;](../start/v7-to-v8.md#limitations) | [&#x200B; architectuur FFDA &#x200B;](../architecture/enterprise-deployment.md)

+++

+++ Mag ik als Campaign Classic v7-gebruiker migreren naar Campaign v8?

Geautomatiseerde migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.

Campagne v8 is **slechts** beschikbaar als Beheerde Cloud Service, en kan niet op een op-gebouw of hybride milieu&#39;s worden opgesteld.

Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie over het migratieproces.

Leer meer in de [&#x200B; Campagne v8 vs Vorige versies &#x200B;](#v7-differences) sectie.

+++

+++ Wat is mijn versie van Campaign?

Controleer uw [versie en buildnummer](upgrades.md#version) in het menu **Help > Info...** van de Campaign-clientconsole.

+++

+++ Hoe kan ik campagne upgraden naar de nieuwste versie?

Adobe Campaign wordt regelmatig bijgewerkt. Kleine versies worden elk jaar uitgebracht met nieuwe functies, verbeteringen en oplossingen. Bovendien brengen wij periodiek versies uit met uitsluitend cumulatieve oplossingen.

Deze regelmatige frequentie van updates is bedoeld om de nieuwste en beste in uw handen te krijgen, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Daarom vinden wij het van essentieel belang dat u de meest recente versie van Adobe Campaign uitvoert.

**Nota:** als Beheerde gebruiker van de Diensten van de Wolk, wordt uw instantie bevorderd door Adobe met nieuwe versies.

Leer meer over [&#x200B; versies en verbeteringen van de Campagne &#x200B;](upgrades.md).

+++

+++ Hoe kan ik op de hoogte worden gesteld van de vrijgave van een nieuwe versie?

Houd via de volgende kanalen op de hoogte van nieuwe campagnereleases:

* **vertegenwoordiger van Adobe** - Contacteert u direct wanneer een nieuwe versie beschikbaar is
* **de Nota&#39;s van de Versie** - Alle versies en veranderingen die in [&#x200B; worden gedocumenteerd de Nota&#39;s van de Versie van de Campagne &#x200B;](release-notes.md)
* **Updates van het Product van de Prioriteit van Adobe** - [&#x200B; Abonneren &#x200B;](https://www.adobe.com/nl/subscription/priority-product-update.html){target="_blank"} voor e-mailberichten
* **Gemeenschap van de Campagne** - sluit zich aan bij [&#x200B; besprekingen &#x200B;](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} voor vroege updates

Als gebruiker van Managed Cloud Services handelt Adobe upgrades en coördineert de timing met u.

**Verwante onderwerpen:**

[&#x200B; de Nota&#39;s van de Versie &#x200B;](release-notes.md) | [&#x200B; wat nieuw is &#x200B;](whats-new.md) | [&#x200B; de versies en verbeteringen van de Campagne &#x200B;](upgrades.md)

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

[&#x200B; de versies en verbeteringen van de Campagne &#x200B;](upgrades.md) | [&#x200B; wat nieuw is &#x200B;](whats-new.md) | [&#x200B; de matrijs van de Verenigbaarheid &#x200B;](compatibility-matrix.md)

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
* [&#x200B; de cliëntconsoles van de Verbetering &#x200B;](connect.md#upgrade-ac-console) aan de nieuwe versie
* Campagnes en workflows testen na upgrade
* Problemen met Adobe-ondersteuning melden

Adobe voert de infrastructuurupgrade uit. U hoeft geen technische handelingen uit te voeren op servers.

**Verwante onderwerpen:**

[&#x200B; de versies en verbeteringen van de Campagne &#x200B;](upgrades.md) | [&#x200B; de cliëntconsole van de Verbetering &#x200B;](connect.md#upgrade-ac-console) | [&#x200B; de Nota&#39;s van de Versie &#x200B;](release-notes.md)

+++


## Belangrijke concepten {#key-concepts}

Leer over de fundamentele concepten van de Campagne met inbegrip van authentificatie, gebruikersinterface, werkschema&#39;s, en kernfuncties effectief beginnen.

+++ Kan ik verbinding maken met Campaign v8 met een Adobe ID?

Ja! Dankzij de integratie met de IMS (Adobe Identity Management System) maken gebruikers via hun Adobe ID verbinding met de Adobe Campaign-console. Deze integratie biedt de volgende voordelen:

* Dezelfde id kan voor alle Experience Cloud-oplossingen worden gebruikt.
* De verbinding wordt onthouden bij het gebruik van Adobe Campaign met verschillende integraties.
* Veiliger beleid voor wachtwoordbeheer.
* Gebruik van Federated ID-accounts (externe id-provider).

[&#x200B; leer meer &#x200B;](connect.md) over de toegang tot van Campagne v8 met een Adobe ID.

+++

+++ Hoe kan ik gebruikersmachtigingen instellen?

Als Campaign-beheerder kunt u machtigingen instellen voor gebruikers van uw organisatie.

Dit zijn een reeks rechten en beperkingen waarbij wordt toegestaan of geweigerd om:

* Toegang tot bepaalde functies
* Toegang tot bepaalde gegevens
* Gegevens maken, wijzigen en/of verwijderen

[&#x200B; leer meer &#x200B;](../start/gs-permissions.md) over gebruikerstoestemmingen in Campagne v8.

**Verwante onderwerpen:**

[&#x200B; krijgen begonnen met toestemmingen &#x200B;](gs-permissions.md) | [&#x200B; leiden gebruikerstoestemmingen &#x200B;](manage-permissions.md) | [&#x200B; voeg toestemmingen op omslagen &#x200B;](folder-permissions.md) toe

+++

+++ Wat zijn de concepten van het gebruikersinterface van de Campagne ik zou moeten weten?

Verwijs naar [&#x200B; deze sectie &#x200B;](campaign-ui.md) om meer over de grondbeginselen van het gebruikersinterface van Adobe Campaign te leren.

Beginnende Versie van Campagne v8.6, hebt u ook toegang tot het nieuwe **de gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud.

[&#x200B; leer meer in de gebruikersinterfacedocumentatie van het Web van Adobe Campaign &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Hoe kan ik het publiek van mijn berichten selecteren?

Met Adobe Campaign kunt u verschillende strategieën gebruiken om doelgroepen te maken en doelontvangers te selecteren.

[&#x200B; leer meer &#x200B;](../audiences/gs-audiences.md) over hoe te om publiek in Campagne v8 te bepalen.

+++

+++ Wat is een workflow?

Adobe Campaign bevat workflows om het volledige scala aan processen en taken in de verschillende modules van de applicatieserver te orkestreren. Met deze uitgebreide grafische omgeving kunt u processen ontwerpen, zoals segmentatie, uitvoering van campagnes, bestandsverwerking, menselijke participatie, enzovoort. Deze processen worden uitgevoerd en bijgehouden door de workflowengine.

U kunt bijvoorbeeld een workflow gebruiken om een bestand van een server te downloaden, het te decomprimeren en vervolgens records in de Adobe Campaign-database te importeren.

Een workflow kan ook een of meer operatoren omvatten die op de hoogte moeten worden gebracht of die keuzes kunnen maken en processen kunnen goedkeuren. Op deze manier is het mogelijk om een leveringsactie te maken, een taak toe te wijzen aan een of meer operatoren om aan content te werken, doelen op te geven en proeven goed te keuren voordat de levering wordt gestart.

[&#x200B; leer meer &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=nl-NL){target="_blank"} over werkschema&#39;s. U kunt ook [de best practices voor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=nl-NL){target="_blank"} lezen.

**Verwante onderwerpen:**

[&#x200B; worden begonnen met werkschema&#39;s &#x200B;](../config/workflows.md) | [&#x200B; bouwt uw eerste werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=nl-NL){target="_blank"} | [&#x200B; het gebruiksgevallen van het Werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [&#x200B; de werkschemauitvoering van de Monitor &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe maak en verzend een eerste e-mail?

Het maken van uw eerste e-mail in Campagne v8 omvat verschillende belangrijke stappen:

1. **creeer de levering** - Begin door een nieuwe e-maillevering van een malplaatje of van kras te creëren
1. **bepaalt het publiek** - selecteer uw doelontvangers gebruikend vragen, lijsten, of werkschema&#39;s
1. **Ontwerp de inhoud** - gebruik de e-mailontwerper om uw bericht met verpersoonlijking tot stand te brengen
1. **Test met proeven** - verzend teste-mails om inhoud en verpersoonlijking te bevestigen
1. **analyseert en verzendt** - de leveringsanalyse van de Looppas om fouten te controleren, dan uw e-mail te verzenden

Campagne v8 biedt twee interfaces voor het maken van e-mail:

* **de console van de Cliënt** - Volledig-gekenmerkte Desktoptoepassing met geavanceerde mogelijkheden
* **UI van het Web van de Campagne** - Moderne, intuïtieve Webinterface voor snellere e-mailverwezenlijking

[&#x200B; Leer meer over e-mailontwerp en bevestiging &#x200B;](../send/email.md) in Campagne v8.

**Verwante onderwerpen:**

[&#x200B; creeer uw eerste levering &#x200B;](create-message.md) | [&#x200B; Werk met leveringsmalplaatjes &#x200B;](../send/create-templates.md) | [&#x200B; Beste praktijken van de Levering &#x200B;](delivery-best-practices.md) | [&#x200B; Bepaal de e-mailinhoud &#x200B;](../send/defining-the-email-content.md) | [&#x200B; Voorproef en proef &#x200B;](../send/preview-and-proof.md) | [&#x200B; vormen en verzenden &#x200B;](../send/configure-and-send.md) | [&#x200B; Personaliseer inhoud &#x200B;](../send/personalize.md)

+++

+++ Hoe je SMS-berichten verzendt?

Voor het verzenden van SMS-berichten met Campagne v8 is eerst een configuratie nodig en daarna volgt u een eenvoudig leveringsproces:

**Aanvankelijke Opstelling (éénmalige configuratie):**

1. **vorm het kanaal van SMS** - opstelling de de leveringsmontages van SMS en externe rekening
1. **vorm verbinding SMPP** - verbind met uw dienstverlener van SMS via protocol SMPP
1. **Test de verbinding** - bevestigt connectiviteit met uw leverancier van SMS
1. **opstelling die** verplettert - bepaalt hoe de berichten van SMS door uw leverancier worden verpletterd

**Creërend en verzendend SMS:**

1. **creeer levering van SMS** - Begin een nieuwe levering van SMS van een malplaatje
1. **bepaal ontvangers** - selecteer uw mobiel publiek gebruikend de gebieden van het telefoonaantal
1. **schrijf de inhoud van SMS** - creeer uw bericht (160 karakters standaard, of langer met aaneenschakeling)
1. **voeg verpersoonlijking** toe - omvat dynamische gebieden specifiek voor elke ontvanger
1. **verzend proef** - de levering van SMS van de Test om inhoud en levering te bevestigen
1. **analyseert en verzendt** - de analyse van de Looppas en verzendt naar uw publiek

**Zeer belangrijke mogelijkheden van SMS:**

* **Veelvoudige schakelaars SMPP** - Steun voor diverse leveranciers van SMS en protocollen
* **de rapporten van de Levering** - Spoor verzonden, geleverde, en ontbroken berichten
* **het coderen van het Karakter** - Steun voor GSM7, Unicode, en speciale karakters
* **Lange steun van SMS** - Automatische berichtaaneenschakeling voor langere teksten
* **bidirectionele SMS** - de Binnenkomende reacties van SMS met werkschema&#39;s behandelen

[&#x200B; leer meer over de configuratie en het verzenden van SMS &#x200B;](../send/sms/sms.md) in Campagne v8.

**Verwante onderwerpen:**

[&#x200B; worden begonnen met SMS &#x200B;](../send/sms/sms.md) | [&#x200B; de leveringsmontages van SMS &#x200B;](../send/sms/sms-delivery-settings.md) | [&#x200B; SMPP externe rekeningsmontages &#x200B;](../send/sms/smpp-external-account.md) | [&#x200B; creeer een levering van SMS &#x200B;](../send/sms/create-sms.md) | [&#x200B; inhoud van SMS &#x200B;](../send/sms/sms-content.md) | [&#x200B; verzend de proef van SMS &#x200B;](../send/sms/sms-proofs.md) | [&#x200B; Monitor SMS &#x200B;](../send/sms/sms-monitor.md)

+++

+++ Hoe kan ik pushmeldingen verzenden?

Als u pushberichten verzendt met Campagne v8, moet u de integratie van uw mobiele app configureren en aantrekkelijke meldingen maken:

**Aanvankelijke Opstelling (éénmalige configuratie):**

1. **vorm duw kanaal** - de montages van het de duw- berichtkanaal van de opstelling in Campagne
1. **integreer de Campagne SDK** - voeg Adobe Campaign SDK aan uw mobiele app (of gebruik de Inzameling van Gegevens) toe
1. **Vorm mobiele app** - registreer uw iOS en Android apps in Campagne
1. **Certificaten van de opstelling** - vorm het certificaat van APNs (iOS) en sleutel FCM (Android)
1. **registratie van de Test** - verifieer apparaten kunnen tokens registreren en ontvangen

**het Creëren en het verzenden van de Duw Meldingen:**

1. **creeer duimlevering** - Begin een nieuw duw bericht van een malplaatje
1. **Uitgezochte platform** - kies iOS, Android, of beide platforms
1. **bepaal publiek** - doel app abonnees die mobiele gegevens van het toepassingsabonnement gebruiken
1. **Bericht van het Ontwerp** - creeer titel, bericht, en rijke media inhoud
1. **vorm gedrag** - plaats klikacties, diepe verbindingen, en douanegegevens
1. **verzendt testberichten** - bevestigt op echte apparaten alvorens te verzenden
1. **analyseert en verzendt** - het Overzicht richtend en verzendt naar uw mobiel publiek

**het berichtmogelijkheden van de duw:**

* **rijke dupberichten** - omvat beelden, video&#39;s, en interactieve knopen (iOS en Android)
* **Personalization** - Dynamische inhoud die op gebruikersprofiel en gedrag wordt gebaseerd
* **Deep die** verbindt - directe gebruikers aan specifieke toepassingsschermen of inhoud
* **Plannend** - verzend op optimale tijden die op gebruikerstimezone worden gebaseerd
* **het testen A/B** - test verschillende berichten en optimaliseer overeenkomst
* **het Volgen** - de Monitor opent, klikt, en omzettingen

**Platform-specifieke eigenschappen:**

* **iOS** - de Stille berichten, berichtcategorieën, correcte aanpassing
* **Android** - de rijke duw malplaatjes, berichtkanalen, douanelay-outs

[&#x200B; Leer meer over de configuratie van het dupbericht &#x200B;](../send/push-settings.md) in Campagne v8.

**Verwante onderwerpen:**

[&#x200B; creeer en verzend dupberichten &#x200B;](../send/push.md) | [&#x200B; vorm duw berichtkanaal &#x200B;](../send/push-settings.md) | [&#x200B; Ontwerp een rijke duw van Android &#x200B;](../send/rich-push-android.md) | [&#x200B; Ontwerp een rijke duw van iOS &#x200B;](../send/rich-push-ios.md) | [&#x200B; vormt met de Inzameling van Gegevens &#x200B;](../send/push-data-collection.md) | [&#x200B; Spoor en monitor &#x200B;](tracking.md)

+++

+++ Hoe maak je een landingspagina?

U kunt de digitale inhoudeditor van Adobe Campaign gebruiken om bestemmingspagina&#39;s te ontwerpen en toewijzingen te definiëren met databasevelden.

[&#x200B; leer meer &#x200B;](../dev/landing-pages.md) in de documentatie van de Campagne v8.

U kunt het de gebruikersinterface van het Web van de Campagne ook gebruiken om het landen pagina&#39;s tot stand te brengen en te publiceren - [&#x200B; leer meer &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ Hoe kan ik leveringen volgen?

U kunt leveringen volgen die met Campagne v8 door specifieke [&#x200B; leveringsrapporten &#x200B;](../reporting/delivery-reports.md) worden verzonden en dan uw leveringen controleren.

Leer meer over het volgen beheer in Campagne [&#x200B; in deze pagina &#x200B;](../start/tracking.md).

**Verwante onderwerpen:**

[&#x200B; Spoor en monitorberichten &#x200B;](tracking.md) | [&#x200B; Leveringsrapporten &#x200B;](../reporting/delivery-reports.md) | [&#x200B; Begrijp leveringsmislukkingen &#x200B;](../send/delivery-failures.md) | [&#x200B; vorm getraceerde verbindingen &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ Hoe kan ik een foutbericht vertalen?

Een foutbericht wordt weergegeven in een vreemde taal? Alle foutberichten en de vertaling ervan worden weergegeven op [deze pagina](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=nl){target="_blank"}.

+++

+++ Kan ik een webformulier maken en antwoorden verzamelen in Campagne?

Ja. Creeer Webvormen gebruikend &lbrace;de Toepassingen van het Web van de Campagne &amp; Forms **(cliëntconsole) voor volledige controle over vormlogica en bevestiging, of gebruik** het Landen van de Campagne Pagina&#39;s van de Pagina&#39;s **(Web UI) met een moderne belemmering-en-dalingsinterface voor abonnementen en loodgeneratie.** Zowel verzamelen gegevens rechtstreeks in Campagne en integreren met werkschema&#39;s voor geautomatiseerde acties.

**Verwante onderwerpen:**

[&#x200B; leer meer over Webtoepassingen en vormen &#x200B;](../dev/webapps.md) | [&#x200B; het landen van UI van het Web van de Campagne pagina&#39;s &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campagne v8 versus vorige versies {#v7-differences}

Begrijp de belangrijkste verschillen tussen Campagne v8 en vorige versies (Klassieke v7 en Standaard), met inbegrip van architectuur, plaatsing, migratiewegen, en eigenschapveranderingen. Of je nu uit Campaign Classic v7 of Campaign Standard komt, leer wat nieuw is en hoe je vloeiend kunt overstappen.

+++ Kan Campagne v8 worden geïnstalleerd op een bedrijfs- of hybride omgeving?

Nee. De campagne v8 is exclusief beschikbaar als a **Beheerde Cloud Service**, volledig die door Adobe wordt ontvangen.

**Zeer belangrijke voordelen van de Beheerde Diensten van de Wolk:**

* Superieure prestaties en schaalbaarheid
* Automatische upgrades - altijd met de nieuwste versie
* Verbeterde beveiliging met continue bewaking
* Geen infrastructuurbeheer of IT-overhead
* Ingebouwde hoge beschikbaarheid en noodherstel

Leer meer over [&#x200B; de architectuur van de Campagne v8 &#x200B;](../architecture/architecture.md) en [&#x200B; verschillen tussen Campagne v8 en Klassieke v7 &#x200B;](../start/v7-to-v8.md).

+++

+++ Wat zijn de belangrijkste verschillen tussen Campagne v8 en vorige versies?

Campagne v8 is een complete revisie van Adobe Campaign, ontworpen voor moderne cloudnative architectuur en levert aanzienlijke verbeteringen ten opzichte van Campaign Classic v7 en Campaign Standard:

**Model van de Plaatsing:**

* **v8:** Beheerde de Diensten van de Wolk slechts - volledig gehost en beheerd door Adobe
* **v7/Norm:** beschikbare opties op gebouw, hybride, of ontvangen
* **Voordeel:** Nul infrastructuurbeheer, automatisch schrapen, onderneming-rang veiligheid, pro-actieve controle

**Architectuur &amp; Prestaties:**

* **v8:** Verbeterde Volledige architectuur FDA (FFDA) met gegevensbestand PostgreSQL
* **v8:** de verwerkingsproductie van de partij die tot **20 miljoen verrichtingen per uur** bereikt
* **v8:** Transactionele berichtproductie van **1 miljoen per uur**
* **v8:** de exploratie van gegevens in real time en snel publiek het bouwen (notulen versus uren)
* **Voordeel:** betere prestaties voor grootschalige verrichtingen en complexe campagnes

**Gebruikersinterface:**

* **v8:** Nieuwe **gebruikersinterface van het Web van de Campagne** naast cliëntconsole - intuïtief, toegankelijk, ideaal voor marketers
* **v8:** Modern, ontvankelijk ontwerp met belemmering-en-dalingsmogelijkheden
* **v8:** Vereenvoudigde campagne creatie en beheerswerkschema&#39;s
* **v8:** deelt vele gelijkenissen met de interface van Campaign Standard
* **Voordeel:** sneller onboarding, gemakkelijkere campagneuitvoering, betere toegankelijkheid, minimale het leren curve

**Nieuwe Zeer belangrijke Eigenschappen:**

* **rijke dupberichten** met beelden, video&#39;s, interactieve knopen, carrousels, en tijdopnemers
* **AI Medewerker** voor inhoudsgeneratie (e-mail, SMS, duw) met merk groepering het scoring
* **Verbeterde infrastructuur van SMS (SMS v2.0)** met betere betrouwbaarheid en verenigbaarheid
* **integratie van Adobe Experience Manager as a Cloud Service** voor naadloos inhoudsbeheer
* **Verbeterde rapportering** met inbegrip van Dynamische Rapportering voor de gebruikers van Campaign Standard

**Verbeteringen &amp; Onderhoud:**

* **v8:** Automatische verbeteringen die door Adobe worden beheerd - altijd op recentste stabiele versie met ononderbroken leveringsmodel
* **v7/Norm:** Vereiste handmatige verbeterings planning en uitvoering
* **Voordeel:** Verminderde onderhoudslast, directe toegang tot nieuwe eigenschappen, geen onderbreking

**APIs &amp; Integratie:**

* **v8:** Moderne REST APIs met verbeterde prestaties en betrouwbaarheid
* **v8:** Naadloze integratie met Adobe Experience Cloud en Adobe Experience Platform
* **Voordeel:** Gemakkelijkere integratie, betere interoperabiliteit, moderne ontwikkelingspraktijken

[Meer informatie over de belangrijkste mogelijkheden van Campagne v8](whats-new.md)

**Verwante onderwerpen:**

[&#x200B; van Campaign Classic v7 aan v8 &#x200B;](v7-to-v8.md) | [&#x200B; v7 aan v8 overgangsgids &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"} | [&#x200B; Van Campaign Standard aan v8 &#x200B;](acs-to-v8.md) | [&#x200B; de overgang van Campaign Standard &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [&#x200B; Gids van de Goedkeuring van de Campagne v8 &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/acs-to-ac/home){target="_blank"} | [&#x200B; de capaciteitmatrijs van de Campagne v8 &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Campagne v8-architectuur](../architecture/architecture.md)
* [Afvoerkanalen en beperkingen](ac-guardrails.md)

+++

+++ Moet ik migreren van Campaign Classic v7 of Campaign Standard naar v8?

**Campagne v8 is ideaal voor organisaties die nodig hebben:**

* **campagnes van het hoog-volume** - verzend miljoenen berichten met betere prestaties en betrouwbaarheid (20M verrichtingen/uur)
* **scalability van de Onderneming** - Groei uw gegevensbestand en campagnes zonder prestatieszorgen
* **Modern Web gebruikersinterface** - Intuïtieve, ontvankelijke UI van het Web van de Campagne voor snellere campagneverwezenlijking en betere gebruikerservaring
* **wolk-inheemse voordelen** - de automatische updates van de hefboomwerking, beheerde infrastructuur, elastisch schrapen, en pro-actieve controle
* **langdurige steun** - de Campagne v8 is het strategische platform van Adobe met uitgebreide steun, terwijl de vorige versies het Eind van Steun in de komende jaren zullen bereiken
* **Verminderde overheadkosten van IT** - Elimineer infrastructuurbeheer en verbeterings planning
* **Geavanceerde mogelijkheden** - AI Medewerker, rijke duw, verbeterde SMS, de integratie van Adobe Experience Platform

**voor de gebruikers van Campaign Standard:**

Campaign Standard-gebruikers komen nu in aanmerking voor de overgang naar Beheerde Cloud Services voor Campagne v8. Belangrijkste voordelen zijn:

* **Vertrouwde interface** - Het Web UI van de Campagne deelt vele gelijkenissen met Campaign Standard, die de het leren kromme minimaliseren
* **pariteit van de Eigenschap** - de Zeer belangrijke mogelijkheden van Campaign Standard zijn toegevoegd aan v8 (Dynamische Rapportering, Gecentraliseerde Branding, REST APIs, het Bestaan van Pagina&#39;s, Visuele Fragmenten)
* **Verbeterde steun** - Top-notch hulp met vlotte overgang en aan de gang zijnde platform controle
* **de migratie van Gegevens** - al uw gegevens van Campaign Standard worden ingevoerd met minimale verstoring
* **Consistente gebruikerservaring** - blijf het werken met vertrouwde werkschema&#39;s en interface

**voor Campaign Classic v7 gebruikers:**

Campagne v8 biedt aanzienlijke verbeteringen en behoudt tegelijkertijd de kernmogelijkheden voor campagnes:

* **Dubbele interface** - heb toegang tot zowel de krachtige cliëntconsole als de moderne UI van het Web van de Campagne
* **Betere prestaties** - significant betere vraagprestaties en gegevensverwerking
* **de voordelen van de Wolk** - Automatische verbeteringen, veiligheidspatches, steun/terugwinning die door Adobe wordt beheerd
* **Moderne architectuur** - verbeterde architectuur FFDA met PostgreSQL voor betere scalability

**wanneer om het migreren te overwegen:**

* De huidige Campagne-instantie verwerkt grote gegevensvolumes (miljoenen profielen)
* Er zijn prestatieproblemen met complexe workflows of het kiezen voor
* U wilt de kosten voor infrastructuurbeheer en onderhoud verlagen
* U hebt naadloze integratie met Adobe Experience Cloud of Adobe Experience Platform nodig
* U bent toch van plan een belangrijke upgrade uit te voeren of de infrastructuur te vernieuwen
* **u wilt toekomstbestendige technologie** - de Vorige versies zullen Einde van Steun bereiken
* **Uw team heeft een moderne interface** nodig - Het Web UI van de Campagne biedt betere toegankelijkheid voor marketers aan

**Overwegingen van de Migratie:**

* Adobe biedt ondersteuning voor migratie, begeleiding en tools
* v8 is alleen beheerde Cloud Service (geen on-premise of hybride implementatie)
* Sommige technische implementaties kunnen verschillen - herzie de [&#x200B; vermogensmatrijs &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* Gegevensmigratie en testen vereisen planning en bronnen
* **voor de gebruikers van Campaign Standard** - de Overgang wordt ontworpen om met minimale werkschemaverstoring glad te zijn

**Volgende stappen:**

Neem contact op met uw Adobe-vertegenwoordiger om:

* Evalueer uw gereedheid en tijdlijn voor migratie
* Begrijp de specifieke voordelen voor uw gebruiksgeval
* De migratiestrategie en de toewijzing van middelen plannen
* Toegang tot migratiehulpmiddelen en support

**Verwante onderwerpen:**

**voor Campaign Classic v7 gebruikers:** [&#x200B; van Campaign Classic v7 aan v8 &#x200B;](v7-to-v8.md) | [&#x200B; v7 aan v8 gedetailleerde gids &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**voor de gebruikers van Campaign Standard:** [&#x200B; overgang van Campaign Standard aan v8 &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [&#x200B; Gids van de Goedkeuring van de Campagne v8 &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/acs-to-ac/home){target="_blank"} | [&#x200B; van Campaign Standard aan v8 overzicht &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/acs-to-ac/overview){target="_blank"} | [&#x200B; worden begonnen begonnen voor marketers &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/acs-to-ac/marketers){target="_blank"} | [&#x200B; krijgen begonnen voor admin/ontwikkelaars &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**Algemene middelen:** [&#x200B; de capaciteitmatrijs van de Campagne v8 &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Compatibiliteitsmatrix](compatibility-matrix.md)

+++

+++ Hoe migreer ik mijn Campaign Classic v7 On-Premise of Hybride omgeving naar Adobe Managed Services?

Het migreren van uw Campaign Classic v7 On-Premise- of Hybrid-omgeving naar Adobe Managed Services is vaak een strategische opstap voordat u overschakelt naar Campaign v8. Deze migratie biedt directe voordelen en legt de basis voor toekomstige v8-adoptie.

**waarom migreren aan Managed Services?**

* **Weg aan Campagne v8** - Managed Services verstrekt een vloeiender verbeteringspad aan v8 met zijn Webinterface en mogelijkheden van GenAI
* **Schaalbaarheid &amp; betrouwbaarheid** - de wolkeninfrastructuur van Adobe voor betere prestaties en het automatische schrapen
* **Verbeterde veiligheid** - voordeel van ononderbroken controle, automatische veiligheidspatches, en onderneming-rang bescherming
* **Professionele steun** - de steun van de Toegang Adobe ondersteuningsteam en infrastructuurmiddelen
* **Verminderde overheadkosten van IT** - Geen infrastructuurbeheer, automatische steunen, en rampenterugwinning inbegrepen
* **integratie van Adobe Experience Platform** - naadloos integreren met Adobe Experience Platform voor uitvoerige marketing oplossingen

**Belangrijke overwegingen:**

* **Geen geautomatiseerde migratie** - momenteel, is er geen geautomatiseerd migratiehulpmiddel beschikbaar. Handmatige planning en uitvoering zijn vereist
* **de steun van Adobe Professional Services** - adviseert hoogst om Adobe Professional Services voor begeleiding en deskundigheid in dienst te nemen
* **vereiste Voorbereiding** - organiseer uw gegevens, evalueer vereisten, controleer huidige praktijken, en zorg verenigbaarheid
* **de ingewikkeldheid van de Migratie** - Overweeg factoren zoals milieu ingewikkeldheid, gegevensvolume, aanpassingen, en objecten gebiedsdelen

**Zeer belangrijke uitdagingen om voor te plannen:**

1. **XML/Blob de beperkingen van de gegevensimport** - kan slechts worden ingevoerd gebruikend pakketten of stortplaats-en-terugzetmethodes
2. **Grote gegevenslijsten** - de Ontvankelijke lijsten en levering/het volgen logboeken vereisen speciale optimalisatiestrategieën
3. **identiteitskaarts van Objecten** - Elk ingevoerd voorwerp ontvangt een nieuwe identiteitskaart, die identiteitskaart voor continuïteit vereist opnieuw uitlijnen
4. **bouwt verbeteringen** - Plan om aan de recentste beschikbare versie v7 vóór migratie te bevorderen

**migratie op hoog niveau roadmap:**

1. **due diligence &amp; werkingsgebieddefinitie** - voer grondige analyse uit, bepaal werkingsgebied, en evalueer leveringsbehoeften met het team van Adobe Managed Services
2. **Controle &amp; werkingsgebiedverfijning** - herzie huidige praktijken, evalueer gegevensmodel en stromen, identificeer slechte praktijken, en verminder onnodige migratieelementen
3. **Schone-up &amp; voorbereiding** - het Adres geïdentificeerde kwesties, verwijdert ongebruikte gegevens, en voert bouwstijlverbeteringen aan recentste versie uit
4. **Aanvankelijke migratie (Stadium)** - Voorziening nieuwe wolkeninstantie, reservestructuur, de invoerpakketten, opstellingsopeenvolgingen/tellers, de invoervoorwerpen, het opnieuw uitlijnen IDs, de invoer niet-XML gegevens, en bevestigt
5. **Definitieve migratie (Productie)** - verfrist productie met geverifieerde werkgebiedinstantie, leidt prestaties het testen, direct migreren aan productie, en laat het volgen/mogelijkheden in real time toe

**Beste praktijken:** presteer altijd aanvankelijke migratie op een werkgebiedinstantie alvorens aan productie te werk te gaan om risico&#39;s te minimaliseren en het proces te bevestigen.

**Aan de slag:**

Neem contact op met uw Adobe-vertegenwoordiger en neem contact op met Adobe Professional Services om:

* Evalueer uw huidige omgeving en gereedheid voor migratie
* Een gedetailleerd migratieplan ontwikkelen met tijdlijnen en afhankelijkheden
* Ontvang deskundig advies door het gehele migratieproces
* Gebruik beproefde beste praktijken en vermijd gemeenschappelijke valkuilen

Leer meer over [&#x200B; migrerend aan Managed Services &#x200B;](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"} op de Gemeenschap van Adobe Campaign.

**Verwante onderwerpen:**

[&#x200B; van Campaign Classic v7 aan v8 &#x200B;](v7-to-v8.md) | [&#x200B; v7 aan v8 overgangsgids &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"} | [&#x200B; Campagne v8 architectuur &#x200B;](../architecture/architecture.md) | [&#x200B; Adobe Professional Services &#x200B;](https://business.adobe.com/nl/customers/consulting-services/main.html){target="_blank"}

+++

+++ Wat zijn de belangrijkste terminologie en eigenschapverschillen in Campaign v8?

Campagne v8 biedt de meeste Campaign Classic v7- en Campaign Standard-mogelijkheden verbeteringen, maar sommige functies hebben wijzigingen als gevolg van de native architectuur van de cloud en sommige terminologie verschilt per versie.

**Terminologieverschillen (Campaign Standard aan v8):**

* **de middelen van de Douane** zijn nu **Schema&#39;s**
* **Berichten** worden bedoeld als **Leveringen**
* **de gebruikers van het Product** zijn nu **Operatoren**
* **Rollen** worden gevormd met **Benoemde Rechten**
* **de Groepen van de Veiligheid** zijn nu **Groepen van de Exploitant**
* **Organisatorische eenheden** worden beheerd door **Toestemmingen van de Omslag**

**de terminologieupdates van het Web van de Campagne UI:**

De volgende termijnen zijn bijgewerkt in het Web UI van de Campagne (de gebruiks traditionele termijnen van de cliëntconsole):

* **Ontvangers** zijn nu **Profielen**
* **zaadadressen** zijn nu **profielen van de Test**
* **de analyse van de Levering** is nu **voorbereiding van de Levering** (klik **voorbereidingen treffen** knoop)
* **E-mailVoorproef** is beschikbaar door **inhoud** knoop simuleren
* **Lijsten** zijn nu **Publiek**

**niet beschikbaar in v8:**

* **Op-gebouw en hybride plaatsingen** - v8 is de Beheerde Diensten van de Wolk slechts
* **Directe gegevensbestandtoegang** - Gebruik verstrekte APIs en hulpmiddelen in plaats daarvan
* **Klantbeheerde infrastructuur** - Adobe beheert alle infrastructuur
* **Hand bouwt verbeteringen** - nu automatisch (beheerde Adobe)

**Verschillende implementaties in v8:**

* **Technische werkschema&#39;s** - wat voor wolkenarchitectuur wordt geoptimaliseerd, kan verschillend werken
* **structuur van het Gegevensbestand** - de verbeterde architectuur FFDA kan schemaaanpassingen vereisen
* **de Integraties van de Douane** - kan updates voor op wolk-gebaseerde architectuur nodig hebben
* **Aanpassingen op laag niveau** - sommige vereisen verschillende benaderingen in beheerd milieu

**Verbeterd of vervangen in v8:**

* **bouwt verbeteringen** - Automatisch met ononderbroken leveringsmodel in plaats van handboek
* **Prestaties het stemmen** - die door de infrastructuuroptimalisering van Adobe wordt behandeld
* **de flarden van de Veiligheid** - die automatisch door Adobe worden toegepast
* **Steun en terugwinning** - die door Adobe als deel van de dienst wordt beheerd
* **Gebruikersinterface** - het Nieuwe Web UI van de Campagne naast cliëntconsole

**Eigenschappen die voor de gebruikers van Campaign Standard worden toegevoegd die aan v8 overgaan:**

* **Dynamische Rapportering** - Aanpasbare, rapporten in real time met demografische analyse
* **Gecentraliseerde Branding** - bepaal merk visuele en technische richtlijnen
* **REST APIs** - creeer integraties en bouw uw ecosysteem
* **het Bestaan de Verbeteringen van Pagina&#39;s** - Verbeterde eigenschappariteit met Campaign Standard
* **Visuele Fragments** - opnieuw bruikbare visuele componenten voor e-mail en inhoudsmalplaatjes

**Belangrijk:** de meeste marketing en operationele eigenschappen zijn beschikbaar en verbeterd in v8. In de cloudomgeving worden functies op technisch en infrastructuurniveau door Adobe beheerd.

**Verwante onderwerpen:**

[&#x200B; matrijs van de Mogelijkheid &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [&#x200B; de matrijs van de Verenigbaarheid &#x200B;](compatibility-matrix.md) | [&#x200B; Grafieken en beperkingen &#x200B;](ac-guardrails.md) | [&#x200B; v7 aan v8 overgangsgids &#x200B;](v7-to-v8.md)

[&#x200B; Campaign Standard aan v8 overgang &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## Profielen en doelgroepen {#audiences}

Vind antwoorden op vragen over het beheren van profielen, het creëren van publiek, het invoeren van gegevens, en het richten van ontvangers voor uw campagnes.

+++ Hoe te om ontvangers tot stand te brengen?

Handmatig ontvangers maken in de clientconsole voor afzonderlijke profielen, importeren uit bestanden (CSV/TXT) voor bulktoevoegingen, webformulieren gebruiken voor zelfregistratie of integreren via API&#39;s van externe systemen. Gebruik workflows voor importeren voor het terugkeren van gegevens.

**Verwante onderwerpen:**

[&#x200B; creeer manueel profielen &#x200B;](../audiences/create-profiles.md) | [&#x200B; de profielen van de Invoer van een dossier &#x200B;](../audiences/import-profiles.md) | [&#x200B; verzamel profielen met Webvormen &#x200B;](../audiences/collect-profiles.md)

+++

+++ Hoe kan ik profielen importeren?

Campagne biedt meerdere importmethoden: eenvoudige bestandsimporten met de wizard Importeren, op workflow gebaseerde import voor complexe transformaties, terugkerende import met geplande workflows uit SFTP en API-import voor programmatische integratie.

Bereid voor het importeren van bestanden uw gegevensbestand voor (CSV/TXT, UTF-8-codering), gebruik de wizard of workflow voor importeren, wijs kolommen toe aan Campagnevelden, definieer de regels voor bijwerken/invoegen en test eerst met een klein voorbeeld. Gebruik workflows voor terugkerende importbewerkingen en pas deduplicatieregels toe.

**Verwante onderwerpen:**

[&#x200B; de gegevensgids van de Invoer &#x200B;](../start/import.md) | [&#x200B; Terugkerend de invoerwerkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=nl-NL){target="_blank"} | [&#x200B; het laden van Gegevens activiteit &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe kan ik de doelpopulatie van een marketingcampagne definiëren?

De campagne biedt veelvoudige het richten methodes aan: bouwt vragen met visuele criteria, richt bestaande lijsten of segmenten, invoerontvangers uit externe dossiers (CSV, TXT), of pas vooraf bepaalde filters toe. U kunt criteria met logica combineren AND/OR, specifieke populaties uitsluiten, controlegroepen gebruiken, en voor het testen A/B verdelen. Geef altijd een voorvertoning weer van de grootte van de doelpopulatie voordat u deze verzendt.

[&#x200B; bepalen campagnedoelstellingen &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=nl-NL){target="_blank"} | [&#x200B; de activiteit van de Vraag &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=nl-NL){target="_blank"} | [&#x200B; creeer publiek &#x200B;](../audiences/create-audiences.md)

+++

+++ Hoe kan ik een lijst met profielen maken?

Een lijst is een statische reeks ontvangers die u in leveringen en hergebruik over campagnes kunt richten.

**Drie creatiemethodes:**

* **Handmatige verwezenlijking:** navigeer aan **[!UICONTROL Profiles and Targets > Lists]** en klik **[!UICONTROL Create]**. Voeg ontvangers van een vraag, door individuele selectie, of van een omslag toe.

* **automatisering van het Werkschema:** gebruik de **[!UICONTROL List update]** activiteit om lijsten automatisch van vraagresultaten of ingevoerde gegevens tot stand te brengen en te handhaven.

* **tijdens de invoer:** creeer een lijst wanneer het invoeren van profielen om hen als herbruikbare groep te bewaren.

**Uiteinde:** werkschema&#39;s van het gebruik voor lijsten die regelmatige updates, en handverwezenlijking voor éénmalige segmentatie vereisen.

**Verwante onderwerpen:**

[&#x200B; creeer publiek &#x200B;](../audiences/create-audiences.md) | [&#x200B; de updateactiviteit van de Lijst &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe kan ik een populatie dedupliceren voordat ik een bericht verstuurt?

Gebruik de **[!UICONTROL Deduplication]** -activiteit in een werkstroom om dubbele ontvangers te verwijderen vóór levering. Plaats de locatie tussen uw **[!UICONTROL Query]** - en **[!UICONTROL Delivery]** -activiteiten en kies vervolgens de deduplicatiecriteria (doorgaans het e-mailadres of de id van de ontvanger) en de record die u wilt bijhouden.

**Uiteinde:** dedupliceer altijd alvorens te verzenden om ervoor te zorgen elke persoon uw bericht slechts eenmaal ontvangt.

Leer meer over de [&#x200B; activiteit van de Deduplicatie &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe te om abonnees aan een nieuwsbrief te identificeren en te richten?

De campagne volgt automatisch nieuwsbrieven abonnementen door informatiediensten. Abonnees activeren:

* Gebruik een **[!UICONTROL Query]** activiteit en filter op **[!UICONTROL Subscriptions]** > om uw nieuwsbrief service te selecteren
* Kies **[!UICONTROL To > Subscribers of an information service]** als u direct vanaf uw levering abonnees wilt activeren
* Abonnementenlijsten samenstellen met de **[!UICONTROL Subscription Services]** -workflowactiviteit

De campagne volgt abonnement/unsubscription geschiedenis en beheert automatisch opt-in/opt-out.

**Verwante onderwerpen:**

[&#x200B; beheert abonnementen &#x200B;](../start/subscriptions.md) | [&#x200B; de activiteit van de Vraag &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=nl-NL){target="_blank"}

+++

+++ Wat is de beste praktijk om profielen uit te sluiten van een doelpopulatie?

Gebruik de activiteit **[!UICONTROL Exclusion]** in een werkstroom om ongewenste profielen uit uw doel te verwijderen. Plaats het na uw gerichte activiteiten en bepaal welke populatie om uit te sluiten.

Leer meer over de [&#x200B; activiteit van de Uitsluiting &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=nl-NL){target="_blank"}

+++

+++ Kan ik externe profielen gebruiken zonder deze te importeren in Campagne?

Ja, met Campagne v8 kunt u werken met externe profielen die zijn opgeslagen in een externe database zonder deze te laden in Adobe Campaign. [Meer informatie](../audiences/external-profiles.md).

+++

+++ Hoe maak ik testprofielen voor mijn leveringen?

Testprofielen zijn speciale ontvangers die worden gebruikt om proefdrukken te verzenden en leveringen te valideren zonder dat dit gevolgen heeft voor uw productiedatabase. Maak ze in **[!UICONTROL Profiles and Targets > Test profiles]** of gebruik de functie **[!UICONTROL Seed addresses]** om automatisch testontvangers aan uw leveringen toe te voegen voor kwaliteitsborging en controle in de Postvak IN.

Leer meer over [&#x200B; profielen van de Test &#x200B;](../audiences/test-profiles.md)

+++

## Berichtontwerp {#design}

Leer hoe u effectieve marketingberichten kunt ontwerpen in Campaign v8, inclusief e-mailsjablonen, personalisatietechnieken en meertalige inhoud. Ontwerp uw berichten in de cliëntconsole of gebruik moderne **E-mail Designer** in het Web UI van de Campagne voor verbeterde visuele het uitgeven ervaring.

+++ Wat zijn de beste werkwijzen voor het ontwerpen van e-mails in Campagne?

Belangrijke richtlijnen: zorg voor een ontwerp dat reageert op mobiele apparaten, gebruik HTML 4.0/XHTML-compatibele code met inline CSS, optimaliseer afbeeldingen (onder 100 KB) met alternatieve tekst, gebruik velden voor het samenvoegen van personalisatie, test voor alle e-mailclients voordat u het verzendt en voeg een gewone tekstversie toe. Doel voor totale e-mailgrootte van minder dan 500 kB voor optimale prestaties.

[&#x200B; het ontwerpgids van de E-mail &#x200B;](../send/email.md) | [&#x200B; Beste praktijken van de Levering &#x200B;](delivery-best-practices.md)

+++

+++ Wat is een leveringssjabloon?

Een leveringsmalplaatje is een pre-gevormde levering die alle montages en parameters voor hergebruik over veelvoudige campagnes bewaart. De malplaatjes omvatten doelregels, inhoudsontwerp, verpersoonlijking, technische montages (afzender, antwoord-aan), en typologieregels. Creëer eens en hergebruik om consistentie te behouden en het creëren van campagnes te versnellen.

Leer hoe te [&#x200B; leveringsmalplaatjes &#x200B;](../send/create-templates.md) creëren

+++

+++ Kan ik eenvoudig een bestaande HTML importeren om een e-mailbericht te maken in Campagne?

Ja. Importeer HTML-inhoud via directe kopiëren/plakken in de inhoudeditor, upload het bestand vanaf uw computer of laad de inhoud via een URL. Zorg ervoor dat uw HTML e-mailcompatibele code (HTML 4.0/XHTML) met inline CSS gebruikt en dat u afbeeldingen host op een openbare server. De campagne voegt automatisch personalisatie en het volgen aan ingevoerde HTML toe.

**Uiteinde:** voor de beste ervaring van het e-mailontwerp, gebruik **E-mail Designer** in het Web UI van de Campagne, die moderne belemmering-en-dalingsmogelijkheden en ingebouwde ontvankelijke malplaatjes, eerder dan het invoeren van ruwe HTML aanbiedt.

Leer hoe te [&#x200B; de inhoud van HTML van de Invoer &#x200B;](../send/defining-the-email-content.md)

+++

+++ Hoe kan ik een nieuwsbrief op abonnementsbasis in Campaign tot stand brengen?

Ja. Gebruik de informatieservices van Campagne om nieuwsbrieven te beheren. De belangrijkste mogelijkheden omvatten automatische opt-in/opt-out behandeling, abonnement volgen, nalevingsbeheer (GDPR, CAN-SPAM), multi-nieuwsbrief steun, Webintegratie voor sign-up vormen, en gerichte levering aan abonnees.

Leer hoe te [&#x200B; abonnementen &#x200B;](../start/subscriptions.md) beheren

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

[&#x200B; de gids van Personalization &#x200B;](../send/personalize.md) | [&#x200B; de gebieden van de Personalisatie &#x200B;](../send/personalization-fields.md) | [&#x200B; Voorwaardelijke inhoud &#x200B;](../send/conditions.md)

+++

+++ Kan ik meertalige berichten versturen?

Ja. De campagne v8 biedt meertalige mogelijkheden, met het **Web UI van de Campagne** die de gemakkelijkste benadering verstrekt. Het Web UI biedt inheemse meertalige levering met taalvarianten-voegt taalvarianten aan uw levering toe, en de Campagne verzendt automatisch de aangewezen die versie op de aangewezen taal van de ontvanger wordt gebaseerd. Beschikbaar voor e-mail-, push-berichten, SMS- en transactieberichten.

Belangrijkste functies: automatische duplicatie van inhoud, automatisch verzenden op basis van taal, standaardtalenfallback en eenvoudig beheer van varianten.

De clientconsole ondersteunt ook meertalige inhoud met behulp van voorwaardelijke inhoud en workflows, maar vereist meer handmatige configuratie.

[&#x200B; Meertalige leveringen (Web UI) &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [&#x200B; Voorwaardelijke inhoud (de console van de Cliënt) &#x200B;](../send/conditions.md)

+++

+++ Kan ik een webformulier lokaliseren?

Ja. Campagne voor webtoepassingen ondersteunt meertalige lokalisatie. Definieer vertalingen voor alle formulierelementen (labels, knoppen, berichten, fouttekst) met automatische taaldetectie op basis van het profiel van de ontvanger of de browserinstellingen. Meerdere taalversies worden ondersteund in één webtoepassing, waarbij zo nodig een standaardtaal wordt gebruikt.

Leer meer over [&#x200B; de toepassingslocalisatie van het Web &#x200B;](../dev/webapps.md)

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

[&#x200B; AI Hulpoverzicht &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [&#x200B; AI Hulpgevallen van het gebruiksgeval &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [&#x200B; Merk groepering &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Berichten testen en verzenden {#send}

Leer beste praktijken voor het testen, het bevestigen, het verzenden van, en het volgen van uw marketing berichten om succesvolle campagnelevering te verzekeren.

+++ Wat is de leveringanalyse?

De analyse van de levering is een looppas van de de bevestigingsfase Campagne alvorens te verzenden. Het berekent de doelpopulatie, valideert inhoud, controleert fouten, past typologische regels toe, en schat leveringsvolume.

Campagne genereert logboeken met waarschuwingen en fouten. Fouten bij blokoplevering en moeten worden gecorrigeerd. Waarschuwingen zijn een advies. Analyselogs altijd controleren voordat ze worden verzonden.

Leer meer in de [&#x200B; de analysegids van de Levering &#x200B;](../send/delivery-analysis.md)

+++

+++ Waarom zou ik proefdrukken maken?

Proofs zijn testberichten die uw levering bevestigen alvorens naar uw belangrijkste publiek te verzenden. Gebruik proefdrukken om de personalisatie te controleren, de weergave van inhoud voor verschillende e-mailclients te testen, koppelingen te bevestigen en het werk te volgen, afbeeldingen en bijlagen te controleren en de reactiesnelheid van mobiele apparaten te valideren.

Proefdrukken helpen fouten af te vangen voordat ze duizenden ontvangers bereiken, maken goedkeuring van belanghebbenden en plaatsing van inbox testen mogelijk. Verzend proef naar veelvoudige e-mailcliënten en apparaten, en verkrijg altijd goedkeuring alvorens de productie verzendt.

Leer meer in de [&#x200B; Proefdrukken en voorproefgids &#x200B;](../send/preview-and-proof.md)

+++

+++ Hoe te om zaadadressen in Adobe Campaign te gebruiken?

Zaadadressen zijn speciale ontvangers die automatisch aan elke levering voor het testen, de kwaliteitsborging, en controle-zonder het aanpassen van uw doelcriteria worden toegevoegd. Nuttig voor doorlopende bewaking, plaatsingstests in de postbus, directe-mailvalidatie en zichtbaarheid van belanghebbenden.

**Zeer belangrijke verschillen van proeven:**

* **zaadadressen** - die aan productieleveringen automatisch worden toegevoegd, tellen naar verzendt volume
* **Proefdrukken** - de Test verzendt vóór productie, telt niet naar volume, dat voor bevestiging wordt gebruikt

Zaadadressen beheren in **[!UICONTROL Resources > Campaign management > Seed addresses]** . Houd lijsten klein om te voorkomen dat de leveringswaarden worden beïnvloed.

[&#x200B; zaadadresgids &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe kan ik opstelling een goedkeuringsproces alvorens berichten te verzenden?

De campagne verstrekt goedkeuringswerkschema&#39;s om ervoor te zorgen dat de berichten aan kwaliteitsnormen alvorens verzenden voldoen. Configureer goedkeuringen voor inhoud, doel, extractie (direct mail) en budget op campagne- of leveringsniveau.

**Opstelling:**

Maak in **[!UICONTROL Administration > Access management > Operator groups]** groepen met operatoren en wijs vervolgens goedkeuringsgroepen toe in campagne- of leveringseigenschappen. Tijdens de campagne worden e-mailberichten verzonden naar revisoren die wijzigingen kunnen goedkeuren, afwijzen of aanvragen.

**voor standalone leveringen (niet in een campagne):**

Gebruik **proeven als uw goedkeuringsproces**. Verzend proefdrukken naar uw goedkeuringsgroep voor validatie en verzend altijd een nieuwe proefdruk nadat u wijzigingen hebt aangebracht om ervoor te zorgen dat belanghebbenden de nieuwste versie controleren.

**Verwante onderwerpen:**

[&#x200B; Bevestiging van de Levering &#x200B;](../send/preview-and-proof.md) | [&#x200B; Goedkeuringen van de Campagne &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=nl-NL){target="_blank"}

+++

+++ Wat is een typologieregel?

De typologische regels zijn geautomatiseerde bedrijfslogica die tijdens leveringsanalyse wordt toegepast om bericht het verzenden te bevestigen en te optimaliseren. Zij verzekeren naleving van marketing beleid, beschermen leverbaarheid, en verhinderen klantenvermoeidheid.

**Belangrijkste regeltypes:**

* **het Filtreren regels** - sluit (gevoegde op lijst van gewenste personen, unsubscribed, quarantined) ontvangers uit
* **Regels van de Druk** - het berichtfrequentie van de Controle om overweldigende ontvangers te vermijden
* **Regels van de Capaciteit** - het berichtvolume van de Grens voor verwerkingscapaciteit of ISP grenzen
* **Regels van de Controle** - de berichtgeldigheid van de controle (onderwerpregel, unsubscribe verbinding, afzenderformaat)

De regels worden gegroepeerd in typologieën en tijdens leveringsanalyse toegepast. De campagne kan ontvangers uitsluiten, de levering blokkeren, of waarschuwingen produceren die op de regels worden gebaseerd.

[&#x200B; de gids van de Typologieregels &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe kan ik e-mails sturen in golven?

Ja. Golf die uw levering verdeelt in veelvoudige partijen verzendt die met geplande intervallen worden verzonden. Dit is essentieel voor groot-volumecampagnes om serverlading in evenwicht te brengen, ISP throttling te verhinderen, afzenderreputatie met nieuwe IPs te bouwen, en opt-outs/grenzen tussen golven te beheren.

**Configuratie:**

In uw leveringseigenschappen, laat golf toe die en bepaalt het aantal golven (of partijgrootte) verzendt, interval tussen golven, en golfdistributie (lineaire of douanepercentages). De campagne verdeelt automatisch uw doelbevolking en verzendt elke golf op programma.

Gebruik golven voor grote campagnes, controleer eerste golfprestaties alvorens verder te gaan, en sta voldoende tijd tussen golven toe om schommelingen en opt-outs te verwerken.

Leer hoe te om [&#x200B; golf te vormen die &#x200B;](../send/configure-and-send.md#sending-using-multiple-waves) verzendt

+++

+++ Welke zijn de belangrijkste stappen om een e-mail in Campagne tot stand te brengen?

Het creëren van een e-mail in Campagne v8 impliceert deze belangrijkste stappen: creeer de levering, bepaal het doelpubliek, ontwerp de inhoud, voeg verpersoonlijking toe, vorm montages (afzender, onderwerp, antwoord-aan), in werking gestelde leveringsanalyse, verzend proefdrukken voor het testen, en verzend of programma ten slotte.

**Zeer belangrijke stappen:**

1. **creeer de levering** - kies e-mail als kanaal en selecteer naar keuze een leveringsmalplaatje
1. **bepaalt het doel** - selecteer uw ontvangend publiek gebruikend vragen, lijsten, of ingevoerde dossiers
1. **Ontwerp de inhoud** - creeer uw bericht gebruikend de e-mailredacteur (E-mail UI van het Web Designer of de redacteur van de cliëntconsole)
1. **voeg verpersoonlijking** toe - neem dynamische gebieden, verpersoonlijkingsblokken, en voorwaardelijke inhoud op
1. **vorm montages** - plaats afzenderadres, onderwerpregel, antwoord-aan, en leveringsparameters
1. **de leveringsanalyse van de Looppas** - de Campagne bevestigt inhoud, berekent het doel, en controleert fouten
1. **verzend proef** - test uw e-mail met goedkeuringsgroepen om het teruggeven en inhoud te bevestigen
1. **verzend of programma** - verzend onmiddellijk naar het belangrijkste doel of programma voor een recentere datum

**Twee interfaceopties:**

* **UI van het Web van de Campagne** - Moderne interface met verbeterde E-mail Designer, AI Medewerker, en meertalige mogelijkheden
* **console van de Cliënt** - Traditionele interface met geavanceerde het richten en werkschemamogelijkheden

**Tip:** gebruik het Web UI van de Campagne voor snellere, intuïtievere e-mailverwezenlijking met moderne ontwerphulpmiddelen. Gebruik de clientconsole voor complexe doelgerichte of geavanceerde workflowcampagnes.

**Verwante onderwerpen:**

[&#x200B; creeer uw eerste e-mail &#x200B;](create-message.md) | [&#x200B; E-mail ontwerpgids &#x200B;](../send/email.md)

+++

+++ Hoe een levering te plannen?

Met campagnes kunt u leveringen plannen voor toekomstig verzending om verzendtijden te optimaliseren en campagnes te coördineren.

**Plannend opties:**

* **de eigenschappen van de Levering** - verzend onmiddellijk, programma voor specifieke datum/tijd, of vertragen door uren/dagen
* **het niveau van de Campagne** - coördineer alle leveringen binnen een campagne
* **activiteit van de Planner van het Werkschema** - voor terugkomende leveringen, complexe patronen, en gebeurtenis-teweeggebrachte campagnes

De campagne steunt ook optimalisering van de contactdatum (het beste verzendt tijd per ontvanger) en aanpassing van de tijdzone (zelfde lokale tijd voor alle ontvangers).

Leer hoe te [&#x200B; levering van het Programma verzendend &#x200B;](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Kan ik een bijlage toevoegen aan e-mails?

Ja. De campagne steunt statische gehechtheid (het zelfde dossier voor alle ontvangers) en gepersonaliseerde gehechtheid (verschillende dossiers per ontvanger die op profielgegevens worden gebaseerd). Voeg bijlagen toe in de sectie **[!UICONTROL Attachments]** van de leveringseigenschappen.

**Belangrijke overwegingen:**

* Bijlagen onder 1 MB houden voor optimale prestaties
* Bijlagen kunnen spamfilters activeren; test grondig alvorens te verzenden
* Bestandstypen die vaak door e-mailclients worden geblokkeerd (.exe, .zip, .js), worden voorkomen
* Gebruik voor grote bestanden liever bijgehouden downloadkoppelingen

Gebruik veilige bestandsindelingen (PDF, JPEG, PNG, DOCX) en test met zaadadressen voordat de productie wordt verzonden.

Leer meer in de [&#x200B; gids van de Bijlagen E-mail &#x200B;](../send/email.md#attachments)

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

[&#x200B; het volgen van de Verbinding gids &#x200B;](../start/tracking.md) | [&#x200B; het Volgen beste praktijken &#x200B;](../send/send.md)

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

[&#x200B; Controle van de Levering &#x200B;](../send/send.md) | [&#x200B; het Volgen gids &#x200B;](../start/tracking.md)

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

[&#x200B; Ingebouwde leveringsrapporten &#x200B;](../reporting/delivery-reports.md) | [&#x200B; Campagne die &#x200B;](../reporting/gs-reporting.md) rapporteert

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

[&#x200B; het beheersgids van de quarantaine &#x200B;](../send/quarantines.md) | [&#x200B; Stuitbeheer &#x200B;](../send/delivery-failures.md)

+++

## Workflows {#workflows}

Ontdek hoe u workflows kunt gebruiken om processen te automatiseren, gegevens te beheren en complexe marketingcampagnes in Adobe Campaign te organiseren.

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

[&#x200B; bouwt een werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=nl-NL){target="_blank"} | [&#x200B; de activiteiten van het Werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [&#x200B; Beste praktijken van het Werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=nl-NL){target="_blank"} | [&#x200B; het gebruiksgevallen van het Werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Hoe kan ik gegevens importeren in Campagne?

Importeer gegevens naar Campagne met meerdere methoden, afhankelijk van uw behoeften:

**Eenvoudige dossierinvoer:**

* De wizard Importeren gebruiken voor eenmalige CSV/TXT-import met een geleide interface
* Ideaal voor handmatig uploaden en snel laden van gegevens

**Op werkschema-gebaseerde invoer:**

* Workflows maken met **[!UICONTROL Data loading (file)]** activiteit voor complexe importbewerkingen
* Gegevenstransformaties, verrijking en deduplicatie toevoegen
* Herhalende import plannen vanuit SFTP, lokale mappen of cloudopslag

**API integratie:**

* REST API&#39;s gebruiken om gegevens via programmacode te importeren van externe systemen
* Ideaal voor realtime synchronisatie met CRM, e-commerce of andere platforms

**Beste praktijken:** altijd test met kleine steekproeven, gebruik UTF-8 codering, kaartgebieden correct, pas deduplicatieregels toe, en programma grote invoer tijdens off-piekuren.

**Verwante onderwerpen:**

[&#x200B; de beste praktijken van de Invoer &#x200B;](../start/import.md) | [&#x200B; het laden van Gegevens activiteit &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=nl-NL){target="_blank"} | [&#x200B; Terugkerend de invoerwerkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=nl-NL){target="_blank"}

+++

+++ Wat zijn algemene voorbeelden van workflowgebruik in Campagne?

Campagne-workflows kunnen vrijwel elk marketingproces automatiseren. Hier volgen de meest gebruikte gevallen:

**het beheer van Gegevens:**

* **de Invoer en ladingsgegevens** - Automatiseer dossierinvoer van SFTP, API, of wolkenopslag
* **het zuiveren van Gegevens** - Dedupliceerde profielen, normaliseer formaten, verwijder ongeldige verslagen
* **de verrijking van Gegevens** - verbeter profielen met externe gegevens of berekende gebieden
* **beheer van de Lijst** - werk automatisch segmenten bij die op gedrag of criteria worden gebaseerd

**automatisering van de Campagne:**

* **Welkome reeksen** - de Trekker automatiseerde onboarding e-mails voor nieuwe abonnees
* **campagnes van de Verjaardag** - verzend gepersonaliseerde berichten op klanten verjaardagen of verjaardagen
* **re-engagement** - de Inactieve abonnees van het doel met win-back campagnes
* **Verlaat van de Kaart** - verzend herinneringen aan klanten die punten in kar verlieten

**Geavanceerd het richten:**

* **het testen A/B** - Splits publiek en test verschillende inhoudvariaties
* **Dynamische segmentatie** - creeer segmenten die op gedrag in real time of attributen worden gebaseerd
* **Lood het scoren** - bereken en werk loodscores bij die op overeenkomst worden gebaseerd
* **Kanaalorkestatie** - Coördineer overseinen over e-mail, SMS, en duw

**Controle en alarm:**

* **de controle van het Werkschema** - de werkschemastatus van het spoor en verzendt alarm over mislukkingen
* **de controle van de Levering** - de prestaties van de campagne van de monitor en stuitende tarieven
* **onderhoud van het Gegevensbestand** - Automatiseer schoonmaakbeurt van oude logboeken en tijdelijke gegevens

**Integratie en synchronisatie:**

* **synchronisatie van CRM** - houd klantgegevens die met Salesforce, Dynamica, enz. worden gesynchroniseerd.
* **API integraties** - verbind met e-commerceplatforms, analysehulpmiddelen, of douanesystemen
* **gebeurtenis-teweeggebrachte werkschema&#39;s** - Reageer aan gebeurtenissen in real time van websites of apps

**Verwante onderwerpen:**

[&#x200B; het gebruikscasebibliotheek van het Werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [&#x200B; Bouw een werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=nl-NL){target="_blank"} | [&#x200B; Beste praktijken van het Werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=nl-NL){target="_blank"} | [&#x200B; het richten werkschema&#39;s &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=nl-NL){target="_blank"} | [&#x200B; de werkschema&#39;s van het gegevensbeheer &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/about-data-management.html){target="_blank"}

+++

+++ Hoe kan ik Campagnegegevens bijwerken met een workflow?

Gebruik de **[!UICONTROL Update data]** -activiteit in workflows om bulkbewerkingen uit te voeren op uw database:

**Gesteunde verrichtingen:**

* **Tussenvoegsel** - voeg nieuwe verslagen aan het gegevensbestand toe
* **Update** - wijzig bestaande verslagen die op passende criteria worden gebaseerd
* **Tussenvoegsel of update** - voeg nieuwe verslagen toe of werk bestaande degenen (oppas) bij
* **Schrapping** - verwijder verslagen die specifieke criteria aanpassen

**Gemeenschappelijke gebruiksgevallen:**

* Profielkenmerken bijwerken na gegevensverrijking
* Gegevens synchroniseren met externe systemen
* Laaglidmaatschap behouden op basis van gedrag
* Gegevens opschonen en dupliceren
* Wijzigingen in de bulkstatus toepassen (bijvoorbeeld Weigeren, quarantaine)

Configureer de afstemmingssleutels zodat deze op de juiste wijze overeenkomen met de records en kies updateopties (werk alle velden bij of gebruik alleen lege velden).

**Verwante onderwerpen:**

[&#x200B; de gegevensactiviteit van de Update &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=nl-NL){target="_blank"} | [&#x200B; de beheersactiviteiten van Gegevens &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Hoe kan ik mogelijkheden voor gegevensbeheer benutten?

De activiteiten van het gegevensbeheer van de campagne laten verfijnde gegevensverrichtingen binnen werkschema&#39;s voor complexe het richten en segmentatie toe.

**Zeer belangrijke activiteiten van het gegevensbeheer:**

* **Verrijking** - voeg gegevens van verwante lijsten of externe bronnen aan uw werkende bevolking toe
* **Gesplitste** - de populaties van het segment die op criteria worden gebaseerd of willekeurig verdelen
* **Deduplicatie** - verwijder dubbele verslagen die op gespecificeerde sleutels worden gebaseerd
* **gegevens van de Update** - voer bulktussenvoegsel uit, werk, of schrap verrichtingen bij
* **dimensie van de Verandering** - schakelaar richtend dimensies (b.v., van ontvangers aan abonnementen)
* **Intersection/Union/Exclusion** - combineer of filter veelvoudige populaties

**Gemeenschappelijke gebruiksgevallen:**

* Profielen verrijken met aankoopgeschiedenis of gedragsgegevens
* Het publiek van het segment in veelvoudige groepen voor verschillende berichten
* Duplicaten verwijderen vóór levering
* Gegevens uit externe databases (FDA - Federated Data Access) integreren
* Complexe multitable query&#39;s en verbindingen maken

Deze activiteiten staan u toe om met gegevens niet direct in de belangrijkste ontvankelijke lijst te werken en geavanceerde gegevensbestandverrichtingen uit te voeren.

**Verwante onderwerpen:**

[&#x200B; de beheersactiviteiten van Gegevens &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [&#x200B; het richten werkschema&#39;s &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=nl-NL){target="_blank"} | [&#x200B; de activiteit van de Verrijking &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=nl-NL){target="_blank"}

+++

+++ Kan ik het verzenden van persoonlijke berichten automatiseren?

Ja. De werkstromen laten volledig geautomatiseerde gepersonaliseerde berichtcampagnes toe die op ontvankelijke gegevens, gedrag, en douanecriteria worden gebaseerd.

**het werkschemastructuur van de Automatisering:**

1. **Vraag** - selecteer uw doelpubliek dat op criteria wordt gebaseerd
1. **Verrijking** - voeg verpersoonlijkingsgegevens van verwante lijsten toe
1. **Gesplitst** - Segment in groepen voor verschillende (facultatieve) berichtvarianten
1. **Levering** - verzend gepersonaliseerde berichten met fusievelden
1. **Planner** - Opstelling terugkomende uitvoering voor geautomatiseerde campagnes

**de opties van Personalization:**

* Bronprofielgegevens gebruiken (naam, locatie, voorkeuren)
* Inclusief gedragsgegevens (aankoopgeschiedenis, betrokkenheidsscores)
* Voorwaardelijke inhoud toepassen op basis van segmenten of kenmerken
* Dynamische waarden berekenen (loyaliteitspunten, vervaldatums)

Veelvoorkomende scenario&#39;s: verjaardagscampagnes, het verlaten van het winkelwagentje, loyaliteitsprogramma&#39;s, win-back campagnes, en gebeurtenis-teweeggebrachte berichten.

**Verwante onderwerpen:**

[&#x200B; de gids van Personalization &#x200B;](../send/personalize.md) | [&#x200B; het gebruikscase van het Werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=nl-NL){target="_blank"} | [&#x200B; de activiteit van de Verrijking &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe kan ik een publiek in subsets splitsen met een workflow?

Gebruik de **[!UICONTROL Split]** -activiteit om één populatie te verdelen in meerdere subsets op basis van criteria of distributieregels.

**Gesplitste methodes:**

* **het Filtreren voorwaarden** - creeer subsets die op criteria (b.v., leeftijdsgroepen, plaats, status van VIP worden gebaseerd)
* **distributie van het Percentage** - Splits willekeurig in gelijke of douanepercentages voor het testen A/B
* **verslagen van de Grensgrens** - Beperk subsetgrootte (eerste N verslagen, bovenkant X%, willekeurige selectie)
* **Gegevens groeperen** - creeer één ondergroep per verschillende waarde (bijvoorbeeld, één ondergroep per land)

**Gemeenschappelijke gebruiksgevallen:**

* A/B-tests met controlegroepen
* Kanaalvoorkeur voor routering (e-mail versus SMS)
* Progressieve rollout (verstuur naar 10% en vervolgens naar 90%)
* Segmentspecifieke berichten (VIP, reguliere, nieuwe klanten)
* Taakverdeling over meerdere leveringsservers

Elke gesplitste subset leidt naar een aparte overgang, waardoor verschillende verwerking of levering voor elke groep mogelijk is.

**Verwante onderwerpen:**

[&#x200B; Gesplitste activiteit &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=nl-NL){target="_blank"} | [&#x200B; A/B testende gids &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Hoe kan ik ontvangergegevens bijwerken uit een extern bestand?

Ja. Gebruik workflows om Campagnegegevens bij te werken met waarden uit externe bestanden (CSV, TXT).

**structuur van het Werkschema:**

1. **het laden van Gegevens (dossier)** - Laad het externe dossier en kaartkolommen
1. **Verrijking** (facultatief) - voeg extra gegevens of transformaties toe
1. **Verzoening** - bepaal sleutels om dossierverslagen met gegevensbestandverslagen (b.v., e-mailadres, ontvankelijke identiteitskaart) aan te passen
1. **gegevens van de Update** - kies updateopties:
   * Alleen overeenkomende records bijwerken
   * Bestaande velden of alleen lege velden bijwerken
   * Nieuwe records invoegen als er geen overeenkomst is gevonden

**Gemeenschappelijke scenario&#39;s:**

* Profielkenmerken bijwerken van CRM-export
* Abonnementsstatussen vernieuwen vanaf externe systemen
* Synchroniseer loyaliteitspunten of klantenscores
* Voorkeuren voor opt-in/opt-out bijwerken
* Profielen verrijken met gedragsgegevens

**Beste praktijken:** gebruik unieke herkenningstekens voor verzoening, bevestigt gegevens vóór update, test met kleine steekproeven, en programma regelmatige updates voor aan de gang zijnde synchronisatie.

**Verwante onderwerpen:**

[&#x200B; de gegevensgids van de Invoer &#x200B;](../start/import.md) | [&#x200B; het laden van Gegevens activiteit &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=nl-NL){target="_blank"} | [&#x200B; de gegevensactiviteit van de Update &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe kan ik nieuwe ontvangers identificeren en richten?

De werkschema&#39;s van het gebruik met vraagactiviteiten om onlangs toegevoegde ontvangers te identificeren en geautomatiseerde welkomstcampagnes teweeg te brengen.

**benadering van de Vraag:**

Maak een query-filtering op het veld **[!UICONTROL Created date]** om ontvangers te selecteren die binnen een specifiek tijdsbestek zijn toegevoegd (bijvoorbeeld vorige week, afgelopen 24 uur).

**Geautomatiseerde welkomstwerkschemastructuur:**

1. **Planner** - Looppas dagelijks of bij specifieke intervallen
1. **Vraag** - Uitgezochte ontvangers die sinds laatste uitvoering worden gecreeerd
1. **Deduplicatie** (facultatief) - verzeker geen duplicaten
1. **Levering** - verzend welkomstbericht
1. **gegevens van de Update** (facultatief) - de ontvangers van het teken als &quot;verwelkomd&quot;

**Geavanceerde techniek met aggregaten:**

Gebruik statistische functies om de meest recente toevoegingen dynamisch te identificeren en te vergelijken met eerder verwerkte ontvangers voor geavanceerde nieuwe ontvankelijkheidsdetectie.

**Verwante onderwerpen:**

[&#x200B; activiteit van de Vraag &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=nl-NL){target="_blank"} | [&#x200B; Gebruikend aggregaten &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=nl-NL){target="_blank"} | [&#x200B; Welkome programma&#39;s &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe gebruik ik workflowactiviteiten?

De workflows van de campagne worden gebouwd gebruikend vier hoofdcategorieën van activiteiten, elk die specifieke doeleinden dienen:

**richtend activiteiten** - bepaal en verfijn uw publiek

* Query, splitsen, dedupliceren, verrijken, doorsnede, Vereniging, Uitsluiting
* Gebruik deze om ontvangers, segmentpopulaties en gegevensbronnen te selecteren

**de controleactiviteiten van de Stroom** - beheer werkschemalogica en timing

* Planner, Wacht, Test, Fork, AND-join, OR-join, Jump
* De uitvoeringsstroom van de controle, voegt voorwaarden toe en beheert parallelle wegen

**activiteiten van de Actie** - voer verrichtingen uit en verzend berichten

* Levering, Gegevens bijwerken, Gegevens laden (bestand), Gegevens extraheren (bestand), JavaScript-code
* Voer databasebewerkingen, bestandsoverdrachten en het verzenden van berichten uit

**de activiteiten van de Gebeurtenis** - Reageer aan externe trekkers

* Extern signaal, Bestandscollector, HTTP-overdracht, SMS, e-mail
* Binnenkomende gegevens en externe systeeminteracties verwerken

Als u activiteiten wilt gebruiken, sleept u deze van het palet naar het werkstroomcanvas, dubbelklikt u om parameters te configureren en verbindt u ze met overgangen.

**Verwante onderwerpen:**

[&#x200B; het richten activiteitenverwijzing &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=nl-NL){target="_blank"} | [&#x200B; Verwijzing van de de controleactiviteiten van de Stroom &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=nl-NL){target="_blank"} | [&#x200B; de activiteitenverwijzing van de Actie &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=nl-NL){target="_blank"} | [&#x200B; Verwijzing van de activiteiten van de Gebeurtenis &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=nl-NL){target="_blank"}

+++

+++ Wat zijn best practices voor workflows?

Volg deze best practices om efficiënte, onderhoudsbare en betrouwbare workflows te maken:

**Ontwerp en organisatie:**

* Gebruik duidelijke, beschrijvende namen voor workflows en activiteiten
* Labels en beschrijvingen toevoegen aan documentlogica
* Gerelateerde activiteiten visueel groeperen voor leesbaarheid
* Complexe processen onderbrengen in meerdere kleinere workflows

**optimalisering van Prestaties:**

* Grootte van queryresultaten beperken met de juiste filters
* Tijdelijke tabellen gebruiken voor tussentijdse gegevensopslag
* Workflows plannen die veel resources vereisen tijdens niet-piekuren
* Overbodige lussen en herhalingen voorkomen

**de behandeling en controle van de Fout:**

* Paden voor foutafhandeling toevoegen met toezichthouders
* Waarschuwingen voor mislukte workflows configureren
* Testen met kleine gegevensmonsters vóór volledige uitvoering
* Regelmatig uitvoeringslogboeken controleren voor prestatieproblemen

**Onderhoud en bestuur:**

* Verouderde workflows archiveren of verwijderen
* Wijzigingen in werkstroom van versiebeheer en documentwijzigingen
* Complexiteit werkstroom beperken (doel voor &lt; 20 activiteiten)
* Workflowsjablonen gebruiken voor terugkerende patronen

**Veiligheid en gegevensbeheer:**

* Pas de juiste operatormachtigingen toe
* Tijdelijke gegevens opschonen met werkstroomopruiming
* Harde-coderingswaarden vermijden—variabelen gebruiken en opties
* Workflows die slecht presteren regelmatig evalueren en optimaliseren

**Verwante onderwerpen:**

[&#x200B; de beste praktijken van het Werkschema gids &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=nl-NL){target="_blank"} | [&#x200B; Bouw een werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=nl-NL){target="_blank"} | [&#x200B; werkschema&#39;s van de Monitor &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=nl-NL){target="_blank"}

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

[&#x200B; taal van de Verandering in het Web UI van de Campagne &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [&#x200B; krijgen begonnen met de cliëntconsole van de Campagne &#x200B;](connect.md)

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

[&#x200B; documentatie van het Controlebord &#x200B;](https://experienceleague.adobe.com/nl/docs/control-panel/using/control-panel-home){target="_blank"} | [&#x200B; de zelfstudievideo&#39;s van het Comité van de Controle &#x200B;](https://experienceleague.adobe.com/nl/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

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

[&#x200B; Spoor en controleer leveranties &#x200B;](tracking.md) | [&#x200B; vorm getraceerde verbindingen &#x200B;](../send/email.md)

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

[&#x200B; Ongeveer leverability in Campagne &#x200B;](../send/about-deliverability.md) | [&#x200B; Gids van de Beste praktijken van de Levering &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}

+++

+++ Met welke externe databases kan ik een campagne verbinden?

Campagne v8 biedt ondersteuning voor FDA-verbindingen (Federated Data Access) met grote databasesystemen voor bedrijven, zodat u de bestaande gegevensinfrastructuur kunt benutten.

**Gesteunde gegevensbestanden:**

* **de gegevensbestanden van de Wolk:** Amazon Redshift, Google BigQuery, Snowflake, Azure Synapse Analytics
* **de gegevensbestanden van de Onderneming:** Oracle, de Server van Microsoft SQL, PostgreSQL, MySQL
* **de entrepots van Gegevens:** Teradata, Vertica, SAP HANA
* **Grote gegevens:** Hadoop via Hive

**Platform-specifieke overwegingen:** de gesteunde gegevensbestandversies en de verbindingsvereisten variëren. Campagne v8 als Beheerde Cloud Service kan specifieke netwerk- en beveiligingsvereisten voor externe databasetoegang hebben.

**Belangrijk:** controleer altijd de officiële verenigbaarheidsmatrijs voor uw versie van de Campagne v8 om steun voor specifieke gegevensbestandversies te bevestigen en behoorlijk vergunning te verzekeren voor externe gegevensbestandschakelaars.

**Verwante onderwerpen:**

[&#x200B; de matrijs van de Verenigbaarheid &#x200B;](compatibility-matrix.md) | [&#x200B; vormen verbindingen FDA &#x200B;](../connect/fda.md)

+++

+++ Kan Adobe Campaign integreren met CRM-systemen?

Ja. De campagne verstrekt inheemse schakelaars van CRM voor naadloze bidirectionele synchronisatie tussen Campagne en uw systeem van CRM, die verenigbare klantengegevens over platforms verzekeren.

**Ondersteunde systemen van CRM:**

* **Salesforce** - Leads, contacten, rekeningen, kansen, campagnes
* **Microsoft Dynamics 365** - Contacten, rekeningen, lood, douaneentiteiten
* Andere CRM&#39;s via aangepaste API-integratie

**wat syncs:**

* **van CRM aan Campagne:** de verslagen van het Contact, rekeningsinformatie, leidt, douanegebieden, segmentatiegegevens
* **van Campagne aan CRM:** Logboeken van de levering, het volgen gegevens, betrokkenheidsmetriek, campagnereacties, abonnementsstatus

**de wijzen van de Synchronisatie:**

* **Gepland** - Automatische synchronisatie bij bepaalde intervallen (uur, dagelijks)
* **Hand** - op bestelling synchronisatie die door exploitanten wordt teweeggebracht
* **Real-time** - via API voor directe updates (douaneontwikkeling)

**Configuratie:** de ingebouwde de schakelaarmedewerker van CRM van de Campagne van het Gebruik aan kaartCRM gebieden aan de attributen van de Campagne, uitgezochte lijsten aan synchronisatie, en planningssynchronisatie. De schakelaar behandelt conflictoplossing en handhaaft gegevensconsistentie.

**Beste praktijken:** Begin met read-only synchronisatie aan testafbeelding, dan laat bidirectionele synchronisatie toe. Synchronisatielogboeken controleren op fouten en in beide systemen schone gegevens bijhouden.

**Verwante onderwerpen:**

[&#x200B; de schakelaarconfiguratie van CRM &#x200B;](../connect/crm.md) | [&#x200B; de activiteiten van CRM van het Werkschema &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=nl-NL){target="_blank"}

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

**Verwante onderwerpen:**

[Client-console installeren en configureren](connect.md)

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
* **groep van de Exploitant** - Montages die door alle groepsleden worden geërft

**Verwante onderwerpen:**

[&#x200B; vorm montages UI &#x200B;](../config/ui-settings.md) | [&#x200B; de toestemmingen van de Gebruiker &#x200B;](gs-permissions.md)

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

[&#x200B; breid gegevensmodel &#x200B;](../dev/extend-schema.md) uit | [&#x200B; de structuur van het Schema &#x200B;](../dev/schemas.md) | [&#x200B; beste praktijken van het gegevensmodel &#x200B;](../dev/datamodel-best-practices.md)

+++

## Rapportage {#reporting}

Krijg inzicht in de rapporteringsmogelijkheden van de Campagne, met inbegrip van ingebouwde rapporten, douanerapporten, en hulpmiddelen van de gegevensanalyse zoals kubussen.

+++ Hoe kan ik nieuwe rapporten maken?

De campagne biedt meerdere rapportopties afhankelijk van uw behoeften en technische expertise. U kunt ingebouwde rapporten gebruiken, douanerapporten in de cliëntconsole tot stand brengen, of visuele dashboards ontwerpen in het Web UI van de Campagne.

**het Melden van opties:**

* **Ingebouwde rapporten** - klaar-aan-gebruiklevering, campagne, en het volgen rapporten toegankelijk van het **[!UICONTROL Reports]** lusje
* **Beschrijvende analyse** - Snelle statistische rapporten over om het even welke gegevens met een tovenaar-gedreven interface
* **de rapporten van de Douane** - Geavanceerde die rapporten door technische gebruikers worden gebouwd gebruikend de rapporteringsredacteur
* **Web UI dashboards** - Moderne visuele rapporten en dashboards met belemmering-en-dalingsinterface
* **Kubussen** - Multidimensionale gegevensexploratie en de analyse van de spillijst

**Belangrijk:** de Campagne wordt ontworpen voor het op de markt brengen van verrichtingen die, niet als gespecialiseerd bedrijfsintelligentiehulpmiddel melden. Voor complexe analytische behoeften kunt u overwegen om te integreren met Adobe Analytics of specifieke BI-platforms.

**Verwante onderwerpen:**

[&#x200B; worden begonnen met het melden &#x200B;](../reporting/gs-reporting.md) | [&#x200B; rapporten UI van het Web van de Campagne &#x200B;](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

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

Leer meer over [&#x200B; Beschrijvende analyse &#x200B;](../reporting/built-in-reports.md)

+++

+++ Hoe kan ik geavanceerde rapporten over mijn gegevens ontwerpen?

De campagne biedt twee benaderingen voor het creëren van geavanceerde douanerapporten aan: technische rapporten in de cliëntconsole voor complexe analyse, en visuele dashboards voor gemakkelijkere rapportbouw.

In de clientconsole kunt u:

* Complexe rapporten maken met SQL-query&#39;s en aangepaste berekeningen
* Rapporten met meerdere pagina&#39;s maken met grafieken, tabellen en draaitabellen
* Voorwaardelijke opmaak en dynamische inhoud ontwerpen
* Toegang tot het volledige gegevensmodel van de Campagne en externe gegevensbestanden (FDA)

Leer hoe te om [&#x200B; douanerapporten (cliëntconsole) te creëren &#x200B;](../reporting/custom-reports.md)

+++

+++ Wat is een kubus en hoe kan ik deze gebruiken voor rapportage?

De kubussen zijn multidimensionele gegevensstructuren die bedrijfsgebruikers toelaten om de gegevens van de Campagne door spillijsten zonder technische vaardigheden te onderzoeken en te analyseren. Beschouw ze als vooraf geconfigureerde gegevensmodellen die complexe rapportage vereenvoudigen.


* De technische gebruikers creëren en vormen kubussen die afmetingen (tijd, aardrijkskunde, kanalen) en maatregelen (opent, klikt, opbrengst) bepalen
* Zakelijke gebruikers selecteren een kubus wanneer ze rapporten maken en dimensies slepen en neerzetten om gegevens te verkennen
* Gegevens worden automatisch samengevoegd en berekend op basis van de kubusconfiguratie
* De resultaten kunnen worden weergegeven als draaitabellen, grafieken of worden geëxporteerd naar Excel

Leer hoe te [&#x200B; gegevens met kubussen &#x200B;](../reporting/gs-cubes.md) ontdekken

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

**Ingebouwde enquêterapporten:**

* **Algemeen rapport** - de tendensen van de Reactie in tijd, distributie door oorsprong en taal
* **Uitsplitsing van reacties** - Gedetailleerde uitsplitsing van antwoorden voor elke vraag
* **het rapport van de Documentatie** - Visuele vertegenwoordiging van de onderzoeksstructuur

**Geavanceerde analyse:**

* enquêteantwoorden openen op het tabblad **[!UICONTROL Responses]** en gegevens exporteren
* Gebruik **[!UICONTROL Survey responses]** -activiteit in workflows om ontvangers als doel in te stellen op basis van hun antwoorden
* De onderzoeksgegevens van de combinatie met andere gegevens van de Campagne voor segmentatie en verpersoonlijking
* Aangepaste rapporten en kubussen maken voor multidimensionale enquêteanalyse

**Verwante onderwerpen:**

[&#x200B; worden begonnen met onderzoeken &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [&#x200B; de rapporten van het Onderzoek &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Hoe kan ik de toegang tot mijn rapporten delen?

De campagne verstrekt flexibele opties om rapporten met verschillende gebruikersgroepen te delen, die zicht en toegangstoestemmingen controleren die op rollen en verantwoordelijkheden worden gebaseerd.

**de toegangscontrole van het Rapport:**

* **toestemmingen van de Omslag** - Plaats rapporten in omslagen met aangewezen lees/schrijf toegang voor gebruikersgroepen
* **Genoemde rechten** - wijs specifieke rechten toe om, rapporten te bekijken tot stand te brengen of te wijzigen
* **context van de Vertoning** - bepaal waar de rapporten verschijnen: in **[!UICONTROL Reports]** omslag, campagnelusjes, of leveringsschermen
* **het delen van het Web UI** - het dashboardverbindingen van het aandeel met teamleden door het Web UI van de Campagne

**hoe te om toegang te vormen:**

1. Sla uw rapport op in een specifieke map in de clientconsole
2. Machtigingen voor maptoegang configureren voor relevante groepen operatoren
3. Bepaal rapporteigenschappen: rapporttype, vertoningscontext, en beschikbaarheid
4. Toegang testen met een gebruiker uit de doelgroep voordat de toepassing breder wordt

**Beste praktijken:** creeer specifieke rapportomslagen voor verschillende teams (marketing, verrichtingen, beheer) met op maat gemaakte toegangstoestemmingen. Het rapportdoel van het document en verfrist programma&#39;s.

**Verwante onderwerpen:**

[&#x200B; de rapporten van de Douane &#x200B;](../reporting/custom-reports.md) | [&#x200B; de toestemmingen van de Gebruiker &#x200B;](gs-permissions.md)

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

[&#x200B; de rapporten van de Douane &#x200B;](../reporting/custom-reports.md) | [&#x200B; rapporten UI van het Web van de Campagne &#x200B;](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Ontwikkelaars {#developers}

Toegang tot technische informatie voor ontwikkelaars, waaronder gegevens over gegevensmodellen, schema&#39;s, API&#39;s en aanpassingsmogelijkheden.

+++ Wat is het gegevensmodel van de Campagne?

Het gegevensmodel van de campagne is een schema-gedreven relationele gegevensbestandstructuur die bepaalt hoe de marketing gegevens wordt georganiseerd en verwant. Het bestaat uit ingebouwde lijsten voor kern marketing voorwerpen (ontvangers, leveringen, campagnes) en kan worden uitgebreid om aan uw specifieke bedrijfsbehoeften te voldoen.

**Zeer belangrijke concepten van het gegevensmodel:**

* **Schema&#39;s** - de definities van XML beschrijvend lijststructuur, gebieden, en verhoudingen
* **Ingebouwde lijsten** - de marketing van de Kern entiteiten (ontvangers, leveringen, werkschema&#39;s, campagnes)
* **Verbindingen** - Verhoudingen tussen lijsten (1-1, 1-N, N-N)
* **Opsommingen** - Vooraf bepaalde waardelijsten voor dropdown gebieden
* **Uitbreidingen** - de gebieden en de lijsten van de Douane die aan het standaardmodel worden toegevoegd

**Belangrijkste ingebouwde schema&#39;s:**

* **Ontvanger (nms :recipient)** - de profielen van de Klant en contactinformatie
* **Levering (nms :delivery)** - E-mail, SMS, en duwcampagnes
* **Werkschema (xtk :workflow)** - de processen van de Automatisering
* **Campagne (nms :operation)** - de campagneorkest van de marketing
* **het Volgen logboeken** - opent, klikt, en betrokkenheidsgegevens

**waarom het van belang is:** Begrijpen van het gegevensmodel is essentieel voor het creëren van werkschema&#39;s, het bouwen van vragen, het uitbreiden van schema&#39;s, en het ontwikkelen van douaneintegratie. De op schema-gebaseerde benadering verzekert gegevensconsistentie en laat krachtige het vragen mogelijkheden toe.

**Verwante onderwerpen:**

[&#x200B; het gegevensmodel van de Campagne &#x200B;](../dev/datamodel.md) | [&#x200B; Beste praktijken van het gegevensmodel &#x200B;](../dev/datamodel-best-practices.md)

+++

+++ Hoe te met de schema&#39;s van de Campagne werken?

De schema&#39;s zijn de stichting van de gegevensstructuur van de Campagne, die lijsten, gebieden, en verhoudingen in het formaat van XML bepaalt. Kennis van schema&#39;s is van cruciaal belang voor aanpassing, integratie en geavanceerde workflowontwikkeling.

**Welke schema&#39;s bepalen:**

* **structuur van de Lijst** - de lijsten van het Gegevensbestand en hun overeenkomstige toepassingsvoorwerpen
* **Eigenschappen van het Gebied** - de types van Gegevens, etiketten, bevestigingsregels, en standaardwaarden
* **Verhoudingen** - Verbindingen tussen lijsten (toetreedt) en kardinaliteit
* **Indexen** - de optimalisering van het Gegevensbestand voor vraagprestaties
* **controle van de Toegang** - welke gebieden gebruikers kunnen bekijken en wijzigen

**Werkend met schema&#39;s:**

* **schema&#39;s van de Mening:** Toegang via **[!UICONTROL Administration > Configuration > Data schemas]** in de cliëntconsole
* **breidt schema&#39;s uit:** creeer uitbreidingsschema&#39;s (b.v., `cus:recipient` breidt `nms:recipient`) uit om douanevelden toe te voegen zonder kernschema&#39;s te wijzigen
* **creeer douaneschema&#39;s:** bouw volledig nieuwe lijsten voor zaken-specifieke gegevens
* **gegevensbestand van de Update:** pas schemaveranderingen toe gebruikend **[!UICONTROL Tools > Advanced > Update database structure]**

**Gemeenschappelijke gebruiksgevallen:**

* Aangepaste velden toevoegen aan de tabel met ontvangers (bedrijfs-id, loyaliteitslaag, voorkeuren)
* Aangepaste tabellen maken voor producten, winkels of transacties
* Relaties definiëren tussen aangepaste en ingebouwde tabellen
* Bedrijfsspecifieke gegevensmodellen implementeren

**Belangrijk:** wijzig nooit direct ingebouwde schema&#39;s. Gebruik altijd extensieschema&#39;s om de compatibiliteit met upgrades en Adobe-ondersteuning te behouden.

**Verwante onderwerpen:**

[&#x200B; worden begonnen met schema&#39;s &#x200B;](../dev/schemas.md) | [&#x200B; breid een schema &#x200B;](../dev/extend-schema.md) uit

+++

+++ Hoe te om een douane ontvankelijke lijst te gebruiken?

De campagne staat u toe om een douanetabel in plaats van de ingebouwde ontvankelijke lijst te gebruiken wanneer uw zaken een verschillende gegevensstructuur voor het richten vereisen (b.v., B2B rekeningen, abonnees, lood, of externe contacten).

**waarom gebruik een douane ontvankelijke lijst:**

* Doel B2B-ondernemingen of organisatorische eenheden in plaats van individuele contacten
* Afzonderlijke abonneegegevens van belangrijkste klantengegevensbestand
* Een bestaande klantentabel van een ander systeem gebruiken
* Implementeer architecturen voor meerdere merken met aparte contacttabellen
* Voldoen aan specifieke vereisten inzake gegevensbeheer

**de stappen van de Implementatie:**

1. Uw aangepaste schema maken voor het definiëren van de tabelstructuur voor de ontvanger
2. Inclusief verplichte velden (e-mail, primaire sleutel, uitsluitingsvlaggen)
3. Doeltoewijzingen configureren om uw tabel te koppelen aan leveringen
4. De leveringsmalplaatjes van de update om de nieuwe doelafbeelding te gebruiken
5. Workflows en query&#39;s aanpassen om naar de aangepaste tabel te verwijzen

**Zeer belangrijke overwegingen:**

* Aangepaste tabellen voor ontvangers moeten vereiste velden voor leveringen bevatten (e-mail, uitsluitingen, bijhouden)
* Workflows en formulieren moeten worden aangepast aan de aangepaste structuur
* Voor sommige ingebouwde functies moet de configuratie mogelijk worden aangepast
* Testen is van essentieel belang voordat productiecampagnes worden gemigreerd

**Beste praktijken:** Begin met het uitbreiden van de standaard ontvankelijke lijst alvorens een douanetabel te overwegen. Aangepaste ontvankelijke lijsten voegen ingewikkeldheid toe en zouden slechts moeten worden gebruikt wanneer echt noodzakelijk.

**Verwante onderwerpen:**

[&#x200B; de ontvankelijke lijst van de Douane &#x200B;](../dev/custom-recipient.md) | [&#x200B; de afbeeldingen van het Doel &#x200B;](../audiences/target-mappings.md)

+++

+++ Wat zijn de beste praktijken om vragen in Campagne te bepalen?

De vraagredacteur van de campagne is een krachtig visueel hulpmiddel om gegevensbestandvragen zonder SQL kennis op te bouwen. Het beheersen van het is essentieel voor efficiënte richten, segmentatie, en gegevensanalyse.

**waar de vragen worden gebruikt:**

* **de activiteiten van het Werkschema** - Vraag, Gesplitst, gegevens van de Update, de activiteiten van de Verrijking
* **Levering richtend** - bepaal ontvankelijke populaties voor campagnes
* **Lijsten** - creeer dynamische of statische ontvankelijke lijsten
* **Rapporten** - bouw de extracties en de analyse van douanegegevens
* **Filters** - creeer herbruikbare het richten criteria

**beste praktijken van de Vraag:**

* **Begin eenvoudig** - bouw vragen incrementeel, het testen bij elke stap
* **het filtreren van het gebruik dimensies** - de verhoudingen van de hefboomwerking tussen lijsten (ontvangers → leveringen → volgende logboeken)
* **optimaliseer prestaties** - Index vaak vraagde gebieden, vermijd complexe berekende gebieden
* **Hefboomwerking predefined filters** - hergebruik en combineer bestaande filters voor consistentie
* **Test met kleine steekproeven** - bevestigt vraaglogica alvorens op volledig gegevensbestand te lopen
* **complexe vragen van het Document** - voeg beschrijvingen voor onderhoud en kennisoverdracht toe

**Gemeenschappelijke vraagpatronen:**

* Doelontvangers die specifieke levering hebben geopend: Filter op trackinglogboeken gekoppeld aan ontvangers
* Inactieve contactpersonen zoeken: query op laatste leveringsdatum of trackingactiviteit
* Segmenteren op gedrag: criteria voor levering, bijhouden en profiel combineren
* Eerdere ontvangers uitsluiten: gebruik ingestelde bewerkingen (union, intersection, exclusion)

**de generische vraagredacteur van de Toegang:** **[!UICONTROL Tools > Generic query editor]** voor ad hoc gegevensbestandexploratie en gegevensextractie buiten werkschema&#39;s.

**Verwante onderwerpen:**

[&#x200B; redacteur van de Vraag &#x200B;](../start/query-editor.md) | [&#x200B; de activiteit van de Vraag in werkschema&#39;s &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=nl-NL){target="_blank"}

+++

+++ Hoe kan ik een gegevenspakket importeren?

Met gegevenspakketten kunt u Campagnerconfiguraties (schema&#39;s, workflows, typologieën, filters) en gegevens tussen instanties exporteren en importeren. Dit is essentieel voor het opstellen van configuraties van ontwikkeling aan productie of het delen van componenten over organisaties.

**wat kan worden verpakt:**

* **de voorwerpen van de Configuratie** - Schema&#39;s, werkschema&#39;s, typologische regels, vormen, filters
* **componenten van de Campagne** - de malplaatjes van de Levering, campagnemalplaatjes, inhoudsblokken
* **montages van de Toepassing** - Exploitanten, exploitantgroepen, omslagstructuren
* **Gegevens** - de Ontvankelijke lijsten, zaadadressen, inhoudsfragmenten
* **de ontwikkelingen van de Douane** - de code van JavaScript, SQL manuscripten, Webtoepassingen


**de types van Pakket:**

* **het pakket van de Gebruiker** - de configuraties van de Douane u creeert en uitvoert
* **het pakket van het Platform** - Adobe-Verstrekte eigenschappen en updates
* **het pakket van Gegevens** - bevat daadwerkelijke gegevensverslagen, niet alleen structuur

**Beste praktijken:**

* Pakketten altijd exporteren vanuit dezelfde of een oudere versie van Campagne
* Invoer van testpakketten in de ontwikkelomgeving vóór de productie
* Inhoud en afhankelijkheden van documentpakketten
* Versiebeheer gebruiken voor pakket-XML-bestanden
* Back-up maken van instantie vóór grote pakketimport

Leer meer over hoe te [&#x200B; werken met gegevenspakketten &#x200B;](../dev/packages.md)

+++

+++ Waar vind ik de lijst met API&#39;s voor Campagne v8?

Campagne v8 biedt uitgebreide API-documentatie die zowel SOAP API&#39;s (voor interactie met de clientconsole) als REST API&#39;s (voor moderne integratie) omvat. De API-naslaggids bevat alle beschikbare methoden, parameters en responsindelingen.

**Campagne API types:**

* **SOAP APIs** - Traditionele APIs voor de verrichtingen van de de cliëntconsole van de Campagne, schemamanipulatie, en werkschemacontrole
* **REST APIs** - Moderne HTTP APIs voor externe systeemintegratie, profielbeheer, en gebeurtenis die teweegbrengen
* **JavaScript APIs** - server-zij scripting APIs voor werkschemaactiviteiten en douane bedrijfslogica

**API documentatiemiddelen:**

* **Volledige API verwijzing:** Uitgebreide documentatie van SOAP API met methodehandtekeningen, parameters, en voorbeelden
* **REST API gids:** Moderne eindpunten van REST voor profielen, gebeurtenissen, en organisatorische eenheden
* **JavaScript API:** server-zijfuncties beschikbaar in werkschemamuscripten en Webtoepassingen

**Gemeenschappelijke API gebruiksgevallen:**

* Integreer Campagne met CRM, ERP, of douanetoepassingen
* Campagne en workflowuitvoering automatiseren
* Gegevens synchroniseren tussen systemen in real-time
* Aangepaste oplossingen voor bewaking en waarschuwingen ontwikkelen
* Externe interfaces maken voor Campagnegegevens en -bewerkingen

**Toegang:** [&#x200B; de documentatie van de Campagne v8 API &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=nl){target="_blank"}

+++


+++ Hoe kan ik workflows controleren vanuit API?

Met campagne-API&#39;s kunt u de uitvoering van de workflow programmatisch beheren en controleren, externe bewakingssystemen, geautomatiseerde waarschuwingen en aangepaste orchestratieoplossingen inschakelen.

**wat u via API kunt doen:**

* **werkschema&#39;s van het Begin** - de werkschemauitvoering van de trekker programmatically
* **de werkschema&#39;s van de Pauze/van de Hervat** - de stroom van de werkschemauitvoering van de controle
* **werkschema&#39;s van het Einde** - beëindig lopende werkschema&#39;s
* **het werkschemastatus van de Vraag** - controleer als de werkschema&#39;s lopen, gepauzeerd of voltooid zijn
* **wint logboeken** terug - de logboeken van de werkschemauitvoering van de toegang en foutenmeldingen
* **de activiteitenvooruitgang van de Monitor** - de voltooiing van de individuele werkschemaactiviteit van het spoor

**API eindpunt:**

Alle werkschemacontrolebevelen gebruiken het zelfde eindpunt van POST met verschillende methodeparameters:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Beschikbare bevelen:**

* `{"method":"start"}` - Een workflow starten
* `{"method":"pause"}` - Een actieve workflow pauzeren
* `{"method":"resume"}` - Een gepauzeerde workflow hervatten
* `{"method":"stop"}` - Een workflow stoppen

**Gemeenschappelijke gebruiksgevallen:**

* Aangepaste controledashboards maken met de status van de workflow
* Automatische waarschuwingen implementeren wanneer workflows mislukken of te lang duren
* Workflows ordenen van externe planners of gebeurtenissystemen
* Workflowafhankelijkheden maken voor meerdere campagneinstanties
* Rapporten voor aangepaste workflowuitvoering genereren

**Beste praktijken:** combineer API controle met het spoor van de werkschemacontrole voor uitvoerig werkschemabeheer. Gebruik externe controlehulpmiddelen om werkschema SLAs en prestatiesmetriek te volgen.

Leer hoe te [&#x200B; werkschema&#39;s van de Controle via API &#x200B;](../dev/api/controlling-a-workflow.md)

+++

+++ Hoe kan ik de databasestructuur bijwerken?

Na het wijzigen van de schema&#39;s van de Campagne (het toevoegen van gebieden, het creëren van lijsten, het veranderen van gegevenstypes), moet u de fysieke gegevensbestandstructuur bijwerken om uw veranderingen toe te passen. Deze synchronisatie zorgt ervoor dat de database overeenkomt met uw schemadefinities.

**wanneer de gegevensbestandupdates nodig zijn:**

* Nieuwe velden toevoegen aan bestaande schema&#39;s
* Aangepaste tabellen maken of ingebouwde tabellen uitbreiden
* Veldeigenschappen wijzigen (gegevenstype, lengte, vereiste status)
* Koppelingen tussen tabellen toevoegen of verwijderen
* Nieuwe indexen maken voor queryoptimalisatie


**Belangrijke overwegingen:**

* **Steun eerst** - altijd file uw gegevensbestand vóór structurele veranderingen
* **Test in ontwikkeling** - bevestigt schemaveranderingen in dev milieu vóór productie
* **planning van de Onderbreking** - de grote structurele veranderingen kunnen korte onderhoudvensters vereisen
* **voor de Beheerde Diensten van de Wolk** - coördineer belangrijke veranderingen met de steun van Adobe
* **Omkeerbaarheid** - sommige veranderingen (als het verwijderen van gebieden) kunnen gegevensverlies veroorzaken

**Beste praktijken:** het schema van het gebruik versioning en verandering het volgen. Documenteer alle wijzigingen van het douaneschema voor onderhoud en het oplossen van problemen.

**Verwante onderwerpen:**

[&#x200B; de gegevensbestandstructuur van de Update &#x200B;](../dev/update-database-structure.md) | [&#x200B; breid schema &#x200B;](../dev/extend-schema.md) uit

+++

## Privacy {#privacy}

Begrijp hoe Adobe Campaign u helpt aan privacyverordeningen zoals GDPR en CCPA te voldoen, en de verzoeken van de gegevenssubject te beheren.

+++ Wat zijn de belangrijkste privacyconcepten in Campagne?

De campagne helpt u aan privacyverordeningen (GDPR, CCPA, PDPA, LGPD) door hulpmiddelen te voldoen om de rechten van de gegevenssubject, toestemming, en gegevensbehoud te beheren. Belangrijke concepten zijn onder andere privacyregels, identificatie van persoonsgegevens, rechten van betrokkenen (toegang, verwijdering, meeneembaarheid), toestemmingsbeheer en beleid inzake gegevensbewaring.

Als Datacontrole, bent u verantwoordelijk voor de behandeling van gegevensonderwerpverzoeken, het handhaven van toestemmingsverslagen, en het verzekeren van transparant gegevensgebruik.

Leer meer over [&#x200B; het beheer van de Privacy &#x200B;](../start/privacy.md)

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

Leer meer over [&#x200B; het beheer van de Privacy &#x200B;](../start/privacy.md)

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

[&#x200B; de diensten van het Abonnement &#x200B;](../start/subscriptions.md) | [&#x200B; Privacy en toestemming &#x200B;](../start/privacy.md#consent-retention-roles) | [&#x200B; Het beheer van de Privacy &#x200B;](../start/privacy.md)

+++

+++ Welke gegevens worden geschrapt wanneer ik een schrappingsverzoek verwerkt?

Met Campagne worden automatisch alle gegevens verwijderd die aan een gegevenssubject zijn gekoppeld: logboek voor het profiel van de ontvanger, de levering en het bijhouden van de gegevens, aangepaste gegevens met eigendomsrelaties, abonnementsgeschiedenis en webvolggegevens.

**hoe het werkt:** de Campagne schrapt alle gegevens waar de verbinding aan de ontvanger `integrity="own"` in de schemadefinitie heeft, die het draperen schrapping over verwante lijsten verzekeren.

U kunt schrappingswerkingsgebied aanpassen door verbindingsintegriteit in schema&#39;s te wijzigen, maar raadpleeg eerst juridische adviseur. Verwijderen is permanent en kan niet ongedaan worden gemaakt.

**Verwante onderwerpen:**

[&#x200B; het beheer van de Privacy &#x200B;](../start/privacy.md) | [&#x200B; de verbindingen van het Schema &#x200B;](../dev/schemas.md)

+++

+++ Heeft het verwijderen van privacy invloed op mijn leveringsrapporten?

Nee. Campagnerapporten zijn gebaseerd op vooraf berekende geaggregeerde metriek (totaal verzonden, geopend, geklikt), niet live query&#39;s op individuele logboeken. Het schrappen van individuele ontvankelijke gegevens verandert geen historische statistische aggregaten.

De algemene leveringsstatistieken en prestatiesmetriek blijven intact, terwijl de individuele het volgen logboeken en de persoonlijke details worden verwijderd. Op deze manier kunt u marketinganalyses bijhouden met inachtneming van de rechten van de betrokkene.

**Verwante onderwerpen:**

[&#x200B; het beheer van de Privacy &#x200B;](../start/privacy.md) | [&#x200B; Rapporten &#x200B;](../reporting/gs-reporting.md)

+++

+++ Hoe voorkom ik het opnieuw importeren van verwijderde gegevens?

U moet gegevens van alle bronsystemen, niet alleen Campagne schrappen. De gegevens vloeien vaak voort uit externe systemen (CRM, e-commerce, data-entrepots).

**Vereiste acties:** identificeer alle gegevensbronnen, schrap uit bronsystemen, voeg aan uitsluiting/onderdrukking lijsten toe, werk de invoerwerkschema&#39;s bij om schrappingsvlaggen te respecteren, en documenteer het proces.

Als Data Controller bent u verantwoordelijk voor de volledige verwijdering van gegevens in uw gehele technologie-ecosysteem.

**Verwante onderwerpen:**

[&#x200B; het beheer van de Privacy &#x200B;](../start/privacy.md) | [&#x200B; de werkschema&#39;s van de Invoer &#x200B;](../config/workflows.md)

+++

+++ Kunnen verwijderde gebruikers zich opnieuw aanmelden?

Ja. Personen met gegevens kunnen na verwijdering opnieuw aanmelden. Met Campagne maakt u een volledig nieuwe ontvanger-record zonder koppeling naar eerder verwijderde gegevens. Het profiel begint met een schone lei.

In het audittrail van Campaign worden zowel de gebeurtenis die werd verwijderd als het creëren van nieuwe profielen vastgelegd, waarmee wordt aangetoond dat de nieuwe opt-in-optie werd nageleefd en die na verwijdering vrij werd gegeven.

**Verwante onderwerpen:**

[&#x200B; het beheer van de Privacy &#x200B;](../start/privacy.md) | [&#x200B; Abonnementen &#x200B;](../start/subscriptions.md)

+++

## Nog steeds hulp nodig? {#get-help}

Kun je niet vinden wat je zoekt? Hier zijn aanvullende bronnen om u te helpen slagen met Adobe Campaign v8.

### Communautaire steun

Maak contact met andere campagnegebruikers en Adobe-experts om kennis te delen en antwoorden te krijgen.

* **[Gemeenschap van Adobe Campaign &#x200B;](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** - stel vragen, deel oplossingen, en verbind met de gemeenschap van de Campagne
* **[Forums van Experience League &#x200B;](https://experienceleaguecommunities.adobe.com/){target="_blank"}** - doorblader besprekingen over alle producten van Adobe
* **[de Uren van het Communautair Bureau van de Campagne &#x200B;](https://experienceleague.adobe.com/nl){target="_blank"}** - sluit zich aan bij levende zittingen met de deskundigen van Adobe

### Documentatie en leren

Toegang tot uitgebreide handleidingen, zelfstudies en trainingsmateriaal.

* **[&#128279;](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=nl-NL){target="_blank"} de Zelfstudies van de Campagne - Step-by-step videogidsen en hands-on leerprogramma&#39;s**
* **[wat](whats-new.md)** nieuw is - de Meest recente eigenschappen en mogelijkheden
* **[Nota&#39;s van de Versie](release-notes.md)** - Huidige en vorige versieinformatie
* **[Versies en Verbeteringen](upgrades.md)** - Leer over de versies van de Campagne, verbeteringen, en hoe te om uw versie te controleren

### Technische bronnen

Zoek gedetailleerde technische documentatie en ontwikkelaarsmiddelen.

* **[Campagne APIs &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=nl){target="_blank"}** - Volledige API verwijzingsdocumentatie
* **[Matrijs van de Verenigbaarheid](compatibility-matrix.md)** - Ondersteunde systemen en versies
* **[Veelgestelde vragen van Versies en van Verbeteringen Veelgestelde vragen](upgrades.md#upgrades-faq)** - controleer uw versie en leer over verbeteringen

### Ondersteuning en services

Vraag hulp aan het ondersteuningsteam van Adobe en beheer uw exemplaar.

* **[Adobe Admin Console &#x200B;](https://adminconsole.adobe.com/){target="_blank"}** - de steungevallen van het logboek en leiden gebruikers
* **[de Zorg van de Klant van Adobe &#x200B;](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - contacteer het ondersteuningsteam
* **[Controlebord &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl){target="_blank"}** - beheer uw de instantiemontages van de Campagne
* **[Status van het Systeem &#x200B;](https://status.adobe.com/){target="_blank"}** - de status van de Diensten van Adobe van de Controle

### Training en certificering

Werk uw vaardigheden verder met officiële Adobe-trainings- en certificeringsprogramma&#39;s.

* **[Hulp van Experience League &#x200B;](https://experienceleague.adobe.com/nl/browse/campaign/campaign-v8){target="_blank"}** - de middelen van de Hulp voor Campagne v8 (Web UI en console CLient)
* **[&#128279;](https://learning.adobe.com/){target="_blank"} de Digitale Lerende Diensten van Adobe** - Officiële instructeur-geleide en zelf-afgepaste cursussen
* **[de Certificatie van Adobe Campaign &#x200B;](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=nl-NL){target="_blank"}** - bevestigt uw deskundigheid met professionele certificatie
* **[Experience League Lerende Wegen &#x200B;](https://experienceleague.adobe.com/nl?lang=en#dashboard/learning){target="_blank"}** - Geleide het leren reizen

### Andere nuttige bronnen

* **[de Documentatie van Campaign Classic v7 &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=nl){target="_blank"}** - Verwijzing voor Klassieke v7 gebruikers
* **[&#128279;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/campaign-web-home){target="_blank"} de Documentatie van het Web UI van de Campagne - Nieuwe gids van de Webinterface**
* **[Beste praktijken van de Levering &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}** - optimaliseer e-maillevering

