---
title: Aan de slag met profielen en doelgroepen in campagne
description: Leer profielen en publiek maken en beheren in Campagne
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
source-git-commit: c316da3c431e42860c46b5a23c73a7c129abf3ac
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 9%

---

# Aan de slag met profielen en doelgroepen in campagne{#gs-profiles-and-audiences}

Profielen zijn contacten die in het gegevensbestand van de Campagne, zoals klanten, abonnees aan de dienst of vooruitzichten worden opgeslagen. Er zijn vele mogelijke mechanismen om profielen te verwerven en dit gegevensbestand op te bouwen: online verzameling via webformulieren, handmatige of automatische import van tekstbestanden, replicatie met bedrijfsdatabases of andere informatiesystemen. Met Adobe Campaign kunt u de marketinggeschiedenis, aankoopgegevens, voorkeuren, CRM-gegevens en alle relevante PI-gegevens in een geconsolideerde weergave opnemen om te analyseren en actie te ondernemen. Profielen bevatten alle informatie die vereist is voor het toewijzen van doelen, kwalificeren en volgen van personen.

Een profiel is een record in het dialoogvenster **nmsRecipient** een tabel of een externe tabel waarin alle profielkenmerken zijn opgeslagen, zoals voornaam, achternaam, e-mailadres, een cookie-id, de klant-id, de mobiele id of andere informatie die relevant is voor een bepaald kanaal. Andere lijsten verbonden aan de ontvankelijke lijst bevatten op profiel betrekking hebbende gegevens, bijvoorbeeld de lijst van leveringslogboeken die verslagen van alle leveringen bevat die naar ontvangers worden verzonden. Meer informatie over ingebouwde profielen en tabellen voor ontvangers vindt u in [deze sectie](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign: **ontvangers** Dit zijn de standaardprofielen die worden gebruikt voor het verzenden van leveringen (e-mails, SMS, enz.). De ontvangende gegevens die in het gegevensbestand worden opgeslagen laten u toe om het doel te filtreren dat om het even welke bepaalde levering zal ontvangen en verpersoonlijkingsgegevens in uw leveringsinhoud toe te voegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.


Als u Adobe Campaign wilt vullen met profielgegevens, kunt u:

* [gegevensbestanden importeren](../start/import.md) van een externe gegevensbron zoals een CRM-systeem
* [webformulieren maken](../dev/webapps.md) om klanten toe te staan om hun eigen informatie in te gaan en hun eigen profiel tot stand te brengen
* [toewijzen aan een externe database](../connect/fda.md) waarin profielen zijn opgeslagen
* Geef profielen handmatig op in de clientconsole, zoals hieronder:

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as “external” deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->
