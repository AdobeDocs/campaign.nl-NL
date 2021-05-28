---
solution: Campaign v8
product: Adobe Campaign
title: De standaardtabel voor ontvangers wijzigen
description: Leer hoe u een aangepaste tabel voor ontvangers gebruikt
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 2%

---

# Een aangepaste tabel voor ontvangers gebruiken{#gs-ac-custom-recipient}

Adobe Campaign wordt geleverd met een ingebouwde profielentabel: **nmsRecipient**. Deze tabel bevat een aantal vooraf gedefinieerde velden en tabellen die u eenvoudig kunt uitbreiden. Meer informatie over deze tabel vindt u op [deze pagina](datamodel.md#ootb-profiles).

De ingebouwde tabeluitbreiding biedt flexibiliteit, maar het is niet toegestaan om enkele ongebruikte velden of koppelingen te verwijderen. Als gevolg hiervan kan het gebruik van een aangepaste ontvankelijke tabel een goede optie zijn wanneer uw datamodel sterk afwijkt van de geïntegreerde tabelstructuur van de campagne voor ontvangers of wanneer u een groot aantal profielen hebt.  Deze methode vereist echter bepaalde voorzorgsmaatregelen bij de toepassing ervan.

Met deze functionaliteit kan Adobe Campaign gegevens uit een externe database verwerken: deze gegevens worden gebruikt als een reeks profielen voor leveringen . De implementatie van dit proces omvat beperkingen, zoals:

* Geen updatestream van en naar de Campagne Cloud-database: gegevens uit deze tabel kunnen rechtstreeks worden bijgewerkt via de database-engine die de tabel host.
* De processen die op het bestaande gegevensbestand werken moeten stabiel zijn.
* Een profieldatabase gebruiken met een niet-standaardstructuur: de mogelijkheid om profielen die in verschillende tabellen zijn opgeslagen, met verschillende structuren te leveren met behulp van één exemplaar.

In deze sectie worden de hoofdpunten beschreven voor het toewijzen van bestaande tabellen in Adobe Campaign en de configuratie-instellingen die moeten worden toegepast om leveringen uit te voeren op basis van een tabel. Het beschrijft ook hoe te om het vragen van interfaces voor eindgebruikers te ontwerpen.

>[!CAUTION]
>
>Adobe Campaign-aanpassingen zijn alleen bestemd voor deskundige gebruikers. Hiervoor is expertise vereist op het gebied van invoerformulieren en schemaontwerp.

