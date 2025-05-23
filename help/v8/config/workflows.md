---
title: Processen beheren en automatiseren met Adobe Campaign-workflows
description: Aan de slag met workflows
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 8e1401ef0aada30d941905936b45c6c1819c83a7
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 0%

---

# Aan de slag met workflows{#gs-with-workflows}

Configureer Campagne om krachtige mogelijkheden voor automatisering van marketingcampagnes te benutten.

U kunt instellen:

* Workflows
* Recurricampagnes
* Eindvalidatiecyclus
* Waarschuwingen
* Automatisch rapport verzenden
* Gebeurtenissen geactiveerd

>[!NOTE]
>
>De gebruikersinterface van het Web van Adobe Campaign komt met een herbedacht canvas voor werkschema&#39;s, die toestaan om dynamischere en gepersonaliseerde klantenreizen tot stand te brengen. Meer over Werkschema&#39;s voor Web UI leren, gelieve te verwijzen naar [ documentatie van het Web UI van Adobe Campaign ](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/wf/gs-workflows){target=_blank}.


## Workflows ontwerpen en gebruiken {#gs-ac-wf}

Gebruik Adobe Campaign-workflows om de snelheid en schaal van elk aspect van uw marketingcampagnes te verbeteren, van het maken van segmenten en het voorbereiden van berichten tot de levering.

Leer hoe te om werkschema&#39;s in deze [ gebruiksgevallen van begin tot eind te ontwerpen ](#end-to-end-uc).

Meer informatie over de gebruikersinterface en uitvoering van workflows vindt u op de volgende pagina&#39;s:

* [Aan de slag met workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=nl-NL){target="_blank"}

* [Best practices voor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=nl-NL){target="_blank"}

