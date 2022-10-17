---
title: Processen beheren en automatiseren met Adobe Campaign-workflows
description: Aan de slag met workflows
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: b323dbf9504e39cca78f7082089b864544ee1633
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 1%

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

## Workflows ontwerpen en gebruiken{#gs-ac-wf}

Gebruik Adobe Campaign-workflows om de snelheid en schaal van elk aspect van uw marketingcampagnes te verbeteren, van het maken van segmenten en het voorbereiden van berichten tot de levering.

Leer hoe u workflows ontwerpt in deze [gebruiksgevallen van begin tot eind](#end-to-end-uc).

Meer informatie over de gebruikersinterface en uitvoering van workflows vindt u op de volgende pagina&#39;s:

* [Aan de slag met workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)

* [Best practices voor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html)

* [Ingebouwde technische workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html)

* [Uitvoering van workflows controleren](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html)

* [Een publiek maken in een workflow voor een marketingcampagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)

## Workflowactiviteiten {#wf-activities}

Meer informatie over de beschikbare workflowactiviteiten vindt u in [deze sectie](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html)

Workflowactiviteiten worden gegroepeerd op categorie. De vier categorieën activiteiten zijn beschikbaar:

* [Gerichte activiteiten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html): Query, lijst Lezen, Verrijking, Vereniging en meer
* [Stroombeheeractiviteiten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html): Planner, Fork, Alert, Extern signaal, en meer
* [Acties](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html): Kanaalleveringen, JavaScript-code, CRM-activiteiten, aggregaat bijwerken en meer
* [Gebeurtenisactiviteiten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html): Bestandsoverdracht, webdownload en meer

### Gegevensbronactiviteit wijzigen {#change-data-source-activity}

De **[!UICONTROL Change data source]** activiteit staat u toe om de gegevensbron van een werkschema te veranderen **[!UICONTROL Working table]**. Dit biedt meer flexibiliteit voor het beheer van gegevens in verschillende gegevensbronnen, zoals FDA, FFDA en de lokale database.

De **[!UICONTROL Working table]** staat Adobe Campaign-workflow toe om gegevens te verwerken en gegevens te delen met de workflowactiviteiten.
Standaard worden de **[!UICONTROL Working table]** wordt gecreeerd in het zelfde gegevensbestand zoals de bron van de gegevens wij waarvragen.

Wanneer u bijvoorbeeld het **[!UICONTROL Profiles]** tabel, opgeslagen in de Cloud-database, maakt u een **[!UICONTROL Working table]** in dezelfde Cloud-database.
Als u dit wilt wijzigen, kunt u de opdracht **[!UICONTROL Change Data Source]** activiteit om een verschillende gegevensbron voor uw te kiezen **[!UICONTROL Working table]**.

Wanneer u de opdracht **[!UICONTROL Change Data Source]** is, moet u terugschakelen naar de Cloud-database om door te gaan met de uitvoering van de workflow.

Als u de opdracht **[!UICONTROL Change Data Source]** activiteit:

1. Een workflow maken.

1. Vraag uw beoogde ontvangers om een query met een **[!UICONTROL Query]** activiteit.

   Voor meer informatie over de **[!UICONTROL Query]** activiteit, zie [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).

1. Van de **[!UICONTROL Targeting]** tabblad, voegt u een **[!UICONTROL Change data source]** activiteit en dubbelklik het om te selecteren **[!UICONTROL Default data source]**.

   De het werk lijst, die het resultaat van uw vraag bevat, wordt dan bewogen aan het gebrek PostSQL- gegevensbestand.

1. Van de **[!UICONTROL Actions]** tabblad, slepen en neerzetten **[!UICONTROL JavaScript code]** activiteit om unitaire verrichtingen op de werkende lijst uit te voeren.

   Voor meer informatie over de **[!UICONTROL JavaScript code]** activiteit, zie [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html).

1. Nog een toevoegen **[!UICONTROL Change data source]** om terug te schakelen naar de Cloud-database.

   Dubbelklik op uw activiteit en selecteer **[!UICONTROL Active FDA external account]** vervolgens de overeenkomstige externe rekening.

1. U kunt nu uw workflow starten.

## Virtuele opslagruimten beheren {#warehouse}

Nadat u de workflow hebt gemaakt, hebt u toegang tot extra opties via de **[!UICONTROL Properties]** voor verdere configuratie.

Meer informatie over **Workflow-eigenschappen** in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html).

