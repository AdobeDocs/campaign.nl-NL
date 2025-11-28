---
title: Veelgestelde vragen over campagne v8
description: Geniet van antwoorden op algemene Adobe Campaign v8-vragen over setup, configuratie, berichten, workflows en meer
feature: Overview
role: User
level: Beginner
keywords: Veelgestelde vragen, campagne v8, vragen, antwoorden, Help, ondersteuning, problemen oplossen
hide: true
hidefromtoc: true
source-git-commit: adaa37a43da1156ee1a84eb7ffe455ed4a30d9b1
workflow-type: tm+mt
source-wordcount: '12355'
ht-degree: 3%

---

# Veelgestelde vragen {#faq}

Geniet van snelle antwoorden op de meest voorkomende vragen over Adobe Campaign v8. Of u enkel begonnen bent of het zoeken naar geavanceerde configuratiehulp, zult u antwoorden vinden die door onderwerp hieronder worden georganiseerd.

**Nieuw aan Campagne?** Begin met [ Algemene Vragen ](#general) en [ Zeer belangrijke Concepten ](#key-concepts).\
**technische hulp nodig?** Controle [ Ontwikkelaars ](#developers) en [ de Montages van de Campagne ](#settings).\
**Kan uw antwoord niet vinden?** Bezoek onze [ Communautaire Forums ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} of [ contactsteun ](#get-help).

**Uiteinde:** Gebruik Ctrl+F (Cmd+F op Mac) om naar specifieke sleutelwoorden op deze pagina te zoeken. Klik op een vraag om het antwoord uit te vouwen.


## Algemene vragen {#general}

Beantwoord de meest voorkomende vragen over Adobe Campaign v8, zoals hoe u verbinding kunt maken, een upgrade kunt uitvoeren en ondersteuning kunt krijgen.

+++ Hoe kan ik verbinding maken met Campaign v8?

U moet de clientconsole van Campagne downloaden en installeren om verbinding te maken met Adobe Campaign.

[Klik hier voor meer informatie](connect.md).

De aanvang van de Versie van Campagne v8.6, hebt u toegang tot het **de gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud. Experience Cloud is een geïntegreerde Adobe-reeks met digitale marketingtoepassingen, producten en services.

Leer hoe te met Adobe Experience Cloud te verbinden, en tot de interface van het Web van Adobe Campaign [ in deze pagina ](campaign-ui.md#ac-web-ui) toegang te hebben. Leer meer in de [ gebruikersinterfacedocumentatie van het Web van Adobe Campaign ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Verwante onderwerpen:**

[ installeer de cliëntconsole ](connect.md) | [ Campagne gebruikersinterface ](campaign-ui.md) | [ de toestemmingen van de Gebruiker ](gs-permissions.md)

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

+++ Hoe kan ik campagne upgraden naar de nieuwste versie?

Adobe Campaign wordt regelmatig bijgewerkt. Kleine versies worden elk jaar uitgebracht met nieuwe functies, verbeteringen en oplossingen. Bovendien brengen wij periodiek versies uit met uitsluitend cumulatieve oplossingen.

Deze regelmatige frequentie van updates is bedoeld om de nieuwste en beste in uw handen te krijgen, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Daarom vinden wij het van essentieel belang dat u de meest recente versie van Adobe Campaign uitvoert.

**Nota:** als Beheerde gebruiker van de Diensten van de Wolk, wordt uw instantie bevorderd door Adobe met nieuwe versies.

Leer meer over [ versies en verbeteringen van de Campagne ](upgrades.md).

+++

+++ Hoe kan ik de e-mailleverbaarheid verbeteren?

E-maillevering, een essentieel onderdeel van het succes van het marketingprogramma van elke afzender, wordt gekenmerkt door voortdurend veranderende criteria en regels. Voor een effectieve navigatie in deze digitale wereld is een regelmatige afstemming van uw e-mailstrategie vereist, waarbij rekening wordt gehouden met belangrijke ontwikkelingen op het gebied van de leverbaarheid, zodat uw publiek het beste kan bereiken.

Verwijs naar deze gids om [ Aanbevolen Praktijken van de Levering te leren ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}

Leer hoe te om leverbaarheid in Campagne [ in deze gids uit te voeren ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html){target="_blank"}

**Verwante onderwerpen:**

[ Ongeveer leverability ](../send/about-deliverability.md) | [ het berichtinhoud van de Controle ](../send/control-message-content.md) | [ de leverbaarheid van de Monitor ](../send/monitoring-deliverability.md) | [ SpamAssassin ](../send/spamassassin.md)

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

Leer meer over [ controlerende leveringen ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html){target="_blank"} en [ levering beste praktijken ](delivery-best-practices.md).

+++

+++ Kan ik de uitvoering van de workflow controleren?

Ja. De campagne biedt verschillende gereedschappen om de uitvoering van de workflow te controleren:

* **dashboard van het Werkschema** - de status van de Mening real time, vooruitgang, en fouten voor elke werkschemageactiviteit
* **[Logboeken van het Werkschema ](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** - toegang gedetailleerde uitvoeringslogboeken om kwesties problemen op te lossen
* **[Heatmap ](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** - visualiseer werkschemaactiviteit en identificeer prestatiesknelpunten
* **[spoor van de Controle](../reporting/audit-trail.md)** - spoor alle wijzigingen die aan werkschema&#39;s worden aangebracht
* **[Alarm ](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** - de berichten van de opstelling voor werkschemamislukkingen of vertragingen

Om een werkschema te controleren, open het en klik de **Logboeken** tabel. Mislukte activiteiten worden rood gemarkeerd en u kunt de foutgegevens weergeven door erop te klikken.

Leer meer over [ controle werkschemauitvoering ](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} en [ werkschemabeste praktijken ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}.

+++

+++ Met welke systemen en componenten is Campagne v8 compatibel?

U kunt de lijst van alle systemen en componenten krijgen die voor de recentste bouw van Campagne in [ de matrijs van de Verenigbaarheid van Adobe Campaign ](compatibility-matrix.md) worden gesteund.

+++

+++ Hoe kan ik campagne downloaden?

U kunt het installatieprogramma en de clientconsole ophalen vanuit Adobe Download Center.

Als Admin gebruiker, heb toegang tot de Distributie van de Software van Adobe [ ](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"} om Adobe Campaign te downloaden.

Leer meer over het Centrum van de Distributie [ op deze pagina ](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html){target="_blank"}.

+++

+++ Hoe kan ik een probleem registreren?

U kunt een ticket maken om contact op te nemen met de Adobe-klantenondersteuning voor problemen die u ondervindt in Adobe-producten. In de Adobe Admin Console kunt u chatten met de Adobe-klantenondersteuning om uw problemen op te lossen.

Als u een probleem wilt melden of een chatsessie wilt starten in dat nieuwe systeem, maakt u verbinding met de [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}.

Dit systeem vereist individuele rekeningen voor elke gebruiker, met correcte toestemmingen. Als u zich niet kunt aanmelden met uw Adobe ID, kunt u om toegang vragen via de Experience League. Het klantenserviceteam helpt u dan zo snel mogelijk. [Meer informatie](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Deelnemen aan de Campagne-gemeenschap: zoeken naar antwoorden in bestaande vragen of de experts raadplegen. [Deelnemen aan het gesprek](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

+++


## Belangrijke concepten {#key-concepts}

Leer over de fundamentele concepten van de Campagne met inbegrip van authentificatie, gebruikersinterface, werkschema&#39;s, en kernfuncties effectief beginnen.

+++ Kan ik verbinding maken met Campaign v8 met een Adobe ID?

Ja! Dankzij de integratie met de IMS (Adobe Identity Management System) maken gebruikers via hun Adobe ID verbinding met de Adobe Campaign-console. Deze integratie biedt de volgende voordelen:

* Dezelfde id kan voor alle Experience Cloud-oplossingen worden gebruikt.
* De verbinding wordt onthouden bij het gebruik van Adobe Campaign met verschillende integraties.
* Veiliger beleid voor wachtwoordbeheer.
* Gebruik van Federated ID-accounts (externe id-provider).

[ leer meer ](connect.md) over de toegang tot van Campagne v8 met een Adobe ID.

+++

+++ Wat is mijn versie van Campaign?

Controleer uw [versie en buildnummer](upgrades.md#version) in het menu **Help > Info...** van de Campaign-clientconsole.

+++

+++ Wat zijn de verschillen tussen Campaign Classic v7 en Campaign v8?

Campaign v8 is de nieuwste versie van Campagne, die is ontworpen voor Beheerde Cloud Services. Het brengt significante verbeteringen in infrastructuur, veiligheid, leverbaarheid, en controle.

Adobe Campaign v8 is exclusief beschikbaar als a **Beheerde Cloud Service**, en kan niet op een op-gebouw of hybride milieu worden opgesteld.

[ Leer meer over de overgang van Campaign Classic v7 aan v8 ](v7-to-v8.md).

+++

+++ Hoe kan ik gebruikersmachtigingen instellen?

Als Campaign-beheerder kunt u machtigingen instellen voor gebruikers van uw organisatie.

Dit zijn een reeks rechten en beperkingen waarbij wordt toegestaan of geweigerd om:

* Toegang tot bepaalde functies
* Toegang tot bepaalde gegevens
* Gegevens maken, wijzigen en/of verwijderen

[ leer meer ](../start/gs-permissions.md) over gebruikerstoestemmingen in Campagne v8.

**Verwante onderwerpen:**

[ krijgen begonnen met toestemmingen ](gs-permissions.md) | [ leiden gebruikerstoestemmingen ](manage-permissions.md) | [ voeg toestemmingen op omslagen ](folder-permissions.md) toe

+++

+++ Hoe te om de naleving van de Privacy met Campagne te verzekeren?

Adobe Campaign biedt een reeks tools om u te helpen met uw privacynaleving voor GDPR, CCPA en andere privacyregels.

[ leer meer ](../start/privacy.md) over privacybeheer en de hulpmiddelen en de functionaliteiten die Adobe Campaign verstrekt om u met uw privacynaleving te helpen.

+++

+++ Wat zijn de concepten van het gebruikersinterface van de Campagne ik zou moeten weten?

Verwijs naar [ deze sectie ](campaign-ui.md) om meer over de grondbeginselen van het gebruikersinterface van Adobe Campaign te leren.

Beginnende Versie van Campagne v8.6, hebt u ook toegang tot het nieuwe **de gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud.

[ leer meer in de gebruikersinterfacedocumentatie van het Web van Adobe Campaign ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Hoe kan ik het publiek van mijn berichten selecteren?

Met Adobe Campaign kunt u verschillende strategieën gebruiken om doelgroepen te maken en doelontvangers te selecteren.

[ leer meer ](../audiences/gs-audiences.md) over hoe te om publiek in Campagne v8 te bepalen.

+++

+++ Wat is een workflow?

Adobe Campaign bevat workflows om het volledige scala aan processen en taken in de verschillende modules van de applicatieserver te orkestreren. Met deze uitgebreide grafische omgeving kunt u processen ontwerpen, zoals segmentatie, uitvoering van campagnes, bestandsverwerking, menselijke participatie, enzovoort. Deze processen worden uitgevoerd en bijgehouden door de workflowengine.

U kunt bijvoorbeeld een workflow gebruiken om een bestand van een server te downloaden, het te decomprimeren en vervolgens records in de Adobe Campaign-database te importeren.

Een workflow kan ook een of meer operatoren omvatten die op de hoogte moeten worden gebracht of die keuzes kunnen maken en processen kunnen goedkeuren. Op deze manier is het mogelijk om een leveringsactie te maken, een taak toe te wijzen aan een of meer operatoren om aan content te werken, doelen op te geven en proeven goed te keuren voordat de levering wordt gestart.

[ leer meer ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html){target="_blank"} over werkschema&#39;s. U kunt ook [de best practices voor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} lezen.

**Verwante onderwerpen:**

[ worden begonnen met werkschema&#39;s ](../config/workflows.md) | [ bouwt uw eerste werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [ het gebruiksgevallen van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [ de werkschemauitvoering van de Monitor ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

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

[ Leer meer over e-mailontwerp en bevestiging ](../send/email.md) in Campagne v8.

**Verwante onderwerpen:**

[ creeer uw eerste levering ](create-message.md) | [ Werk met leveringsmalplaatjes ](../send/create-templates.md) | [ Beste praktijken van de Levering ](delivery-best-practices.md) | [ Bepaal de e-mailinhoud ](../send/defining-the-email-content.md) | [ Voorproef en proef ](../send/preview-and-proof.md) | [ vormen en verzenden ](../send/configure-and-send.md) | [ Personaliseer inhoud ](../send/personalize.md)

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

[ leer meer over de configuratie en het verzenden van SMS ](../send/sms/sms.md) in Campagne v8.

**Verwante onderwerpen:**

[ worden begonnen met SMS ](../send/sms/sms.md) | [ de leveringsmontages van SMS ](../send/sms/sms-delivery-settings.md) | [ SMPP externe rekeningsmontages ](../send/sms/smpp-external-account.md) | [ creeer een levering van SMS ](../send/sms/create-sms.md) | [ inhoud van SMS ](../send/sms/sms-content.md) | [ verzend de proef van SMS ](../send/sms/sms-proofs.md) | [ Monitor SMS ](../send/sms/sms-monitor.md)

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

[ Leer meer over de configuratie van het dupbericht ](../send/push-settings.md) in Campagne v8.

**Verwante onderwerpen:**

[ creeer en verzend dupberichten ](../send/push.md) | [ vorm duw berichtkanaal ](../send/push-settings.md) | [ Ontwerp een rijke duw van Android ](../send/rich-push-android.md) | [ Ontwerp een rijke duw van iOS ](../send/rich-push-ios.md) | [ vormt met de Inzameling van Gegevens ](../send/push-data-collection.md) | [ Spoor en monitor ](tracking.md)

+++

+++ Hoe maak je een landingspagina?

U kunt de digitale inhoudeditor van Adobe Campaign gebruiken om bestemmingspagina&#39;s te ontwerpen en toewijzingen te definiëren met databasevelden.

[ leer meer ](../dev/landing-pages.md) in de documentatie van de Campagne v8.

U kunt het de gebruikersinterface van het Web van de Campagne ook gebruiken om het landen pagina&#39;s tot stand te brengen en te publiceren - [ leer meer ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ Hoe kan ik leveringen volgen?

U kunt leveringen volgen die met Campagne v8 door specifieke [ leveringsrapporten ](../reporting/delivery-reports.md) worden verzonden en dan uw leveringen controleren.

Leer meer over het volgen beheer in Campagne [ in deze pagina ](../start/tracking.md).

**Verwante onderwerpen:**

[ Spoor en monitorberichten ](tracking.md) | [ Leveringsrapporten ](../reporting/delivery-reports.md) | [ Begrijp leveringsmislukkingen ](../send/delivery-failures.md) | [ vorm getraceerde verbindingen ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ Hoe kan ik een foutbericht vertalen?

Een foutbericht wordt weergegeven in een vreemde taal? Alle foutberichten en de vertaling ervan worden weergegeven op [deze pagina](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=nl){target="_blank"}.

+++

+++ Kan ik een webformulier maken en antwoorden verzamelen in Campagne?

Ja. Creeer Webvormen gebruikend {de Toepassingen van het Web van de Campagne &amp; Forms **(cliëntconsole) voor volledige controle over vormlogica en bevestiging, of gebruik** het Landen van de Campagne Pagina&#39;s van de Pagina&#39;s **(Web UI) met een moderne belemmering-en-dalingsinterface voor abonnementen en loodgeneratie.** Zowel verzamelen gegevens rechtstreeks in Campagne en integreren met werkschema&#39;s voor geautomatiseerde acties.

[ leer meer over Webtoepassingen en vormen ](../dev/webapps.md) | [ het landen van UI van het Web van de Campagne pagina&#39;s ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campagne v8 versus vorige versies {#v7-differences}

Begrijp de belangrijkste verschillen tussen Campagne v8 en vorige versies (Klassieke v7 en Standaard), met inbegrip van architectuur, plaatsing, migratiewegen, en eigenschapveranderingen. Of je nu uit Campaign Classic v7 of Campaign Standard komt, leer wat nieuw is en hoe je vloeiend kunt overstappen.

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

[ van Campaign Classic v7 aan v8 ](v7-to-v8.md) | [ v7 aan v8 overgangsgids ](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"} | [ Van Campaign Standard aan v8 ](acs-to-v8.md) | [ de overgang van Campaign Standard ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [ Gids van de Goedkeuring van de Campagne v8 ](https://experienceleague.adobe.com/nl/docs/campaign-web/acs-to-ac/home){target="_blank"} | [ de capaciteitmatrijs van de Campagne v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
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
* Sommige technische implementaties kunnen verschillen - herzie de [ vermogensmatrijs ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* Gegevensmigratie en testen vereisen planning en bronnen
* **voor de gebruikers van Campaign Standard** - de Overgang wordt ontworpen om met minimale werkschemaverstoring glad te zijn

**Volgende stappen:**

Neem contact op met uw Adobe-vertegenwoordiger om:

* Evalueer uw gereedheid en tijdlijn voor migratie
* Begrijp de specifieke voordelen voor uw gebruiksgeval
* De migratiestrategie en de toewijzing van middelen plannen
* Toegang tot migratiehulpmiddelen en support

**Verwante onderwerpen:**

**voor Campaign Classic v7 gebruikers:** [ van Campaign Classic v7 aan v8 ](v7-to-v8.md) | [ v7 aan v8 gedetailleerde gids ](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**voor de gebruikers van Campaign Standard:** [ overgang van Campaign Standard aan v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [ Gids van de Goedkeuring van de Campagne v8 ](https://experienceleague.adobe.com/nl/docs/campaign-web/acs-to-ac/home){target="_blank"} | [ van Campaign Standard aan v8 overzicht ](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/overview){target="_blank"} | [ worden begonnen begonnen voor marketers ](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/marketers){target="_blank"} | [ krijgen begonnen voor admin/ontwikkelaars ](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**Algemene middelen:** [ de capaciteitmatrijs van de Campagne v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Compatibiliteitsmatrix](compatibility-matrix.md)

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

[ matrijs van de Mogelijkheid ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [ de matrijs van de Verenigbaarheid ](compatibility-matrix.md) | [ Grafieken en beperkingen ](ac-guardrails.md) | [ v7 aan v8 overgangsgids ](v7-to-v8.md)
* [ Campaign Standard aan v8 overgang ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++

## Profielen en doelgroepen {#audiences}

Vind antwoorden op vragen over het beheren van profielen, het creëren van publiek, het invoeren van gegevens, en het richten van ontvangers voor uw campagnes.

+++ Hoe te om ontvangers tot stand te brengen?

Handmatig ontvangers maken in de clientconsole voor afzonderlijke profielen, importeren uit bestanden (CSV/TXT) voor bulktoevoegingen, webformulieren gebruiken voor zelfregistratie of integreren via API&#39;s van externe systemen. Gebruik workflows voor importeren voor het terugkeren van gegevens.

[ creeer manueel profielen ](../audiences/create-profiles.md) | [ de profielen van de Invoer van een dossier ](../audiences/import-profiles.md) | [ verzamel profielen met Webvormen ](../audiences/collect-profiles.md)

+++

+++ Hoe kan ik profielen importeren?

Campagne biedt meerdere importmethoden: eenvoudige bestandsimporten met de wizard Importeren, op workflow gebaseerde import voor complexe transformaties, terugkerende import met geplande workflows uit SFTP en API-import voor programmatische integratie.

Bereid voor het importeren van bestanden uw gegevensbestand voor (CSV/TXT, UTF-8-codering), gebruik de wizard of workflow voor importeren, wijs kolommen toe aan Campagnevelden, definieer de regels voor bijwerken/invoegen en test eerst met een klein voorbeeld. Gebruik workflows voor terugkerende importbewerkingen en pas deduplicatieregels toe.

[ de gegevensgids van de Invoer ](../start/import.md) | [ Terugkerend de invoerwerkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [ het laden van Gegevens activiteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}

+++

+++ Hoe kan ik de doelpopulatie van een marketingcampagne definiëren?

De campagne biedt veelvoudige het richten methodes aan: bouwt vragen met visuele criteria, richt bestaande lijsten of segmenten, invoerontvangers uit externe dossiers (CSV, TXT), of pas vooraf bepaalde filters toe. U kunt criteria met logica combineren AND/OR, specifieke populaties uitsluiten, controlegroepen gebruiken, en voor het testen A/B verdelen. Geef altijd een voorvertoning weer van de grootte van de doelpopulatie voordat u deze verzendt.

[ bepalen campagnedoelstellingen ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html){target="_blank"} | [ de activiteit van de Vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [ creeer publiek ](../audiences/create-audiences.md)

+++

+++ Hoe kan ik een lijst met profielen maken?

Een lijst is een statische reeks ontvangers die u in leveringen en hergebruik over campagnes kunt richten.

**Drie creatiemethodes:**

* **Handmatige verwezenlijking:** navigeer aan **[!UICONTROL Profiles and Targets > Lists]** en klik **[!UICONTROL Create]**. Voeg ontvangers van een vraag, door individuele selectie, of van een omslag toe.

* **automatisering van het Werkschema:** gebruik de **[!UICONTROL List update]** activiteit om lijsten automatisch van vraagresultaten of ingevoerde gegevens tot stand te brengen en te handhaven.

* **tijdens de invoer:** creeer een lijst wanneer het invoeren van profielen om hen als herbruikbare groep te bewaren.

**Uiteinde:** werkschema&#39;s van het gebruik voor lijsten die regelmatige updates, en handverwezenlijking voor éénmalige segmentatie vereisen.

[ creeer publiek ](../audiences/create-audiences.md) | [ de updateactiviteit van de Lijst ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ Hoe kan ik een populatie dedupliceren voordat ik een bericht verstuurt?

Gebruik de **[!UICONTROL Deduplication]** -activiteit in een werkstroom om dubbele ontvangers te verwijderen vóór levering. Plaats de locatie tussen uw **[!UICONTROL Query]** - en **[!UICONTROL Delivery]** -activiteiten en kies vervolgens de deduplicatiecriteria (doorgaans het e-mailadres of de id van de ontvanger) en de record die u wilt bijhouden.

**Uiteinde:** dedupliceer altijd alvorens te verzenden om ervoor te zorgen elke persoon uw bericht slechts eenmaal ontvangt.

[ activiteit van de Deduplicatie ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}

+++

+++ Hoe te om abonnees aan een nieuwsbrief te identificeren en te richten?

De campagne volgt automatisch nieuwsbrieven abonnementen door informatiediensten. Abonnees activeren:

* Gebruik een **[!UICONTROL Query]** activiteit en filter op **[!UICONTROL Subscriptions]** > om uw nieuwsbrief service te selecteren
* Kies **[!UICONTROL To > Subscribers of an information service]** als u direct vanaf uw levering abonnees wilt activeren
* Abonnementenlijsten samenstellen met de **[!UICONTROL Subscription Services]** -workflowactiviteit

De campagne volgt abonnement/unsubscription geschiedenis en beheert automatisch opt-in/opt-out.

[ beheert abonnementen ](../start/subscriptions.md) | [ de activiteit van de Vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ Wat is de beste praktijk om profielen uit te sluiten van een doelpopulatie?

Gebruik de activiteit **[!UICONTROL Exclusion]** in een werkstroom om ongewenste profielen uit uw doel te verwijderen. Plaats het na uw gerichte activiteiten en bepaal welke populatie om uit te sluiten.

[ activiteit van de Uitsluiting ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Kan ik externe profielen gebruiken zonder deze te importeren in Campagne?

Ja, met Campagne v8 kunt u werken met externe profielen die zijn opgeslagen in een externe database zonder deze te laden in Adobe Campaign. [Meer informatie](../audiences/external-profiles.md).

+++

+++ Hoe maak ik testprofielen voor mijn leveringen?

Testprofielen zijn speciale ontvangers die worden gebruikt om proefdrukken te verzenden en leveringen te valideren zonder dat dit gevolgen heeft voor uw productiedatabase. Maak ze in **[!UICONTROL Profiles and Targets > Test profiles]** of gebruik de functie **[!UICONTROL Seed addresses]** om automatisch testontvangers aan uw leveringen toe te voegen voor kwaliteitsborging en controle in de Postvak IN.

[Test profiles](../audiences/test-profiles.md)

+++

## Berichtontwerp {#design}

Leer hoe u effectieve marketingberichten kunt ontwerpen in Campaign v8, inclusief e-mailsjablonen, personalisatietechnieken en meertalige inhoud. Ontwerp uw berichten in de cliëntconsole of gebruik moderne **E-mail Designer** in het Web UI van de Campagne voor verbeterde visuele het uitgeven ervaring.

+++ Wat zijn de beste werkwijzen voor het ontwerpen van e-mails in Campagne?

Belangrijke richtlijnen: zorg voor een ontwerp dat reageert op mobiele apparaten, gebruik HTML 4.0/XHTML-compatibele code met inline CSS, optimaliseer afbeeldingen (onder 100 KB) met alternatieve tekst, gebruik velden voor het samenvoegen van personalisatie, test voor alle e-mailclients voordat u het verzendt en voeg een gewone tekstversie toe. Doel voor totale e-mailgrootte van minder dan 500 kB voor optimale prestaties.

[ het ontwerpgids van de E-mail ](../send/email.md) | [ Beste praktijken van de Levering ](delivery-best-practices.md)

+++

+++ Wat is een leveringssjabloon?

Een leveringsmalplaatje is een pre-gevormde levering die alle montages en parameters voor hergebruik over veelvoudige campagnes bewaart. De malplaatjes omvatten doelregels, inhoudsontwerp, verpersoonlijking, technische montages (afzender, antwoord-aan), en typologieregels. Creëer eens en hergebruik om consistentie te behouden en het creëren van campagnes te versnellen.

[Leveringssjablonen maken](../send/create-templates.md)

+++

+++ Kan ik eenvoudig een bestaande HTML importeren om een e-mailbericht te maken in Campagne?

Ja. Importeer HTML-inhoud via directe kopiëren/plakken in de inhoudeditor, upload het bestand vanaf uw computer of laad de inhoud via een URL. Zorg ervoor dat uw HTML e-mailcompatibele code (HTML 4.0/XHTML) met inline CSS gebruikt en dat u afbeeldingen host op een openbare server. De campagne voegt automatisch personalisatie en het volgen aan ingevoerde HTML toe.

**Uiteinde:** voor de beste ervaring van het e-mailontwerp, gebruik **E-mail Designer** in het Web UI van de Campagne, die moderne belemmering-en-dalingsmogelijkheden en ingebouwde ontvankelijke malplaatjes, eerder dan het invoeren van ruwe HTML aanbiedt.

[HTML-inhoud importeren](../send/defining-the-email-content.md)

+++

+++ Hoe kan ik een nieuwsbrief op abonnementsbasis in Campaign tot stand brengen?

Ja. Gebruik de informatieservices van Campagne om nieuwsbrieven te beheren. De belangrijkste mogelijkheden omvatten automatische opt-in/opt-out behandeling, abonnement volgen, nalevingsbeheer (GDPR, CAN-SPAM), multi-nieuwsbrief steun, Webintegratie voor sign-up vormen, en gerichte levering aan abonnees.

[Lidmaatschappen beheren](../start/subscriptions.md)

+++

+++ Hoe kan ik berichten personaliseren?

De campagne biedt verpersoonlijkingsmogelijkheden aan om relevante, gerichte berichten tot stand te brengen die op ontvankelijke gegevens, gedrag, en voorkeur worden gebaseerd.

**de opties van Personalization:**

* **de gebieden van de Personalisatie** - neem ontvankelijke gegevens (b.v., `"Hello {{firstName}}")` op
* **de blokken van de Personalisatie** - Gebruik vooraf bepaalde of blokken van de douaneinhoud
* **Voorwaardelijke inhoud** - de verschillende inhoud van de vertoning die op ontvankelijke criteria wordt gebaseerd
* **gedragsgegevens** - het doorbladeren van hefboomwerkingen geschiedenis, aankooppatronen, of betrokkenheidsmetriek

Test personalisatie alvorens te verzenden om fusievelden en voorwaardelijke logica te verifiëren correct werken.

[ de gids van Personalization ](../send/personalize.md) | [ de gebieden van de Personalisatie ](../send/personalization-fields.md) | [ Voorwaardelijke inhoud ](../send/conditions.md)

+++

+++ Kan ik meertalige berichten versturen?

Ja. De campagne v8 biedt meertalige mogelijkheden, met het **Web UI van de Campagne** die de gemakkelijkste benadering verstrekt. Het Web UI biedt inheemse meertalige levering met taalvarianten-voegt taalvarianten aan uw levering toe, en de Campagne verzendt automatisch de aangewezen die versie op de aangewezen taal van de ontvanger wordt gebaseerd. Beschikbaar voor e-mail-, push-berichten, SMS- en transactieberichten.

Belangrijkste functies: automatische duplicatie van inhoud, automatisch verzenden op basis van taal, standaardtalenfallback en eenvoudig beheer van varianten.

De clientconsole ondersteunt ook meertalige inhoud met behulp van voorwaardelijke inhoud en workflows, maar vereist meer handmatige configuratie.

[ Meertalige leveringen (Web UI) ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [ Voorwaardelijke inhoud (de console van de Cliënt) ](../send/conditions.md)

+++

+++ Kan ik een webformulier lokaliseren?

Ja. Campagne voor webtoepassingen ondersteunt meertalige lokalisatie. Definieer vertalingen voor alle formulierelementen (labels, knoppen, berichten, fouttekst) met automatische taaldetectie op basis van het profiel van de ontvanger of de browserinstellingen. Meerdere taalversies worden ondersteund in één webtoepassing, waarbij zo nodig een standaardtaal wordt gebruikt.

[Webtoepassingslokalisatie](../dev/webapps.md)

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

[ AI Hulpoverzicht ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [ AI Hulpgevallen van het gebruiksgeval ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [ Merk groepering ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Berichten testen en verzenden {#send}

Leer beste praktijken voor het testen, het bevestigen, het verzenden van, en het volgen van uw marketing berichten om succesvolle campagnelevering te verzekeren.

+++ Wat is de leveringanalyse?

De analyse van de levering is een looppas van de de bevestigingsfase Campagne alvorens te verzenden. Het berekent de doelpopulatie, valideert inhoud, controleert fouten, past typologische regels toe, en schat leveringsvolume.

Campagne genereert logboeken met waarschuwingen en fouten. Fouten bij blokoplevering en moeten worden gecorrigeerd. Waarschuwingen zijn een advies. Analyselogs altijd controleren voordat ze worden verzonden.

[Handleiding voor leveringsanalyse](../send/delivery-analysis.md)

+++

+++ Waarom zou ik proefdrukken maken?

Proofs zijn testberichten die uw levering bevestigen alvorens naar uw belangrijkste publiek te verzenden. Gebruik proefdrukken om de personalisatie te controleren, de weergave van inhoud voor verschillende e-mailclients te testen, koppelingen te bevestigen en het werk te volgen, afbeeldingen en bijlagen te controleren en de reactiesnelheid van mobiele apparaten te valideren.

Proefdrukken helpen fouten af te vangen voordat ze duizenden ontvangers bereiken, maken goedkeuring van belanghebbenden en plaatsing van inbox testen mogelijk. Verzend proef naar veelvoudige e-mailcliënten en apparaten, en verkrijg altijd goedkeuring alvorens de productie verzendt.

[Proefdrukken en voorbeeldhulplijn](../send/preview-and-proof.md)

+++

+++ Hoe te om zaadadressen in Adobe Campaign te gebruiken?

Zaadadressen zijn speciale ontvangers die automatisch aan elke levering voor het testen, de kwaliteitsborging, en controle-zonder het aanpassen van uw doelcriteria worden toegevoegd. Nuttig voor doorlopende bewaking, plaatsingstests in de postbus, directe-mailvalidatie en zichtbaarheid van belanghebbenden.

**Zeer belangrijke verschillen van proeven:**

* **zaadadressen** - die aan productieleveringen automatisch worden toegevoegd, tellen naar verzendt volume
* **Proefdrukken** - de Test verzendt vóór productie, telt niet naar volume, dat voor bevestiging wordt gebruikt

Zaadadressen beheren in **[!UICONTROL Resources > Campaign management > Seed addresses]** . Houd lijsten klein om te voorkomen dat de leveringswaarden worden beïnvloed.

[ zaadadresgids ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ Hoe kan ik opstelling een goedkeuringsproces alvorens berichten te verzenden?

De campagne verstrekt goedkeuringswerkschema&#39;s om ervoor te zorgen dat de berichten aan kwaliteitsnormen alvorens verzenden voldoen. Configureer goedkeuringen voor inhoud, doel, extractie (direct mail) en budget op campagne- of leveringsniveau.

**Opstelling:**

Maak in **[!UICONTROL Administration > Access management > Operator groups]** groepen met operatoren en wijs vervolgens goedkeuringsgroepen toe in campagne- of leveringseigenschappen. Tijdens de campagne worden e-mailberichten verzonden naar revisoren die wijzigingen kunnen goedkeuren, afwijzen of aanvragen.

**voor standalone leveringen (niet in een campagne):**

Gebruik **proeven als uw goedkeuringsproces**. Verzend proefdrukken naar uw goedkeuringsgroep voor validatie en verzend altijd een nieuwe proefdruk nadat u wijzigingen hebt aangebracht om ervoor te zorgen dat belanghebbenden de nieuwste versie controleren.

[ Bevestiging van de Levering ](../send/preview-and-proof.md) | [ Goedkeuringen van de Campagne ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html){target="_blank"}

+++

+++ Wat is een typologieregel?

De typologische regels zijn geautomatiseerde bedrijfslogica die tijdens leveringsanalyse wordt toegepast om bericht het verzenden te bevestigen en te optimaliseren. Zij verzekeren naleving van marketing beleid, beschermen leverbaarheid, en verhinderen klantenvermoeidheid.

**Belangrijkste regeltypes:**

* **het Filtreren regels** - sluit (gevoegde op lijst van gewenste personen, unsubscribed, quarantined) ontvangers uit
* **Regels van de Druk** - het berichtfrequentie van de Controle om overweldigende ontvangers te vermijden
* **Regels van de Capaciteit** - het berichtvolume van de Grens voor verwerkingscapaciteit of ISP grenzen
* **Regels van de Controle** - de berichtgeldigheid van de controle (onderwerpregel, unsubscribe verbinding, afzenderformaat)

De regels worden gegroepeerd in typologieën en tijdens leveringsanalyse toegepast. De campagne kan ontvangers uitsluiten, de levering blokkeren, of waarschuwingen produceren die op de regels worden gebaseerd.

[ de gids van de Typologieregels ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html){target="_blank"}

+++

+++ Hoe kan ik e-mails sturen in golven?

Ja. Golf die uw levering verdeelt in veelvoudige partijen verzendt die met geplande intervallen worden verzonden. Dit is essentieel voor groot-volumecampagnes om serverlading in evenwicht te brengen, ISP throttling te verhinderen, afzenderreputatie met nieuwe IPs te bouwen, en opt-outs/grenzen tussen golven te beheren.

**Configuratie:**

In uw leveringseigenschappen, laat golf toe die en bepaalt het aantal golven (of partijgrootte) verzendt, interval tussen golven, en golfdistributie (lineaire of douanepercentages). De campagne verdeelt automatisch uw doelbevolking en verzendt elke golf op programma.

Gebruik golven voor grote campagnes, controleer eerste golfprestaties alvorens verder te gaan, en sta voldoende tijd tussen golven toe om schommelingen en opt-outs te verwerken.

[Vorm golf die](../send/configure-and-send.md#sending-using-multiple-waves)

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

[ creeer uw eerste e-mail ](create-message.md) | [ E-mail ontwerpgids ](../send/email.md)

+++

+++ Hoe een levering te plannen?

Met campagnes kunt u leveringen plannen voor toekomstig verzending om verzendtijden te optimaliseren en campagnes te coördineren.

**Plannend opties:**

* **de eigenschappen van de Levering** - verzend onmiddellijk, programma voor specifieke datum/tijd, of vertragen door uren/dagen
* **het niveau van de Campagne** - coördineer alle leveringen binnen een campagne
* **activiteit van de Planner van het Werkschema** - voor terugkomende leveringen, complexe patronen, en gebeurtenis-teweeggebrachte campagnes

De campagne steunt ook optimalisering van de contactdatum (het beste verzendt tijd per ontvanger) en aanpassing van de tijdzone (zelfde lokale tijd voor alle ontvangers).

[Levering planning](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Kan ik een bijlage toevoegen aan e-mails?

Ja. De campagne steunt statische gehechtheid (het zelfde dossier voor alle ontvangers) en gepersonaliseerde gehechtheid (verschillende dossiers per ontvanger die op profielgegevens worden gebaseerd). Voeg bijlagen toe in de sectie **[!UICONTROL Attachments]** van de leveringseigenschappen.

**Belangrijke overwegingen:**

* Bijlagen onder 1 MB houden voor optimale prestaties
* Bijlagen kunnen spamfilters activeren; test grondig alvorens te verzenden
* Bestandstypen die vaak door e-mailclients worden geblokkeerd (.exe, .zip, .js), worden voorkomen
* Gebruik voor grote bestanden liever bijgehouden downloadkoppelingen

Gebruik veilige bestandsindelingen (PDF, JPEG, PNG, DOCX) en test met zaadadressen voordat de productie wordt verzonden.

[Handleiding voor e-mailbijlagen](../send/email.md#attachments)

+++

+++ Hoe kan ik bijgehouden koppelingen in een e-maillevering configureren?

Met Campagne worden alle URL&#39;s in uw e-mail automatisch omgezet in bijgehouden koppelingen om de betrokkenheid van ontvangers te controleren. Open de sectie **[!UICONTROL Tracking]** in uw levering om het volgen montages voor elke verbinding te vormen.

**de opties van de Configuratie:**

* **laat/maakt het volgen** - Controle het volgen per verbinding toe
* **de etiketten van de Verbinding** - voeg beschrijvende namen voor het melden (b.v., &quot;Shop nu CTA&quot;) toe
* **categorieën van de Verbinding** - de verbindingen van de Groep door type voor bijeengevoegde analyse
* **Volgend type** - het Spoor klikt, opent, of allebei

De campagne volgt inhoudsverbindingen, spiegelt paginakoppelingen, unsubscribe verbindingen, en kan een facultatieve volgende pixel voor e-mail omvatten opent. Gebruik duidelijke labels en categorieën om de rapportage te vereenvoudigen en snel hoogwaardige inhoud te identificeren.

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

[ het beheersgids van de quarantaine ](../send/quarantines.md) | [ Stuitbeheer ](../send/delivery-failures.md)

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

[ bouwt een werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [ de activiteiten van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [ Beste praktijken van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [ het gebruiksgevallen van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

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

[ de beste praktijken van de Invoer ](../start/import.md) | [ het laden van Gegevens activiteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [ Terugkerend de invoerwerkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ Kan ik de uitvoering van de workflow controleren?

Ja. De campagne biedt uitgebreide mogelijkheden voor workflowbewaking om de uitvoering te volgen, problemen op te sporen en de prestaties te optimaliseren.

**de opties van de Controle:**

* **dashboard van het Werkschema** - de uitvoeringsstatus van de Mening in real time, vooruitgang, en activiteitenstaten
* **Logboeken van de Uitvoering** - toegang tot gedetailleerde logboeken voor elke activiteit en overgang
* **spoor van de Controle** - de werkschemawijzigingen van het spoor en uitvoeringsgeschiedenis
* **Alarm en berichten** - de alarm van de opstelling e-mail alarm voor mislukkingen of specifieke voorwaarden

**Zeer belangrijke controleeigenschappen:**

* Visuele statusindicatoren (in behandeling, in uitvoering, voltooid, mislukt)
* Uitvoeringstijd bijhouden voor optimalisatie van prestaties
* Foutberichten op activiteitsniveau voor probleemoplossing
* Workflows onderbreken, stoppen of opnieuw starten, indien nodig

Toegang tot controle vanaf **[!UICONTROL Administration > Production > Objects created automatically > Campaign workflows]** of rechtstreeks vanaf het werkstroomdashboard.

**Verwante onderwerpen:**

[ de werkschemauitvoering van de Monitor ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"} | [ Beste praktijken van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [ Begin een werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html){target="_blank"}

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

[ de gegevensactiviteit van de Update ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"} | [ de beheersactiviteiten van Gegevens ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

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

[ de beheersactiviteiten van Gegevens ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [ het richten werkschema&#39;s ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"} | [ de activiteit van de Verrijking ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

[ de gids van Personalization ](../send/personalize.md) | [ het gebruikscase van het Werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"} | [ de activiteit van de Verrijking ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

[ Gesplitste activiteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"} | [ A/B testende gids ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

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

[ de gegevensgids van de Invoer ](../start/import.md) | [ het laden van Gegevens activiteit ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [ de gegevensactiviteit van de Update ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

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

[ activiteit van de Vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [ Gebruikend aggregaten ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"} | [ Welkome programma&#39;s ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"}

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

[ het richten activiteitenverwijzing ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [ Verwijzing van de de controleactiviteiten van de Stroom ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [ de activiteitenverwijzing van de Actie ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"} | [ Verwijzing van de activiteiten van de Gebeurtenis ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}

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

[ de beste praktijken van het Werkschema gids ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [ Bouw een werkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [ werkschema&#39;s van de Monitor ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

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


[ taal van de Verandering in het Web UI van de Campagne ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [ krijgen begonnen met de cliëntconsole van de Campagne ](connect.md)

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

[ de integraties van Adobe Campaign ](../connect/integration.md) | [ verbind met Adobe ID ](connect.md)

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

[ Ongeveer leverability in Campagne ](../send/about-deliverability.md) | [ Gids van de Beste praktijken van de Levering ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}

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

[ de matrijs van de Verenigbaarheid ](compatibility-matrix.md) | [ vormen verbindingen FDA ](../connect/fda.md)

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


[ breid gegevensmodel ](../dev/extend-schema.md) uit | [ de structuur van het Schema ](../dev/schemas.md) | [ beste praktijken van het gegevensmodel ](../dev/datamodel-best-practices.md)

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

[Beschrijvende analyse](../reporting/built-in-reports.md)

+++

+++ Hoe kan ik geavanceerde rapporten over mijn gegevens ontwerpen?

De campagne biedt twee benaderingen voor het creëren van geavanceerde douanerapporten aan: technische rapporten in de cliëntconsole voor complexe analyse, en visuele dashboards voor gemakkelijkere rapportbouw.

In de clientconsole kunt u:

* Complexe rapporten maken met SQL-query&#39;s en aangepaste berekeningen
* Rapporten met meerdere pagina&#39;s maken met grafieken, tabellen en draaitabellen
* Voorwaardelijke opmaak en dynamische inhoud ontwerpen
* Toegang tot het volledige gegevensmodel van de Campagne en externe gegevensbestanden (FDA)


[ creeer douanerapporten (cliëntconsole) ](../reporting/custom-reports.md)

+++

+++ Wat is een kubus en hoe kan ik deze gebruiken voor rapportage?

De kubussen zijn multidimensionele gegevensstructuren die bedrijfsgebruikers toelaten om de gegevens van de Campagne door spillijsten zonder technische vaardigheden te onderzoeken en te analyseren. Beschouw ze als vooraf geconfigureerde gegevensmodellen die complexe rapportage vereenvoudigen.


* De technische gebruikers creëren en vormen kubussen die afmetingen (tijd, aardrijkskunde, kanalen) en maatregelen (opent, klikt, opbrengst) bepalen
* Zakelijke gebruikers selecteren een kubus wanneer ze rapporten maken en dimensies slepen en neerzetten om gegevens te verkennen
* Gegevens worden automatisch samengevoegd en berekend op basis van de kubusconfiguratie
* De resultaten kunnen worden weergegeven als draaitabellen, grafieken of worden geëxporteerd naar Excel


[Gegevens verkennen met kubussen](../reporting/gs-cubes.md)

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


[ worden begonnen met onderzoeken ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [ de rapporten van het Onderzoek ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

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

[ de rapporten van de Douane ](../reporting/custom-reports.md) | [ rapporten UI van het Web van de Campagne ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

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

[ het gegevensmodel van de Campagne ](../dev/datamodel.md) | [ Beste praktijken van het gegevensmodel ](../dev/datamodel-best-practices.md)

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

[ worden begonnen met schema&#39;s ](../dev/schemas.md) | [ breid een schema ](../dev/extend-schema.md) uit

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

[ de ontvankelijke lijst van de Douane ](../dev/custom-recipient.md) | [ de afbeeldingen van het Doel ](../audiences/target-mappings.md)

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

[ redacteur van de Vraag ](../start/query-editor.md) | [ de activiteit van de Vraag in werkschema&#39;s ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

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

[Werken met gegevenspakketten](../dev/packages.md)

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

**Toegang:** [ de documentatie van de Campagne v8 API ](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=nl){target="_blank"}

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

**API methodes:**

* `xtk:workflow#Start` - Een workflowinstantie starten
* `xtk:workflow#Pause` - De actieve workflow pauzeren
* `xtk:workflow#Stop` - De uitvoering van de workflow stoppen
* `xtk:workflow#GetState` - Huidige workflowstatus ophalen
* `xtk:workflow#GetLogs` - Logboeken voor uitvoering ophalen

**Gemeenschappelijke gebruiksgevallen:**

* Aangepaste controledashboards maken met de status van de workflow
* Automatische waarschuwingen implementeren wanneer workflows mislukken of te lang duren
* Workflows ordenen van externe planners of gebeurtenissystemen
* Workflowafhankelijkheden maken voor meerdere campagneinstanties
* Rapporten voor aangepaste workflowuitvoering genereren

**Beste praktijken:** combineer API controle met het spoor van de werkschemacontrole voor uitvoerig werkschemabeheer. Gebruik externe controlehulpmiddelen om werkschema SLAs en prestatiesmetriek te volgen.

[Workflows beheren via API](../dev/api/controlling-a-workflow.md)

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

[ de gegevensbestandstructuur van de Update ](../dev/update-database-structure.md) | [ breid schema ](../dev/extend-schema.md) uit

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

[ Campagne v7 aan v8 migratie ](../start/v7-to-v8.md#limitations) | [ architectuur FFDA ](../architecture/enterprise-deployment.md)

+++

## Privacy {#privacy}

Begrijp hoe Adobe Campaign u helpt aan privacyverordeningen zoals GDPR en CCPA te voldoen, en de verzoeken van de gegevenssubject te beheren.

+++ Wat zijn de belangrijkste privacyconcepten in Campagne?

De campagne helpt u aan privacyverordeningen (GDPR, CCPA, PDPA, LGPD) door hulpmiddelen te voldoen om de rechten van de gegevenssubject, toestemming, en gegevensbehoud te beheren. Belangrijke concepten zijn onder andere privacyregels, identificatie van persoonsgegevens, rechten van betrokkenen (toegang, verwijdering, meeneembaarheid), toestemmingsbeheer en beleid inzake gegevensbewaring.

Als Datacontrole, bent u verantwoordelijk voor de behandeling van gegevensonderwerpverzoeken, het handhaven van toestemmingsverslagen, en het verzekeren van transparant gegevensgebruik.

[Privacybeheer](../start/privacy.md)

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

[Privacybeheer](../start/privacy.md)

+++

+++ Hoe moet ik de toestemming van de gebruiker verzamelen en beheren?

Geldige toestemming vereist actieve, specifieke, geïnformeerde en herroepbare overeenkomst. Gebruikers moeten expliciete actie ondernemen. Er zijn geen vooraf aangevinkte vakjes of stilte nodig als toestemming. Afzonderlijke toestemmingen voor verschillende doeleinden (ontbundeld), geef duidelijke verklaringen, en handhaaf verslagen met timestamps.

**Beste praktijken:** verstrek korrelige opt-in opties, vernieuw periodiek toestemming, maak voorkeurscentra gemakkelijk tot toegang, en kadertoestemming als bouwend vertrouwen.

De campagne biedt de abonnementsdiensten, voorkeurscentra, gebieden van de douanetoestemming met timestamp het volgen, en werkschema-gebaseerde toestemming aan verfrist zich.

[ Abonnementen ](../start/subscriptions.md) | [ Privacy en toestemming ](../start/privacy.md#consent-retention-roles)

+++

+++ Hoe implementeer ik beheer van toestemming in Campaign?

Campagne biedt abonnementsservices, voorkeurscentra, vlaggen voor opt-out en velden voor aangepaste machtigingen voor het bijhouden van toestemming.

**de benadering van de Implementatie:** breid ontvankelijke schema voor toestemmingsgebieden (datum, type, bron) uit, creeer de abonnementsdiensten voor elk toestemmingstype, bouwt de Web-formulieren van het voorkeur centrum, gebruik werkschema&#39;s om toestemming in het richten af te dwingen, en handhaaf controletrails.

Raadpleeg de juridische adviseur om ervoor te zorgen dat uw implementatie voldoet aan de wettelijke vereisten.

[ de diensten van het Abonnement ](../start/subscriptions.md) | [ Het beheer van de Privacy ](../start/privacy.md)

+++

+++ Welke gegevens worden geschrapt wanneer ik een schrappingsverzoek verwerkt?

Met Campagne worden automatisch alle gegevens verwijderd die aan een gegevenssubject zijn gekoppeld: logboek voor het profiel van de ontvanger, de levering en het bijhouden van de gegevens, aangepaste gegevens met eigendomsrelaties, abonnementsgeschiedenis en webvolggegevens.

**hoe het werkt:** de Campagne schrapt alle gegevens waar de verbinding aan de ontvanger `integrity="own"` in de schemadefinitie heeft, die het draperen schrapping over verwante lijsten verzekeren.

U kunt schrappingswerkingsgebied aanpassen door verbindingsintegriteit in schema&#39;s te wijzigen, maar raadpleeg eerst juridische adviseur. Verwijderen is permanent en kan niet ongedaan worden gemaakt.

[ het beheer van de Privacy ](../start/privacy.md) | [ de verbindingen van het Schema ](../dev/schemas.md)

+++

+++ Heeft het verwijderen van privacy invloed op mijn leveringsrapporten?

Nee. Campagnerapporten zijn gebaseerd op vooraf berekende geaggregeerde metriek (totaal verzonden, geopend, geklikt), niet live query&#39;s op individuele logboeken. Het schrappen van individuele ontvankelijke gegevens verandert geen historische statistische aggregaten.

De algemene leveringsstatistieken en prestatiesmetriek blijven intact, terwijl de individuele het volgen logboeken en de persoonlijke details worden verwijderd. Op deze manier kunt u marketinganalyses bijhouden met inachtneming van de rechten van de betrokkene.

[ het beheer van de Privacy ](../start/privacy.md) | [ Rapporten ](../reporting/gs-reporting.md)

+++

+++ Hoe voorkom ik het opnieuw importeren van verwijderde gegevens?

U moet gegevens van alle bronsystemen, niet alleen Campagne schrappen. De gegevens vloeien vaak voort uit externe systemen (CRM, e-commerce, data-entrepots).

**Vereiste acties:** identificeer alle gegevensbronnen, schrap uit bronsystemen, voeg aan uitsluiting/onderdrukking lijsten toe, werk de invoerwerkschema&#39;s bij om schrappingsvlaggen te respecteren, en documenteer het proces.

Als Data Controller bent u verantwoordelijk voor de volledige verwijdering van gegevens in uw gehele technologie-ecosysteem.

[ het beheer van de Privacy ](../start/privacy.md) | [ de werkschema&#39;s van de Invoer ](../config/workflows.md)

+++

+++ Kunnen verwijderde gebruikers zich opnieuw aanmelden?

Ja. Personen met gegevens kunnen na verwijdering opnieuw aanmelden. Met Campagne maakt u een volledig nieuwe ontvanger-record zonder koppeling naar eerder verwijderde gegevens. Het profiel begint met een schone lei.

In het audittrail van Campaign worden zowel de gebeurtenis die werd verwijderd als het creëren van nieuwe profielen vastgelegd, waarmee wordt aangetoond dat de nieuwe opt-in-optie werd nageleefd en die na verwijdering vrij werd gegeven.

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

* **[het Huis van de Documentatie van de Campagne v8](../campaign-home.md)** - Volledige productdocumentatie
* **[](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html){target="_blank"} de Zelfstudies van de Campagne - Step-by-step videogidsen en hands-on leerprogramma&#39;s**
* **[wat](whats-new.md)** nieuw is - de Meest recente eigenschappen en mogelijkheden
* **[Nota&#39;s van de Versie](release-notes.md)** - Huidige en vorige versieinformatie
* **[Versies en Verbeteringen](upgrades.md)** - Leer over de versies van de Campagne, verbeteringen, en hoe te om uw versie te controleren
* **[Beste praktijken](delivery-best-practices.md)** - geadviseerde benaderingen voor gemeenschappelijke taken

### Technische bronnen

Zoek gedetailleerde technische documentatie en ontwikkelaarsmiddelen.

* **[Campagne APIs ](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=nl){target="_blank"}** - Volledige API verwijzingsdocumentatie
* **[Campagne GitHub ](https://github.com/AdobeDocs/campaign.en)** - draag aan documentatie bij
* **[Technische Nota&#39;s ](https://experienceleague.adobe.com/en/docs/campaign/technotes-ac/technotes-home){target="_blank"}** - diepgaande technische artikelen
* **[Matrijs van de Verenigbaarheid](compatibility-matrix.md)** - Ondersteunde systemen en versies
* **[Veelgestelde vragen van Versies en van Verbeteringen Veelgestelde vragen](upgrades.md#upgrades-faq)** - controleer uw versie en leer over verbeteringen

### Ondersteuning en services

Vraag hulp aan het ondersteuningsteam van Adobe en beheer uw exemplaar.

* **[Adobe Admin Console ](https://adminconsole.adobe.com/){target="_blank"}** - de steungevallen van het logboek en leiden gebruikers
* **[de Zorg van de Klant van Adobe ](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - contacteer het ondersteuningsteam
* **[Controlebord ](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl){target="_blank"}** - beheer uw de instantiemontages van de Campagne
* **[Status van het Systeem ](https://status.adobe.com/){target="_blank"}** - de status van de Diensten van Adobe van de Controle

### Training en certificering

Werk uw vaardigheden verder met officiële Adobe-trainings- en certificeringsprogramma&#39;s.

* **[](https://learning.adobe.com/){target="_blank"} de Digitale Lerende Diensten van Adobe** - Officiële instructeur-geleide en zelf-afgepaste cursussen
* **[de Certificatie van Adobe Campaign ](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - bevestigt uw deskundigheid met professionele certificatie
* **[Experience League Lerende Wegen ](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** - Geleide het leren reizen

### Andere nuttige bronnen

* **[de Documentatie van Campaign Classic v7 ](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=nl){target="_blank"}** - Verwijzing voor Klassieke v7 gebruikers
* **[](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"} de Documentatie van het Web UI van de Campagne - Nieuwe gids van de Webinterface**
* **[Beste praktijken van de Levering ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}** - optimaliseer e-maillevering
* **[Updates van het Product ](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current){target="_blank"}** - de recentste updates van Adobe Experience Cloud

**Laatst bijgewerkt:** November 2025 | **is op van toepassing:** Campagne v8.6 en later

*vond een fout of wil een verbetering voorstellen? [ geef deze pagina op GitHub ](https://github.com/AdobeDocs/campaign.en/edit/main/help/v8/start/campaign-faq-comprehensive.md) uit*

