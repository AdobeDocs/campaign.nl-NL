---
title: Aan de slag met het gegevensmodel van de campagne
description: Ga aan de slag met het datamodel van Campaign en maak gebruik van gegevens van uw bronnen om te profiteren van uw communicatie- en marketinguitvoer.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 4%

---

# Aan de slag met het gegevensmodel van de campagne {#gs-ac-datamodel}

Adobe Campaign bevat een vooraf gedefinieerd datamodel. In deze sectie vindt u enkele details over de ingebouwde tabellen van het Adobe Campaign-gegevensmodel en de interactie ervan. Adobe Campaign vertrouwt op een Cloud-database die tabellen bevat die aan elkaar zijn gekoppeld.

De basisstructuur van het Adobe Campaign-gegevensmodel kan als volgt worden beschreven:

* **Ontvankelijke lijst**: Het gegevensmodel baseert zich op een belangrijkste lijst die door gebrek de Ontvankelijke lijst (**nmsRecipient**) is. In deze tabel worden alle marketingprofielen opgeslagen. Leer meer over de ontvankelijke lijst in [ deze sectie ](#ootb-profiles).

* **lijst van de Levering**: Deze lijst slaat één verslag per leveringsactie op. Gewoonlijk is het de lijst van de Levering (**NmsDelivery**). in deze tabel staat voor een leveringsactie of een leveringssjabloon. Het bevat alle parameters die nodig zijn voor het uitvoeren van leveringen, zoals doel, inhoud, enz. Elke record wordt meerdere malen bijgewerkt om de voortgang van de levering te weerspiegelen

* **Logs lijsten**: Deze lijsten slaan alle logboeken op verbonden aan de uitvoering van de campagnes.

   * De logboeken van de levering zijn alle berichten die naar ontvangers of apparaten over alle kanalen worden verzonden. De belangrijkste lijst van Logboeken van de Levering (**NmsBroadLogRcp**) bevat de leveringslogboeken voor alle ontvangers.
   * De **nmsBroadlog** lijst is de grootste lijst in het systeem. Het slaat één verslag per verzonden bericht op, en deze verslagen worden opgenomen, bijgewerkt om de leveringsstatus te volgen, en geschrapt wanneer de geschiedenis wordt gezuiverd.
   * De belangrijkste het Volgen logboeklijst (**NmsTrackingLogRcp**) slaat de volgende logboeken voor alle ontvangers op. De trackinglogboeken verwijzen naar reacties van ontvangers, zoals het openen van e-mail en klikken. Elke reactie komt overeen met een trackinglog.

  Logbestanden voor aflevering en tracering worden na een bepaalde periode verwijderd, die in Adobe Campaign is opgegeven en kan worden gewijzigd. Daarom wordt het ten zeerste aanbevolen de stammen regelmatig uit te voeren.

* **Technische lijsten**: Verzamel technische gegevens die voor het toepassingsproces worden gebruikt, met inbegrip van exploitanten en gebruikersrechten (**xtkGroup**), gebruikerszittingen (**xtkSessionInfo**), omslagen in de ontdekkingsboom (**XtkFolder**), werkschema&#39;s (**xtkWorkflow**), en meer.

>[!NOTE]
>
>Om tot de beschrijving van elke lijst toegang te hebben, doorblader aan **Beleid > Configuratie > de schema&#39;s van Gegevens**, selecteer een middel van de lijst, en klik de **Documentatie** tabel.

Wanneer u begint met Adobe Campaign, moet u het standaardgegevensmodel beoordelen om te controleren welke tabel het meest geschikt is om uw marketinggegevens op te slaan.

U kunt de standaard Ontvanger lijst met de uit-van-de-doos gebieden gebruiken, zoals die in [ wordt beschreven deze sectie ](#ootb-profiles). Indien nodig, kunt u het uitbreiden met twee mechanismen:

* [ breid een bestaande lijst ](extend-schema.md) met nieuwe gebieden uit. U kunt bijvoorbeeld een nieuw veld Loyalty toevoegen aan de tabel Ontvanger.
* [ creeer een nieuwe lijst ](create-schema.md), bijvoorbeeld een lijst van de &quot;Aankoop&quot;die van alle aankopen een lijst maakt die door elk profiel van het gegevensbestand worden gemaakt, en verbind het met de Ontvankelijke lijst.

Ontdek beste praktijken wanneer het werken met het gegevensmodel van de Campagne in [ deze sectie ](datamodel-best-practices.md).

## Ingebouwde profielentabel {#ootb-profiles}

De ingebouwde ontvankelijke lijst (nmsreceiver) in Adobe Campaign verstrekt een goed uitgangspunt voor de bouw van uw gegevensmodel. Het bevat een aantal vooraf gedefinieerde velden en tabelkoppelingen die gemakkelijk kunnen worden uitgebreid. Dit is met name nuttig wanneer u zich vooral richt op ontvangers, omdat het een eenvoudig ontvanger-centric gegevensmodel past.

De voordelen van de standaardtabel voor ontvangers zijn:

* Het werken uit-van-de-doos met zeer belangrijke functionaliteiten zoals abonnementen, zaadlijsten, en meer
* Het verstrekken van een marketing gegevensbestand van een ontvanger-centric gegevensmodel
* Snellere implementatie
* Gemakkelijk onderhoud door steun en partners

Het is mogelijk de tabel voor ontvangers uit te breiden, maar niet om het aantal velden of koppelingen in de tabel te verminderen.

Leer hoe te om een bestaand schema in [ uit te breiden deze sectie ](extend-schema.md).

Ontdek voorbeelden van ingebouwde ontvankelijke lijstuitbreidingen in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#extending-a-table){target="_blank"}

U kunt een verschillende ontvankelijke lijst ook gebruiken om beter met uw zaken of functionele vereisten te passen. Deze methode komt met beperkingen en wordt beschreven in [ deze sectie ](custom-recipient.md).

## Campagnetabellen en Cloud-database

Voor een beter inzicht in lijstbeheer in Campagne v8, merk op dat, in de context van een [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), de lijsten tussen Campagne en zijn gegevensbestand van de Wolk van Snowflake worden herhaald.

Leer meer over replicatiestrategie en mechanismen in [ deze sectie ](../architecture/replication.md).

**Verwante onderwerpen**

Ontdek hoe te om profielen in [ in deze sectie in te voeren ](../start/import.md)
Leer meer over het publiek van de Campagne in [ deze sectie ](../start/audiences.md)
