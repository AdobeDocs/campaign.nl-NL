---
title: Bekende problemen in de campagne v8
description: Bekende problemen in de nieuwste campagnerelease
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 96e9f5fe5f07ea0c476395d33efa4d6bcf10cf60
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---

# Bekende problemen{#known-issues}

Deze pagina bevat een lijst met bekende problemen die zijn geïdentificeerd in het dialoogvenster **nieuwste release van Campagne v8**. Bovendien worden de beperkingen die bij Campagne v8 worden geleverd, vermeld [op deze pagina](ac-guardrails.md).


>[!NOTE]
>
>Adobe publiceert deze lijst met bekende problemen naar eigen goeddunken. Het is gebaseerd op het aantal klantenrapporten, de strengheid, en de tijdelijke beschikbaarheid. Als een probleem dat u tegenkomt niet in de lijst voorkomt, voldoet het mogelijk niet aan de criteria voor publicatie op deze pagina.

## Campaign v8.3.8{#8.3-issues}

### Probleem met gegevensbronactiviteit wijzigen #1 {#issue-1}

#### Beschrijving{#issue-1-desc}

De **Gegevensbron wijzigen** De activiteit ontbreekt wanneer het overbrengen van gegevens van lokale gegevensbestand van de Campagne aan Snowflake wolkengegevensbestand. Wanneer het schakelen van richtingen, kan de activiteit kwesties produceren.

#### Reproductiestappen{#issue-1-repro}

1. Maak verbinding met de clientconsole en maak een workflow.
1. Voeg een **Query** en **Gegevensbron wijzigen** activiteit.
1. Definieer een query op het tabblad **email**, wat een tekenreeks is.
1. Voer de workflow uit en klik met de rechtermuisknop op de overgang om de populatie weer te geven: de e-mailrecords worden vervangen door `****`.
1. Controleer de workflowlogboeken: de **Gegevensbron wijzigen** activiteit interpreteert deze verslagen als numerieke waarden.

#### Foutbericht{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

#### Workaround{#issue-1-workaround}

Om de gegevens te hebben die van de de wolkengegevensbestand van Snowflake naar de lokale gegevensbestand van de Campagne en terug naar Snowflake worden overgebracht, moet u twee verschillende gebruiken **Gegevensbron wijzigen** activiteiten.

#### Interne referentie{#issue-1-ref}

Referentie: NEO-45549



### Probleem met gegevensbronactiviteit wijzigen {#issue-2}

#### Beschrijving{#issue-2-desc}

Bij het injecteren van gegevens in de Snowflake cloud-database met een campagne **Query** en **Gegevensbron wijzigen** activiteit, ontbreekt het proces wanneer een backslash karakter in de gegevens aanwezig is. De brontekenreeks wordt niet beschermd en gegevens worden niet correct verwerkt op Snowflake.

Dit probleem doet zich alleen voor als de backslash het einde van een tekenreeks is, bijvoorbeeld: `Barker\`.


#### Reproductiestappen{#issue-2-repro}

1. Maak verbinding met de clientconsole en maak een workflow.
1. Voeg een **Query** activiteit en vorm het.
1. Selecteer gegevens met de hierboven beschreven kenmerken.
1. Voeg een **Gegevensbron wijzigen** en configureer deze om de Snowflake cloud-database te selecteren.
1. Voer de workflow uit en controleer de logboeken van de workflow om de fout te zien.


#### Foutbericht{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Workaround{#issue-2-workaround}

Als tussenoplossing kunt u gegevens uitsluiten die backslash-tekens bevatten aan het einde van een tekenreeks of deze verwijderen uit het bronbestand.


#### Interne referentie{#issue-2-ref}

Referentie: NEO-45549


### Actie voor het laden van gegevens (bestand) is mislukt. Bestand wordt geüpload naar de server {#issue-3}

#### Beschrijving{#issue-3-desc}

Wanneer u een bestand uploadt naar een Campagneserver met een **Gegevens laden (bestand)** het proces stopt bij 100% maar eindigt nooit.

#### Reproductiestappen{#issue-3-repro}

1. Maak verbinding met de clientconsole en maak een workflow.
1. Voeg een **Gegevens laden (bestand)** activiteit en vorm het.
1. Selecteer **Uploaden op server** optie.
1. Selecteer het bestand op uw lokale computer.
1. Klikken **Uploaden**


#### Foutbericht{#issue-3-error}

Het proces eindigt nooit.

#### Workaround{#issue-3-workaround}

De oplossing is om een oudere cliëntconsole te gebruiken. Vervolgens kunt u het bestand uploaden naar de server.

Als beheerder van de Campagne kunt u Campagne v8.3.1 cliëntconsole in downloaden [Adobe-softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;layout by.sort=desc=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;}.

Leer hoe u toegang krijgt tot Adobe Software Distribution [op deze pagina](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html){target=&quot;_blank&quot;}.

Leer hoe u uw clientconsole kunt upgraden [op deze pagina](connect.md)

#### Interne referentie{#issue-3-ref}

Referentie: NEO-47269