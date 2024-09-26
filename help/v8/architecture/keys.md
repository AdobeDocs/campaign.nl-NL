---
title: Belangrijk beheer in de campagne
description: Aan de slag met sleutelbeheer
feature: Configuration, FFDA
role: Developer
level: Intermediate
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: 9d500f185a9e706b6558135978c4f8c79d92d0d4
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# Sleutelbeheer en eenheid {#key-management}

In de context van een [ plaatsing van de Onderneming (FFDA) ](enterprise-deployment.md), is de primaire sleutel een Universally Unique IDentifier (UUID), die een koord van karakters is. Om deze UUID tot stand te brengen, moet het belangrijkste element van het schema **auto** bevatten en **automatische** attributen die aan **waar** worden geplaatst.

Adobe Campaign v8 gebruikt [!DNL Snowflake] als de hoofddatabase. De verspreide architectuur van de [!DNL Snowflake] -database biedt geen mechanisme om de eenheid van een sleutel binnen een tabel te garanderen: eindgebruikers zijn verantwoordelijk voor de consistentie van de sleutel binnen de Adobe Campaign-database.

Om de consistentie van relationele databases te behouden, is het verplicht duplicaten van sleutels, en met name van primaire sleutels, te voorkomen. De duplicaten op primaire sleutels leiden tot kwesties met de werkschemaactiviteiten van het gegevensbeheer zoals **Vraag**, **Verzoening**, **gegevens van de Update**, en meer. Dit is essentieel voor het definiëren van juiste afstemmingscriteria bij het bijwerken van [!DNL Snowflake] -tabellen.


>[!CAUTION]
>
>Gedupliceerde toetsen zijn niet beperkt tot UUID&#39;s. Dit kan gebeuren in combinatie met id&#39;s, inclusief aangepaste sleutels die in aangepaste tabellen zijn gemaakt.


## Uniciteitsservice{#unicity-service}

Unicity Service is een Cloud Database Manager-component die gebruikers helpt de integriteit van unieke sleutelbeperkingen in Cloud Database-tabellen te behouden en te controleren. Hierdoor kunt u het risico van het invoegen van dubbele toetsen verkleinen.

Aangezien de Gegevensbestand van de Wolk uniciteitsbeperkingen niet afdwingt, vermindert de Dienst van de Uniciteit het risico om duplicaten op te nemen wanneer het beheren van de gegevens met Adobe Campaign.

### Uniciteitsworkflow{#unicity-wf}

De Unicity Service wordt geleverd met een toegewijde **[!UICONTROL Unicity alerting]** ingebouwde workflow om eenheidbeperkingen te controleren en te waarschuwen wanneer duplicaten worden gedetecteerd.

Deze technische workflow is beschikbaar via het knooppunt **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Unicity]** van Campagne Explorer. **het moet niet worden gewijzigd**.

Deze workflow controleert alle aangepaste en ingebouwde schema&#39;s om dubbele rijen te detecteren.

![](assets/unicity-alerting-wf.png)

Als het **[!UICONTROL Unicity alerting]** (ffdaUnicity) werkschema sommige dubbele sleutels ontdekt, worden zij toegevoegd aan een specifieke **lijst van de Uniciteit van de Controle**, die de naam van het schema, het type van sleutel, het aantal beïnvloede rijen, en de datum omvat. U hebt toegang tot gedupliceerde sleutels via het knooppunt **[!UICONTROL Administration > Audit > Key Unicity]** .

![](assets/unicity-table.png)

Als beheerder van het Gegevensbestand, kunt u een SQL activiteit gebruiken om de duplicaten te verwijderen of de Zorg van de Klant van de Adobe voor meer begeleiding te contacteren.

### Waarschuwing{#unicity-wf-alerting}

Er wordt een specifiek bericht verzonden naar de **[!UICONTROL Workflow Supervisors]** -operatorgroep wanneer dubbele sleutels worden gedetecteerd. De inhoud en het publiek van dit alarm kunnen in de **Waakzame** activiteit van het **[!UICONTROL Unicity alerting]** werkschema worden veranderd.

![](assets/wf-alert-activity.png)


## Aanvullende geleiders {#duplicates-guardrails}

De campagne wordt geleverd met een set nieuwe instructies om te voorkomen dat een gedupliceerde sleutel wordt ingevoegd in de [!DNL Snowflake] -database.

>[!NOTE]
>
>Deze instructies zijn beschikbaar vanaf Campagne v8.3. Om uw versie te controleren, verwijs naar [ deze sectie ](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Aflevering voorbereiden {#remove-duplicates-delivery-preparation}

Adobe Campaign verwijdert automatisch gedupliceerde UUID&#39;s uit een publiek tijdens de voorbereiding van de levering. Dit mechanisme voorkomt dat er een fout optreedt bij het voorbereiden van een levering. Als eindgebruiker kunt u deze informatie controleren in de leveringslogboeken: sommige ontvangers kunnen van het hoofddoel worden uitgesloten vanwege een gedupliceerde sleutel. In dat geval wordt de volgende waarschuwing weergegeven: `Exclusion of duplicates (based on the primary key or targeted records)` .

![](assets/exclusion-duplicates-log.png)

### Gegevens bijwerken in een workflow {#duplicates-update-data}

In de context van een [ plaatsing van de Onderneming (FFDA) ](enterprise-deployment.md), kunt u geen interne sleutel (UUID) als gebied selecteren om gegevens in een werkschema bij te werken.

![](assets/update-data-no-internal-key.png)

### Een query uitvoeren op een schema met duplicaten {#query-with-duplicates}

Wanneer een werkschema begint vraag op een schema in werking te stellen, controleert Adobe Campaign als om het even welk gedupliceerd verslag in de [ lijst van de Uniciteit van de Controle ](#unicity-wf) wordt gemeld. Als dat het geval is, wordt een waarschuwing weergegeven als de volgende bewerking op de gedupliceerde gegevens mogelijk van invloed is op het resultaat van de workflow.

![](assets/query-with-duplicates.png)

Deze controle wordt uitgevoerd in de volgende werkschemaactiviteiten:

* Query
* Incrementele query
* Lijst lezen


>[!NOTE]
>
>Als uw overgang van een andere versie van de Campagne overgaat, is het noodzakelijk om duplicaten te verwijderen, problemen op te lossen en gegevens te ontsmetten om te vermijden beïnvloedend uw overgang.
