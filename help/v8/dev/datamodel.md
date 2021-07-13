---
product: Adobe Campaign
title: Aan de slag met het gegevensmodel van de campagne
description: Aan de slag met het gegevensmodel van de campagne
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 1%

---

# Aan de slag met het gegevensmodel van de campagne{#gs-ac-datamodel}

Adobe Campaign bevat een vooraf gedefinieerd datamodel. In deze sectie vindt u enkele details over de ingebouwde tabellen van het Adobe Campaign-gegevensmodel en de interactie ervan. Adobe Campaign vertrouwt op een Cloud-database die tabellen bevat die aan elkaar zijn gekoppeld.

De basisstructuur van het Adobe Campaign-gegevensmodel kan als volgt worden beschreven:

* **Ontvangertabel**: Het gegevensmodel is gebaseerd op een hoofdtabel die standaard de tabel Ontvanger is (nmsRecipient). In deze tabel kunt u alle marketingprofielen opslaan.

   ?? Zie [deze sectie](#ootb-profiles) voor meer informatie over de tabel Ontvanger.

* **Afleveringstabel**: Het gegevensmodel bevat ook een deel dat is gewijd aan de opslag van alle marketingactiviteiten. Meestal is dit de afleveringstabel (NmsDelivery). Elke record in deze tabel vertegenwoordigt een leveringsactie of een leveringssjabloon. Het bevat alle parameters die nodig zijn voor het uitvoeren van leveringen, zoals doel, inhoud, enz.

* **Logtabellen**: In deze tabellen worden alle logbestanden opgeslagen die bij de uitvoering van de campagnes horen.

   De logboeken van de levering zijn alle berichten die naar ontvangers of apparaten over alle kanalen worden verzonden. De hoofdtabel met leveringslogbestanden (NmsBroadLogRcp) bevat de leveringslogboeken voor alle ontvangers.
In de hoofdtabel Logbestanden voor bijhouden (NmsTrackingLogRcp) worden de logbestanden voor bijhouden opgeslagen voor alle ontvangers. De trackinglogboeken verwijzen naar reacties van ontvangers, zoals het openen van e-mail en klikken. Elke reactie komt overeen met een trackinglog.
Logbestanden voor aflevering en tracering worden na een bepaalde periode verwijderd, die in Adobe Campaign is opgegeven en kan worden gewijzigd. Daarom wordt het ten zeerste aanbevolen de stammen regelmatig uit te voeren.

* **Technische tabellen**: Verzamel technische gegevens die voor het toepassingsproces worden gebruikt, met inbegrip van exploitanten en gebruikersrechten (xtkGroup), omslagen (XtkFolder).

>[!NOTE]
>
>Om tot de beschrijving van elke lijst toegang te hebben, ga naar Admin > Configuratie > de schema&#39;s van Gegevens, selecteer een middel van de lijst en klik **Documentatie** tabel.

Wanneer u begint met Adobe Campaign, moet u het standaardgegevensmodel beoordelen om te controleren welke tabel het meest geschikt is om uw marketinggegevens op te slaan.

U kunt de standaard Ontvanger lijst met de uit-van-de-doos gebieden gebruiken, zoals die in [deze sectie](#ootb-profiles) worden beschreven. Indien nodig kunt u het uitbreiden met twee mechanismen:

* [Een bestaande ](extend-schema.md) tabel uitbreiden met nieuwe velden. U kunt bijvoorbeeld een nieuw veld Loyalty toevoegen aan de tabel Ontvanger.
* [Maak een nieuwe tabel](create-schema.md), bijvoorbeeld een tabel met aankopen die alle aankopen bevat die door elk profiel van de database zijn gedaan, en koppel deze aan de tabel met ontvangers.

?? Ontdek beste praktijken wanneer het werken met het datamodel van de Campagne in [deze sectie](datamodel-best-practices.md).

## Ingebouwde profielentabel {#ootb-profiles}

De ingebouwde ontvankelijke lijst (nmsreceiver) in Adobe Campaign verstrekt een goed uitgangspunt voor de bouw van uw gegevensmodel. Het heeft een aantal vooraf bepaalde gebieden en lijstverbindingen die gemakkelijk kunnen worden uitgebreid. Dit is met name nuttig wanneer u zich vooral richt op ontvangers, omdat het een eenvoudig ontvanger-centric gegevensmodel past.

De voordelen van de standaardtabel voor ontvangers zijn:

* Het werken uit-van-de-doos met zeer belangrijke functionaliteiten zoals abonnementen, zaadlijsten, en meer
* Het verstrekken van een marketing gegevensbestand van een ontvanger-centric gegevensmodel
* Snellere implementatie
* Gemakkelijk onderhoud door steun en partners

Het is mogelijk de tabel voor ontvangers uit te breiden, maar niet om het aantal velden of koppelingen in de tabel te verminderen.

?? Leer hoe te om een bestaand schema in [deze sectie](extend-schema.md) uit te breiden.

↗️ Ontdek voorbeelden van ingebouwde ontvankelijke lijstuitbreidingen in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

U kunt een verschillende ontvankelijke lijst ook gebruiken om met uw zaken of functionele vereisten beter te passen. Deze methode wordt geleverd met beperkingen en wordt beschreven in [deze sectie](custom-recipient.md).

## Campagnetabellen en Cloud-database

Voor een beter begrip van lijstbeheer in Campagne v8, merk op dat de lijsten tussen Campagne en zijn gegevensbestand van de Snowflake Cloud worden herhaald.

?? Meer informatie over replicatiestrategie en mechanismen in [deze sectie](../config/replication.md).

**Verwante onderwerpen**

?? Ontdek hoe u profielen kunt importeren in [deze sectie](../start/import.md)
?? Meer informatie over campagnepubliek vindt u in [deze sectie](../start/audiences.md)
