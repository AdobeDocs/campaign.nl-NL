---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: b83222774b026348ae70f41a8193f88856af99a9
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 2%

---

# Laatste versies {#latest-release}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met Campagne v8 (console) **** komen meest recente versies. Leer meer over de versies, versies, en verbeteringen van de Campagne in [ deze pagina ](upgrades.md). Andere versies worden vermeld in de sectie Vorige releases van deze documentatie.

## Release 8.6.4 {#release-8-6-4}

_jan 15, 2025_

### Algemene verbeteringen {#improvements-8-6-4}

* De stabiliteit van de toepassing van de campagne is verbeterd tijdens leveringsanalyse in de context van een [ plaatsing van de Onderneming (FFDA) ](../../v8/architecture/enterprise-deployment.md).
* Deze release wordt geleverd met verbeterde en verbeterde FFDA-architectuurmechanismen, waaronder sleutelbeheer, staging en gegevensreplicatie.
* De nieuwe technische werkschema&#39;s zijn geïntroduceerd voor de [ plaatsing van de Onderneming (FFDA) ](../../v8/architecture/enterprise-deployment.md). Deze werkschema&#39;s repliceren levering en verwante gegevens door parallelle replicatieverzoeken op overeenkomstige lijsten te centraliseren. Deze workflow begint met `Replicate nms` .
* Een nieuwe **laat controleur van de controlehond toe om werkschema te houden dat permanent** optie loopt is nu beschikbaar in de werkschemaeigenschappen. Als deze optie is ingeschakeld, worden workflows na een fout automatisch opnieuw gestart. Het opnieuw opstarten gebeurt standaard elke 30 seconden als de werkstroom nog steeds een fout vertoont. Als u dit interval wilt aanpassen, maakt u een nieuwe optie `XtkWorkflow_WatchdogTimerTimeout` en stelt u een gegevenstype Geheel getal in om de nieuwe vertraging op te geven. Deze optie moet alleen worden ingeschakeld in technische workflows. [Meer informatie](../../automation/workflow/workflow-properties.md#execution)

### Beveiligingsverbeteringen {#security-8-6-4}

De verbinding met oplossingen en toepassingen voor Adoben via de externe account van **[!UICONTROL Adobe Experience Cloud]** is bijgewerkt om de beveiliging te verbeteren.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Compatibiliteitsupdates {#comp-8-6-4}

Databases worden nu ondersteund als externe database met FDA (Adobe Campaign Federated Data Access). Meer informatie vindt u [op deze pagina](compatibility-matrix.md#FederatedDataAccessFDA).

### Oplossingen {#fixes-8-6-4}

De volgende problemen zijn opgelost in deze release:

NEO-77452, NEO-81127, NEO-81209, NEO-80243, NEO-80314, NEO-81223, NEO-81287, NEO-812 90, NEO-81312, NEO-81512, NEO-81520, NEO-8156, NEO-81704, NEO-83096, NEO-83081.

## Release 8.7.2 {#release-8-7-2}

_sep 3, 2024_

>[!AVAILABILITY]
>
>Deze versie is in **Beperkte Beschikbaarheid** (LA). Het is beperkt tot klanten die **van Adobe Campaign Standard aan Adobe Campaign v8** migreren, en kan niet op een ander milieu worden opgesteld.
>
>Als gebruiker die van het Campaign Standard aan Campagne v8 overgaat, leer meer over deze overgang in [ het document van het Webgebruikersinterface van de Campagne v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration) {target="_blank"}.

### Nieuwe functies {#new-8-7-2}

* **Nieuwe SMS die schakelaar verzenden** - SMS die schakelaar verzenden is gemoderniseerd en verbeterd om de verbindingen van de zendwijzeSMPP toe te laten, blijvende verbindingen toe te laten SMPP, en betere verenigbaarheid voor milieu&#39;s te verzekeren die van Adobe Campaign Standard overgaan. Een nieuwe externe SMS-account is nu beschikbaar voor alle nieuwe SMS-implementaties. De bestaande implementatie wordt nog steeds ondersteund, maar de aanbeveling is om over te stappen op deze nieuwe, moderne en uitgebreide aansluiting. [Meer informatie](../send/sms/sms.md).

* **Rich Push Bericht (GA)** - u kunt rijke dupberichten nu verzenden. Een veeleisende pushmelding is een verbeterde vorm van mobiele meldingen die verder gaat dan eenvoudige tekstberichten door het opnemen van multimedia-elementen, zoals afbeeldingen, interactieve knoppen of andere rijke media-inhoud. Met deze versie is een set sjablonen voor uitgebreide pushmeldingen nu beschikbaar voor uw iOS- en Android-apps. [Meer informatie](../send/rich-push-android.md).

* **het Brandmerken** - de Brandende opties zijn nu beschikbaar voor alle kanalen, met inbegrip van SMS en Directe post. [ las meer ](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html) {target="_blank"}

### Oplossingen {#fixes-8-7-2}

De volgende problemen zijn opgelost in deze release:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-770 14, NEO-7795, NEO-78843, NEO-79328.