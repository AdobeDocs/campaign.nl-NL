---
title: Aan de slag met het gegevensmodel van de campagne
description: Ga aan de slag met het datamodel van Campaign en maak gebruik van gegevens van uw bronnen om te profiteren van uw communicatie- en marketinguitvoer.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 87e56e7c296884458a0c8fd704b82611f56e695d
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 4%

---

# Aan de slag met het gegevensmodel van de campagne{#gs-ac-datamodel}

Adobe Campaign bevat een vooraf gedefinieerd datamodel. In deze sectie vindt u enkele details over de ingebouwde tabellen van het Adobe Campaign-gegevensmodel en de interactie ervan. Adobe Campaign vertrouwt op een Cloud-database die tabellen bevat die aan elkaar zijn gekoppeld.

De basisstructuur van het Adobe Campaign-gegevensmodel kan als volgt worden beschreven:

* **Ontvangertabel**: Het gegevensmodel is gebaseerd op een hoofdtabel die standaard de tabel Ontvanger is (**nmsRecipient**). In deze tabel worden alle marketingprofielen opgeslagen. Meer informatie over de tabel met ontvangers vindt u in [deze sectie](#ootb-profiles).

* **Afleveringstabel**: In deze tabel wordt één record per leveringsactie opgeslagen. Doorgaans is dit de afleveringstabel (**NmsDelivery**). in deze tabel staat voor een leveringsactie of een leveringssjabloon. Het bevat alle parameters die nodig zijn voor het uitvoeren van leveringen, zoals doel, inhoud, enz. Elke record wordt meerdere malen bijgewerkt om de voortgang van de levering te weerspiegelen

* **Logtabellen**: In deze tabellen worden alle logbestanden opgeslagen die bij de uitvoering van de campagnes horen.

   * De logboeken van de levering zijn alle berichten die naar ontvangers of apparaten over alle kanalen worden verzonden. De belangrijkste leveringstabel (**NmsBroadLogRcp**) bevat de leveringslogboeken voor alle ontvangers.
   * De **nmsBroadlog** tabel is de grootste tabel in het systeem . Het slaat één verslag per verzonden bericht op, en deze verslagen worden opgenomen, bijgewerkt om de leveringsstatus te volgen, en geschrapt wanneer de geschiedenis wordt gezuiverd.
   * De hoofdtabel met trackinglogbestanden (**NmsTrackingLogRcp**) slaat de volgende logboeken voor alle ontvangers op. De trackinglogboeken verwijzen naar reacties van ontvangers, zoals het openen van e-mail en klikken. Elke reactie komt overeen met een trackinglog.

  Logbestanden voor aflevering en tracering worden na een bepaalde periode verwijderd, die in Adobe Campaign is opgegeven en kan worden gewijzigd. Daarom wordt het ten zeerste aanbevolen de stammen regelmatig uit te voeren.

* **Technische tabellen**: Verzamelen van technische gegevens die voor het aanvraagproces worden gebruikt, met inbegrip van exploitanten en gebruikersrechten (**xtkGroup**), gebruikerssessies (**xtkSessionInfo**), mappen in de verkenner-boomstructuur (**XtkFolder**), workflows (**xtkWorkflow**) en meer.

>[!NOTE]
>
>Ga naar Beheer > Configuratie > Gegevensschema&#39;s om de beschrijving van elke tabel te openen, selecteer een bron in de lijst en klik op de knop **Documentatie** tab.

Wanneer u begint met Adobe Campaign, moet u het standaardgegevensmodel beoordelen om te controleren welke tabel het meest geschikt is om uw marketinggegevens op te slaan.

U kunt de standaardtabel Ontvanger gebruiken voor de velden buiten het vak, zoals wordt beschreven in [deze sectie](#ootb-profiles). Indien nodig, kunt u het uitbreiden met twee mechanismen:

* [Een bestaande tabel uitbreiden](extend-schema.md) met nieuwe velden. U kunt bijvoorbeeld een nieuw veld Loyalty toevoegen aan de tabel Ontvanger.
* [Een nieuwe tabel maken](create-schema.md), bijvoorbeeld een tabel met alle aankopen die door elk profiel van de database zijn gedaan, en koppel deze aan de tabel Ontvanger.

![](../assets/do-not-localize/glass.png) Ontdek beste praktijken wanneer het werken met het datamodel van de Campagne in [deze sectie](datamodel-best-practices.md).

## Ingebouwde profielentabel {#ootb-profiles}

De ingebouwde ontvankelijke lijst (nmsreceiver) in Adobe Campaign verstrekt een goed uitgangspunt voor de bouw van uw gegevensmodel. Het bevat een aantal vooraf gedefinieerde velden en tabelkoppelingen die gemakkelijk kunnen worden uitgebreid. Dit is met name nuttig wanneer u zich vooral richt op ontvangers, omdat het een eenvoudig ontvanger-centric gegevensmodel past.

De voordelen van de standaardtabel voor ontvangers zijn:

* Het werken uit-van-de-doos met zeer belangrijke functionaliteiten zoals abonnementen, zaadlijsten, en meer
* Het verstrekken van een marketing gegevensbestand van een ontvanger-centric gegevensmodel
* Snellere implementatie
* Gemakkelijk onderhoud door steun en partners

Het is mogelijk de tabel voor ontvangers uit te breiden, maar niet om het aantal velden of koppelingen in de tabel te verminderen.

![](../assets/do-not-localize/glass.png) Leer hoe u een bestaand schema kunt uitbreiden in [deze sectie](extend-schema.md).

![](../assets/do-not-localize/book.png) Voorbeelden van ingebouwde tabelextensies voor ontvangers ontdekken in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#extending-a-table){target="_blank"}

U kunt een verschillende ontvankelijke lijst ook gebruiken om beter met uw zaken of functionele vereisten te passen. Deze methode heeft beperkingen en wordt beschreven in [deze sectie](custom-recipient.md).

## Campagnetabellen en Cloud-database

Voor een beter inzicht in tabelbeheer in Campaign v8, moet u in de context van een [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md), worden tabellen gerepliceerd tussen Campagne en de bijbehorende Snowflake Cloud-database.

![](../assets/do-not-localize/glass.png) Meer informatie over replicatiestrategie en -mechanismen in [deze sectie](../architecture/replication.md).

**Verwante onderwerpen**

![](../assets/do-not-localize/glass.png) Ontdek hoe u profielen kunt importeren in [deze sectie](../start/import.md)
![](../assets/do-not-localize/glass.png) Meer informatie over campagnepubliek in [deze sectie](../start/audiences.md)
