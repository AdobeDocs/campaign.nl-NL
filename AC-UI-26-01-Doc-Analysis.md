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

1. **[wisselstroom-UI-26-01-Maandelijkse Artikelen ](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - de Hoofdversieverhalen
2. **[NEO-92400 Verbeteringen ](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** - De verbeteringen van de versie verbonden kwesties
3. **[wisselstroom-UI-25-11-Maandelijkse Artikelen ](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Vorige versieoverdracht
4. **[wisselstroom-UI-25-11 die 8.8.2 ](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20en%20type%20%3D%20story%20order%20by%20status) uitsluiten** - Gegilterde vorige versie

---

## 🟢 DOCAC maken

### [ NEO-91565 ](https://jira.corp.adobe.com/browse/NEO-91565) - voeg steun voor verpersoonlijkingsgebieden (de Geavanceerde Integratie van AEM) toe
**Status:** Resolved\
**vereiste Doc:** ja\
**Bestaande DOCAC:** niets\
**Actie:** creeer DOCAC

**Reikwijdte:**
- Documentondersteuning voor verpersoonlijkingsvelden in Geavanceerde AEM-integratie
- UI-workflow en configuratiestappen
- AEM-mogelijkheden voor meertalige integratie

**Beschrijving van de Eigenschap:**
Ondersteuning voor het toevoegen van verpersoonlijkingsvelden in leveringen met behulp van Geavanceerde AEM-integratie, zodat dynamische inhoud vanuit Campagnegegevens kan worden ingevoegd in e-mailsjablonen die door AEM zijn gemaakt.

**Context:** ACS aan ACC pariteit, MSFT-Specifiek vereiste

**Verwijzingen:** [ meertalige wiki van AEM ](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

---

### [ NEO-93487 ](https://jira.corp.adobe.com/browse/NEO-93487) - Levering die verwerkt proces (pariteit ACS) plant
**Status:** Nieuw\
**vereiste Doc:** ja\
**Bestaande DOCAC:** niets\
**Actie:** creeer DOCAC

**Reikwijdte:**
- De levering van het document plannend verwerkt proces voor dupberichten
- Tijdzonegebaseerde planningsformules
- Bestandsupload voor doelen voor meerdere tijdzones

**Beschrijving van de Eigenschap:**
Schakel op OOTB-bestanden gebaseerde planning voor levering met berekende verzendtijden in op basis van de tijdzone van de ontvanger, zodat één levering voor meerdere tijdzones met geoptimaliseerde verzendtijden per regio mogelijk is.

**Context:** Klant-gedreven (H&amp;M), ACS aan ACC pariteit vereiste

**Verwijzingen:** [ documentatie ACS ](https://experienceleague.adobe.com/en/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

---

## 🔄 DOCAC bijwerken

### [ NEO-80973 ](https://jira.corp.adobe.com/browse/NEO-80973) - Dynamische rapporteringsbeschikbaarheid voor alle gebruikers van Web UI
**Status:** Bezig\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-11070 ](https://jira.corp.adobe.com/browse/DOCAC-11070) (Gesloten), [ DOCAC-13432 ](https://jira.corp.adobe.com/browse/DOCAC-13432) (Opgelost)\
**Actie:** Overzicht DOCAC

**Reikwijdte:**
- De beschikbaarheidsinformatie van de update (nu voor alle gebruikers van het Web UI, niet alleen 8.7)
- Taalbeperkingen voor documenten
- Conflicterende metrische weergave verduidelijken met verouderde rapportage

**Beschrijving van de Eigenschap:**
De dynamische Rapportering is nu beschikbaar voor alle gebruikers van het Web UI van de Campagne (eerder beperkt tot 8.7 ACS aan klanten ACC), die geavanceerde analyses en douane rapporteringsmogelijkheden van interface ACS-Stijl verstrekken.

**Context:** De uitbreiding van de Eigenschap, achterste bouwt gebiedsdeel (8.8.1)

**Verwijzingen:** [ Wiki - de vergelijking van Rapporten ](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

---

### [ NEO-86754 ](https://jira.corp.adobe.com/browse/NEO-86754) - het Testen A/B
**Status:** Bezig\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-13104 ](https://jira.corp.adobe.com/browse/DOCAC-13104) (Nieuw)\
**Actie:** Update DOCAC

**Reikwijdte:**
- Documentatie van de testworkflow voor A/B voltooien
- Instellen en configuratie van varianten voor het experimenteren met inhoud
- Bepaling van de voorbeeldverhouding en selectiecriteria voor de winnaar
- Verzameling en evaluatie van statistieken

**Beschrijving van de Eigenschap:**
Inhoud experimenteren en A/B testen op e-mailleveringen, zodat marketers verschillende inhoudsvarianten kunnen testen, voorbeeldgrootten kunnen definiëren, prestatiestatistieken kunnen verzamelen en de winnende variant automatisch naar de resterende ontvangers kunnen sturen.

**Context:** het project van Europa, Microsoft vereiste, toegelaten eigenschapvlag

**Verwijzingen:** [ Wiki ](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [ Mocks van Figma ](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

---

### [ NEO-76126 ](https://jira.corp.adobe.com/browse/NEO-76126) - het auteursrecht van Schema&#39;s (creeer nieuwe lijst, breid schema&#39;s, toegang externe OB uit)
**Status:** Bezig\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-13826 ](https://jira.corp.adobe.com/browse/DOCAC-13826) (Nieuw)\
**Actie:** Update DOCAC

**Reikwijdte:**
- Ontwerpworkflow voor documentschema (alleen drie opties: tabel maken, schema uitbreiden, externe DB openen)
- Formulierdefinitie voor aangepaste entiteiten
- Navigeren en CRUD-bewerkingen op aangepaste schema&#39;s
- Mogelijkheden van fase 2 en fase 3

**Beschrijving van de Eigenschap:**
De auteursmogelijkheden van het schema in Web UI die beheerders toestaan om nieuwe gegevensbestandlijsten tot stand te brengen, bestaande schema&#39;s met douanevelden uit te breiden, en met externe gegevensbestanden - essentieel voor de aanpassing van het gegevensmodel te verbinden.

**Context:** Microsoft vereiste, Europa project, gefaseerde levering (Fase 2 actief, Fase 3 Feb eind)

**Verwijzingen:** [ PRD ](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [ Cijfer ](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

---

### [ NEO-92668 ](https://jira.corp.adobe.com/browse/NEO-92668) - de Analytics van het Web
**Status:** Nieuw\
**vereiste Doc:** ja\
**Bestaande DOCAC:** niets\
**Actie:** creeer DOCAC

**Reikwijdte:**
- Webanalyse externe accountconfiguratie
- Instellen en verifiëren van integratie
- Gebruik van analysegegevens in campagnes

**Beschrijving van de Eigenschap:**
Integratie met Web Analytics maakt verbinding met webanalyseplatforms mogelijk voor het bijhouden en rapporteren van de campagneprestaties en het gedrag van de websitebezoeker.

**Context:** verzoek van de Klant (P2E-RSC), hangende milieubeschikbaarheid

**Verwijzingen:** niets verstrekte

---

### [ NEO-86753 ](https://jira.corp.adobe.com/browse/NEO-86753) - de integratie van AEM voor Levende exemplaren/de exemplaren van de Taal
**Status:** Nieuw\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-13829 ](https://jira.corp.adobe.com/browse/DOCAC-13829) (Opgelost)\
**Actie:** Overzicht DOCAC

**Reikwijdte:**
- Door AEM geleverde templates bekijken
- Met één klik persoonlijke kopieën en taalkopieën maken
- Workflow voor het maken van meerdere inhoudvarianten

**Beschrijving van de Eigenschap:**
Dankzij de gestroomlijnde AEM-integratie kunt u met één muisklik persoonlijke kopieën en taalkopieën maken van AEM-leveringssjablonen, waardoor het maken van meertalige campagnes voor AEM-gebruikers wordt vereenvoudigd.

**Context:** vereiste van Microsoft, het werk dat aan het team van Himanshu wordt overgebracht

**Verwijzingen:** [ documentatie ACS ](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html)

---

### [ NEO-88838 ](https://jira.corp.adobe.com/browse/NEO-88838) - de Redacteur van de Inhoud: De themavariabelen van het gebruik in fragment
**Status:** Nieuw\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-12941 ](https://jira.corp.adobe.com/browse/DOCAC-12941) (Nieuw)\
**Actie:** Update DOCAC

**Reikwijdte:**
- Themavariabelen in e-mailontwerper (Beta)
- Thema&#39;s in fragmenten gebruiken
- Activering van de Actie

**Beschrijving van de Eigenschap:**
Ondersteuning voor het gebruik van themavariabelen in inhoudsfragmenten, waardoor consistente branding en ontwerpsysteemtoepassingen in e-mailcomponenten met gecentraliseerd themabeheer mogelijk zijn.

**Context:** Op greep, de eigenschap van Acrite om worden herzien

**Verwijzingen:** [ ATU-5460 ](https://jira.corp.adobe.com/browse/ATU-5460)

---

## ➕ DOCAC maken (verbeteringen)

### [ NEO-92942 ](https://jira.corp.adobe.com/browse/NEO-92942) - Vooraf bepaalde filters - Gedeelde optie
**Status:** Resolved\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-13697 ](https://jira.corp.adobe.com/browse/DOCAC-13697) (het Overzicht van de Code), [ DOCAC-13522 ](https://jira.corp.adobe.com/browse/DOCAC-13522) (Gesloten - Helper)\
**Actie:** Overzicht DOCAC

**Reikwijdte:**
- Gedeelde optie voor vooraf gedefinieerde filters
- Zichtbaarheid filteren met andere operatoren (ACC vs gedrag Handelsreis)
- Gebruikersbeheer van gedeelde filters

**Beschrijving van de Eigenschap:**
Vooraf gedefinieerde filters kunnen nu worden gemarkeerd als ‘gedeeld’ om ze zichtbaar te maken voor andere operatoren, met een ander gedrag voor ACC (standaard) en Handelsreis (gebruikerspecifieke filtering).

**Context:** de bouwerverbetering van de Regel, eigenschapvlag: toelaat-vraag-filter-gedeeld

**Verwijzingen:** Verwant met [ NEO-88441 ](https://jira.corp.adobe.com/browse/NEO-88441)

---

### [ NEO-91299 ](https://jira.corp.adobe.com/browse/NEO-91299) - Ononderbroken leveringsactiviteit
**Status:** Gesloten\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-13586 ](https://jira.corp.adobe.com/browse/DOCAC-13586) (Nieuw), [ DOCAC-13808 ](https://jira.corp.adobe.com/browse/DOCAC-13808) (Gesloten - contextuele hulp)\
**Actie:** Update DOCAC

**Reikwijdte:**
- Continue workflow voor levering
- Configuratie van de sjabloonkiezer voor levering
- Automatisch uitgaande overgangsgeneratie
- Doelopties (geen toegang tot inhoud)

**Beschrijving van de Eigenschap:**
De ononderbroken leveringsactiviteit voor werkschema&#39;s laat terugkomende leveringsuitvoering van malplaatjes toe, die automatisch uitgaande overgangen voor werkschemorchestratie produceren zonder inhoudwijziging.

**Context:** markering van de Eigenschap: laat-ononderbroken-levering toe

**Verwijzingen:** Verwante epische [ NEO-67972 ](https://jira.corp.adobe.com/browse/NEO-67972)

---

### [ NEO-90130 ](https://jira.corp.adobe.com/browse/NEO-90130) - laat OTB Dossier toe uploadt voor Meertalige Push Meldingen
**Status:** Gesloten\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-13606 ](https://jira.corp.adobe.com/browse/DOCAC-13606) (Nieuw)\
**Actie:** Update DOCAC

**Reikwijdte:**
- Bestanden uploaden voor meertalige pushberichten (iOS en Android)
- CSV-indeling en veldtoewijzing
- Krachtige pushondersteuning met meertalige mogelijkheden

**Beschrijving van de Eigenschap:**
OOTB-mogelijkheid voor het uploaden van bestanden voor het maken van meertalige pushberichten via CSV-import, overeenkomende ACS-functionaliteit en efficiënte meertalige campagneconfiguratie.

**Context:** Klantgedreven (H&amp;M), ACS aan ACC pariteit, kritiek voor migratie

**Verwijzingen:** [ documentatie ACS ](https://experienceleague.adobe.com/en/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

---

## ❌ Geannuleerd / Niet meer van toepassing

### [ NEO-91566 ](https://jira.corp.adobe.com/browse/NEO-91566) - Steun voor het volgen van CTA in webui
**Status:** Gesloten (niet meer van toepassing)\
**vereiste Doc:** Nr.\
**Bestaande DOCAC:** [ DOCAC-13821 ](https://jira.corp.adobe.com/browse/DOCAC-13821) (Nieuw)\
**Actie:** Sluiten DOCAC

**Reden:** Nieuwe eigenschap ACS om MSFT te steunen - niet begonnen, hangende info van MSFT, geen werk UI verwacht

**Context:** Microsoft-Specifiek, het volgen van CTA vereiste

---

### [ NEO-91564 ](https://jira.corp.adobe.com/browse/NEO-91564) - de meertalige steun van de UI van AEM
**Status:** Gesloten (niet meer van toepassing)\
**vereiste Doc:** Nr.\
**Bestaande DOCAC:** [ DOCAC-13822 ](https://jira.corp.adobe.com/browse/DOCAC-13822) (Nieuw)\
**Actie:** Sluiten DOCAC

**Reden:** het werk UI dat door het team van Himanshu (verschillend verhaal) wordt geleid

**Context:** vereiste van Microsoft, overgebracht werk

---

### [ NEO-91567 ](https://jira.corp.adobe.com/browse/NEO-91567) - voeg steun voor Eigenschap NRT toe
**Status:** Resolved (past niet meer toe)\
**vereiste Doc:** Nr.\
**Bestaande DOCAC:** [ DOCAC-13824 ](https://jira.corp.adobe.com/browse/DOCAC-13824) (Nieuw)\
**Actie:** Sluiten DOCAC

**Reden:** Nieuwe ACS specifieke eigenschap voor MSFT - specificatie beschikbaar maar geen Web UI effect

**Context:** Microsoft vereiste, transactioneel overseinen

---

### [ NEO-91563 ](https://jira.corp.adobe.com/browse/NEO-91563) - Transactionele Rest API voor Profiel Gebaseerde Verrijking
**Status:** Resolved (past niet meer toe)\
**vereiste Doc:** Nr.\
**Bestaande DOCAC:** [ DOCAC-13825 ](https://jira.corp.adobe.com/browse/DOCAC-13825) (Nieuw)\
**Actie:** Sluiten DOCAC

**Reden:** Geen het werk van Web UI, in afwachting van promotieinstantie, bouwt verplichte verbetering voor versie

**Context:** REST API eindpunteigenschap

---

### [ NEO-92151 ](https://jira.corp.adobe.com/browse/NEO-92151) - Profiel gebaseerde Fase 2 van het Overseinen van de Transactionele Verrijking van het Profiel
**Status:** Resolved (past niet meer toe)\
**vereiste Doc:** Nr.\
**Bestaande DOCAC:** [ DOCAC-13823 ](https://jira.corp.adobe.com/browse/DOCAC-13823) (Nieuw)\
**Actie:** Sluiten DOCAC

**Reden:** het Artikel heeft geen taken, duidelijk als &quot;niet meer van toepassing is&quot;

**Context:** Microsoft vereiste, project Europa

---

## 🟢 Documentatie gereed (van AC-UI-25-11)

### [ NEO-90183 ](https://jira.corp.adobe.com/browse/NEO-90183) - Meertalig Rich Push - UI
**Status:** Gesloten\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-13565 ](https://jira.corp.adobe.com/browse/DOCAC-13565) (Nieuw)\
**Actie:** Overzicht DOCAC

**Reikwijdte:**
- Rijke pushvelden voor meertalige leveringen
- iOS- en Android-platformondersteuning
- Configuratie van sjablonen en inhoud

**Beschrijving van de Eigenschap:**
Uitgebreide ondersteuning voor pushmeldingen met meertalige mogelijkheden, waardoor marketers verbeterde pushmeldingen kunnen maken met afbeeldingen, knoppen en geavanceerde media voor zowel iOS als Android in meerdere talen.

**Context:** Klantgedreven (H&amp;M), die in 25-11 wordt geleverd, voltooide achterste werk

**Verwijzingen:** [ Wiki ](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

---

### [ NEO-84916 ](https://jira.corp.adobe.com/browse/NEO-84916) - opstelling en beheer het goedkeuringsproces
**Status:** Resolved\
**vereiste Doc:** ja\
**Bestaande DOCAC:** [ DOCAC-13827 ](https://jira.corp.adobe.com/browse/DOCAC-13827) (Nieuw)\
**Actie:** Update DOCAC

**Reikwijdte:**
- Validatieoperatoren configureren in levering/campagne
- Setup van goedkeuringswerkstroom
- Goedkeuringsprocedure voor inhoud en doel
- Ondersteuning voor meerdere kanalen (e-mail, SMS, push, direct mail, callcenter, aangepast)

**Beschrijving van de Eigenschap:**
Het beheer van het goedkeuringsproces dat bevestigingswerkschema&#39;s voor leveringsinhoud en het richten toelaat, met exploitant toewijzing en goedkeuring het volgen over alle leveringskanalen.

**Context:** Klantgedreven (Pierre Fabre), Microsoft vereiste, dev volledig en in test

**Verwijzingen:** [ Klassieke documentatie ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [ Mocks van Figma ](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

---

## 📊 Samenvatting door actie

| Actie | Aantal |
|--------|-------|
| 🟢 DOCAC maken | 3 |
| 🔄 DOCAC bijwerken | 6 |
| ✅ DOCAC controleren | 3 |
| ❌ DOCAC sluiten | 5 |
| **Totaal** | **17** |

---

## ⚠️ Vragen openen

1. NEO-93487 - H&amp;M-escalatie - vereist dringende aandacht voor het plannen van het computerproces
2. NEO-92668 - Web Analytics - wachtend op milieubeschikbaarheid alvorens de documentatie kan worden voltooid
3. NEO-76126 - Schemas Fase 3 - ETA Feb end, behoefte aan een apart documentatieverhaal
4. NEO-88838 - Themavariabelen - in afwachting van Acrite-functieherziening in behandeling
5. Dynamische rapportering - verduidelijk conflicterende metriek vertoningsbegeleiding met erfenisrapportering

---

## 🔗 Verwante objecten

- NEO-85263 - ACS naar bovenliggende epic van ACC (EUROPA)
- NEO-67972 - Workflowverbeteringen
- NEO-87980 - Geavanceerde AEM-integratie
- NEO-90199 - Dynamische gereedheid voor release van rapporten
- NEO-63067 - Inhoudsexperimentatie UX/UI
- NEO-67726 - A/B-tests en inhoudexperimenten
- NEO-85274 - Schema en formulier (fase 2)
- NEO-87993 - Schema en formulier (fase 3)
