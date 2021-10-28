---
title: Aan de slag met het publiek
description: Aan de slag met het publiek
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 889400a238f32968464f1425bb7d6c2dc3ff3cd0
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 19%

---

# Aan de slag met het publiek{#gs-ac-audiences}

## Werken met profielen{#gs-ac-profiles}

Profielen zijn contactpersonen die zijn opgeslagen in de Campagne-database, waaronder klanten, abonnees en vooruitzichten. Er zijn vele mogelijke mechanismen om profielen te verwerven en deze database op te bouwen: online verzameling via webformulieren, handmatig of automatisch importeren van tekstbestanden, replicatie met bedrijfsdatabases of andere informatiesystemen. Met Adobe Campaign kunt u de marketinggeschiedenis, aankoopgegevens, voorkeuren, CRM-gegevens en alle relevante PI-gegevens in een geconsolideerde weergave opnemen om te analyseren en actie te ondernemen. Profielen bevatten alle informatie die vereist is voor het toewijzen van doelen, kwalificeren en volgen van personen.

Een profiel is een record in het dialoogvenster **nmsRecipient** een tabel of een externe tabel waarin alle profielkenmerken zijn opgeslagen, zoals voornaam, achternaam, e-mailadres, een cookie-id, de klant-id, de mobiele id of andere informatie die relevant is voor een bepaald kanaal. Andere lijsten verbonden aan de ontvankelijke lijst bevatten op profiel betrekking hebbende gegevens, bijvoorbeeld de lijst van leveringslogboeken die verslagen van alle leveringen bevat die naar ontvangers worden verzonden. Meer informatie over ingebouwde profielen en tabellen voor ontvangers vindt u in [deze sectie](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign: **ontvangers** Dit zijn de standaardprofielen die worden gebruikt voor het verzenden van leveringen (e-mails, SMS, enz.). De ontvangende gegevens die in het gegevensbestand worden opgeslagen laten u toe om het doel te filtreren dat om het even welke bepaalde levering zal ontvangen en verpersoonlijkingsgegevens in uw leveringsinhoud toe te voegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.

Profielen kunnen worden gegroepeerd in lijsten of worden verzameld door een query uit te voeren op de database.

Als u campagne wilt vullen met profielgegevens, kunt u:

* [gegevensbestanden importeren](import.md) van een externe gegevensbron zoals een CRM-systeem
* [webformulieren maken](../dev/webapps.md) om klanten toe te staan om hun eigen informatie in te gaan en hun eigen profiel tot stand te brengen
* [toewijzen aan een externe database](../connect/fda.md) waarin profielen zijn opgeslagen
* voer profielen handmatig in met behulp van de clientconsole, zoals hieronder:

![](assets/create-profile.png)

![](../assets/do-not-localize/book.png) Leer hoe u profielen beheert in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html){target=&quot;_blank&quot;}.


## Privacy en toestemming

Adobe Campaign is een krachtig instrument voor het verzamelen en verwerken van grote hoeveelheden gegevens, waaronder persoonlijke informatie en gevoelige gegevens. Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en gevoelige informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

![](../assets/do-not-localize/book.png) Leer hoe u privacy en toestemming beheert in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target=&quot;_blank&quot;}.

## Lijsten maken

Een lijst is een statische set profielen die kan worden gebruikt voor leveringsacties of die kan worden bijgewerkt tijdens importbewerkingen of tijdens workflowuitvoering. Een populatie die via een query uit de database is geëxtraheerd, kan bijvoorbeeld een lijst leveren.

![](../assets/do-not-localize/book.png) Leer hoe u lijsten maakt en beheert in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html){target=&quot;_blank&quot;}.

## De database opvragen

Gebruik de **Query** activiteit in een werkschema om uw gegevensbestand te vragen, gegevens te segmenteren en complex publiek te bouwen.

![](../assets/do-not-localize/book.png) Meer informatie over Campagne-query&#39;s vindt u in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html){target=&quot;_blank&quot;}.

![](../assets/do-not-localize/book.png) Alle gerichte activiteiten worden vermeld in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target=&quot;_blank&quot;}.

## Een publiek maken in een workflow

Het richten kan door een combinatie vragen in een grafische opeenvolging in een werkschema worden gecreeerd. U kunt een publiek maken dat afhankelijk van uw vereisten als doelgroep wordt gebruikt. Klik op de knop **[!UICONTROL Targeting and workflows]** in het campagnedashboard.

![](../assets/do-not-localize/book.png) Leer hoe u een publiek kunt maken in een campagneworkflow in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}.


## Actieve profielen{#active-profiles}

Volgens uw contract worden al uw Campaign-instanties ingericht met een specifieke hoeveelheid actieve profielen die voor factureringsdoeleinden worden geteld. Raadpleeg uw meest recente contract voor informatie over het aantal aangeschafte actieve profielen.

**Profiel** een informatiedossier (bv.: een record in het [Ontvangertabel](../dev/datamodel.md) of een externe tabel met een cookie-id, een klant-id, een mobiele id of andere informatie die relevant is voor een bepaald kanaal) die een eindklant, perspectief of lead vertegenwoordigt. Profielen worden als actief beschouwd als ze in de afgelopen twaalf maanden via een kanaal zijn aangewezen of meegedeeld.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->


**Verwante onderwerpen** in Campaign Classic v7-documentatie:

* [Een specifieke workflow voor een campagne ontwerpen en uitvoeren](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target=&quot;_blank&quot;}

* [Leer hoe u het publiek van een campagne kunt selecteren](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target=&quot;_blank&quot;}

* [Aan de slag met workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target=&quot;_blank&quot;}