Van de **[!UICONTROL Execution]** tabblad van de workflow **[!UICONTROL Properties]**, kunt u uw workflow koppelen aan verschillende opslagruimten en het werklastbeheer optimaliseren. Voor meer informatie over **Waresthuizen**, verwijst u naar de [Snowflake-documentatie](https://docs.snowflake.com/en/user-guide/warehouses-overview.html).

![](assets/warehouse.png)

Afhankelijk van het doel van uw workflow kunt u kiezen tussen de volgende drie opslagruimten in het menu **[!UICONTROL Warehouse]** vervolgkeuzelijst:

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**: Wordt standaard ingesteld wanneer u een nieuwe workflow maakt.

* **[!UICONTROL Import / Export]**: moet worden ingesteld met workflows voor importeren of exporteren om de prestaties van uw activiteiten te optimaliseren.

* **[!UICONTROL Campaign Burst]**: moet worden ingesteld met campagne- of leveringsworkflows om de verwerkingstijd van de leveringen te optimaliseren.

>[!NOTE]
>
>De **[!UICONTROL System]** magazijn is alleen ingesteld voor ingebouwde workflows.

## Herhalende campagnes instellen

Regelterugkerende workflows ontwerpen en telkens wanneer de workflow wordt uitgevoerd, een nieuwe leveringsinstantie maken. Als uw workflow bijvoorbeeld eenmaal per week wordt uitgevoerd, levert dat na één jaar 52 leveringen op. Dit betekent ook dat de logboeken door elke leveringsinstantie zullen worden gescheiden.

Leer hoe u een terugkerende campagne kunt maken in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html)


## Hefboomtriggergebeurtenissen

Het Transactionele overseinen van de Campagne van het gebruik om berichten te automatiseren die van gebeurtenissen worden geproduceerd die van informatiesystemen worden teweeggebracht. Deze transactiemeldingen kunnen bijvoorbeeld bestaan uit facturen, orderbevestiging, bevestiging van verzending, wijziging van het wachtwoord, kennisgeving van onbeschikbaarheid van het product, rekeningafschriften of het maken van websiteaccounts. Deze berichten kunnen individueel of in partij via e-mail, SMS of push berichten worden verzonden.

![](../assets/do-not-localize/glass.png) Meer informatie over mogelijkheden voor transactieberichten vindt u in [deze sectie](../send/transactional.md).

Verbind Adobe Campaign en Adobe Analytics om gebruikersacties terug te winnen en dichtbij real-time gepersonaliseerde berichten te verzenden.

![](../assets/do-not-localize/glass.png) Leer hoe u campagne kunt integreren met andere oplossingen in [deze sectie](../start/connect.md)


## Gebruiksgevallen van end-to-end werkstroom{#end-to-end-uc}

In deze sectie vindt u verschillende gebruiksgevallen waarbij gebruik wordt gemaakt van de mogelijkheden van de campagne-workflows.

### Leveringen {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [Een verjaardags-e-mail verzenden](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html)

   In dit geval wordt beschreven hoe u een terugkerende e-mail naar een lijst met ontvangers op de dag van hun geboortedatum wilt sturen.

* [Leveringsinhoud laden](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html)
Wanneer uw leveringsinhoud beschikbaar is in een HTML-bestand dat zich op een externe server bevindt, kunt u deze inhoud gemakkelijk laden in Adobe Campaign-leveringen.

* [Workflow voor levering tussen kanalen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)
Leer hoe u een workflow voor levering tussen kanalen kunt maken. Het doel is een publiek van de ontvangers van uw gegevensbestand in verschillende groepen te segmenteren en een e-mail naar de eerste groep en een SMS naar andere te verzenden.

