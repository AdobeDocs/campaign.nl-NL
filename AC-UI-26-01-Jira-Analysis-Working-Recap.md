---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '2430'
ht-degree: 0%

---
# AC-UI Jira Tickets Analysis - Working Recap&#x200B;**Datum:** 12 Januari, 2026&#x200B;**Type van Document:** het Werkdocument/Interne Analyse

&#x200B;---

## Samenvatting

Dit document analyseert productJira kaartjes van veelvoudige vragen met betrekking tot versies AC-UI (Januari 2026 en November 2025). De analyse richt zich op het identificeren van documentatievereisten, het voorstellen van DOCAC-tickets, en het benadrukken van open vragen.

**Totaal Unieke geanalyseerde Tickets:** 19
**Tickets die Documentatie vereisen:** 14
**reeds Gedocumenteerde kaartjes:** 5
**Tickets met Geen behoefte van het Document:** 5

&#x200B;---

## &#x200B;1. Lijst van geanalyseerde ticket

### 1.1 AC-UI-26-01-Maandbericht (januari 2026)

| Ticket-id | Titel | Status | Prioriteit | Componenten |
|-----------|-------|--------|----------|------------|
| NEO-91565 | [ UI van het Web ] voegt steun voor verpersoonlijkingsgebieden (de Geavanceerde Integratie van AEM) toe | Opgelost | Normaal | ACS naar ACC, PIX UI/UX |
| NEO-80973 | De dynamische beschikbaarheid van Rapportering voor alle gebruikers van WebUI | In uitvoering | Normaal | ACS naar ACC, PIX UI/UX |
| NEO-86754 | [ UX/UI ] het Testen A/B | In uitvoering | Blocker | PIX UI/UX |
| NEO-76126 | Ontwerpprogramma&#39;s - nieuwe tabel maken, schema&#39;s uitbreiden en externe database openen | In uitvoering | Kritiek | PIX UI/UX |
| NEO-93487 | [ UI van het Web ] Levering die verwerkt proces gelijkaardig aan in ACS plant | Nieuw | Kritiek | PIX UI/UX |
| NEO-92400 | Verbeteringen in de release - 26 januari | Nieuw | Normaal | PIX UI/UX |
| NEO-88838 | Inhoudseditor: Themavariabelen gebruiken in fragment | Nieuw | Normaal | PIX UI/UX |
| NEO-92668 | [ UX/UI ] Analyse van het Web | Nieuw | Normaal | PIX UI/UX |
| NEO-86753 | [ UX/UI ] de integratie van AEM voor Levende exemplaren/de exemplaren van de Taal | Nieuw | Blocker | ACS naar ACC, PIX UI/UX |

### 1.2 Verbeteringen van de release aan gekoppelde Tickets (NEO-92400)

| Ticket-id | Titel | Status | Prioriteit | Componenten |
|-----------|-------|--------|----------|------------|
| NEO-92942 | [ Vooraf gedefinieerde filters van de Bouwer van 0&rbrace; Regel - Gedeelde optie] | Opgelost | Normaal | PIX UI/UX |
| NEO-91299 | Web UI - Continuïteit van leveringsactiviteit | Gesloten | Majoor | PIX UI/UX |
| NEO-90130 | OOTB-bestanden uploaden inschakelen voor meertalige pushberichten | Gesloten | Kritiek | ACS naar ACC, PIX UI/UX |

### 1.3 AC-UI-25-11-Maandbericht (november 2025)

| Ticket-id | Titel | Status | Prioriteit | Componenten |
|-----------|-------|--------|----------|------------|
| NEO-91566 | [ UI van het Web ] Steun voor het volgen van CTA in webui | Gesloten | Normaal | ACS naar ACC, PIX UI/UX |
| NEO-91564 | [ Web UI ] [ meertalige AEM in ACC ] UI steun voor AEM meertalig | Gesloten | Normaal | ACS naar ACC, PIX UI/UX |
| NEO-90183 | [ UX/UI ] Meertalige Rich Push - UI | Gesloten | Blocker | PIX UI/UX |
| NEO-91567 | [ UI van het Web ] voegt steun voor Eigenschap NRT toe | Opgelost | Normaal | ACS naar ACC, PIX UI/UX |
| NEO-91563 | Transactiereeks-API voor op profiel gebaseerde verrijking - webinterface | Opgelost | Normaal | ACS naar ACC, PIX UI/UX |
| NEO-92151 | [ UI/UX ] Profiel baseerde het Transactionele Overseinen van de Verrijking - Fase 2 | Opgelost | Majoor | ACS naar ACC, PIX UI/UX |
| NEO-84916 | [ UX/UI ] opstelling en beheer het goedkeuringsproces | Opgelost | Kritiek | PIX UI/UX |

