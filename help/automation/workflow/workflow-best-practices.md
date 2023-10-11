---
product: campaign
title: Best practices voor workflows
description: Meer informatie over best practices voor de campagnereschemap
feature: Workflows
role: User, Admin
exl-id: 8bcaf367-5b1f-4d31-80c9-c77df43c6ed1
source-git-commit: d4e28ddf6081881f02042416aa8214761ea42be9
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 6%

---

# Best practices voor workflows{#workflow-best-practices}

Hieronder vindt u algemene richtlijnen voor het optimaliseren van de prestaties van de campagneworkflow, het verbeteren van het workflowontwerp en het selecteren van de juiste instellingen.

## Workflowmappen {#workflow-folders}

Adobe raadt u aan uw workflows in een specifieke map te maken.

Als de workflow het hele platform beïnvloedt (bijvoorbeeld reinigingsprocessen), kunt u overwegen een submap toe te voegen aan de ingebouwde **[!UICONTROL Technical Workflows]** map.

## Workflownaamgeving {#workflow-naming}

Om het gemakkelijker te maken om workflows te vinden en problemen op te lossen als ze niet naar behoren functioneren, wordt u aangeraden om uw workflows duidelijke namen en labels te geven. Vul het beschrijvingsveld van de workflow in om het uit te voeren proces samen te vatten, zodat de operator het gemakkelijk kan begrijpen.

Als de workflow deel uitmaakt van een proces waarbij meerdere workflows zijn betrokken, kunt u expliciet zijn wanneer u een label invoert. Het gebruik van nummers is een goede manier om de workflows te bestellen (met Label).

Bijvoorbeeld:

* 001 - Invoer - Ontvangers van de invoer
* 002 - Invoer - Uitvoer
* 003 - Invoer - Gegevens over de verkoop bij invoer
* 010 - Exporteren - Leveringslogboeken exporteren
* 011 - Logbestanden voor bijhouden van export

## Ernst van werkstroom {#workflow-severity}

U kunt de ernst van een werkstroom in de werkschemaeigenschappen, in vormen **[!UICONTROL Execution]** tab:

* Normaal
* Productie
* Kritiek

Door deze informatie op te geven tijdens het maken van een workflow, kunt u de ernst van het geconfigureerde proces beter begrijpen.

Deze optie heeft geen andere functionele gevolgen voor workflows dan campagneworkflows.

Workflows voor campagnes (workflows die zijn gemaakt als onderdeel van een campagne/bewerking) met een hogere prioriteit worden uitgevoerd als de campagne veel processen heeft die gelijktijdig moeten worden uitgevoerd. Standaard kunnen slechts 10 processen tegelijkertijd worden uitgevoerd in een campagne, volgens de optie NmsOperation_LimitConcurrency. Als een campagne bijvoorbeeld 25 workflows bevat, worden workflows met een hogere ernst uitgevoerd in de eerste pool van 10 processen.

## Workflowbewaking {#workflow-monitoring}

Alle geplande workflows die op productieomgevingen worden uitgevoerd, moeten worden gecontroleerd om te worden gewaarschuwd als er een fout optreedt.

In de werkschemaeigenschappen, selecteer een groep van de Supervisor, of het gebrek **[!UICONTROL Workflow supervisors]** of een aangepaste groep. Zorg ervoor dat ten minste één operator tot deze groep behoort, met een e-mailinstelling.

