---
title: De standaardtabel voor ontvangers wijzigen
description: Leer hoe u een aangepaste tabel voor ontvangers gebruikt
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 3205b492552afc0aa0514f8995f508439a7a9a0b
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

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

