---
product: campaign
title: Workflowuitvoering controleren
description: Workflowuitvoering controleren
feature: Workflows
role: Admin
exl-id: bc13d706-7888-42eb-9116-5538e68cd515
source-git-commit: a78019d11a0a2acbd8c0d9ba7c2082c09f90356c
workflow-type: tm+mt
source-wordcount: '1926'
ht-degree: 0%

---

# Workflowuitvoering controleren {#monitoring-workflow-execution}

Deze sectie geeft informatie over hoe te om de uitvoering van uw werkschema&#39;s te controleren.

Er is ook een gebruiksscenario beschikbaar voor het maken van een workflow waarmee u de status kunt controleren van een set werkstromen die worden gepauzeerd, gestopt of met fouten. [deze sectie](workflow-supervision.md#supervising-workflows).

Daarnaast kunnen beheerders van de instantie de opdracht **Audittrail** om activiteiten en laatste wijzigingen te controleren aan werkschema&#39;s, de staat van uw werkschema&#39;s. Meer informatie over het audittrail in dit [page](../../v8/reporting/audit-trail.md){target="_blank"}.

## Voortgang weergeven {#displaying-progress}

U kunt de uitvoering controleren door de voortgang weer te geven met het juiste pictogram op de werkbalk.

De **[!UICONTROL Display progress information]** kunt u de status en het activiteitenresultaat weergeven in het uitvoeringsscherm.

![](assets/s_user_segmentation_toolbar_progr.png)

Als deze optie is geselecteerd, worden uitgevoerde activiteiten in blauw weergegeven, knipperende activiteiten in behandeling, worden waarschuwingen in oranje weergegeven en fouten in rood. Met deze optie geeft u ook het resultaat weer van activiteiten bij de uitgaande overgang, gevolgd door het label van het resultaat zoals gedefinieerd in de eigenschappen activity en de duur van de taak als deze langer is dan één seconde

![](assets/s_user_segmentation_results.png)

## Logboeken weergeven {#displaying-logs}

Het logbestand bevat de geschiedenis of audittrail van de workflow. Hiermee worden alle gebruikersacties, alle uitgevoerde bewerkingen en aangetroffen fouten geregistreerd. U kunt:

* Selecteer de **[!UICONTROL Tracking]** in het detail. Deze lijst bevat alle workflowberichten.

  ![](assets/new-workflow-display-log-tab.png)

* Filter de logboekberichten door activiteit. Om dit te doen, klik **[!UICONTROL Display the tasks and the log]** op de werkbalk boven het diagram om het **[!UICONTROL Log]** en **[!UICONTROL Tasks]** tabs onder het diagram. Selecteer een activiteit om alle verwante berichten te bekijken. Deze lijst bevat alle berichten als er geen activiteit is geselecteerd.

  ![](assets/new-workflow-display-log-activity.png)

  >[!NOTE]
  >
  >Klik op de achtergrond van het diagram om de selectie van alle elementen op te heffen.

* Alleen die berichten weergeven die zijn gekoppeld aan een bepaalde taak. Selecteer de optie **[!UICONTROL Tasks]** en selecteert u vervolgens een activiteit in het diagram om de lijst te beperken. Dubbelklik op een taak om de informatie weer te geven. Het laatste tabblad in het venster bevat het logboek.

  ![](assets/new-workflow-display-tasks-activity.png)

  De **[!UICONTROL Details...]** kunt u alle aanvullende informatie over de uitvoering van de activiteit weergeven. U kunt bijvoorbeeld de validatieoperator weergeven en, indien van toepassing, de opmerking die ze tijdens de goedkeuring hebben ingevoerd.

>[!NOTE]
>
>Het logbestand wordt niet gewist wanneer een workflow opnieuw wordt gestart. Alle berichten worden bewaard. Als u de berichten van een vorige uitvoering wilt verwijderen, moet u de geschiedenis wissen.

Het logboek toont de chronologische lijst van uitvoeringsberichten met betrekking tot het richten van werkschemaactiviteiten.

* Logboek van een doelgerichte campagne

  Als een doelcampagne is uitgevoerd, klikt u op de knop **[!UICONTROL Tracking]** om het uitvoerspoor weer te geven.

  ![](assets/s_user_segmentation_journal.png)

  Alle campagneberichten worden getoond: campagnes worden uitgevoerd evenals waarschuwingen of fouten.

* Logboek van een activiteit

  U kunt het uitvoeringslogboek en de details van elke activiteit ook bekijken. Er zijn twee manieren om dit te doen:

   1. Selecteer de doelactiviteit en klik op de knop **[!UICONTROL Display the tasks and the log]** pictogram.

      ![](assets/s_user_segmentation_show_logs.png)

      De onderste sectie van het diagram toont twee lusjes: Logboek en Taken.

      De activiteiten die binnen het diagram worden geselecteerd handelen als filters op het logboek en de taaklijst.

      ![](assets/s_user_segmentation_logs.png)

   1. Klik met de rechtermuisknop op de doelactiviteit en selecteer **[!UICONTROL Display logs]**.

      ![](assets/s_user_segmentation_logs_menu.png)

      Het logboek wordt getoond in een afzonderlijk venster.

## De logbestanden leegmaken {#purging-the-logs}

De historie van de workflow wordt niet automatisch gewist: alle berichten worden standaard bijgehouden. De geschiedenis kan worden gewist via **[!UICONTROL File > Actions]** of door op de knop **[!UICONTROL Actions]** in de werkbalk boven de lijst. Selecteer **[!UICONTROL Purge history]**. De opties in het dialoogvenster **[!UICONTROL Actions]** wordt gedetailleerd in het dialoogvenster [Werkbalk Handelingen](start-a-workflow.md) sectie.

![](assets/purge_historique.png)

## Worktables and workflow schema {#worktables-and-workflow-schema}

De workflow geeft worktables weer die via bepaalde activiteiten kunnen worden bewerkt. Met Adobe Campaign kunt u via gegevensbeheeractiviteiten de kolommen van workflows aanpassen, hernoemen en verrijken, bijvoorbeeld om ze aan te passen aan de nomenclatuur afhankelijk van de behoeften van de klant, om aanvullende informatie te verzamelen over de co-begunstigde van een contract, enz.

Het is ook mogelijk om verbindingen tussen diverse het werkdimensies tot stand te brengen en afmetingsveranderingen te bepalen. Voor elk contract dat bijvoorbeeld in de database is opgenomen, richt u zich tot de hoofdhouder en gebruikt u de gegevens van de medehouder in de aanvullende informatie.

De werktafels van de workflow worden automatisch verwijderd wanneer de workflow wordt gepassiveerd. Als u een werktabel wilt behouden, slaat u deze op in een lijst via het dialoogvenster **[!UICONTROL List update]** activiteit (zie [Lijstupdate](list-update.md)).

## Fouten beheren {#managing-errors}

Wanneer een fout optreedt, wordt de werkstroom gepauzeerd en wordt de activiteit uitgevoerd wanneer de fout optrad met rood. In het workflowoverzicht, onder de **[!UICONTROL Monitoring]** tab -  **[!UICONTROL Workflows]** koppeling, kunt u workflows alleen met fouten weergeven, zoals hieronder wordt weergegeven.

![](assets/wf-global-view_filter_only_errors.png)

In de Adobe Campaign Explorer wordt in de workflowlijst een **[!UICONTROL Failed]** kolom standaard.

![](assets/wf-explorer_errors_col.png)

Wanneer een workflow een fout bevat, worden de operatoren die tot de groep voor workflowtoezicht behoren, via e-mail op de hoogte gebracht, zolang hun e-mailadres in hun profiel wordt vermeld. Deze groep is geselecteerd in het dialoogvenster **[!UICONTROL Supervisor(s)]** veld van de workfloweigenschappen.

![](assets/wf-properties_select-supervisors.png)

De berichtinhoud wordt gevormd in **[!UICONTROL Workflow manager notification]** standaardsjabloon: deze sjabloon is geselecteerd in het dialoogvenster **[!UICONTROL Execution]** tabblad van de workfloweigenschappen. In het bericht wordt de naam van de foutworkflow en de betreffende taak weergegeven.

Voorbeeld van melding:

![](assets/wf-notification_error-msg.png)

Met de koppeling hebt u toegang tot de Adobe Campaign-clientconsole in de webmodus en kunt u werken aan de foutworkflow nadat u zich hebt aangemeld.

![](assets/wf-notification_error-console.png)

U kunt de workflow zodanig configureren dat deze niet wordt onderbroken en verder wordt uitgevoerd in het geval van fouten. Hiervoor kunt u de workflow bewerken **[!UICONTROL Properties]** en in de **[!UICONTROL Error management]** selecteert u de **[!UICONTROL Ignore]** in de **[!UICONTROL In case of error]** veld. Vervolgens kunt u opgeven hoeveel opeenvolgende fouten kunnen worden genegeerd voordat het proces wordt gepauzeerd.

In dit geval wordt de fouttaak afgebroken. Deze modus is vooral geschikt voor workflows die zijn ontworpen om de campagne later weer te geven (periodieke acties).

![](assets/wf_edit_properties_for_error_mgt.png)

>[!NOTE]
>
>U kunt deze configuratie afzonderlijk toepassen voor elke activiteit. Hiervoor bewerkt u de eigenschappen van de activiteit en selecteert u de modus voor foutbeheer in het dialoogvenster **[!UICONTROL Advanced]** tab.

## Verwerkingsfouten {#processing-errors}

Met betrekking tot activiteiten **[!UICONTROL Process errors]** geeft een specifieke overgang weer die wordt ingeschakeld als een fout wordt gegenereerd. In dit geval gaat de workflow niet naar de foutmodus en gaat de uitvoering verder.

Fouten waarmee rekening wordt gehouden, zijn fouten in het bestandssysteem (het bestand kan niet worden verplaatst, de map kan niet worden geopend, enz.).

Deze optie verwerkt geen fouten met betrekking tot activiteitsconfiguratie, d.w.z. ongeldige waarden. Fouten met betrekking tot een onjuiste configuratie maken deze overgang niet mogelijk (map bestaat niet, enz.).

Als een werkstroom wordt gepauzeerd (handmatig of automatisch na een fout), **[!UICONTROL Start]** start de uitvoering van de workflow opnieuw op de plaats waar deze is gestopt. De foutieve activiteit (of gepauzeerde activiteit) wordt opnieuw uitgevoerd. De vorige activiteiten worden niet opnieuw uitgevoerd.

Als u alle workflowactiviteiten opnieuw wilt uitvoeren, gebruikt u de opdracht **[!UICONTROL Restart]** knop.

Als u activiteiten wijzigt die al werden uitgevoerd, worden de wijzigingen niet in aanmerking genomen wanneer de werkstroom opnieuw wordt uitgevoerd.

Als u niet-uitgevoerde activiteiten wijzigt, wordt hiermee rekening gehouden wanneer de werkstroom opnieuw wordt uitgevoerd.

Als u gepauzeerde activiteiten wijzigt, kunnen de wijzigingen niet correct worden doorgevoerd wanneer de workflow opnieuw wordt gestart.

Indien mogelijk raden we u aan de workflow opnieuw te starten nadat u wijzigingen hebt aangebracht.

## Instantie controleren {#instance-supervision}

De **[!UICONTROL Instance supervision]** kunt u de Adobe Campaign-serveractiviteit weergeven en een lijst met workflows en leveringen met fouten weergeven.

Ga voor toegang tot deze pagina naar **[!UICONTROL Monitoring]** en klik op de knop **[!UICONTROL General view]** koppeling.

![](assets/wf-monitoring_from-homepage.png)

Als u alle workflows wilt weergeven, klikt u op de knop **[!UICONTROL Workflows]** koppeling. Gebruik de vervolgkeuzelijst om de workflows op het platform weer te geven op basis van hun status.

![](assets/wf-monitoring_edit-wf.png)

Klik op de koppeling in een workflow met fouten om deze te openen en het bijbehorende logboek weer te geven.

![](assets/wf-monitoring_edit-task-wf.png)

## Meerdere uitvoeringen voorkomen {#preventing-simultaneous-multiple-executions}

Eén workflow kan meerdere uitvoeringen tegelijk uitvoeren. In sommige gevallen moet u dit voorkomen.

Bijvoorbeeld, kunt u een planner hebben die de werkschemauitvoering elk uur teweegbrengt, maar soms neemt de uitvoering van het volledige werkschema meer dan een uur. U kunt de uitvoering overslaan als de workflow al wordt uitgevoerd.

Als u een signaalactiviteit aan het begin van het werkschema hebt kunt u het signaal willen overslaan als het werkschema loopt.

Het algemene beginsel is als volgt:

![](assets/workflow-reentrancy-protection-principle.png)

De oplossing is een instantievariabele te gebruiken. Instantievariabelen worden gedeeld door alle parallelle uitvoeringen van de workflows.

Hier volgt een eenvoudige testworkflow:

![](assets/wkf_simultaneous_execution1.png)

De **[!UICONTROL Scheduler]** activeert elke minuut een gebeurtenis. Het volgende **[!UICONTROL Test]** de activiteit gaat testen **isRunning** instantievariabele om te beslissen al dan niet om de uitvoering voort te zetten:

![](assets/wkf_simultaneous_execution2.png)

>[!NOTE]
>
>**isRunning** is een variabelenaam die voor dit voorbeeld wordt gekozen. Dit is geen ingebouwde variabele.

De activiteit onmiddellijk na de **[!UICONTROL Test]** in de **ja** vertakking moet de instantievariabele in zijn plaatsen **Initialisatiescript**:

```
instance.vars.isRunning = true
```

De allerlaatste activiteit in de **ja** vertakking moet de variabele in zijn **Initialisatiescript**:

```
instance.vars.isRunning = false
```

Let op:

* U kunt de huidige waarde van de instantievariabele controleren via **Variabelen** tabblad in de workflow **Eigenschappen**.
* Instantievariabelen worden opnieuw ingesteld wanneer u een workflow opnieuw start.
* In JavaScript is een ongedefinieerde waarde in een test false, zodat de instantievariabele ook kan worden getest voordat deze is geïnitialiseerd.
* U kunt de activiteiten controleren die niet wegens dit mechanisme door een registrereninstructie aan het initialiseringsmanuscript van &quot;geen&quot;beëindigend worden verwerkt toe te voegen.

  ```
  logInfo("Workflow already running, parallel execution not allowed.");
  ```

In deze rubriek wordt een gebruiksgeval weergegeven: [Gegevensupdates coördineren](coordinate-data-updates.md).

## Database-onderhoud {#database-maintenance}

Workflows gebruiken veel werktabellen die ruimte verbruiken en het hele platform vertragen als het niet wordt onderhouden.

De **Database opschonen** via de **Beheer > Productie > Technische workflows** knoop, laat u verouderde gegevens schrappen om exponentiële groei van het gegevensbestand te vermijden. De workflow wordt automatisch geactiveerd zonder tussenkomst van de gebruiker.

U kunt ook specifieke technische workflows maken om overbodige gegevensverbruikende ruimte te wissen. Zie en deze [sectie](#purging-the-logs).

## Afhandeling van gepauzeerde workflows {#handling-of-paused-workflows}

Als een werkstroom wordt gepauzeerd, worden de werktabellen standaard niet gewist. Vanaf build 8880 worden workflows die al te lang in een pauzestatus zijn gepauzeerd, automatisch gestopt en worden hun werktabellen gewist. Dit gedrag wordt als volgt geactiveerd:

* De werkschema&#39;s die sinds meer dan 7 dagen zijn gepauzeerd verschijnen als waarschuwing in het controledashboard (en controle API) en een bericht wordt verzonden naar de supervisorgroep.
* Hetzelfde gebeurt elke week, wanneer **[!UICONTROL cleanupPausedWorkflows]** de technische workflow wordt geactiveerd. Raadpleeg voor meer informatie over de workflow de [deze sectie](delivery.md).
* Na 4 meldingen (dat wil zeggen een maand in de pauzestatus) wordt de workflow onvoorwaardelijk gestopt. Er wordt een logboek weergegeven in de workflow nadat het is gestopt. De tabellen worden gewist bij de volgende uitvoering **[!UICONTROL cleanup]** werkstroom

Deze periodes kunnen via de optie NmsServer_PausedWorkflowPeriod worden gevormd.

Workflowtoezichthouders worden op de hoogte gesteld. De maker en laatste gebruiker die de workflow heeft gewijzigd, wordt ook op de hoogte gesteld. Beheerders ontvangen de meldingen niet.

## Workflows filteren op basis van hun status {#filtering-workflows-status}

Met de interface van het Campaign Classic kunt u de uitvoeringsstatus van alle workflows op uw instantie controleren met behulp van vooraf gedefinieerde **views**. Als u deze weergaven wilt openen, opent u het dialoogvenster **[!UICONTROL Administration]** / **[!UICONTROL Audit]** / **[!UICONTROL Workflows Status]** knooppunt.

De volgende weergaven zijn beschikbaar:

* **[!UICONTROL Running]**: geeft een overzicht van alle actieve workflows.
* **[!UICONTROL Paused]**: geeft een overzicht van alle gepauzeerde workflows.
* **[!UICONTROL Failed]**: geeft alle mislukte workflows weer.
* ** ).

![](assets/workflow-monitoring-views.png)

Deze weergaven zijn standaard toegankelijk in het dialoogvenster **[!UICONTROL Audit]** map. U kunt ze echter wel opnieuw maken op de locatie die u kiest in de mappenstructuur. Op deze manier zijn ze beschikbaar voor standaardgebruikers zonder beheerrechten.

Dit doet u als volgt:

1. Klik met de rechtermuisknop op de map waaraan u de weergave wilt toevoegen.
1. In **[!UICONTROL Add new folder]** / **[!UICONTROL Administration]** selecteert u de weergave die u wilt toevoegen.
1. Nadat de map aan de structuur is toegevoegd, configureert u deze als een weergave, zodat alle workflows worden weergegeven, ongeacht de oorspronkelijke map. Voor meer op hoe te om meningen te vormen, verwijs naar [deze pagina](../../v8/audiences/folders-and-views.md#turn-a-folder-to-a-view).

Naast deze weergaven kunt u ook mappen met filters instellen waarmee u de lijst met workflows kunt filteren op basis van hun uitvoeringsstatus. Dit doet u als volgt:

1. Open een map van het type workflow en selecteer vervolgens de **[!UICONTROL Filters]** / **[!UICONTROL Advanced filter]** -menu.
1. Configureer het filter zodat de workflow **[!UICONTROL @status]** is gelijk aan de status van uw keuze.
1. Sla het filter op en geef het een naam. Deze functie is dan rechtstreeks beschikbaar in de lijst met filters.

![](assets/workflow-monitoring-filter.png)

Raadpleeg de volgende secties voor meer informatie:
