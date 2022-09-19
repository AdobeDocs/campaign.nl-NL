---
title: Werken met campagnes en externe databases (FDA)
description: Leer hoe u kunt werken met Campagne en externe databases
feature: Federated Data Access
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: bb03c804c1c65322d275d0a2ca1db0bfe974636d
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# Federated Data Access (FDA){#gs-fda}

Gebruik de FDA-connector (Federated Data Access) om de campagne aan te sluiten op een of meer **externe databases** en procesgegevens die in deze bestanden zijn opgeslagen, zonder dat dit van invloed is op de gegevens van de Campagne Cloud Database. U kunt externe gegevens vervolgens openen zonder de structuur van Adobe Campaign-gegevens te wijzigen.

![](../assets/do-not-localize/speech.png)   Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support) om Experience Cloud-triggers te implementeren met Campagne.


>[!NOTE]
>
>* De compatibele gegevensbestanden voor Federatieve Toegang van Gegevens zijn vermeld in [Compatibiliteitsmatrix](../start/compatibility-matrix.md).
>
>* In de context van een [Implementatie van ondernemingen (FFDA)](../architecture/enterprise-deployment.md), is er een specifieke externe account beschikbaar voor het beheer van de communicatie tussen de lokale database van Campagne en de cloud-database van Snowflake. Deze externe account is voor u ingesteld door Adobe en **mogen** worden gewijzigd.
>



## Best practices en beperkingen

Voor de optie FDA gelden de beperkingen van het databasesysteem van derden dat u gebruikt.

Houd ook rekening met de volgende beperkingen en beste praktijken:

* De optie FDA is bedoeld om de gegevens in externe databases in batchmodus te manipuleren in workflows. Om prestatieproblemen te voorkomen, wordt het niet aanbevolen de FDA-module te gebruiken in het kader van eenheidsoperaties, zoals: personalisatie, interactie, real-time overseinen, enz.

* Vermijd de bewerkingen die zowel de Adobe Campaign als de externe database zoveel mogelijk moeten gebruiken. Hiervoor kunt u:

   * Exporteer de Adobe Campaign-database naar de externe database en voer de bewerkingen alleen uit vanuit de externe database voordat u de resultaten opnieuw importeert in Adobe Campaign.

   * Verzamel de gegevens in de externe Adobe Campaign-database en voer de bewerkingen lokaal uit.
   Als u personalisatie in uw leveringen wilt uitvoeren gebruikend gegevens van het externe gegevensbestand, verzamel de gegevens in een werkschema te gebruiken om het ter beschikking te stellen in een tijdelijke lijst. Dan gebruik de gegevens van de tijdelijke lijst om uw levering te personaliseren. Om dit uit te voeren, pre-proces berichtverpersoonlijking in een specifieke werkschema gebruikend **[!UICONTROL Prepare the personalization data with a workflow]** beschikbaar in het dialoogvenster **[!UICONTROL Analysis]** tabblad van de leveringseigenschappen. Tijdens de leveringsanalyse, leidt deze optie automatisch tot en voert een werkschema uit dat alle gegevens met betrekking tot het doel in een tijdelijke lijst, met inbegrip van gegevens van lijsten verbonden in een extern gegevensbestand opslaat.

   >[!CAUTION]
   >
   >Met deze optie worden de prestaties aanzienlijk verbeterd wanneer de stap voor personalisatie wordt uitgevoerd.


## Externe gegevens gebruiken in een workflow

De campagne wordt geleverd met verschillende workflowactiviteiten die u kunt gebruiken voor interactie met gegevens uit uw externe database(s):

* **Filter op externe gegevens** - Gebruik de **[!UICONTROL Query]** activiteit om externe gegevens toe te voegen en het te gebruiken in de bepaalde filterconfiguraties.

* **Subsets maken** - Gebruik de **[!UICONTROL Split]** activiteit om subsets te maken. U kunt externe gegevens gebruiken om de filtercriteria te bepalen aan gebruik.

* **Externe database laden** - Gebruik de externe gegevens in de **[!UICONTROL Data loading (RDBMS)]** activiteit.

* **Informatie en koppelingen toevoegen** - Gebruik de **[!UICONTROL Enrichment]** om aanvullende gegevens toe te voegen aan de werktabel van de werkstroom en aan een externe tabel. In deze context kan het gegevens uit een externe database gebruiken.

U kunt ook rechtstreeks een verbinding met een externe database definiëren vanuit alle hierboven vermelde workflowactiviteiten, voor een tijdelijk gebruik. In dit geval bevindt de database zich op een lokale externe database die alleen binnen de huidige workflow wordt gebruikt.

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
