---
title: Aan de slag met het publiek
description: Aan de slag met het publiek
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 19%

---

# Aan de slag met het publiek{#gs-ac-audiences}

## Werken met profielen{#gs-ac-profiles}

Profielen zijn contactpersonen die zijn opgeslagen in de Campagne-database, waaronder klanten, abonnees en vooruitzichten. Er zijn vele mogelijke mechanismen om profielen te verwerven en deze database op te bouwen: online verzameling via webformulieren, handmatig of automatisch importeren van tekstbestanden, replicatie met bedrijfsdatabases of andere informatiesystemen. Met Adobe Campaign kunt u de marketinggeschiedenis, aankoopgegevens, voorkeuren, CRM-gegevens en alle relevante PI-gegevens in een geconsolideerde weergave opnemen om te analyseren en actie te ondernemen. Profielen bevatten alle informatie die vereist is voor het toewijzen van doelen, kwalificeren en volgen van personen.

Een profiel is een record in de tabel **nmsRecipient** of een externe tabel waarin alle profielkenmerken zijn opgeslagen, zoals voornaam, achternaam, e-mailadres, een cookie-id, de klant-id, de mobiele id of andere informatie die relevant is voor een bepaald kanaal. Andere lijsten verbonden aan de ontvankelijke lijst bevatten op profiel betrekking hebbende gegevens, bijvoorbeeld de lijst van leveringslogboeken die verslagen van alle leveringen bevat die naar ontvangers worden verzonden. Meer informatie over ingebouwde profielen en ontvankelijke lijsten in [deze sectie](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign zijn **ontvangers** de standaardprofielen voor het verzenden van leveringen (e-mails, SMS, enz.). De ontvangende gegevens die in het gegevensbestand worden opgeslagen laten u toe om het doel te filtreren dat om het even welke bepaalde levering zal ontvangen en verpersoonlijkingsgegevens in uw leveringsinhoud toe te voegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.

Profielen kunnen worden gegroepeerd in lijsten of worden verzameld door een query uit te voeren op de database.


Als u campagne wilt vullen met profielgegevens, kunt u:

* [gegevensbestanden importeren ](import.md) uit een externe gegevensbron, zoals een CRM-systeem
* [webformulieren maken waarmee klanten hun eigen gegevens kunnen invoeren en hun eigen profiel kunnen maken ](../dev/webapps.md) 
* [toewijzen aan een externe ](../connect/fda.md) database waar profielen worden opgeslagen
* voer profielen handmatig in met behulp van de clientconsole, zoals hieronder:

![](assets/create-profile.png)


↗️ Leer hoe te om profielen in [Adobe Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html){target=&quot;_blank&quot;} te beheren.


## Privacy en toestemming

Adobe Campaign is een krachtig instrument voor het verzamelen en verwerken van grote hoeveelheden gegevens, waaronder persoonlijke informatie en gevoelige gegevens. Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en gevoelige informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

↗️ Leer hoe te om privacy en toestemming in [Adobe Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target=&quot;_blank&quot;} te beheren.

## Lijsten maken

Een lijst is een statische set profielen die kan worden gebruikt voor leveringsacties of die kan worden bijgewerkt tijdens importbewerkingen of tijdens workflowuitvoering. Een populatie die via een query uit de database is geëxtraheerd, kan bijvoorbeeld een lijst leveren.

↗️ Leer hoe te om lijsten in [Adobe Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html){target= &quot;_blank&quot;} tot stand te brengen en te beheren.

## De database opvragen

Gebruik **Query** activiteit in een werkschema om uw gegevensbestand te vragen, gegevens te segmenteren en complexe publiek te bouwen.

↗️ meer over de vragen van de Campagne in [Adobe Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html){target=&quot;_blank&quot;}.

↗️ Alle gerichte activiteiten worden vermeld in [Adobe Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target=&quot;_blank&quot;}.

## Een publiek maken in een workflow

Het richten kan door een combinatie vragen in een grafische opeenvolging in een werkschema worden gecreeerd. U kunt een publiek maken dat afhankelijk van uw vereisten als doelgroep wordt gebruikt. Als u de werkstroomeditor wilt weergeven, klikt u op het tabblad **[!UICONTROL Targeting and workflows]** in het campagnedashboard.

↗️ Leer hoe te om een publiek in een campagnewerkschema in [Adobe Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;} te bouwen.


## Actieve profielen{#active-profiles}

Volgens uw contract worden al uw Campaign-instanties ingericht met een specifieke hoeveelheid actieve profielen die voor factureringsdoeleinden worden geteld. Raadpleeg uw meest recente contract voor informatie over het aantal aangeschafte actieve profielen.

**** Profilemedewerkers houden een register van informatie bij (bijv.: een record in de  [tabel ](../dev/datamodel.md) Ontvanger of een externe tabel met een cookie-id, de id van de klant, de mobiele id of andere informatie die relevant is voor een bepaald kanaal) die een eindklant, perspectief of lead vertegenwoordigt. Profielen worden als actief beschouwd als ze in de afgelopen twaalf maanden via een kanaal zijn aangewezen of meegedeeld.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

↗️ For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**Verwante** onderwerpen in Campaign Classic v7 documentatie:

↗️ [Een campagespecifieke workflow ontwerpen en uitvoeren](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target=&quot;_blank&quot;}

↗️ [Leer hoe te om het publiek van een campagne te selecteren](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target=&quot;_blank&quot;}

↗️ [Aan de slag met workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target=&quot;_blank&quot;}
