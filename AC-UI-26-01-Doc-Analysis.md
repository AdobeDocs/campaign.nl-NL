---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01 Documentatieanalyse

## Inhoud volgende release

Dit document analyseert product JIRAs voor AC-UI-26-01 en AC-UI-25-11 maandversies om documentatieacties te plannen.

### JIRA-filters

1. **[wisselstroom-UI-26-01-Maandelijkse Artikelen &#x200B;](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - de Hoofdversieverhalen
2. **[NEO-92400 Verbeteringen &#x200B;](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** - De verbeteringen van de versie verbonden kwesties
3. **[wisselstroom-UI-25-11-Maandelijkse Artikelen &#x200B;](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Vorige versieoverdracht
4. **[wisselstroom-UI-25-11 die 8.8.2 &#x200B;](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20en%20type%20%3D%20story%20order%20by%20status) uitsluiten** - Gegilterde vorige versie

&#x200B;---

## 🟢 DOCAC maken

### [&#x200B; NEO-91565 &#x200B;](https://jira.corp.adobe.com/browse/NEO-91565) - voeg steun voor verpersoonlijkingsgebieden (de Geavanceerde Integratie van AEM) toe&#x200B;**Status:** Resolved\**vereiste Doc:** ja\**Bestaande DOCAC:** niets\**Actie:** creeer DOCAC

**Reikwijdte:**
- Documentondersteuning voor verpersoonlijkingsvelden in Geavanceerde AEM-integratie
- UI-workflow en configuratiestappen
- AEM-mogelijkheden voor meertalige integratie

**Beschrijving van de Eigenschap:**
Ondersteuning voor het toevoegen van verpersoonlijkingsvelden in leveringen met behulp van Geavanceerde AEM-integratie, zodat dynamische inhoud vanuit Campagnegegevens kan worden ingevoegd in e-mailsjablonen die door AEM zijn gemaakt.

**Context:** ACS aan ACC pariteit, MSFT-Specifiek vereiste

**Verwijzingen:** [&#x200B; meertalige wiki van AEM &#x200B;](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

&#x200B;---

### [&#x200B; NEO-93487 &#x200B;](https://jira.corp.adobe.com/browse/NEO-93487) - Levering die verwerkt proces (pariteit ACS) plant&#x200B;**Status:** Nieuw\**vereiste Doc:** ja\**Bestaande DOCAC:** niets\**Actie:** creeer DOCAC

**Reikwijdte:**
- De levering van het document plannend verwerkt proces voor dupberichten
- Tijdzonegebaseerde planningsformules
- Bestandsupload voor doelen voor meerdere tijdzones

**Beschrijving van de Eigenschap:**
Schakel op OOTB-bestanden gebaseerde planning voor levering met berekende verzendtijden in op basis van de tijdzone van de ontvanger, zodat één levering voor meerdere tijdzones met geoptimaliseerde verzendtijden per regio mogelijk is.

**Context:** Klant-gedreven (H&amp;M), ACS aan ACC pariteit vereiste

**Verwijzingen:** [&#x200B; documentatie ACS &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

&#x200B;---

## 🔄 DOCAC bijwerken

### [&#x200B; NEO-80973 &#x200B;](https://jira.corp.adobe.com/browse/NEO-80973) - Dynamische rapporteringsbeschikbaarheid voor alle gebruikers van Web UI&#x200B;**Status:** Bezig\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-11070 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-11070) (Gesloten), [&#x200B; DOCAC-13432 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13432) (Opgelost)\**Actie:** Overzicht DOCAC

**Reikwijdte:**
- De beschikbaarheidsinformatie van de update (nu voor alle gebruikers van het Web UI, niet alleen 8.7)
- Taalbeperkingen voor documenten
- Conflicterende metrische weergave verduidelijken met verouderde rapportage

**Beschrijving van de Eigenschap:**
De dynamische Rapportering is nu beschikbaar voor alle gebruikers van het Web UI van de Campagne (eerder beperkt tot 8.7 ACS aan klanten ACC), die geavanceerde analyses en douane rapporteringsmogelijkheden van interface ACS-Stijl verstrekken.

**Context:** De uitbreiding van de Eigenschap, achterste bouwt gebiedsdeel (8.8.1)

**Verwijzingen:** [&#x200B; Wiki - de vergelijking van Rapporten &#x200B;](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

&#x200B;---

### [&#x200B; NEO-86754 &#x200B;](https://jira.corp.adobe.com/browse/NEO-86754) - het Testen A/B&#x200B;**Status:** Bezig\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-13104 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13104) (Nieuw)\**Actie:** Update DOCAC

**Reikwijdte:**
- Documentatie van de testworkflow voor A/B voltooien
- Instellen en configuratie van varianten voor het experimenteren met inhoud
- Bepaling van de voorbeeldverhouding en selectiecriteria voor de winnaar
- Verzameling en evaluatie van statistieken

**Beschrijving van de Eigenschap:**
Inhoud experimenteren en A/B testen op e-mailleveringen, zodat marketers verschillende inhoudsvarianten kunnen testen, voorbeeldgrootten kunnen definiëren, prestatiestatistieken kunnen verzamelen en de winnende variant automatisch naar de resterende ontvangers kunnen sturen.

**Context:** het project van Europa, Microsoft vereiste, toegelaten eigenschapvlag

**Verwijzingen:** [&#x200B; Wiki &#x200B;](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [&#x200B; Mocks van Figma &#x200B;](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

&#x200B;---

### [&#x200B; NEO-76126 &#x200B;](https://jira.corp.adobe.com/browse/NEO-76126) - het auteursrecht van Schema&#39;s (creeer nieuwe lijst, breid schema&#39;s, toegang externe OB uit)**Status:** Bezig\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-13826 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13826) (Nieuw)\**Actie:** Update DOCAC

**Reikwijdte:**
- Ontwerpworkflow voor documentschema (alleen drie opties: tabel maken, schema uitbreiden, externe DB openen)
- Formulierdefinitie voor aangepaste entiteiten
- Navigeren en CRUD-bewerkingen op aangepaste schema&#39;s
- Mogelijkheden van fase 2 en fase 3

**Beschrijving van de Eigenschap:**
De auteursmogelijkheden van het schema in Web UI die beheerders toestaan om nieuwe gegevensbestandlijsten tot stand te brengen, bestaande schema&#39;s met douanevelden uit te breiden, en met externe gegevensbestanden - essentieel voor de aanpassing van het gegevensmodel te verbinden.

**Context:** Microsoft vereiste, Europa project, gefaseerde levering (Fase 2 actief, Fase 3 Feb eind)

**Verwijzingen:** [&#x200B; PRD &#x200B;](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [&#x200B; Cijfer &#x200B;](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

&#x200B;---

### [&#x200B; NEO-92668 &#x200B;](https://jira.corp.adobe.com/browse/NEO-92668) - de Analytics van het Web&#x200B;**Status:** Nieuw\**vereiste Doc:** ja\**Bestaande DOCAC:** niets\**Actie:** creeer DOCAC

**Reikwijdte:**
- Webanalyse externe accountconfiguratie
- Instellen en verifiëren van integratie
- Gebruik van analysegegevens in campagnes

**Beschrijving van de Eigenschap:**
Integratie met Web Analytics maakt verbinding met webanalyseplatforms mogelijk voor het bijhouden en rapporteren van de campagneprestaties en het gedrag van de websitebezoeker.

**Context:** verzoek van de Klant (P2E-RSC), hangende milieubeschikbaarheid

**Verwijzingen:** niets verstrekte

&#x200B;---

### [&#x200B; NEO-86753 &#x200B;](https://jira.corp.adobe.com/browse/NEO-86753) - de integratie van AEM voor Levende exemplaren/de exemplaren van de Taal&#x200B;**Status:** Nieuw\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-13829 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13829) (Opgelost)\**Actie:** Overzicht DOCAC

**Reikwijdte:**
- Door AEM geleverde templates bekijken
- Met één klik persoonlijke kopieën en taalkopieën maken
- Workflow voor het maken van meerdere inhoudvarianten

**Beschrijving van de Eigenschap:**
Dankzij de gestroomlijnde AEM-integratie kunt u met één muisklik persoonlijke kopieën en taalkopieën maken van AEM-leveringssjablonen, waardoor het maken van meertalige campagnes voor AEM-gebruikers wordt vereenvoudigd.

**Context:** vereiste van Microsoft, het werk dat aan het team van Himanshu wordt overgebracht

**Verwijzingen:** [&#x200B; documentatie ACS &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html?lang=nl-NL)

&#x200B;---

### [&#x200B; NEO-88838 &#x200B;](https://jira.corp.adobe.com/browse/NEO-88838) - de Redacteur van de Inhoud: De themavariabelen van het gebruik in fragment&#x200B;**Status:** Nieuw\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-12941 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-12941) (Nieuw)\**Actie:** Update DOCAC

**Reikwijdte:**
- Themavariabelen in e-mailontwerper (Beta)
- Thema&#39;s in fragmenten gebruiken
- Activering van de Actie

**Beschrijving van de Eigenschap:**
Ondersteuning voor het gebruik van themavariabelen in inhoudsfragmenten, waardoor consistente branding en ontwerpsysteemtoepassingen in e-mailcomponenten met gecentraliseerd themabeheer mogelijk zijn.

**Context:** Op greep, de eigenschap van Acrite om worden herzien

**Verwijzingen:** [&#x200B; ATU-5460 &#x200B;](https://jira.corp.adobe.com/browse/ATU-5460)

&#x200B;---

## ➕ DOCAC maken (verbeteringen)

### [&#x200B; NEO-92942 &#x200B;](https://jira.corp.adobe.com/browse/NEO-92942) - Vooraf bepaalde filters - Gedeelde optie&#x200B;**Status:** Resolved\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-13697 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13697) (het Overzicht van de Code), [&#x200B; DOCAC-13522 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13522) (Gesloten - Helper)\**Actie:** Overzicht DOCAC

**Reikwijdte:**
- Gedeelde optie voor vooraf gedefinieerde filters
- Zichtbaarheid filteren met andere operatoren (ACC vs gedrag Handelsreis)
- Gebruikersbeheer van gedeelde filters

**Beschrijving van de Eigenschap:**
Vooraf gedefinieerde filters kunnen nu worden gemarkeerd als ‘gedeeld’ om ze zichtbaar te maken voor andere operatoren, met een ander gedrag voor ACC (standaard) en Handelsreis (gebruikerspecifieke filtering).

**Context:** de bouwerverbetering van de Regel, eigenschapvlag: toelaat-vraag-filter-gedeeld

**Verwijzingen:** Verwant met [&#x200B; NEO-88441 &#x200B;](https://jira.corp.adobe.com/browse/NEO-88441)

&#x200B;---

### [&#x200B; NEO-91299 &#x200B;](https://jira.corp.adobe.com/browse/NEO-91299) - Ononderbroken leveringsactiviteit&#x200B;**Status:** Gesloten\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-13586 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13586) (Nieuw), [&#x200B; DOCAC-13808 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13808) (Gesloten - contextuele hulp)\**Actie:** Update DOCAC

**Reikwijdte:**
- Continue workflow voor levering
- Configuratie van de sjabloonkiezer voor levering
- Automatisch uitgaande overgangsgeneratie
- Doelopties (geen toegang tot inhoud)

**Beschrijving van de Eigenschap:**
De ononderbroken leveringsactiviteit voor werkschema&#39;s laat terugkomende leveringsuitvoering van malplaatjes toe, die automatisch uitgaande overgangen voor werkschemorchestratie produceren zonder inhoudwijziging.

**Context:** markering van de Eigenschap: laat-ononderbroken-levering toe

**Verwijzingen:** Verwante epische [&#x200B; NEO-67972 &#x200B;](https://jira.corp.adobe.com/browse/NEO-67972)

&#x200B;---

### [&#x200B; NEO-90130 &#x200B;](https://jira.corp.adobe.com/browse/NEO-90130) - laat OTB Dossier toe uploadt voor Meertalige Push Meldingen&#x200B;**Status:** Gesloten\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-13606 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13606) (Nieuw)\**Actie:** Update DOCAC

**Reikwijdte:**
- Bestanden uploaden voor meertalige pushberichten (iOS en Android)
- CSV-indeling en veldtoewijzing
- Krachtige pushondersteuning met meertalige mogelijkheden

**Beschrijving van de Eigenschap:**
OOTB-mogelijkheid voor het uploaden van bestanden voor het maken van meertalige pushberichten via CSV-import, overeenkomende ACS-functionaliteit en efficiënte meertalige campagneconfiguratie.

**Context:** Klantgedreven (H&amp;M), ACS aan ACC pariteit, kritiek voor migratie

**Verwijzingen:** [&#x200B; documentatie ACS &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

&#x200B;---

## ❌ Geannuleerd / Niet meer van toepassing

### [&#x200B; NEO-91566 &#x200B;](https://jira.corp.adobe.com/browse/NEO-91566) - Steun voor het volgen van CTA in webui&#x200B;**Status:** Gesloten (niet meer van toepassing)\**vereiste Doc:** Nr.\**Bestaande DOCAC:** [&#x200B; DOCAC-13821 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13821) (Nieuw)\**Actie:** Sluiten DOCAC

**Reden:** Nieuwe eigenschap ACS om MSFT te steunen - niet begonnen, hangende info van MSFT, geen werk UI verwacht

**Context:** Microsoft-Specifiek, het volgen van CTA vereiste

&#x200B;---

### [&#x200B; NEO-91564 &#x200B;](https://jira.corp.adobe.com/browse/NEO-91564) - de meertalige steun van de UI van AEM&#x200B;**Status:** Gesloten (niet meer van toepassing)\**vereiste Doc:** Nr.\**Bestaande DOCAC:** [&#x200B; DOCAC-13822 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13822) (Nieuw)\**Actie:** Sluiten DOCAC

**Reden:** het werk UI dat door het team van Himanshu (verschillend verhaal) wordt geleid

**Context:** vereiste van Microsoft, overgebracht werk

&#x200B;---

### [&#x200B; NEO-91567 &#x200B;](https://jira.corp.adobe.com/browse/NEO-91567) - voeg steun voor Eigenschap NRT toe&#x200B;**Status:** Resolved (past niet meer toe)\**vereiste Doc:** Nr.\**Bestaande DOCAC:** [&#x200B; DOCAC-13824 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13824) (Nieuw)\**Actie:** Sluiten DOCAC

**Reden:** Nieuwe ACS specifieke eigenschap voor MSFT - specificatie beschikbaar maar geen Web UI effect

**Context:** Microsoft vereiste, transactioneel overseinen

&#x200B;---

### [&#x200B; NEO-91563 &#x200B;](https://jira.corp.adobe.com/browse/NEO-91563) - Transactionele Rest API voor Profiel Gebaseerde Verrijking&#x200B;**Status:** Resolved (past niet meer toe)\**vereiste Doc:** Nr.\**Bestaande DOCAC:** [&#x200B; DOCAC-13825 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13825) (Nieuw)\**Actie:** Sluiten DOCAC

**Reden:** Geen het werk van Web UI, in afwachting van promotieinstantie, bouwt verplichte verbetering voor versie

**Context:** REST API eindpunteigenschap

&#x200B;---

### [&#x200B; NEO-92151 &#x200B;](https://jira.corp.adobe.com/browse/NEO-92151) - Profiel gebaseerde Fase 2 van het Overseinen van de Transactionele Verrijking van het Profiel&#x200B;**Status:** Resolved (past niet meer toe)\**vereiste Doc:** Nr.\**Bestaande DOCAC:** [&#x200B; DOCAC-13823 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13823) (Nieuw)\**Actie:** Sluiten DOCAC

**Reden:** het Artikel heeft geen taken, duidelijk als &quot;niet meer van toepassing is&quot;

**Context:** Microsoft vereiste, project Europa

&#x200B;---

## 🟢 Documentatie gereed (van AC-UI-25-11)

### [&#x200B; NEO-90183 &#x200B;](https://jira.corp.adobe.com/browse/NEO-90183) - Meertalig Rich Push - UI&#x200B;**Status:** Gesloten\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-13565 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13565) (Nieuw)\**Actie:** Overzicht DOCAC

**Reikwijdte:**
- Rijke pushvelden voor meertalige leveringen
- iOS- en Android-platformondersteuning
- Configuratie van sjablonen en inhoud

**Beschrijving van de Eigenschap:**
Uitgebreide ondersteuning voor pushmeldingen met meertalige mogelijkheden, waardoor marketers verbeterde pushmeldingen kunnen maken met afbeeldingen, knoppen en geavanceerde media voor zowel iOS als Android in meerdere talen.

**Context:** Klantgedreven (H&amp;M), die in 25-11 wordt geleverd, voltooide achterste werk

**Verwijzingen:** [&#x200B; Wiki &#x200B;](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

&#x200B;---

### [&#x200B; NEO-84916 &#x200B;](https://jira.corp.adobe.com/browse/NEO-84916) - opstelling en beheer het goedkeuringsproces&#x200B;**Status:** Resolved\**vereiste Doc:** ja\**Bestaande DOCAC:** [&#x200B; DOCAC-13827 &#x200B;](https://jira.corp.adobe.com/browse/DOCAC-13827) (Nieuw)\**Actie:** Update DOCAC

**Reikwijdte:**
- Validatieoperatoren configureren in levering/campagne
- Setup van goedkeuringswerkstroom
- Goedkeuringsprocedure voor inhoud en doel
- Ondersteuning voor meerdere kanalen (e-mail, SMS, push, direct mail, callcenter, aangepast)

**Beschrijving van de Eigenschap:**
Het beheer van het goedkeuringsproces dat bevestigingswerkschema&#39;s voor leveringsinhoud en het richten toelaat, met exploitant toewijzing en goedkeuring het volgen over alle leveringskanalen.

**Context:** Klantgedreven (Pierre Fabre), Microsoft vereiste, dev volledig en in test

**Verwijzingen:** [&#x200B; Klassieke documentatie &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [&#x200B; Mocks van Figma &#x200B;](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

&#x200B;---

## 📊 Samenvatting door actie

| Actie | Aantal |
|--------|-------|
| 🟢 DOCAC maken | 3 |
| 🔄 DOCAC bijwerken | 6 |
| ✅ DOCAC controleren | 3 |
| ❌ DOCAC sluiten | 5 |
| **Totaal** | **17** |

&#x200B;---

## ⚠️ Vragen openen

1. NEO-93487 - H&amp;M-escalatie - vereist dringende aandacht voor het plannen van het computerproces
2. NEO-92668 - Web Analytics - wachtend op milieubeschikbaarheid alvorens de documentatie kan worden voltooid
3. NEO-76126 - Schemas Fase 3 - ETA Feb end, behoefte aan een apart documentatieverhaal
4. NEO-88838 - Themavariabelen - in afwachting van Acrite-functieherziening in behandeling
5. Dynamische rapportering - verduidelijk conflicterende metriek vertoningsbegeleiding met erfenisrapportering

&#x200B;---

## 🔗 Verwante objecten

- NEO-85263 - ACS naar bovenliggende epic van ACC (EUROPA)
- NEO-67972 - Workflowverbeteringen
- NEO-87980 - Geavanceerde AEM-integratie
- NEO-90199 - Dynamische gereedheid voor release van rapporten
- NEO-63067 - Inhoudsexperimentatie UX/UI
- NEO-67726 - A/B-tests en inhoudexperimenten
- NEO-85274 - Schema en formulier (fase 2)
- NEO-87993 - Schema en formulier (fase 3)