&#x200B;---

## &#x200B;2. Tickets die documentatie vereisen

### 2.1 HOGE PRIORITEIT - Actieve ontwikkeling (AC-UI-26-01)

#### **NEO-86754: Testen A/B**- **Status:** Bezig (op Spoor)- **waarom Documentatie nodig had:** Belangrijke nieuwe eigenschap voor het experimenteren van e-mailinhoud met A/B testende mogelijkheden- **Bestaande DOCAC:** DOCAC-13104 (Nieuwe status)- **de Reikwijdte van de Documentatie:**   - A/B-testexperimenten in leveringen maken   - Varianten voor inhoud/levering definiëren   - Monsterverhoudingen instellen en testvarianten verzenden   - Vaststelling van evaluatiecriteria   - Experimentele resultaten analyseren en winnaars selecteren   - Best practices en beperkingen- **publiek van het Doel:** de gebruikers van de marketing, de managers van de Campagne- **Versie:** 8.9.1, AC-UI-26-01-Maandelijks- **Open Vragen:**   - Uiteindelijke UI/UX-validatiestatus?   - Zijn er beperkingen voor transactieberichten?   - Integratie met voorvertoning van ActionScript-inhoud?

#### **NEO-80973: De dynamische Beschikbaarheid van de Rapportering**- **Status:** Bezig (klaar voor Overzicht)- **waarom Documentatie nodig had:** Uitbreidend Dynamische Rapportering aan alle gebruikers van het Web UI (niet alleen 8.7 ACS aan klanten ACC)- **Bestaande DOCAC:** DOCAC-11070 (Gesloten), DOCAC-13432 (Opgelost - taalbeperkingen)- **de Reikwijdte van de Documentatie:**   - Beschikbaarheid en toegangsvereisten   - Documentatie over ondersteunde talen   - Bekende beperkingen versus oudere rapportage   - Conflicterende metrische weergave met verouderde rapportage   - Instellen van demomgeving- **publiek van het Doel:** Alle gebruikers van UI van het Web, Analysten- **Versie:** 8.8.1, AC-UI-26-01-Maandelijks- **Open Vragen:**   - Status van beschikbaarheid van omgeving voor demo?   - Volledige lijst van conflicterende metriek met erfenisrapportering?   - Ondersteuningsmatrix voor talen?

#### **NEO-76126: Authoring van Schemas**- **Status:** Bezig (op Spoor)- **waarom Documentatie nodig had:** Belangrijke admin eigenschap voor gegevensmodelbeheer- **Bestaande DOCAC:** DOCAC-13826 (Nieuwe status)- **de Reikwijdte van de Documentatie:**   - Nieuwe tabellen maken   - Bestaande schema&#39;s uitbreiden   - Toegang tot externe databases   - Formulierdefinitie voor aangepaste entiteiten   - Navigatie- en CRUD-bewerkingen   - Fase 3 mogelijkheden (maak en breid schema&#39;s uit) - ETA Feb eind- **publiek van het Doel:** Admin gebruikers, Technische beheerders- **Versie:** AC-UI-26-01-Maandelijks- **Vervaldatum:** 28 feb, 2026- **Open Vragen:**   - Wanneer zal Fase 2 voor activering van FF worden voltooid?   - Bevestiging van leveringstijdlijn fase 3?   - De vereisten voor instellingen van omgeving?

#### **NEO-93487: Levering plannend Compute Proces (H&amp;M)**- **Status:** Nieuw- **waarom Documentatie nodig had:** Kritieke klantenescalatie - op tijdzone-gebaseerde levering die plant- **Bestaande DOCAC:** geïdentificeerde niets- **de Reikwijdte van de Documentatie:**   - Leveringen plannen op basis van tijdzone van gebruiker   - Berekende formules gebruiken voor gebieden met meerdere tijdzones   - Configuratievoorbeelden (bijvoorbeeld VS met meerdere tijdzones)   - Aanbevolen procedures voor wereldwijde campagnes   - Vergelijking van functies met ACS- **publiek van het Doel:** de managers van de Campagne, de gebruikers van de Marketing- **Gevolgen van de Klant:** H&amp;M (50+ markten)- **Versie:** 8.9.1, AC-UI-26-01-Maandelijks, 8.8.2.NEO-90300- **Open Vragen:**   - Feature demo scheduled with PM?   - Volledige functionele specificaties beschikbaar?   - UI-modellen gereed?

