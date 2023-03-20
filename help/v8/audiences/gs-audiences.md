---
title: Aan de slag met profielen en doelgroepen in campagne
description: Leer profielen en publiek maken en beheren in Campagne
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 11%

---

# Aan de slag met profielen en doelgroepen{#gs-profiles-and-audiences}

Profielen zijn contacten die in het gegevensbestand van de Campagne, zoals klanten, abonnees aan de dienst of vooruitzichten worden opgeslagen. Er zijn vele mogelijke mechanismen om profielen te verwerven en dit gegevensbestand op te bouwen: online verzameling via webformulieren, handmatige of automatische import van tekstbestanden, replicatie met bedrijfsdatabases of andere informatiesystemen. Met Adobe Campaign kunt u de marketinggeschiedenis, aankoopgegevens, voorkeuren, CRM-gegevens en alle relevante PI-gegevens in een geconsolideerde weergave opnemen om te analyseren en actie te ondernemen. Profielen bevatten alle informatie die vereist is voor het toewijzen van doelen, kwalificeren en volgen van personen.



Een profiel is een record in het dialoogvenster **nmsRecipient** een tabel of een externe tabel waarin alle profielkenmerken zijn opgeslagen, zoals voornaam, achternaam, e-mailadres, een cookie-id, de klant-id, de mobiele id of andere informatie die relevant is voor een bepaald kanaal. Andere lijsten verbonden aan de ontvankelijke lijst bevatten op profiel betrekking hebbende gegevens, bijvoorbeeld de lijst van leveringslogboeken die verslagen van alle leveringen bevat die naar ontvangers worden verzonden. Meer informatie over ingebouwde profielen en tabellen voor ontvangers vindt u in [deze sectie](../dev/datamodel.md#ootb-profiles).

![](assets/recipients-in-explorer.png)

In Adobe Campaign: **ontvangers** Dit zijn de standaardprofielen die worden gebruikt voor het verzenden van leveringen (e-mails, SMS, enz.).

De ontvangende gegevens die in het gegevensbestand worden opgeslagen laten u toe om het doel te filtreren dat om het even welke bepaalde levering zal ontvangen en verpersoonlijkingsgegevens in uw leveringsinhoud toe te voegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.

Als u Adobe Campaign wilt vullen met profielgegevens, kunt u:

* [gegevensbestanden importeren](../start/import.md) van een externe gegevensbron zoals een CRM-systeem of een plat bestand
* [webformulieren maken](../dev/webapps.md) om klanten toe te staan om hun eigen informatie in te gaan en hun eigen profiel tot stand te brengen
* [toewijzen aan een externe database](../connect/fda.md) waarin profielen zijn opgeslagen
* Geef profielen handmatig op in de clientconsole, zoals hieronder:

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as “external” deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->

Nadat u de berichten hebt geïmporteerd, kunt u een publiek maken dat deze verzendt. Leer hoe u een publiek kunt maken [in deze sectie](create-audiences.md).