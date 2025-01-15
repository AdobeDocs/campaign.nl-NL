---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d4b172bc6b874d542dc9f2725e3bc35679fc7635
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 3%

---

# Laatste versies {#latest-release}

Deze pagina bevat nieuwe mogelijkheden, verbeteringen en oplossingen die worden geleverd met de nieuwste releases van Campagne v8 (console). Leer meer over de versies, versies, en verbeteringen van de Campagne in [ deze pagina ](upgrades.md).

## Release 8.6.4 {#release-8-6-4}

_jan 15, 2025_


### Algemene verbeteringen {#improvements-8-6-4}

* De stabiliteit van de toepassing van de campagne is verbeterd tijdens leveringsanalyse in de context van een [ plaatsing van de Onderneming (FFDA) ](../../v8/architecture/enterprise-deployment.md).
* Deze release wordt geleverd met verbeterde en verbeterde FFDA-architectuurmechanismen, waaronder sleutelbeheer, staging en gegevensreplicatie.
* De nieuwe technische werkschema&#39;s zijn geïntroduceerd voor de [ plaatsing van de Onderneming (FFDA) ](../../v8/architecture/enterprise-deployment.md). Deze werkschema&#39;s repliceren levering en verwante gegevens door parallelle replicatieverzoeken op overeenkomstige lijsten te centraliseren. Deze workflow begint met `Replicate nms` .
* Een nieuwe **laat controleur van de controlehond toe om werkschema te houden dat permanent** optie loopt is nu beschikbaar in de werkschemaeigenschappen. Als deze optie is ingeschakeld, worden workflows na een fout automatisch opnieuw gestart. Het opnieuw beginnen gebeurt door gebrek om de 30 seconden. Als u dit interval wilt aanpassen, maakt u een nieuwe optie `XtkWorkflow_WatchdogTimerTimeout` en stelt u een gegevenstype Geheel getal in om de nieuwe vertraging op te geven. Deze optie moet alleen worden ingeschakeld in technische workflows.

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