#### **NEO-86753: De Integratie van AEM voor Levende Kopieën/de Kopieën van de Taal**- **Status:** Nieuw- **waarom Documentatie nodig had:** Microsoft-Specifieke eigenschap voor meertalig inhoudsbeheer- **Bestaande DOCAC:** DOCAC-13829 (Opgelost)- **de Reikwijdte van de Documentatie:**   - Door AEM-leveringssjablonen bladeren   - Actieve kopieën maken   - Inhoudsvarianten voor taalkopieën maken   - Workflow en best practices   - Integratie-instellingsvereisten- **publiek van het Doel:** de gebruikers van de marketing die met AEM werken, de teams van Microsoft- **Versie:** AC-UI-26-01-Maandelijks- **Prioriteit:** Blocker- **Open Vragen:**   - Werk overgedragen aan Himanshu&#39;s team - huidige status?   - Tijdlijn voor voltooiing?

#### **NEO-92668: Analytics van het Web**- **Status:** Nieuw (op Spoor)- **waarom Documentatie nodig had:** Externe rekeningsconfiguratie voor de integratie van de Webanalyse- **Bestaande DOCAC:** geïdentificeerde niets- **de Reikwijdte van de Documentatie:**   - Webanalyse externe account maken   - Configuratieparameters   - Integratie met het bijhouden van levering   - Rapportagemogelijkheden- **publiek van het Doel:** Admin gebruikers, de analisten van de Marketing- **Versie:** AC-UI-26-01-Maandelijks- **Open Vragen:**   - Status beschikbaarheid van omgeving?   - Vereiste installatiestappen?

### 2.2 MEDIUM PRIORITEIT - Recent geleverd (AC-UI-25-11)

#### **NEO-90183: Meertalig Rich Push**- **Status:** Gesloten- **waarom Documentatie nodig had:** Nieuw vermogen voor de rijke duw van iOS/Android met meertalige steun- **Bestaande DOCAC:** DOCAC-13565 (Nieuwe status)- **de Reikwijdte van de Documentatie:**   - Uitgebreide configuratie voor pushberichten voor iOS en Android   - Meertalige inhoudvarianten   - Sjabloonselectie   - Aanvullende velden voor rijke inhoud   - Uploadmogelijkheden voor bestanden   - Best practices en beperkingen- **publiek van het Doel:** de gebruikers van de marketing, Mobiele kanaalmanagers- **Versie:** AC-UI-25-11-Maandelijks, 8.8.2- **Klant:** H&amp;M

#### **NEO-84916: Het Beheer van het Proces van de goedkeuring**- **Status:** Resolved- **waarom Documentatie nodig had:** Belangrijke werkschemaeigenschap voor leveringsbevestiging- **Bestaande DOCAC:** DOCAC-13827 (Nieuwe status)- **de Reikwijdte van de Documentatie:**   - Erkenningsexploitanten instellen in leveringen/campagnes   - Goedkeuring van inhoud configureren   - Doelgoedkeuring configureren   - Goedkeuringsworkflows beheren via kanalen (E-mail, SMS, Push iOS/Android, Direct Mail, Call Center)   - Processen accepteren/afwijzen   - Goedkeuringsrapportage en -tracking- **publiek van het Doel:** de managers van de Campagne, Admin gebruikers- **Versie:** AC-UI-25-11-Maandelijks- **Prioriteit:** Kritiek- **Klant:** Pierre Fabre

#### **NEO-91299: De ononderbroken Activiteit van de Levering**- **Status:** Gesloten- **waarom Documentatie nodig had:** Nieuwe werkschemaactiviteit voor terugkomende leveringsscenario&#39;s- **Bestaande DOCAC:** DOCAC-13586 (Nieuwe status), DOCAC-13808 (Gesloten - contextuele hulp)- **de Reikwijdte van de Documentatie:**   - Configuratie van continue leveringsactiviteit   - Vereisten voor de leveringssjabloonkiezer   - Verwerking van procesfouten   - Workflowintegratie   - Gebruik voorbeelden en gevallen- **publiek van het Doel:** Technische gebruikers, de ontwerpers van het Werkschema- **Versie:** AC-UI-26.01.06

