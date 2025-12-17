---
title: Aan de slag met profielen en doelgroepen in campagne
description: Leer profielen en publiek maken en beheren in Campagne
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
version: Campaign v8, Campaign Classic v7
source-git-commit: 050612f6d7ab20aed5880454eec9cfc6e5fc18c2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 11%

---

# Aan de slag met profielen en doelgroepen{#gs-profiles-and-audiences}

Profielen zijn contacten die in het gegevensbestand van de Campagne, zoals klanten, abonnees aan de dienst of vooruitzichten worden opgeslagen. Er zijn vele mogelijke mechanismen om profielen te verwerven en dit gegevensbestand op te bouwen: online inzameling via Webvormen, handmatige, of automatische invoer van tekstdossiers, replicatie met bedrijfgegevensbestanden of andere informatiesystemen. Met Adobe Campaign kunt u de marketinggeschiedenis, aankoopgegevens, voorkeuren, CRM-gegevens en alle relevante PI-gegevens in een geconsolideerde weergave opnemen om te analyseren en actie te ondernemen. Profielen bevatten alle informatie die vereist is voor het toewijzen van doelen, kwalificeren en volgen van personen.

Een profiel is een verslag in de **nmsRecipient** lijst of een externe lijst die alle profielattributen, zoals voornaam, familienaam, e-mailadres, een koekjesidentiteitskaart, identiteitskaart van de Klant, mobiele herkenningsteken of andere informatie relevant voor een bepaald kanaal opslaat. Andere lijsten verbonden aan de ontvankelijke lijst bevatten op profiel betrekking hebbende gegevens, bijvoorbeeld de lijst van leveringslogboeken die verslagen van alle leveringen bevat die naar ontvangers worden verzonden. Leer meer over ingebouwde profielen en ontvankelijke lijsten in [&#x200B; deze sectie &#x200B;](../dev/datamodel.md#ootb-profiles).

![](assets/recipients-in-explorer.png)

In Adobe Campaign, **ontvangers** zijn de standaardprofielen die voor het verzenden van leveringen (e-mail, SMS, enz.) worden gericht.

De ontvangende gegevens die in het gegevensbestand worden opgeslagen laten u toe om het doel te filtreren dat om het even welke bepaalde levering zal ontvangen en verpersoonlijkingsgegevens in uw leveringsinhoud toe te voegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.

Als u Adobe Campaign wilt vullen met profielgegevens, kunt u:

* [&#x200B; de dossiers van de de invoergegevens &#x200B;](../start/import.md) van een externe gegevensbron zoals een systeem van CRM, of een plat dossier
* [&#x200B; creeer Webvormen &#x200B;](../dev/webapps.md) om klanten toe te staan om hun eigen informatie in te gaan en hun eigen profiel te creëren
* [&#x200B; kaart aan een extern gegevensbestand &#x200B;](../connect/fda.md) waar de profielen worden opgeslagen
* Geef profielen handmatig op in de clientconsole, zoals hieronder:

![](assets/create-profile.png)

Nadat u de berichten hebt geïmporteerd, kunt u een publiek maken dat deze verzendt. Leer hoe te om publiek [&#x200B; in deze sectie &#x200B;](create-audiences.md) tot stand te brengen.