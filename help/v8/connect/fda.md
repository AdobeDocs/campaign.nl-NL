---
title: Werken met campagnes en externe databases (FDA)
description: Leer hoe u kunt werken met Campagne en externe databases
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 2d0b40e49afdfd71e8bb5c3f0b1d569a715420b2
workflow-type: tm+mt
source-wordcount: '1841'
ht-degree: 3%

---

# Federated Data Access (FDA){#gs-fda}

Gebruik de FDA-connector (Federated Data Access) om de campagne aan te sluiten op een of meer **externe databases** en procesgegevens die in deze bestanden zijn opgeslagen, zonder dat dit van invloed is op de gegevens van de Campagne Cloud Database. U kunt externe gegevens vervolgens openen zonder de structuur van Adobe Campaign-gegevens te wijzigen.

>[!NOTE]
>
>De compatibele gegevensbestanden voor FDA zijn vermeld in [Compatibiliteitsmatrix](../start/compatibility-matrix.md).

De optie FDA van de campagne staat u toe om uw gegevensmodel in een derdegegevensbestand uit te breiden. Het zal automatisch de structuur van de gerichte lijsten ontdekken en gegevens van de SQL bronnen gebruiken.

Specifiek **machtigingen** zijn vereist op [!DNL Adobe Campaign] en op de externe database om samen te werken. Meer informatie in [deze sectie](#fda-permissions).

## Best practices en beperkingen

* **E-mailpersonalisatie optimaliseren met externe gegevens**

   U kunt berichtpersonalisatie vooraf verwerken in een specifieke workflow. Om dit uit te voeren, gebruik **[!UICONTROL Prepare the personalization data with a workflow]** beschikbaar in het dialoogvenster **[!UICONTROL Analysis]** tabblad van de leveringseigenschappen.

   Tijdens de leveringsanalyse, leidt deze optie automatisch tot en voert een werkschema uit dat alle gegevens met betrekking tot het doel in een tijdelijke lijst, met inbegrip van gegevens van lijsten verbonden in een extern gegevensbestand opslaat.

   Met deze optie worden de prestaties aanzienlijk verbeterd wanneer de stap voor personalisatie wordt uitgevoerd.

* **FDA-beperkingen**

   De optie FDA is bedoeld om de gegevens in externe databases in batchmodus te manipuleren in workflows. Om prestatieproblemen te voorkomen, wordt het niet aanbevolen de FDA-module te gebruiken in het kader van eenheidsoperaties, zoals: personalisatie, interactie, real-time overseinen, enz.

   Vermijd de bewerkingen die zowel de Adobe Campaign als de externe database zoveel mogelijk moeten gebruiken. Hiervoor kunt u:

   * Exporteer de Adobe Campaign-database naar de externe database en voer de bewerkingen alleen uit vanuit de externe database voordat u de resultaten opnieuw importeert in Adobe Campaign.

   * Verzamel de gegevens in de externe Adobe Campaign-database en voer de bewerkingen lokaal uit.

   Als u personalisatie in uw leveringen wilt uitvoeren gebruikend gegevens van het externe gegevensbestand, verzamel de gegevens in een werkschema te gebruiken om het ter beschikking te stellen in een tijdelijke lijst. Dan gebruik de gegevens van de tijdelijke lijst om uw levering te personaliseren.

   Voor de optie FDA gelden de beperkingen van het externe databasesysteem dat u gebruikt.


## Configuratiestappen{#fda-configuration-steps}

Om toegang tot een extern gegevensbestand met FDA te plaatsen, zijn de configuratiestappen:

1. Als gebruiker van de Diensten van Adobe Beheerde, contacteer Adobe om de bestuurders op uw instantie van de Campagne te installeren.
1. Als stuurprogramma&#39;s zijn geïnstalleerd, stelt u de externe account in die overeenkomt met uw database op de Adobe Campaign-server en test u de externe account. [Meer informatie](#fda-external-account)
1. Maak het schema van de externe database in Adobe Campaign. Hierdoor kunt u de gegevensstructuur van de externe database identificeren. [Meer informatie](#create-data-schema)
1. Indien nodig, creeer een nieuwe doelafbeelding van het eerder gecreeerd schema. Dit is vereist als de ontvangers van uw leveringen afkomstig zijn uit de externe database. Deze implementatie omvat beperkingen met betrekking tot berichtpersonalisatie. [Meer informatie](#define-data-mapping)

## Externe externe database-account{#fda-external-account}

U moet een specifieke externe rekening tot stand brengen om uw instantie van de Campagne met uw externe gegevensbestand te verbinden.

Volg onderstaande stappen om dit te bereiken:

1. Van campagne **[!UICONTROL Explorer]**, blader naar **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

1. Klik op **[!UICONTROL New]**.

   >[!NOTE]
   >
   > Om actief te zijn, **[!UICONTROL Enabled]** Deze optie moet zijn ingeschakeld. Schakel indien nodig deze optie uit om toegang tot deze database uit te schakelen zonder de configuratie ervan te verwijderen.

1. Selecteren **[!UICONTROL External database]** als externe account **[!UICONTROL Type]**.

1. Kies de externe database in de vervolgkeuzelijst en configureer de externe account. U moet opgeven:

   * **[!UICONTROL Server]**: URL van de server

   * **[!UICONTROL Account]**: Naam van de gebruiker

   * **[!UICONTROL Password]**: Wachtwoord gebruikersaccount

   * **[!UICONTROL Database]**: Naam van de database

      ![](assets/snowflake.png)

1. Klik op de knop **[!UICONTROL Parameters]** dan de **[!UICONTROL Deploy functions]** om functies te maken.

1. Wanneer de parameters zijn ingevoerd, klikt u op de knop **[!UICONTROL Test the connection]** om deze goed te keuren.

1. Als u Adobe Campaign toegang wilt geven tot deze database, moet u de SQL-functies implementeren. Klik op de knop **[!UICONTROL Parameters]** dan de **[!UICONTROL Deploy functions]** knop.

U kunt specifieke werktabelruimten definiëren voor de tabellen en voor de index in het dialoogvenster **[!UICONTROL Parameters]** tab.

Voor [!DNL Snowflake], ondersteunt de connector de volgende opties:

| Option | Beschrijving |
|---|---|
| werkschema | Databaseschema dat moet worden gebruikt voor werktabellen |
| entrepot | Naam van het standaardentrepot aan gebruik. De standaardinstelling van de gebruiker wordt hierdoor genegeerd. |
| TimeZoneName | Standaard leeg, wat betekent dat de systeemtijdzone van de Campaign Classic-toepassingsserver wordt gebruikt. De optie kan worden gebruikt om de TIMEZONE-sessieparameter te forceren. <br>Raadpleeg [deze pagina](https://docs.snowflake.net/manuals/sql-reference/parameters.html#timezone) voor meer informatie. |
| WeekStart | WEEK_START, sessieparameter. Standaard ingesteld op 0. <br>Raadpleeg [deze pagina](https://docs.snowflake.com/en/sql-reference/parameters.html#week-start) voor meer informatie. |
| UseCachedResult | USE_CACHED_RESULTS sessieparameter. Standaard ingesteld op TRUE. U kunt deze optie gebruiken om resultaten in de Snowflake-cache uit te schakelen. <br>Raadpleeg [deze pagina](https://docs.snowflake.net/manuals/user-guide/querying-persisted-results.html) voor meer informatie. |


## Het gegevensschema maken{#create-data-schema}

Voer de volgende stappen uit om het schema van de externe database in Adobe Campaign te maken:

1. Klik op de knop **[!UICONTROL New]** boven de lijst met gegevensschema&#39;s en kies **[!UICONTROL Access external data]**.

   ![](assets/wf_new_schema_fda.png)

1. Voer een naam en beschrijving in voor het schema en selecteer de externe account waarmee verbinding met de database kan worden gemaakt. Hierdoor hebt u toegang tot de lijst met tabellen die beschikbaar zijn in de externe basis. Kies de tabel met de gegevens die moeten worden verzameld.

   ![](assets/wf_new_schema_select_table_fda.png)

1. Klikken **[!UICONTROL OK]** ter bevestiging. Adobe Campaign detecteert automatisch de structuur van de geselecteerde tabel en genereert het logische schema. Adobe Campaign genereert geen koppelingen.

1. Klikken **[!UICONTROL Save]** om de aanmaak te bevestigen.

## De doeltoewijzing definiëren{#define-data-mapping}

U kunt een toewijzing van de gegevens in een externe lijst bepalen.

Om dit te doen, zodra het schema van de externe lijst is gecreeerd, moet u een nieuwe leveringsafbeelding tot stand brengen om de gegevens in deze lijst als leveringsdoel te gebruiken.

Ga als volgt te werk om dit te doen:

1. Bladeren naar **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** van Adobe Campaign Explorer.

1. Creeer een nieuwe doelafbeelding en selecteer het schema u enkel als het richten afmeting creeerde.

   ![](assets/new-target-mapping.png)


1. Geef de velden op waarin de leveringsgegevens zijn opgeslagen (achternaam, voornaam, e-mail, adres, enz.).

   ![](assets/wf_new_mapping_define_join.png)

1. Specificeer de parameters voor informatieopslag, met inbegrip van het achtervoegsel van de uitbreidingsregelingen voor hen om gemakkelijk identificeerbaar te zijn.

   ![](assets/wf_new_mapping_define_names.png)

   U kunt kiezen of u uitsluitingen wilt opslaan (**excludelog**), met berichten (**uitzenden**) of in een aparte tabel.

   U kunt ook kiezen of u het bijhouden van gegevens voor deze leveringstoewijzing wilt beheren (**trackinglog**).

1. Selecteer vervolgens de extensies waarmee u rekening wilt houden. Het extensietype is afhankelijk van de parameters en opties van uw platform (uw licentiecontract weergeven).

   ![](assets/wf_new_mapping_define_extensions.png)

   Klik op de knop **[!UICONTROL Save]** knop voor het maken van de toewijzing van levering: alle gekoppelde tabellen worden automatisch gemaakt op basis van de geselecteerde parameters.


## Machtigingen{#fda-permissions}

Specifiek **machtigingen** zijn vereist op [!DNL Adobe Campaign] en op de externe database om samen te werken.

Ten eerste, zodat de gebruiker bewerkingen kan uitvoeren op een externe database via FDA, moet de exploitant een specifiek benoemd recht hebben in [!DNL Adobe Campaign].

1. Selecteer **[!UICONTROL Administration > Access Management > Named Rights]** in de Adobe Campaign Explorer.
1. Maak een nieuw recht door het gekozen label op te geven.
1. Voer de naam van het benoemde recht in de volgende notatie in **gebruiker:base@server**, waarbij:

   * **user** is de naam van de gebruiker in de externe database
   * **basis** is de naam van de externe database
   * **server** is de naam van de externe databaseserver

1. Sla het recht Benoemd op en koppel het aan de door u gekozen operator vanuit het menu **[!UICONTROL Administration > Access Management > Operators]** knooppunt van de Adobe Campaign-verkenner.

Als u vervolgens de gegevens in een externe database wilt verwerken, moet de Adobe Campaign-operator ten minste de machtiging Schrijven voor de database hebben om werktabellen te kunnen maken. Deze tabellen worden automatisch verwijderd door Adobe Campaign.

De volgende machtigingen zijn vereist:

* **CONNECT**: verbinding met de externe database
* **Gegevens LEZEN**: read-only toegang tot lijsten die klantengegevens bevatten
* **&#39;MetaData&#39; LEZEN**: toegang tot de catalogi van servergegevens om de lijststructuur te verkrijgen
* **LADEN**: massa-belasting in werktabellen (vereist bij het werken aan verzamelingen en verbindingen)
* **MAKEN/NEERZETTEN** for **TABEL/INDEX/PROCEDURE/FUNCTIE** (alleen voor werktabellen die door Adobe Campaign worden gegenereerd)
* **VERKLAREN** (aanbevolen): voor de bewaking van prestaties in geval van een probleem
* **Gegevens SCHRIJVEN** (afhankelijk van het integratiescenario)

De databasebeheerder moet ervoor zorgen dat deze rechten overeenkomen met de specifieke rechten voor elke database-engine, zoals hieronder wordt beschreven.

|   | Snowflake | Amazon Redshift |
|:-:|:-:|:-:|
| **Verbinding maken met externe database** | GEBRUIK OP WAREHOUSE, GEBRUIK OP DATABASE EN GEBRUIK OP SCHEMA-privileges | Een gebruiker maken die is gekoppeld aan de AWS-account |
| **Tabellen maken** | TABEL MAKEN OP SCHEMA-voorrecht | BEVOEGDHEID MAKEN |
| **Indexen maken** | N.v.t. | BEVOEGDHEID MAKEN |
| **Functies maken** | FUNCTIE MAKEN OP SCHEMA-voorrecht | GEBRUIK OP TAALvoorrecht om externe pythonuscripts aan te roepen |
| **Procedures maken** | N.v.t. | GEBRUIK OP TAALpythonbevoegdheid om externe pythonscripts aan te roepen |
| **Objecten verwijderen (tabellen, indexen, functies, procedures)** | Het object in eigendom hebben | Het object in eigendom of supergebruiker zijn |
| **Uitvoeringen controleren** | BEVOEGDHEID MONITOR voor het vereiste object | Geen bevoegdheid vereist om de opdracht EXPLAIN te gebruiken |
| **Gegevens schrijven** | INSERT- en/of UPDATE-bevoegdheden (afhankelijk van schrijfbewerking) | Rechten INVOEGEN en BIJWERKEN |
| **Gegevens in tabellen laden** | WERKGEBIED MAKEN OP SCHEMA, SELECTEREN en INVOEGEN in de rechten voor de doeltabel | SELECTEREN EN INVOEGEN, rechten |
| **Toegang tot clientgegevens** | SELECTEREN OP (TOEKOMSTIGE) TABLE(S)- OF WEERGAVEBEVOEGDHEDEN | SELECT, bevoegdheid |
| **Toegang tot metagegevens** | SELECTEER INFORMATIE_SCHEMA-SCHEMA-voorrecht | SELECT, bevoegdheid |


## Externe gegevens gebruiken in een workflow

Zodra het gegevensschema wordt gecreeerd, kunnen de gegevens in de werkschema&#39;s van Adobe Campaign worden verwerkt.

Met meerdere activiteiten kunt u werken met gegevens uit een externe database:

* **Filter op externe gegevens** - de **[!UICONTROL Query]** Met activiteit kunt u externe gegevens toevoegen en gebruiken in de gedefinieerde filterconfiguraties.

* **Subsets maken** - de **[!UICONTROL Split]** kunt u subsets maken. U kunt externe gegevens gebruiken om de filtercriteria te bepalen aan gebruik.

* **Externe database laden** - U kunt externe gegevens gebruiken in het dialoogvenster **[!UICONTROL Data loading (RDBMS)]** activiteit.

* **Informatie en koppelingen toevoegen** - de **[!UICONTROL Enrichment]** Met activiteit kunt u aanvullende gegevens toevoegen aan de werktabel van de werkstroom en koppelingen maken naar een externe tabel. In deze context kan het gegevens uit een externe database gebruiken.


U kunt ook rechtstreeks een verbinding met een externe database definiëren vanuit deze workflowactiviteiten, voor een tijdelijk gebruik. In dit geval bevindt het bestand zich in een lokale externe database die is gereserveerd voor gebruik in een huidige workflow: het wordt niet opgeslagen op de externe accounts.

>[!CAUTION]
>
>Dit type van configuratie moet slechts tijdelijk worden gebruikt om gegevens te verzamelen. De configuratie van de externe account verdient de voorkeur voor elk ander gebruik.

In het dialoogvenster **[!UICONTROL Query]** activiteit, kunt u een tijdelijke verbinding aan een extern gegevensbestand als volgt bepalen:

1. Open de activiteit en klik op **[!UICONTROL Add data...]**
1. Selecteer **[!UICONTROL External data]** opties
1. Selecteer **[!UICONTROL Locally defining the data source]** option
1. Selecteer de doeldatabase-engine in de vervolgkeuzelijst. Voer de naam van de server in en geef de verificatieparameters op. Geef ook de naam van de externe database op.
1. Selecteer de tabel waarin de gegevens zijn opgeslagen. U kunt de naam van de tabel rechtstreeks in het desbetreffende veld invoeren of op het pictogram Bewerken klikken om de lijst met databasetabellen te openen.
1. Klik op de knop **[!UICONTROL Add]** om een of meer afstemmingsvelden te definiëren tussen de externe databasegegevens en de gegevens in de Adobe Campaign-database. De **[!UICONTROL Edit expression]** pictogrammen van de **[!UICONTROL Remote field]** en **[!UICONTROL Local field]** geeft u toegang tot de lijst van gebieden van elk van de lijsten.
1. Geef zo nodig een filtervoorwaarde en de gegevenssorteermodus op.
1. Selecteer de aanvullende gegevens die in de externe database moeten worden verzameld. Dubbelklik hiertoe op de velden die u wilt toevoegen om deze weer te geven in het dialoogvenster **[!UICONTROL Output columns]**.
1. Klikken **[!UICONTROL Finish]** om deze configuratie te bevestigen.