#### **NEO-90130: Het meertalige Uploaden van het Dossier van de Duw (H&amp;M)**- **Status:** Gesloten- **waarom Documentatie nodig had:** de eigenschappariteit OTB met ACS voor op dossier-gebaseerde meertalige duw- **Bestaande DOCAC:** DOCAC-13606 (Nieuwe status)- **de Reikwijdte van de Documentatie:**   - CSV-bestandsupload voor meertalige pushberichten   - Bestandsindelingsspecificaties   - Veldtoewijzing   - iOS- en Android-specifieke configuraties   - Tekstverwerking gegevensbericht   - Problemen oplossen en bekende problemen- **publiek van het Doel:** de gebruikers van de marketing, de managers van de Campagne- **Versie:** AC-UI-25-10-Maandelijks, AC-UI-25.11.03- **Prioriteit:** Kritiek- **Klant:** H&amp;M (ACS aan migratie ACC)

#### **NEO-92942: Vooraf bepaalde Filters - Gedeelde Optie**- **Status:** Resolved- **waarom Documentatie nodig had:** Verbetering aan de functionaliteit van de regelbouwer- **Bestaande DOCAC:** DOCAC-13697 (de status van het Overzicht van de Code), DOCAC-13522 (Gesloten - helper)- **de Reikwijdte van de Documentatie:**   - Gedeelde optie voor vooraf gedefinieerde filters   - De zichtbaarheid van filters beheren met andere operatoren   - ACC vs gedrag van merk Journey   - Beheer filterlijsten- **publiek van het Doel:** Alle gebruikers, de ontwerpers van de Vraag- **Versie:** Belangrijkste Versie- **FF:** toe:laten-vraag-filter-gedeeld

### 2.3 LAGE PRIORITEIT - Verbetering van de Inhoudseditor

#### **NEO-88838: De Variabelen van het thema in Fragments**- **Status:** Nieuw (op Greep)- **waarom Documentatie nodig had:** E-mailDesigner themacofunctionaliteit- **Bestaande DOCAC:** DOCAC-12941 (Nieuwe status)- **de Reikwijdte van de Documentatie:**   - Themavariabelen gebruiken in e-mailfragmenten   - Themaconfiguratie   - Beheer van variabelen   - Best practices- **publiek van het Doel:** E-mailontwerpers, de gebruikers van de Marketing- **Versie:** AC-UI-26-01-Maandelijks- **Nota:** de Eigenschap is op greep hangende Acrite-side revisit

&#x200B;---

## &#x200B;3. Tickets hoeven geen documentatie te bevatten

### 3.1 Geannuleerd/niet langer van toepassing

| Ticket-id | Titel | Reden |
|-----------|-------|--------|
| NEO-91566 | CTA-tracking in webui | Geen UI-werk verwacht; informatie in behandeling van MSFT |
| NEO-91564 | Ondersteuning voor meertalige gebruikersinterface van AEM | UI-werk beheerd door verschillende teams |
| NEO-91567 | Ondersteuning van NRT-functies | Geen invloed op de webinterface; specificatie beschikbaar |
| NEO-91563 | Transactionele rest-API | Geen werkende Web UI; hangende instantieverbetering |
| NEO-92151 | Profielverrijkingsfase 2 | Artikel heeft geen taken; is gemarkeerd als niet langer van toepassing |

### 3.2 Plaatsaanduiding/Trackingticket

| Ticket-id | Titel | Reden |
|-----------|-------|--------|
| NEO-92400 | Verbeteringen in de release - 26 januari | Tijdelijke aanduiding om de voltooiing van de verbeteringen te volgen |

&#x200B;---

## &#x200B;4. Voorgestelde DOCAC-tickets

### 4.1 NIEUWE DOCAC-Tickets vereist