Voordat u een workflow gaat maken, moet u workflowsupervisors definiëren. Zij zullen per e-mail op de hoogte worden gesteld in het geval van fouten. Raadpleeg voor meer informatie hierover [Fouten beheren](monitor-workflow-execution.md#managing-errors).

De **[!UICONTROL Monitoring]** om de algemene status van de actieve workflows weer te geven. Raadpleeg voor meer informatie hierover [Instantie controleren](monitor-workflow-execution.md#instance-supervision).

Met de Workflow HeatMap kunnen beheerders van het Adobe Campaign-platform de belasting op de instantie controleren en workflows dienovereenkomstig plannen. Raadpleeg voor meer informatie hierover [Workflowbewaking](heatmap.md).

## Activiteiten {#using-activities}

>[!CAUTION]
>
>U kunt activiteiten kopiëren en plakken binnen dezelfde workflow. We raden echter niet aan plakactiviteiten over verschillende workflows te kopiëren. Sommige instellingen die zijn gekoppeld aan activiteiten zoals Leveringen en Planner kunnen leiden tot conflicten en fouten tijdens het uitvoeren van de doelworkflow. We raden u aan  **Dupliceren** workflows. Zie voor meer informatie [Workflows dupliceren](build-a-workflow.md#duplicate-workflows).

### Naam van de activiteit {#name-of-the-activity}

Tijdens het ontwikkelen van uw workflow hebben alle activiteiten een naam, net als alle Adobe Campaign-objecten. Terwijl de naam door het hulpmiddel wordt geproduceerd, adviseren wij u het met een expliciete naam anders te noemen wanneer het vormen van het. Het risico dat het later gebeurt, is dat het de werkstroom kan onderbreken met activiteiten die de naam van een andere voorgaande activiteit gebruiken. Het zou dus moeilijk zijn om de namen achteraf bij te werken.

De naam van de activiteit is te vinden in de **[!UICONTROL Advanced]** tab. Laat ze geen naam geven **[!UICONTROL query]**, **[!UICONTROL query1]**, **[!UICONTROL query11]**, maar geef ze expliciete namen, zoals **[!UICONTROL querySubscribedRecipients]**. Deze naam zal in het dagboek, en indien van toepassing in de SQL logboeken verschijnen, en dit zal helpen om het werkschema te zuiveren wanneer het vormen van het.

### Eerste en laatste activiteiten {#first-and-last-activities}

* Start altijd uw workflow met een **[!UICONTROL Start]** of een **[!UICONTROL Scheduler]** activiteit. Indien relevant kunt u ook een **[!UICONTROL External signal]** activiteit.
* Gebruik bij het samenstellen van uw workflow slechts één **[!UICONTROL Scheduler]** activiteit per bijkantoor. Als dezelfde vertakking van een workflow meerdere planners heeft (die met elkaar gekoppeld zijn), zal het aantal uit te voeren taken exponentieel worden vermenigvuldigd, waardoor de database aanzienlijk overbelast zou worden. Deze regel geldt ook voor alle activiteiten met een **[!UICONTROL Scheduling & History]** tab. Meer informatie over [Planning](scheduler.md).

  ![](assets/wf-scheduler.png)

* Gebruiken **[!UICONTROL End]** activiteiten voor elke workflow. Hierdoor kan Adobe Campaign tijdelijke ruimte vrijmaken die wordt gebruikt voor berekeningen binnen workflows. Raadpleeg voor meer informatie: [Begin en einde](start-and-end.md).

### JavaScript binnen een activiteit {#javascript-within-an-activity}

U kunt JavaScript toevoegen bij het initialiseren van een workflowactiviteit. Dit kan worden gedaan in een activiteit **[!UICONTROL Advanced]** tabblad van de activiteit.

Om het spotting van het werkschema gemakkelijker te maken, adviseren wij gebruikend dubbele streepjes aan het begin en eind van het activiteitenetiket als volgt: — Mijn etiket —.

### Signaal {#signal}

Meestal zult u niet weten waar het signaal vandaan komt. Om dit probleem te voorkomen, gebruikt u de **[!UICONTROL Comment]** in het veld **[!UICONTROL Advanced]** tabblad van de signaalactiviteit om de verwachte oorsprong van een signaal voor deze activiteit te documenteren.

## Workflowupdates {#workflow-update}

Een productiewerkstroom mag niet rechtstreeks worden bijgewerkt. Tenzij het proces bestaat uit het maken van een campagne met sjabloonworkflows, moeten processen eerst op een ontwikkelomgeving worden getest. Na deze validatie kan de workflow worden geïmplementeerd en op productie worden gestart.

Alle tests uitvoeren in ontwikkelings- of testomgevingen, niet in productieomgevingen. In een dergelijk geval kunnen de prestaties niet worden gewaarborgd.

Gearchiveerde workflows kunnen op ontwikkelings- of testplatforms in een gearchiveerde map worden bewaard, maar de productieomgeving moet zo schoon mogelijk blijven. Oude workflows moeten uit de productieomgeving worden verwijderd als ze inactief zijn.

## Uitvoering en prestaties {#execution-and-performance}

### Logboeken {#logs}

De JavaScript-methode **[!UICONTROL logInfo()]** is een oplossing voor het zuiveren van een werkschema. Nochtans moet het zorgvuldig worden gebruikt, vooral voor activiteiten die vaak in werking worden gesteld: het kan de logboeken overladen en beduidend de grootte van de logboeklijst verhogen.

### Tijdelijke populaties behouden

De **Behoud het resultaat van tussentijdse populaties tussen twee executies** houdt tijdelijke lijsten tussen twee uitvoeringen van een werkschema.

Het is beschikbaar in de eigenschappen van de workflow. **[!UICONTROL General]** en kan worden gebruikt voor ontwikkelings- en testdoeleinden om gegevens te controleren en de resultaten te controleren. U kunt deze optie in ontwikkelomgevingen gebruiken, maar nooit in productieomgevingen. Het houden van tijdelijke lijsten zou in de grootte van het gegevensbestand kunnen resulteren die beduidend en uiteindelijk de groottegrens wordt bereikt. Bovendien zal het de back-up vertragen.

Alleen de werktabellen van de laatste uitvoering van de workflow worden bewaard. Werktabellen van eerdere uitvoeringen worden door de **[!UICONTROL cleanup]** werkschema, dat dagelijks loopt.

>[!CAUTION]
>
>Deze optie moet **nooit** worden gecontroleerd in een **productie** workflow. Deze optie wordt gebruikt om de resultaten te analyseren en is alleen ontworpen voor testdoeleinden en moet daarom alleen worden gebruikt in ontwikkelings- of testomgevingen.


### SQL-query&#39;s vastleggen

De **SQL-query&#39;s vastleggen in het journaal** is beschikbaar in het dialoogvenster **[!UICONTROL Execution]** tabblad met workfloweigenschappen. Deze optie registreert alle SQL vragen van de verschillende activiteiten, en verstrekt een manier om te zien wat eigenlijk door het platform wordt uitgevoerd. Deze optie mag echter alleen worden gebruikt **tijdelijk** tijdens de ontwikkeling en **niet geactiveerd bij productie**.

De beste manier is om de logboeken te wissen wanneer ze niet meer nodig zijn. De historie van de workflow wordt niet automatisch gewist: alle berichten worden standaard bijgehouden. De geschiedenis kan worden gewist via **[!UICONTROL File > Actions]** of door op de knop Handelingen op de werkbalk boven de lijst te klikken. Selecteer Geschiedenis leegmaken.
Als u wilt weten hoe u uw logbestanden kunt leegmaken, raadpleegt u deze [documentatie](start-a-workflow.md).

### Workflowplanning {#workflow-planning}

Er moeten extra aanbevolen procedures worden toegepast op de planning voor het uitvoeren van workflows om problemen te voorkomen:

* Houd de dag een stabiel activiteitsniveau en vermijd pieken om te voorkomen dat de instantie overbelast raakt. Hiervoor verdeelt u de werkstroom gelijkmatig over de dag.
* Plan de gegevensbelasting &#39;s nachts om de bronconflict te verminderen.
* De lange werkschema&#39;s kunnen potentieel een effect op de server en gegevensbestandmiddelen hebben. Splits de langste workflows om de verwerkingstijd te verkorten.
* Om de totale uitvoeringstijd te verkorten, vervang tijdrovende activiteiten door vereenvoudigde en snellere activiteiten.
* Gebruik niet meer dan 20 workflows tegelijk. Als er te veel workflows tegelijk worden uitgevoerd, kan uw platform overbelast raken en instabiel worden.


### Uitvoeren in de motoroptie {#execute-in-the-engine-option}

Vermijd het uitvoeren van workflows in de engine in een productieomgeving. Wanneer de **[!UICONTROL Execute in the engine]** Deze optie is ingeschakeld in het dialoogvenster **[!UICONTROL Workflow properties]**, heeft de workflow prioriteit en worden alle andere workflows gestopt door de workflow-engine totdat deze is voltooid.

![](assets/wf-execute-in-engine.png)
