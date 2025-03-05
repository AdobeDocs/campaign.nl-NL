---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 15faa6850c035d2d26dd43dc221e0128c33999c2
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 2%

---

# Laatste versies {#latest-release}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met Campagne v8 (console) **** komen meest recente versies. Leer meer over de versies, versies, en verbeteringen van de Campagne in [ deze pagina ](upgrades.md). Andere versies worden vermeld in de sectie Vorige releases van deze documentatie.

>[!BEGINSHADEBOX]

**In deze pagina**

* Campagne v8.6 - [ Versie 8.6.4 ](#release-8-6-4)
* Campagne v8.7 - [ Versie 8.7.3 ](#release-8-7-3)

>[!ENDSHADEBOX]


## Release 8.7.3 {#release-8-7-3}

_feb 14, 2025_

>[!AVAILABILITY]
>
>Deze versie is in **Beperkte Beschikbaarheid** (LA). Het is beperkt tot klanten die **van Adobe Campaign Standard aan Adobe Campaign v8** migreren, en kan niet op een ander milieu worden opgesteld.
>
>Als gebruiker die van Campaign Standard aan Campagne v8 overgaat, leer meer over deze overgang in [ het document van het Webgebruikersinterface van de Campagne v8 ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration) {target="_blank"}.

### Nieuwe functies {#features-8-7-3}

* **Dynamische Rapportering voor Transactionele berichten** - u kunt uw transactionele berichten in het Dynamische het gebruikersinterface van de Rapportering nu controleren. Deze rapporten verstrekken de capaciteit aan de teler om alle het melden metriek en dimensies van transactionele berichten, uitsplitsing van leveringen te bekijken die door een malplaatje in real time worden verzonden. [ las meer ](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting) {target="_blank"}

* **Transactionele overseinenREST APIs** - Op gebeurtenis-gebaseerde Transactionele APIs is nu beschikbaar voor E-mail. [ las meer ](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages) {target="_blank"}

### Oplossingen {#fixes-8-7-3}

De volgende problemen zijn opgelost in deze release:

NEO-79373, NEO-81908, NEO-83081.


## Release 8.6.4 {#release-8-6-4}

_jan 15, 2025_

### Algemene verbeteringen {#improvements-8-6-4}

* De stabiliteit van de toepassing van de campagne is verbeterd tijdens leveringsanalyse in de context van een [ plaatsing van de Onderneming (FFDA) ](../../v8/architecture/enterprise-deployment.md).
* Deze release wordt geleverd met verbeterde en verbeterde FFDA-architectuurmechanismen, waaronder sleutelbeheer, staging en gegevensreplicatie.
* De nieuwe technische werkschema&#39;s zijn geïntroduceerd voor de [ plaatsing van de Onderneming (FFDA) ](../../v8/architecture/enterprise-deployment.md). Deze werkschema&#39;s repliceren levering en verwante gegevens door parallelle replicatieverzoeken op overeenkomstige lijsten te centraliseren. Deze workflow begint met `Replicate nms` . [Meer informatie](../architecture/replication.md)
* Een nieuwe **laat controleur van de controlehond toe om werkschema te houden dat permanent** optie loopt is nu beschikbaar in de werkschemaeigenschappen. Als deze optie is ingeschakeld, worden workflows na een fout automatisch opnieuw gestart. Het opnieuw opstarten gebeurt standaard elke 30 seconden als de werkstroom nog steeds een fout vertoont. Als u dit interval wilt aanpassen, maakt u een nieuwe optie `XtkWorkflow_WatchdogTimerTimeout` en stelt u een gegevenstype Geheel getal in om de nieuwe vertraging op te geven. Deze optie moet alleen worden ingeschakeld in technische workflows. [Meer informatie](../../automation/workflow/workflow-properties.md#execution)

### Beveiligingsverbeteringen {#security-8-6-4}

De verbinding met Adobe-oplossingen en -toepassingen via de externe account van **[!UICONTROL Adobe Experience Cloud]** is bijgewerkt om de beveiliging te verbeteren.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Compatibiliteitsupdates {#comp-8-6-4}

* Databases worden nu ondersteund als externe database met FDA (Adobe Campaign Federated Data Access). Meer informatie vindt u [op deze pagina](compatibility-matrix.md#FederatedDataAccessFDA).

* Er is nu een nieuwe Amazon Redshift FDA ODBC-connector beschikbaar. Het biedt verbeterde connectiviteit, gemakkelijker onderhoud en verbeterde compatibiliteit. Deze nieuwe versie brengt de volgende verbeteringen aan:

   * De nieuwe schakelaar is gebaseerd op de interface ODBC die zich op onze meest recente schakelaars FDA richt. Dit zorgt voor langdurige ondersteuning.
   * Het introduceert ook een nieuw mechanisme voor het laden van gegevens gebruikend s3 emmers, beduidend verbeterend prestaties.
   * Ondersteuning voor opnieuw verschuiven van spectrum is toegevoegd.

  De oudere schakelaar kan nog worden gebruikt. Neem contact op met uw Adobe-vertegenwoordiger als u de nieuwe versie wilt uitproberen.

### Oplossingen {#fixes-8-6-4}

De volgende problemen zijn opgelost in deze release:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-769 77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-80314 1127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, O-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-826 NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