#### **DOCAC-XXXX: Levering die met de Steun van de Tijdzone plant**&#x200B;**Bediende Ticket van de Ouder:** NEO-93487&#x200B;**Prioriteit:** Kritiek&#x200B;**Versie van het Doel:** AC-UI-26-01-Maandelijks&#x200B;**Beschrijving:**&#x200B;Documenteer de nieuwe levering die verwerkt proces plant dat timezone-based levering die gelijkend op functionaliteit ACS toelaat. Met deze functie kunnen marketers communicatie verzenden op basis van de tijdzones van de ontvangers aan de hand van berekende formules, wat met name van belang is voor markten met meerdere tijdzones, zoals de VS.

**Reikwijdte:**
- De gids van de configuratie voor timezone-based het plannen
- Voorbeelden van berekende formules
- Marktscenario&#39;s voor meerdere tijdzones
- Migratiehandleiding van ACS
- Best practices en beperkingen

**Klant:** H&amp;M (Kritiek voor migratie ACS aan ACC)

#### **DOCAC-XXXX: De Externe Configuratie van de Rekening van de Analyse van het Web**&#x200B;**Bediende Ticket van de Ouder:** NEO-92668&#x200B;**Prioriteit:** Normaal&#x200B;**Versie van het Doel:** AC-UI-26-01-Maandelijks&#x200B;**Beschrijving:**&#x200B;Documenteer de externe van de Analyse van het Web accounttype configuratie en gebruik in het Web UI.

**Reikwijdte:**
- Stappen voor het maken van externe accounts
- Configuratieparameters
- Integratie met het bijhouden van levering
- Rapportagemogelijkheden
- Problemen oplossen

&#x200B;---

### 4.2 BESTAANDE DOCAC-Tickets die moeten worden bijgewerkt

#### **DOCAC-13104: Testen A/B**&#x200B;**Status:** Nieuw&#x200B;**Bediende Ticket van de Ouder:** NEO-86754&#x200B;**Nodig Actie:** documentatie van het Begin - eigenschap in actieve ontwikkeling&#x200B;**Geschatte Levering:** Februari 2026 (in afwachting van ontwikkelingsvoltooiing)

#### **DOCAC-11070 &amp; DOCAC-13432: Dynamische Rapportering**&#x200B;**Status:** Gesloten/Opgelost&#x200B;**Bediende Ticket:** NEO-80973&#x200B;**Nodig Actie:**- Update voor algemene beschikbaarheid (niet alleen 8.7)- Statistische gegevens in documenten die conflicteren met oudere rapporten- Documentatie voor taalondersteuning controleren

#### **DOCAC-13826: Authoring van Schemas**&#x200B;**Status:** Nieuw&#x200B;**Bestelwagen van de ouder:** NEO-76126&#x200B;**Nodig Actie:**- Fase 2-documentatie (navigeren + CRUD + formulierdefinitie)- Voorbereiden voor fase 3 (schema&#39;s maken/uitbreiden) - ETA Feb-einde

#### **DOCAC-13829: Actieve Exemplaren van AEM/de Exemplaren van de Taal**&#x200B;**Status:** Resolved&#x200B;**Bediende Ticket van de Ouder:** NEO-86753&#x200B;**Nodig Actie:** verifieer huidige status en werk zoals nodig bij

#### **DOCAC-13565: Meertalig Rich Push**&#x200B;**Status:** Nieuw&#x200B;**Bestelwagen van de ouder:** NEO-90183&#x200B;**Nodig Actie:** Volledige documentatie - eigenschap die in Nov 2025 wordt geleverd

#### **DOCAC-13827: Het Proces van de goedkeuring**&#x200B;**Status:** Nieuw&#x200B;**Bediende Ticket van de Ouder:** NEO-84916&#x200B;**Nodig Actie:** Volledige documentatie - eigenschap die in Nov 2025 wordt geleverd

#### **DOCAC-13586 &amp; DOCAC-13808: Ononderbroken Levering**&#x200B;**Status:** Nieuw/Gesloten&#x200B;**Bestelwagen van de ouder:** NEO-91299&#x200B;**Vereiste Actie:** Volledige belangrijkste documentatie (13586) - geleverde eigenschap

#### **DOCAC-13606: Het meertalige Dossier van de Duw uploadt**&#x200B;**Status:** Nieuw&#x200B;**Bestelwagen van de Ouder:** NEO-90130&#x200B;**Nodig Actie:** Volledige documentatie - geleverde eigenschap