* [E-mailverrijking met aangepaste datumvelden](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)
Leer hoe u een e-mail met aangepaste gegevensvelden verzendt naar profielen die deze maand hun verjaardagen vieren. Het e-mailbericht bevat een coupon die een week voor en na hun verjaardag geldig is.

En deze pagina&#39;s in Campaign v7 documentatie:

* [Automatisch inhoud maken, edities en publiceren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target=&quot;_blank&quot;} Leer hoe u het maken en leveren van een inhoudsblok kunt automatiseren met de invoegtoepassing Inhoudsbeheer voor campagne.

* [A/B-tests](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target=&quot;_blank&quot;} Leer hoe u twee e-mailverzendinhoud kunt vergelijken via een doelworkflow. Het bericht en de tekst zijn identiek in beide leveringen: alleen de layout wordt gewijzigd. De doelgroep bestaat uit drie groepen: twee testgroepen en de resterende populatie. Een verschillende versie van de levering wordt verzonden naar elke testgroep.

### Controleren {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Een rapport naar een lijst verzenden](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html)
Leer hoe u maandelijks een ingebouwd traceringsindicatoren genereert in de indeling PDF en deze naar een lijst met campagneoperatoren verzendt.

* [Uw workflows controleren](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html)
Leer hoe u een workflow maakt waarmee u de status van een set workflows kunt controleren die &#39;gepauzeerd&#39;, &#39;gestopt&#39; of &#39;met fouten&#39; zijn.

* [Persoonlijke waarschuwingen verzenden aan operatoren](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html)
Leer hoe u een waarschuwing verzendt naar een operator die de naam bevat van profielen die een nieuwsbrief hebben geopend maar niet op de koppeling in die nieuwsbrief hebben geklikt.

### Data management {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Gegevensupdates coördineren](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html)
Leer hoe u kunt controleren of het updateproces is beëindigd voordat u een andere updatebewerking uitvoert. Hiervoor wordt een instantievariabele ingesteld en wordt in de werkstroom getest of de instantie wordt uitgevoerd om te beslissen of de werkstroom verder wordt uitgevoerd en de update wordt uitgevoerd.

* [Een overzichtslijst maken](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html)
Leer hoe u een workflow maakt waarin u na het verzamelen van bestanden en na diverse verbeteringen een overzichtslijst kunt maken. Het voorbeeld is gebaseerd op een lijst van contacten die aankopen in een opslag maakten.

* [Gegevens vergroten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html)
Leer hoe u persoonlijke leveringen kunt verzenden naar profielen die afhankelijk van hun score hebben deelgenomen aan de meest recente wedstrijd.

* [aggregaten gebruiken](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html)
Leer hoe u de ontvangers kunt identificeren die het laatst aan de database zijn toegevoegd.

* [Driemaandelijkse lijstupdate die een stijgende vraag gebruikt](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html)
Leer hoe u een incrementele query gebruikt om een lijst met ontvangers automatisch bij te werken.

* [Een terugkerende importworkflow instellen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html)
Leer hoe u een workflow ontwerpt die opnieuw kan worden gebruikt voor het importeren van profielen die afkomstig zijn van een CRM in de Adobe Campaign-database.

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Vraag de ontvankelijke lijst](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html)
Leer hoe u de namen en e-mails kunt herstellen van ontvangers met als e-maildomein &quot;orange.co.uk&quot; en die niet in Londen wonen.

* [Leveringsgegevens voor query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html)
Leer hoe te om vragen over leveringsinformatie te bepalen om het gedrag van het profiel terug te winnen.

* [Samengevoegde aggregaten berekenen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html)
Leer hoe u het aantal profielen dat in Londen woont, kunt tellen volgens geslacht.

* [Vraag die vele-aan-veel-verhouding gebruikt](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html)
Leer hoe u profielen kunt vinden die de afgelopen 7 dagen niet zijn benaderd.

* [Een instantievariabele aanroepen in een query](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html)
Leer hoe u een instantievariabele gebruikt om dynamisch het splitsingspercentage te berekenen dat op een populatie moet worden toegepast.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

