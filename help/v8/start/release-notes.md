---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 07e0bfdade0356eedb24641259aa754fdb1c6155
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 8%

---

# Laatste versies {#latest-release}

Adobe Campaign wordt regelmatig bijgewerkt. Deze regelmatige frequentie van updates is bedoeld om de nieuwste en beste in uw handen te krijgen, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Adobe raadt alle klanten ten zeerste aan een upgrade uit te voeren naar de nieuwste versie. Deze pagina bevat nieuwe mogelijkheden, verbeteringen en oplossingen die worden geleverd met de nieuwste releases van Campagne v8 (console). Leer meer over de versies en updates van de Campagne in [ deze pagina ](upgrades.md).

Als Beheerde gebruiker van Cloud Servicen, wordt uw instantie bevorderd door Adobe met elke nieuwe versie. Adobe zal contact met u opnemen en uw omgevingen upgraden. De cliëntconsole van de campagne **moet aan de zelfde versie** worden bevorderd zoals de servers van de Campagne. Leer hoe te om uw cliëntconsole in [ te bevorderen deze pagina ](../start/connect.md#upgrade-ac-console).

Bovendien als klant, zorg ervoor dat u de recentste gesteunde versies van de systemen gebruikt die in de [ matrijs van de Verenigbaarheid ](compatibility-matrix.md) worden vermeld.


## Release 8.7.2 {#release-8-7-2}

_sep 3, 2024_

>[!AVAILABILITY]
>
>Deze versie is in **Beperkte Beschikbaarheid** (LA). Het is beperkt tot klanten die **van Adobe Campaign Standard aan Adobe Campaign v8** migreren, en kan niet op een ander milieu worden opgesteld.
>
>Als gebruiker die van het Campaign Standard aan Campagne v8 overgaat, leer meer over deze overgang in [ het document van het Webgebruikersinterface van de Campagne v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration) {target="_blank"}.

### Nieuwe functies {#new-8-7-2}

* **Nieuwe SMS die schakelaar verzenden** - SMS die schakelaar verzenden is gemoderniseerd en verbeterd om de verbindingen van de zendwijzeSMPP toe te laten, blijvende verbindingen toe te laten SMPP, en betere verenigbaarheid voor milieu&#39;s te verzekeren die van Adobe Campaign Standard overgaan. Een nieuwe externe SMS-account is nu beschikbaar voor alle nieuwe SMS-implementaties. De bestaande implementatie wordt nog steeds ondersteund, maar de aanbeveling is om over te stappen op deze nieuwe, moderne en uitgebreide aansluiting. [Meer informatie](../send/sms/sms.md).

* **Rich Push Bericht (GA)** - u kunt rijke dupberichten nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. Met deze versie is een set sjablonen voor uitgebreide pushmeldingen nu beschikbaar voor uw iOS- en Android-apps. [Meer informatie](../send/rich-push-android.md).

* **het Brandmerken** - de Brandende opties zijn nu beschikbaar voor alle kanalen, met inbegrip van SMS en Directe post. [ las meer ](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html) {target="_blank"}


### Oplossingen {#fixes-8-7-2}

De volgende problemen zijn opgelost in deze release:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-770 14, NEO-7795, NEO-78843, NEO-79328.


## Release 8.6.3 {#release-8-6-3}

_woensdag 30 juli 2024_

### Nieuwe functies {#new-8-6-3}

* **Rich Push Bericht** - u kunt rijke dupberichten nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. Met deze versie is een set sjablonen voor uitgebreide pushmeldingen nu beschikbaar voor uw iOS- en Android-apps. [Meer informatie](../send/rich-push-android.md).

* Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. [Meer informatie](release-notes-2024.md#change-8-7-1)

### Algemene verbeteringen {#improvements-8-6-3}

* Om de beveiliging van alle communicatie tussen toepassingen te verbeteren, wordt mTLS nu ondersteund voor externe API-aanroepen.

### Oplossingen {#fixes-8-6-3}

De volgende problemen zijn opgelost in deze release:

NEO-79328, NEO-7843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-725 04, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->