* [ Ingebouwde technische werkschema&#39;s ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=nl-NL){target="_blank"}

* [ de werkschema&#39;s van de Monitor uitvoering ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=nl-NL){target="_blank"}

* [ bouwt een publiek in een marketing campagnewerkschema ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=nl-NL){target="_blank"}

## Workflowactiviteiten {#wf-activities}

Leer meer over de beschikbare werkschemaactiviteiten in [ deze sectie ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=nl-NL){target="_blank"}

Workflowactiviteiten worden gegroepeerd op categorie. De vier categorieën activiteiten zijn beschikbaar:

* [ het richten activiteiten ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=nl-NL){target="_blank"}: Vraag, Gelezen lijst, Verrijking, Vereniging, en meer
* [ de controleactiviteiten van de Stroom ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=nl-NL){target="_blank"}: Planner, Bok, Alarm, Extern signaal, en meer
* [ activiteiten van de Actie ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=nl-NL){target="_blank"}: De leveringen van het dwars-kanaal, code Javascript, de activiteiten van CRM, Update aggregaat, en meer
* [ de activiteiten van de Gebeurtenis ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=nl-NL){target="_blank"}: De overdracht van het dossier, de download van het Web en meer

### Gegevensbronactiviteit wijzigen {#change-data-source-activity}

Met de **[!UICONTROL Change data source]** -activiteit kunt u de gegevensbron van een workflow wijzigen **[!UICONTROL Working table]** . Dit biedt meer flexibiliteit voor het beheer van gegevens in verschillende gegevensbronnen, zoals FDA, FFDA en de lokale database.

Met **[!UICONTROL Working table]** kan Adobe Campaign gegevens verwerken en gegevens delen met de workflowactiviteiten.
Standaard wordt **[!UICONTROL Working table]** gemaakt in dezelfde database als de bron van de gegevens waarop we een query uitvoeren.

Als u bijvoorbeeld een query uitvoert op de tabel **[!UICONTROL Profiles]** die is opgeslagen in de Cloud-database, maakt u een **[!UICONTROL Working table]** in dezelfde Cloud-database.
Als u dit wilt wijzigen, voegt u de **[!UICONTROL Change Data Source]** -activiteit toe en kiest u een andere gegevensbron voor uw **[!UICONTROL Working table]** .

Wanneer u de **[!UICONTROL Change Data Source]** -activiteit gebruikt, moet u terugschakelen naar de Cloud-database om door te gaan met de workflowuitvoering.

De **[!UICONTROL Change Data Source]** -activiteit gebruiken:

1. Maak een workflow.

1. Vraag de beoogde ontvangers naar een **[!UICONTROL Query]** -activiteit.

   Voor meer informatie over de **[!UICONTROL Query]** activiteit, verwijs naar [ deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=nl-NL){target="_blank"}.

1. Voeg op het tabblad **[!UICONTROL Targeting]** een **[!UICONTROL Change data source]** activiteit toe en dubbelklik erop om **[!UICONTROL Default data source]** te selecteren.

   De het werk lijst, die het resultaat van uw vraag bevat, wordt dan bewogen aan het gebrek PostSQL- gegevensbestand.

1. Sleep vanaf het tabblad **[!UICONTROL Actions]** een **[!UICONTROL JavaScript code]** -activiteit om eenheidsbewerkingen uit te voeren op de werktabel.

   Voor meer informatie over de **[!UICONTROL JavaScript code]** activiteit, verwijs naar [ deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=nl-NL){target="_blank"}.

1. Voeg nog een **[!UICONTROL Change data source]** -activiteit toe om terug te schakelen naar de Cloud-database.

   Dubbelklik op uw activiteit en selecteer **[!UICONTROL Active FDA external account]** en vervolgens de bijbehorende externe account.

1. U kunt nu uw workflow starten.

## Virtuele opslagruimten beheren {#warehouse}

Nadat u de workflow hebt gemaakt, hebt u toegang tot extra opties met de knop **[!UICONTROL Properties]** voor verdere configuratie.

Leer meer over **eigenschappen van het Werkschema** in [ deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=nl-NL){target="_blank"}.

Via het tabblad **[!UICONTROL Execution]** van de workflow **[!UICONTROL Properties]** kunt u de workflow aan verschillende opslagruimten koppelen en het werklastbeheer optimaliseren. Voor meer informatie over **Warehouses**, verwijs naar de [ documentatie van Snowflake ](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}.

![](assets/warehouse.png)

Afhankelijk van het doel van uw workflow kunt u kiezen tussen de volgende drie opslagruimten in de vervolgkeuzelijst **[!UICONTROL Warehouse]** :

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]** : wordt standaard ingesteld wanneer u een nieuwe workflow maakt.

* **[!UICONTROL Import / Export]**: moet worden ingesteld met workflows voor importeren of exporteren om de prestaties van uw activiteiten te optimaliseren.

* **[!UICONTROL Campaign Burst]**: moet worden ingesteld met campagne- of leveringsworkflows om de verwerkingstijd van de leveringen te optimaliseren.

>[!NOTE]
>
>Het **[!UICONTROL System]** -pakhuis is alleen ingesteld voor ingebouwde workflows.

## Herhalende campagnes instellen

Regelterugkerende workflows ontwerpen en telkens wanneer de workflow wordt uitgevoerd, een nieuwe leveringsinstantie maken. Als uw workflow bijvoorbeeld eenmaal per week wordt uitgevoerd, levert dat na één jaar 52 leveringen op. Dit betekent ook dat de logboeken door elke leveringsinstantie zullen worden gescheiden.

Leer hoe te om een terugkomende campagne in [ tot stand te brengen deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=nl-NL){target="_blank"}.


## Hefboomtriggergebeurtenissen

Het Transactionele overseinen van de Campagne van het gebruik om berichten te automatiseren die van gebeurtenissen worden geproduceerd die van informatiesystemen worden teweeggebracht. Deze transactiemeldingen kunnen bijvoorbeeld bestaan uit facturen, orderbevestiging, bevestiging van verzending, wijziging van het wachtwoord, kennisgeving van onbeschikbaarheid van het product, rekeningafschriften of het maken van websiteaccounts. Deze berichten kunnen individueel of in partij via e-mail, SMS of push berichten worden verzonden.

Leer meer over transactionele overseinenmogelijkheden in [ deze sectie ](../send/transactional.md).

Verbind Adobe Campaign en Adobe Analytics om gebruikersacties terug te winnen en dichtbij real-time gepersonaliseerde berichten te verzenden.

Leer hoe te om Campagne met andere oplossingen in [ te integreren deze sectie ](../start/connect.md)


## Gebruiksgevallen van end-to-end werkstroom{#end-to-end-uc}

In deze sectie vindt u verschillende gebruiksgevallen waarbij gebruik wordt gemaakt van de mogelijkheden van de campagne-workflows.

### Leveringen {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [Een verjaardags-e-mail verzenden](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=nl-NL){target="_blank"}

  In dit geval wordt beschreven hoe u een terugkerende e-mail naar een lijst met ontvangers op de dag van hun geboortedatum wilt sturen.

* [ de leveringsinhoud van de Lading ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=nl-NL){target="_blank"}
Wanneer uw leveringsinhoud beschikbaar is in een HTML-bestand dat zich op een externe server bevindt, kunt u deze inhoud gemakkelijk laden in Adobe Campaign-leveringen.

* [ het werkschema van de 10 kanaallevering ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html?lang=nl-NL){target="_blank"}
Leer hoe u een workflow voor levering tussen kanalen kunt maken. Het doel is een publiek van de ontvangers van uw gegevensbestand in verschillende groepen te segmenteren en een e-mail naar de eerste groep en een SMS naar andere te verzenden.

* [ de verrijking van e-mail met de gebieden van de douanedatum ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html?lang=nl-NL){target="_blank"}
Leer hoe u een e-mail met aangepaste gegevensvelden verzendt naar profielen die deze maand hun verjaardagen vieren. Het e-mailbericht bevat een coupon die een week voor en na hun verjaardag geldig is.

En deze pagina&#39;s in Campaign v7 documentatie:

* [ Automat inhoudsverwezenlijking, uitgave en het publiceren ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html?lang=nl-NL){target="_blank"}
Leer hoe u het maken en leveren van een inhoudsblok kunt automatiseren met de invoegtoepassing Campagne Content Management.

* [ het testen A/B ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html?lang=nl-NL){target="_blank"}
Leer hoe u twee inhoud van e-mailbezorging via een doelworkflow kunt vergelijken. Het bericht en de tekst zijn identiek in beide leveringen: alleen de layout wordt gewijzigd. De beoogde populatie is verdeeld in drie: twee testgroepen en de resterende populatie. Een verschillende versie van de levering wordt verzonden naar elke testgroep.

### Toezicht {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [ verzend een rapport naar een lijst ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html?lang=nl-NL){target="_blank"}
Leer hoe u maandelijks een ingebouwd traceringsindicatoren genereert in PDF-indeling en deze verzendt naar een lijst met campagneoperatoren.

* [ controleert uw werkschema&#39;s ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html?lang=nl-NL){target="_blank"}
Leer hoe u een workflow maakt waarmee u de status van een set workflows kunt controleren die &#39;gepauzeerd&#39;, &#39;gestopt&#39; of &#39;met fouten&#39; zijn.

* [ verzend gepersonaliseerde alarm naar exploitanten ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html?lang=nl-NL){target="_blank"}
Leer hoe u een waarschuwing verzendt naar een operator die de naam bevat van profielen die een nieuwsbrief hebben geopend maar niet op de koppeling in die nieuwsbrief hebben geklikt.

### Gegevensbeheer {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [ de gegevensupdates van de Coördinaat ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html?lang=nl-NL){target="_blank"}
Leer hoe u kunt controleren of het updateproces is beëindigd voordat u een andere updatebewerking uitvoert. Hiervoor wordt een instantievariabele ingesteld en wordt in de werkstroom getest of de instantie wordt uitgevoerd om te beslissen of de werkstroom verder wordt uitgevoerd en de update wordt uitgevoerd.

* [ creeer een summiere lijst ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html?lang=nl-NL){target="_blank"}
Leer hoe u een workflow maakt waarin u na het verzamelen van bestanden en na diverse verbeteringen een overzichtslijst kunt maken. Het voorbeeld is gebaseerd op een lijst van contacten die aankopen in een opslag maakten.

* [ verrijkt gegevens ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=nl-NL){target="_blank"}
Leer hoe u persoonlijke leveringen kunt verzenden naar profielen die afhankelijk van hun score hebben deelgenomen aan de meest recente wedstrijd.

* [ de aggregaten van het Gebruik ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=nl-NL){target="_blank"}
Leer hoe u de ontvangers kunt identificeren die het laatst aan de database zijn toegevoegd.

* [ driemaandelijkse lijstupdate die een stijgende vraag gebruikt ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html?lang=nl-NL){target="_blank"}
Leer hoe u een incrementele query gebruikt om een lijst met ontvangers automatisch bij te werken.

* [ Opstelling een terugkomende het invoerwerkschema ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=nl-NL){target="_blank"}
Leer hoe u een workflow ontwerpt die opnieuw kan worden gebruikt voor het importeren van profielen die afkomstig zijn van een CRM in de Adobe Campaign-database.

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [ Vraag de ontvankelijke lijst ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html?lang=nl-NL){target="_blank"}
Leer hoe u de namen en e-mails kunt herstellen van ontvangers met als e-maildomein &quot;orange.co.uk&quot; en die niet in Londen wonen.

* [ de leveringsinformatie van de Vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html?lang=nl-NL){target="_blank"}
Leer hoe te om vragen over leveringsinformatie te bepalen om het gedrag van het profiel terug te winnen.

* [ Rekte aggregaten ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html?lang=nl-NL){target="_blank"}
Leer hoe u het aantal profielen dat in Londen woont, kunt tellen op basis van geslacht.

* [ Vraag die een veel-aan-veel-verhouding ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html?lang=nl-NL){target="_blank"} gebruikt
Leer hoe u profielen kunt vinden die de afgelopen 7 dagen niet zijn benaderd.

* [ Vraag een instantievariabele in een vraag ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html?lang=nl-NL){target="_blank"}
Leer hoe u een instantievariabele gebruikt om dynamisch het splitsingspercentage te berekenen dat op een populatie moet worden toegepast.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=nl-NL#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

