---
title: De standaardtabel voor ontvangers wijzigen
description: Leer hoe u een aangepaste tabel voor ontvangers gebruikt
feature: Custom Resources, Profiles
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 3%

---

# Een aangepaste tabel voor ontvangers gebruiken{#gs-ac-custom-recipient}

Adobe Campaign wordt geleverd met een ingebouwde tabel met profielen: **nmsRecipient**. Deze tabel bevat een aantal vooraf gedefinieerde velden en tabellen die u eenvoudig kunt uitbreiden. Meer informatie over deze tabel vindt u in [deze pagina](datamodel.md#ootb-profiles).

De ingebouwde tabeluitbreiding biedt flexibiliteit, maar het is niet toegestaan om enkele ongebruikte velden of koppelingen te verwijderen. Als gevolg hiervan kan het gebruik van een aangepaste ontvankelijke tabel een goede optie zijn wanneer uw datamodel sterk afwijkt van de geïntegreerde tabelstructuur van de campagne voor ontvangers of wanneer u een groot aantal profielen hebt.  Deze methode vereist echter bepaalde voorzorgsmaatregelen bij de toepassing ervan.

![](../assets/do-not-localize/book.png) Leer hoe u uw instantie configureert voor het gebruik van een aangepaste tabel voor ontvangers in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target=&quot;_blank&quot;}.