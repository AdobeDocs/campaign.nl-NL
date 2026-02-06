---
title: Werken met campagnes en externe databases (FDA)
description: Leer hoe u kunt werken met Campagne en externe databases
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 631c4986d24daeff870412566318adb170ce040f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# Federated Data Access (FDA){#gs-fda}

Gebruik de Schakelaar FDA (Federated Toegang van Gegevens) om Campagne met één of meerdere **externe gegevensbestanden** te verbinden en informatie te verwerken die in hen wordt opgeslagen zonder de gegevens van het Gegevensbestand van de Wolk van de Campagne te beïnvloeden. U kunt externe gegevens vervolgens openen zonder de structuur van Adobe Campaign-gegevens te wijzigen.

>[!NOTE]
>
>* De compatibele gegevensbestanden voor Federatieve Toegang van Gegevens zijn vermeld in de [&#x200B; matrijs van de Verenigbaarheid &#x200B;](../start/compatibility-matrix.md).
>
>* In de context van een [&#x200B; plaatsing van de Onderneming (FFDA) &#x200B;](../../v8/architecture/enterprise-deployment.md), is een specifieke externe rekening beschikbaar om mededeling tussen het lokale gegevensbestand van de Campagne en het wolkengegevensbestand van Snowflake te beheren. Deze externe rekening wordt opstelling voor u door Adobe en **moet niet** worden gewijzigd.
>
>* Als Beheerde gebruiker van de Diensten van de Wolk, [&#x200B; contacteer Adobe &#x200B;](../start/campaign-faq.md#support) om uw externe gegevensbestand (s) met Campagne te verbinden.


## Best practices en beperkingen

Voor de optie FDA gelden de beperkingen van het databasesysteem van derden dat u gebruikt.

Houd ook rekening met de volgende beperkingen en beste praktijken:

* De optie FDA is bedoeld om de gegevens in externe databases in batchmodus te manipuleren in workflows. Om prestatieproblemen te voorkomen, wordt het niet aanbevolen de FDA-module te gebruiken in het kader van eenheidsbewerkingen, zoals personalisatie, interactie, realtime berichten, enz.

* Vermijd de bewerkingen die zowel de Adobe Campaign als de externe database zoveel mogelijk moeten gebruiken. Hiervoor kunt u:

   * Exporteer de Adobe Campaign-database naar de externe database en voer de bewerkingen alleen uit vanuit de externe database voordat u de resultaten opnieuw importeert in Adobe Campaign.

   * Verzamel de gegevens in de externe Adobe Campaign-database en voer de bewerkingen lokaal uit.

  Als u personalisatie in uw leveringen wilt uitvoeren gebruikend gegevens van het externe gegevensbestand, verzamel de gegevens in een werkschema te gebruiken om het ter beschikking te stellen in een tijdelijke lijst. Dan gebruik de gegevens van de tijdelijke lijst om uw levering te personaliseren. Hiervoor gebruikt u de optie **[!UICONTROL Prepare the personalization data with a workflow]** , beschikbaar op het tabblad **[!UICONTROL Analysis]** van de leveringseigenschappen, om berichten vóór de verwerking aan te passen in een specifieke workflow. Tijdens de leveringsanalyse, leidt deze optie automatisch tot en voert een werkschema uit dat alle gegevens met betrekking tot het doel in een tijdelijke lijst, met inbegrip van gegevens van lijsten verbonden in een extern gegevensbestand opslaat.

  >[!CAUTION]
  >
  >Met deze optie worden de prestaties aanzienlijk verbeterd wanneer de stap voor personalisatie wordt uitgevoerd.


## Externe gegevens gebruiken in een workflow

De campagne wordt geleverd met verschillende workflowactiviteiten die u kunt gebruiken voor interactie met gegevens uit uw externe database(s):

* **Filter op externe gegevens** - gebruik de **[!UICONTROL Query]** activiteit om externe gegevens toe te voegen en het in de bepaalde filterconfiguraties te gebruiken.

* **creeer ondergroepen** - gebruik de **[!UICONTROL Split]** activiteit om ondergroepen tot stand te brengen. U kunt externe gegevens gebruiken om de filtercriteria te bepalen aan gebruik.

* **Laad externe gegevensbestand** - gebruik de externe gegevens in de **[!UICONTROL Data loading (RDBMS)]** activiteit.

* **Toevoegend informatie en verbindingen** - gebruik de **[!UICONTROL Enrichment]** activiteit om extra gegevens aan de werklijst van het werkschema, en verbindingen aan een externe lijst toe te voegen. In deze context kan het gegevens uit een externe database gebruiken.

U kunt ook rechtstreeks een verbinding met een externe database definiëren vanuit alle hierboven vermelde workflowactiviteiten, voor een tijdelijk gebruik. In dit geval bevindt de database zich op een lokale externe database die alleen binnen de huidige workflow wordt gebruikt.

>[!CAUTION]
>
>Dit type van configuratie moet slechts tijdelijk worden gebruikt om gegevens te verzamelen. De configuratie van de externe account verdient de voorkeur voor elk ander gebruik.

In de activiteit **[!UICONTROL Query]** kunt u bijvoorbeeld als volgt een tijdelijke verbinding met een externe database definiëren:

1. Open de activiteit en klik op **[!UICONTROL Add data...]**
1. Selecteer de opties voor **[!UICONTROL External data]**
1. Selecteer de optie **[!UICONTROL Locally defining the data source]**
1. Selecteer de doeldatabase-engine in de vervolgkeuzelijst. Voer de naam van de server in en geef de verificatieparameters op. Geef ook de naam van de externe database op.
1. Selecteer de tabel waarin de gegevens zijn opgeslagen. U kunt de naam van de tabel rechtstreeks in het desbetreffende veld invoeren of op het pictogram Bewerken klikken om de lijst met databasetabellen te openen.
1. Klik op de knop **[!UICONTROL Add]** om een of meerdere afstemmingsvelden te definiëren tussen de externe databasegegevens en de gegevens in de Adobe Campaign-database. Met de **[!UICONTROL Edit expression]** pictogrammen van de **[!UICONTROL Remote field]** en **[!UICONTROL Local field]** hebt u toegang tot de lijst met velden van elk van de tabellen.
1. Geef zo nodig een filtervoorwaarde en de gegevenssorteermodus op.
1. Selecteer de aanvullende gegevens die in de externe database moeten worden verzameld. Dubbelklik hiertoe op de velden die u wilt toevoegen om deze weer te geven in de **[!UICONTROL Output columns]** .
1. Klik op **[!UICONTROL Finish]** om deze configuratie te bevestigen.
