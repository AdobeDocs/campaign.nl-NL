---
product: Adobe Campaign
title: Aan de slag met de automatisering van campagnes
description: Aan de slag met de automatisering van campagnes
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 40b38168a3704f171f1f389e2d232e6a2c6f1d85
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 7%

---

# Processen beheren en automatiseren

Configureer Campagne om krachtige mogelijkheden voor automatisering van marketingcampagnes te benutten.

U kunt instellen:

* Workflows
* Recurricampagnes
* Eindvalidatiecyclus
* Waarschuwingen
* Automatisch rapport verzenden
* Gebeurtenissen geactiveerd

## Workflows ontwerpen en gebruiken{#gs-ac-wf}

Gebruik Adobe Campaign-workflows om de snelheid en schaal van elk aspect van uw marketingcampagnes te verbeteren, van het maken van segmenten en het voorbereiden van berichten tot de levering.

Leer hoe u workflows ontwerpt in deze [gebruiksgevallen van begin tot eind](#end-to-end-uc).

Meer informatie over de gebruikersinterface en uitvoering van workflows vindt u in de Campaign Classic v7-documentatie:

[!DNL :arrow_upper_right:]  [Aan de slag met workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Workflowactiviteiten:
   * [Doelactiviteiten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html): Query, lijst Lezen, Verrijking, Vereniging en meer
   * [Stroombeheeractiviteiten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html): Planner, Fork, Alert, Extern signaal, en meer
   * [Actie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html): Kanaalleveringen, JavaScript-code, CRM-activiteiten, aggregaat bijwerken en meer
   * [Gebeurtenisactiviteiten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html): Bestandsoverdracht, webdownload en meer
      [!DNL :arrow_upper_right:]  [Een publiek maken in een workflow voor een marketingcampagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)

      [!DNL :arrow_upper_right:]  [Best practices voor workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
      [!DNL :arrow_upper_right:] [Ingebouwde technische workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
      [!DNL :arrow_upper_right:] [Uitvoering van workflows controleren](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)


## Herhalende campagnes instellen

Regelterugkerende workflows ontwerpen en telkens wanneer de workflow wordt uitgevoerd, een nieuwe leveringsinstantie maken. Als uw workflow bijvoorbeeld eenmaal per week wordt uitgevoerd, levert dat na één jaar 52 leveringen op. Dit betekent ook dat de logboeken door elke leveringsinstantie zullen worden gescheiden.

[!DNL :arrow_upper_right:] Leer hoe u een terugkerende campagne kunt maken in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).


## Hefboomtriggergebeurtenissen

Het Transactionele overseinen van de Campagne van het gebruik om berichten te automatiseren die van gebeurtenissen worden geproduceerd die van informatiesystemen worden teweeggebracht. Deze transactiemeldingen kunnen bijvoorbeeld bestaan uit facturen, orderbevestiging, bevestiging van verzending, wijziging van het wachtwoord, kennisgeving van onbeschikbaarheid van het product, rekeningafschriften of het maken van websiteaccounts. Deze berichten kunnen individueel of in partij via e-mail, SMS of push berichten worden verzonden.

[!DNL :bulb:] Meer informatie over mogelijkheden voor transactieberichten vindt u in  [deze sectie](../send/transactional.md).

Verbind Adobe Campaign en Adobe Analytics om gebruikersacties terug te winnen en dichtbij real-time gepersonaliseerde berichten te verzenden.

[!DNL :bulb:] Leer hoe u campagne kunt integreren met andere oplossingen in  [deze sectie](../start/connect.md)


## Gebruiksscenario&#39;s van begin tot eind van het werkschema{#end-to-end-uc}

In deze sectie vindt u verschillende gebruiksgevallen waarbij gebruik wordt gemaakt van de mogelijkheden van de campagne-workflows. Deze gebruiksgevallen zijn ingebouwd in Adobe Campaign Classic v7 en zijn van toepassing op Adobe Campaign v8.

### Leveringen {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [A/B-tests](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html)

   Leer hoe u twee inhoud van e-mailbezorging via een doelworkflow kunt vergelijken. Het bericht en de tekst zijn identiek in beide leveringen: alleen de layout wordt gewijzigd. De doelgroep bestaat uit drie groepen: twee testgroepen en de resterende populatie. Een verschillende versie van de levering wordt verzonden naar elke testgroep.

* [Een verjaardags-e-mail verzenden](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html)

   In dit geval wordt beschreven hoe u een terugkerende e-mail naar een lijst met ontvangers op de dag van hun geboortedatum wilt sturen.

* [Leveringscontent laden](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)

   Wanneer uw leveringsinhoud beschikbaar is in een HTML-bestand dat zich op een externe server bevindt, kunt u deze inhoud gemakkelijk laden in Adobe Campaign-leveringen.

* [Workflow voor levering tussen kanalen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)

   Leer hoe u een workflow voor levering tussen kanalen kunt maken. Het doel is een publiek van de ontvangers van uw gegevensbestand in verschillende groepen te segmenteren en een e-mail naar de eerste groep en een SMS naar andere te verzenden.

* [E-mailverrijking met aangepaste datumvelden](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)

   Leer hoe u een e-mail met aangepaste gegevensvelden verzendt naar profielen die deze maand hun verjaardagen vieren. Het e-mailbericht bevat een coupon die een week voor en na hun verjaardag geldig is.

* [Het maken, bewerken en publiceren van content automatiseren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html)

   Leer hoe u het maken en leveren van een inhoudsblok kunt automatiseren met de invoegtoepassing Campagne Content Management.


### Controle {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Een rapport naar een lijst verzenden](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html)

   Leer hoe u maandelijks een ingebouwd traceringsindicatoren genereert in PDF-indeling en deze naar een lijst met campagneoperatoren verzendt.

* [Uw workflows controleren](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html)

   Leer hoe u een workflow maakt waarmee u de status van een set workflows kunt controleren die &#39;gepauzeerd&#39;, &#39;gestopt&#39; of &#39;met fouten&#39; zijn.

* [Gepersonaliseerde waarschuwingen verzenden naar operatoren](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html)

   Leer hoe u een waarschuwing verzendt naar een operator die de naam bevat van profielen die een nieuwsbrief hebben geopend maar niet op de koppeling in die nieuwsbrief hebben geklikt.

### Data management {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Gegevensupdates coördineren](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html)

   Leer hoe u kunt controleren of het updateproces is beëindigd voordat u een andere updatebewerking uitvoert. Hiervoor wordt een instantievariabele ingesteld en wordt in de workflow getest of de instantie wordt uitgevoerd om te bepalen of de workflow moet worden voortgezet en of de update moet worden uitgevoerd.

* [Een overzichtslijst maken](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html)

   Leer hoe u een workflow maakt waarin u na het verzamelen van bestanden en na diverse verbeteringen een overzichtslijst kunt maken. Het voorbeeld is gebaseerd op een lijst van contacten die aankopen in een opslag maakten.

* [Gegevens verrijken](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)

   Leer hoe u persoonlijke leveringen kunt verzenden naar profielen die afhankelijk van hun score hebben deelgenomen aan de meest recente wedstrijd.

* [Aggregaten gebruiken](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html)

   Leer hoe u de ontvangers kunt identificeren die het laatst aan de database zijn toegevoegd.

* [Driemaandelijkse lijstupdate met een incrementele query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html)

   Leer hoe u een incrementele query gebruikt om een lijst met ontvangers automatisch bij te werken.

* [Een workflow instellen voor terugkerende importactiviteiten](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html)

   Leer hoe u een workflow ontwerpt die opnieuw kan worden gebruikt voor het importeren van profielen die afkomstig zijn van een CRM in de Adobe Campaign-database.

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Een query uitvoeren op de tabel met ontvangers](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html)

   Leer hoe u de namen en e-mails kunt herstellen van ontvangers met als e-maildomein &quot;orange.co.uk&quot; en die niet in Londen wonen.

* [Query uitvoeren voor verzendingsinformatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html)

   Leer hoe te om vragen over leveringsinformatie te bepalen om het gedrag van het profiel terug te winnen.

* [Samengevoegde aggregaten berekenen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html)

   Leer hoe u het aantal profielen dat in Londen woont, kunt tellen volgens geslacht.

* [Een query uitvoeren met behulp van een veel-op-veel-relatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html)

   Leer hoe u profielen kunt vinden die de afgelopen 7 dagen niet zijn benaderd.

* [Een instantievariabele aanroepen in een query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example)

   Leer hoe u een instantievariabele gebruikt om dynamisch het splitsingspercentage te berekenen dat op een populatie moet worden toegepast.