#### **DOCAC-13697 &amp; DOCAC-13522: Vooraf bepaalde Gedeelde Filters**&#x200B;**Status:** Controle van de Code/Gesloten&#x200B;**Bestelwagen van de Ouder:** NEO-92942&#x200B;**Nodig Actie:** voltooi documentatie (13697)

#### **DOCAC-12941: Thema&#39;s in E-mail Designer**&#x200B;**Status:** Nieuw&#x200B;**Bediende Ticket van de Ouder:** NEO-88838&#x200B;**Nodig Actie:** Op greep hangende eigenschaprevisit

&#x200B;---

## &#x200B;5. Open vragen en ontbrekende informatie

### 5.1 Op functie

#### **het Testen A/B (NEO-86754)**- [ ] Wat is de uiteindelijke UI/UX-validatiestatus?- [ ] Zijn er specifieke beperkingen voor transactieberichten?- [ ] Hoe kan dit worden geïntegreerd met de voorvertoning van acrietinhoud (NEO-92516-blokkering)?- [ ] Wat zijn de mogelijkheden voor simuleren/voorvertonen binnen elke variant?

#### **Dynamische Rapportering (NEO-80973)**- [ ] Wat is de status van de reactivering van de demo-omgeving?- [ ] Volledige lijst met conflicterende maatstaven met verouderde rapportage?- [ ] Matrix voor uitgebreide taalondersteuning?- [ ] Prestatievergelijking met oudere rapporten?

#### **Authoring van Schema&#39;s (NEO-76126)**- [ ] Wanneer wordt Fase 2 FF geactiveerd?- [ ] Bevestigde ETA voor Fase 3 (creeer/breid schema&#39;s uit)?- [ ] Wat zijn de vereisten voor het instellen van de omgeving?- [ ] Zijn er beperkingen ten opzichte van de functionaliteit van de clientconsole?

#### **Levering het Plannen (NEO-93487)**- [ ] Is de eigenschapdemo met PM gepland?- [ ] Zijn volledige functionele specificaties beschikbaar?- [ ] UI-modellen voltooid en gereviseerd?- [ ] Wat is de exacte syntaxis/structuur van de formule?

#### **AEM Levende/de Kopieën van de Taal (NEO-86753)**- [ ] Wat is de huidige status met het team van Himanshu?- [ ] Bijgewerkte leveringstermijn?- [ ] Zijn er afhankelijkheden van de AEM-versie?

#### **Analytics van het Web (NEO-92668)**- [ ] Wat is de beschikbaarheidsstatus van de omgeving?- [ ] Wilt u de installatievereisten voltooien?- [ ] Ondersteunde analyseplatforms?

#### **Variabelen van het Thema in Fragments (NEO-88838)**- [ ] Wanneer wordt de functie opnieuw gestart door Acrite?- [ ] Is dit nog gepland voor AC-UI-26-01?

### 5.2 Bij loslaten

#### **wisselstroom-UI-26-01-Maandelijks (Januari 2026)**- [ ] Bevestiging officiële publicatiedatum?- [ ] Vuldatum onderdeel?- [ ] Tijdlijn voltooiing testen?- [ ] Uiterste datum voor levering van documentatie?

#### **November 2025 leverde Eigenschappen**- [ ] Welke functies zijn al geactiveerd tijdens de productie?- [ ] Bekende problemen of beperkingen die na de release zijn ontdekt?- [ ] Feedback van de klant ontvangen?

### 5.3 Documentatieproces

- [ ] Wie zijn de KMO&#39;s voor elke functie?
- [ ] Wat is het revisieproces voor documentatie?
- [ ] Doeldocumentatietaal (alleen NL of meertalig)?
- [ ] Vereisten voor documentatieplatform/indeling?
- [ ] Beschikbaarheid van screenshots en demo-omgeving?

&#x200B;---

## &#x200B;6. Gevolgen voor de klant en doorverwijzingen

### 6.1 Kritieke klantenkaartjes

| Klant | Ticket | Functie | Gevolgen |
|----------|--------|---------|--------|
| **H&amp;M** | NEO-93487 | Leveringsplanning | 50+ markten; vereisten voor levering in meerdere tijdzones; ACS naar ACC-migratieblokker |
| **H&amp;M** | NEO-90130 | Multi-lingual Push File Upload | Kritiek voor migratie ACS naar ACC; vermindert operationele kosten |
| **Pierre Fabre** | NEO-84916 | Goedkeuringsproces | Regelgevings- en workflowvereisten |

