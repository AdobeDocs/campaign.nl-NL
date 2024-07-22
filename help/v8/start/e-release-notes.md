---
title: Opmerkingen bij de release Vroege campagne v8
description: release van Early Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: dfc86ebaa2acc0b7777843b2d1d370939b6bfcc2
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 8%

---

# Vroege aanvullende informatie {#e-new-release}

Op deze pagina vindt u een beschrijving van de verbeteringen en correcties die zijn opgenomen in de volgende versie van Campagne v8. **de vroege versienota&#39;s hieronder zijn onderworpen aan verandering zonder voorafgaande kennisgeving tot de datum van de versiebeschikbaarheid**. De verbindingen, de schermen en de bijgewerkte documentatie worden gepubliceerd in de [ versienota&#39;s ](release-notes.md), bij de versiedatum.

## Release 8.7.2 {#release-8-7-2}

_woensdag 30 juli 2024_


>[!AVAILABILITY]
>
>Deze versie is in **Beperkte Beschikbaarheid** (LA). Het is beperkt tot klanten die **van Adobe Campaign Standard aan Adobe Campaign v8** migreren, en kan niet op een ander milieu worden opgesteld.
>
>Als gebruiker die van het Campaign Standard aan Campagne v8 overgaat, leer meer over deze overgang in [ het document van het Webgebruikersinterface van de Campagne v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration) {target="_blank"}.

### Nieuwe functies {#new-8-7-2}

* **Nieuwe SMS die schakelaar verzenden** - SMS die schakelaar verzenden is gemoderniseerd en verbeterd om de verbindingen van de zendwijzeSMPP toe te laten, blijvende verbindingen toe te laten SMPP, en betere verenigbaarheid voor milieu&#39;s te verzekeren die van Adobe Campaign Standard overgaan. Een nieuwe externe SMS-account is nu beschikbaar voor alle nieuwe SMS-implementaties. De bestaande implementatie wordt nog steeds ondersteund, maar de aanbeveling is om over te stappen op deze nieuwe, moderne en uitgebreide aansluiting.

* **Rich Push Bericht (GA)** - u kunt rijke dupberichten nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. Met deze versie is een set sjablonen voor uitgebreide pushmeldingen nu beschikbaar voor uw iOS- en Android-apps. [Meer informatie](../send/rich-push.md).

* **het Brandmerken** - de Brandende opties zijn nu beschikbaar voor alle kanalen, met inbegrip van SMS en Directe post. [ las meer ](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html) {target="_blank"}


### Oplossingen {#fixes-8-7-2}

De volgende problemen zijn opgelost in deze release:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-760 39, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-7663, NEO-73602, NEO-72915, NEO-7 8134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-76926, NEO-76495, NEO-77168, O-41058, NEO-75581, NEO-74647, NEO-74585, NEO-74586, NEO-74831, NEO-77319, NEO-786 7.

## Release 8.6.3 {#release-8-6-3}

_woensdag 30 juli 2024_


### Nieuwe functies {#new-8-6-3}

* **Rich Push Bericht** - u kunt rijke dupberichten nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. Met deze versie is een set sjablonen voor uitgebreide pushmeldingen nu beschikbaar voor uw iOS- en Android-apps. [Meer informatie](../send/rich-push.md).

* Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. [Meer informatie](release-notes.md#change-8-7-1)


### Algemene verbeteringen {#improvements-8-6-3}

* Om de beveiliging van alle communicatie tussen toepassingen te verbeteren, wordt mTLS nu ondersteund voor externe API-aanroepen.

### Oplossingen {#fixes-8-6-3}

De volgende problemen zijn opgelost in deze release:

NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-631 97, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->