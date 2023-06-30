---
title: Belangrijk beheer in campagne
description: Aan de slag met sleutelbeheer
feature: FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 0%

---

# Sleutelbeheer en eenheid {#key-management}

In de context van een [Implementatie van ondernemingen (FFDA)](enterprise-deployment.md), is de primaire sleutel een Universally Unique IDentifier (UUID), die een tekenreeks op tekens is. Als u deze UUID wilt maken, moet het hoofdelement van het schema het volgende bevatten: **autouuid** en **automatische** kenmerken ingesteld op **true**.

Adobe Campaign v8-gebruik [!DNL Snowflake] als de kerndatabase. De verspreide architectuur van de [!DNL Snowflake] de database biedt geen mechanisme om de eenheid van een sleutel in een tabel te garanderen: eindgebruikers zijn verantwoordelijk voor de belangrijkste consistentie binnen de Adobe Campaign-database.

Om de consistentie van relationele databases te behouden, is het verplicht duplicaten van sleutels, en met name van primaire sleutels, te voorkomen. Duplicaties op primaire sleutels leiden tot problemen met de werkstroomactiviteiten voor gegevensbeheer, zoals **Query**, **Verzoening**, **Gegevens bijwerken** en meer. Dit is van essentieel belang voor het definiëren van juiste afstemmingscriteria bij het bijwerken [!DNL Snowflake] tabellen.


>[!CAUTION]
>
>Gedupliceerde toetsen zijn niet beperkt tot UUID&#39;s. Dit kan gebeuren in combinatie met id&#39;s, inclusief aangepaste sleutels die in aangepaste tabellen zijn gemaakt.


## Uniciteitsservice{#unicity-service}

Unicity Service is een Cloud Database Manager-component die gebruikers helpt de integriteit van unieke sleutelbeperkingen in Cloud Database-tabellen te behouden en te controleren. Hierdoor kunt u het risico van het invoegen van dubbele toetsen verkleinen.

Aangezien de Gegevensbestand van de Wolk uniciteitsbeperkingen niet afdwingt, vermindert de Dienst van de Uniciteit het risico om duplicaten op te nemen wanneer het beheren van de gegevens met Adobe Campaign.

### Uniciteitsworkflow{#unicity-wf}

De Dienst van de Uniciteit komt met specifiek **[!UICONTROL Unicity alerting]** ingebouwde workflow om eenheidbeperkingen te controleren en te waarschuwen wanneer duplicaten worden gedetecteerd.

Deze technische workflow is beschikbaar op het tabblad **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** knooppunt van Campagneverkenner. **Het mag niet worden gewijzigd**.

Deze workflow controleert alle aangepaste en ingebouwde schema&#39;s om dubbele rijen te detecteren.

![](assets/unicity-alerting-wf.png)

Als de **[!UICONTROL Unicity alerting]** (ffdaUnicity) workflow detecteert enkele dubbele sleutels, die worden toegevoegd aan een specifieke **Audit Uniciteit** tabel, die de naam van het schema, het type sleutel, het aantal rijen waarop een effect is toegepast en de datum bevat. U hebt toegang tot gedupliceerde toetsen via de **[!UICONTROL Administration > Audit > Key Unicity]** knooppunt.

![](assets/unicity-table.png)

Als databasebeheerder kunt u een SQL-activiteit gebruiken om de duplicaten te verwijderen of contact opnemen met de klantenservice van Adobe voor meer hulp.

### Waarschuwing{#unicity-wf-alerting}

Er wordt een specifieke kennisgeving verzonden naar de **[!UICONTROL Workflow Supervisors]** exploitantgroep wanneer dubbele sleutels worden ontdekt. De inhoud en het publiek van deze waarschuwing kunnen worden gewijzigd in het gedeelte **Waarschuwing** van de **[!UICONTROL Unicity alerting]** workflow.

![](assets/wf-alert-activity.png)


## Aanvullende geleiders{#duplicates-guardrails}

De campagne wordt geleverd met een set nieuwe instructies om te voorkomen dat een dubbele sleutel wordt ingevoegd in [!DNL Snowflake] database.

>[!NOTE]
>
>Deze instructies zijn beschikbaar vanaf Campagne v8.3. Als u uw versie wilt controleren, raadpleegt u [deze sectie](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Voorbereiding van de levering{#remove-duplicates-delivery-preparation}

Adobe Campaign verwijdert automatisch gedupliceerde UUID&#39;s uit een publiek tijdens de voorbereiding van de levering. Dit mechanisme voorkomt dat er een fout optreedt bij het voorbereiden van een levering. Als eindgebruiker, kunt u deze informatie in de leveringslogboeken controleren: sommige ontvangers kunnen van het hoofddoel worden uitgesloten vanwege een gedupliceerde sleutel. In dat geval wordt de volgende waarschuwing weergegeven: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### Gegevens bijwerken in een workflow{#duplicates-update-data}

In de context van een [Implementatie van ondernemingen (FFDA)](enterprise-deployment.md), kunt u geen interne sleutel (UUID) als gebied selecteren om gegevens in een werkschema bij te werken.

![](assets/update-data-no-internal-key.png)

### Een query uitvoeren op een schema met duplicaten{#query-with-duplicates}

Wanneer een werkschema begint vraag op een schema in werking te stellen, controleert Adobe Campaign of om het even welk gedupliceerd verslag in wordt gemeld [Tabel voor controle-eenheden](#unicity-wf). Als dat het geval is, wordt een waarschuwing weergegeven als de volgende bewerking op de gedupliceerde gegevens mogelijk van invloed is op het resultaat van de workflow.

![](assets/query-with-duplicates.png)

Deze controle wordt uitgevoerd in de volgende werkschemaactiviteiten:

* Query
* Incrementele query
* Lijst lezen