### 6.2 Microsoft-specifieke functies

| Ticket | Functie | Status | Notities |
|--------|---------|--------|-------|
| NEO-86753 | AEM Live/Language-kopieën | Nieuw | Zeer gebruikt door Microsoft |
| NEO-91566 | CTA-tracking | Gesloten/Niet meer van toepassing | Informatie van MSFT in behandeling |
| NEO-91567 | NRT-functie | Opgelost/Geen gevolgen voor de gebruikersinterface | Nieuwe ACS-functie voor MSFT |

&#x200B;---

## &#x200B;7. Documentatieprioriteiten en tijdlijn

### 7.1 Directe actie vereist (januari 2026)

**HOGE PRIORITEIT - Geleverd maar niet gedocumenteerd:**
1. **NEO-90183** - Meertalig Rich Push (DOCAC-13565)
2. **NEO-84916** - het Proces van de Goedkeuring (DOCAC-13827)
3. **NEO-91299** - Ononderbroken Levering (DOCAC-13586)
4. **NEO-90130** - Het meertalige Uploaden van het Dossier van de Duw (DOCAC-13606)

### 7.2 In uitvoering - ontwikkeling aan de gang (februari-maart 2026)

**KRITIEKE PRIORITEIT:**
1. **NEO-86754** - het Testen A/B (DOCAC-13104) - Geldig: Feb 2026
2. **NEO-76126** - Authoring van Schema&#39;s (DOCAC-13826) - Fase 2: Feb, Fase 3: Eind Feb
3. **NEO-93487** - Leveringsplanning (NIEUW DOCAC) - Kritieke klantenescalatie

**NORMALE PRIORITEIT:**
1. **NEO-80973** - Dynamische Rapportering (update DOCAC-11070)
2. **NEO-92668** - de Analytics van het Web (NIEUW DOCAC)
3. **NEO-86753** - de Exemplaren van AEM Live/van de Taal (DOCAC-13829)

### 7.3 In wachtstand/toekomst

1. **NEO-88838** - de Variabelen van het Thema (DOCAC-12941) - in afwachting van Acrite revisit

&#x200B;---

## &#x200B;8. Volgende stappen

### 8.1 Acties van het documentatieteam1. **bevestig geleverde eigenschappen** zonder documentatie (Sectie 7.1)2. **creeer nieuwe DOCAC kaartjes** voor NEO-93487 en NEO-926683. **Update bestaande DOCAC** kaartjes met gedetailleerd werkingsgebied (Sectie 4.2)4. **Kmo-interviews van het Programma** voor het Testen A/B, Schema&#39;s, en Levering het Plannen5. **verzamel screenshots** en bereidt duo milieu&#39;s voor6. **Overzicht en voltooi** taalbeperkingen voor Dynamische Rapportering

### 8.2 Verzameling van informatie1. **de engineeringlood van het Contact** voor statusupdates op:   - A/B Testen van uiteindelijke validatie   - Schema&#39;s Tijdlijn fase 2/3   - Specificaties voor de planning van de levering2. **de eigenschapdemo&#39;s van het Programma** met het Beheer van het Product3. **verzamel klant terugkoppelt** van H&amp;M en Pierre Fabre4. **verifieer milieubeschikbaarheid** voor de Analyse van het Web en Dynamische Rapportering

### 8.3 Coördinatie1. **Synchronisatie met het team van Himanshu** op de Exemplaren van AEM Live/Taal2. **Coördinaat met het team van Acrite** op de status van de Variabelen van het Thema3. **Follow-up op Microsoft-Specifieke** eigenschappen met accountteam

&#x200B;---

## Documentgeschiedenis

| Datum | Auteur | Versie | Wijzigingen |
|------|--------|---------|---------|
| 2026-01-12 | AI-assistent | 1,0 | Eerste analyse van Jira-query&#39;s |

&#x200B;---

## Bijlage: Jira-query&#39;s geanalyseerd

1. `project = NEO AND fixVersion = AC-UI-26-01-Monthly and type = story order by status`
2. `issueFunction in linkedIssuesOf('key=NEO-92400', 'is implemented by')`
3. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and type = story order by status`
4. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and fixVersion != 8.8.2 and type = story order by status`

**Totale Resultaten:** 19 geanalyseerd unieke kaartjes

