---
title: Werken met doelgroepen in campagne
description: Werken met doelgroepen in campagne
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: ad96c126836981f861c246eafa2ec7d2c0e179dc
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 17%

---

# Werken met doelgroepen in campagne{#gs-ac-audiences}

Profielen zijn contactpersonen die zijn opgeslagen in de Campagne-database.

In Adobe Campaign, **ontvangers** zijn de standaardprofielen die voor het verzenden van leveringen (e-mail, SMS, enz.) worden gericht. De ontvangende gegevens die in het gegevensbestand worden opgeslagen laten u toe om het doel te filtreren dat om het even welke bepaalde levering zal ontvangen en verpersoonlijkingsgegevens in uw leveringsinhoud toe te voegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.

Leer om profielen en publiek [ in deze sectie ](../audiences/gs-audiences.md) in te voeren bij te werken en te beheren.

## Lijsten maken{#create-lists}

Een lijst is een statische reeks contacten die in leveringsacties kunnen worden gericht of tijdens de invoer of een andere werkschemaactie worden bijgewerkt. Bijvoorbeeld, kan een populatie die uit het gegevensbestand via een vraag wordt gehaald als lijst worden opgeslagen.

Leer om lijsten in [ tot stand te brengen en te beheren deze pagina ](../audiences/create-audiences.md).

## De database filteren{#filter-the-database}

Met de filterconfiguratie kunt u gegevens in een lijst selecteren **[!UICONTROL dynamically]** : wanneer de gegevens worden gewijzigd, worden de gefilterde gegevens bijgewerkt. U kunt uw eigen filters maken of de ingebouwde filters gebruiken om een doelgroep te definiëren.

Leer hoe te om filters in [ tot stand te brengen en te beheren deze pagina ](../audiences/create-filters.md).

## Een publiek maken in een workflow

Het richten kan door een combinatie vragen in een grafische opeenvolging in een werkschema worden gecreeerd. U kunt een publiek maken dat afhankelijk van uw vereisten als doelgroep wordt gebruikt. Als u de werkstroomeditor wilt weergeven, klikt u op het tabblad **[!UICONTROL Targeting and workflows]** in het campagnedashboard.

Leer hoe te om een publiek in een campagnewerkschema in [ te bouwen deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=nl-NL){target="_blank"} .


## Actieve profielen {#active-profiles}

Een actief profiel is een profiel waarmee de klant de afgelopen twaalf maanden via een willekeurig kanaal heeft geprobeerd te communiceren.

Volgens uw contract worden al uw Campaign-instanties ingericht met een specifieke hoeveelheid actieve profielen die voor factureringsdoeleinden worden geteld. Raadpleeg het meest recente contract voor informatie over het aantal aangeschafte actieve profielen. Leer meer in [ het productbeschrijving van Adobe Campaign ](https://helpx.adobe.com/nl/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"} .

U kunt het aantal actieve profielen op uw instantie direct van het Controlebord van de Campagne controleren. Voor meer op dit, verwijs naar de [ documentatie van het Controlebord ](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=nl-NL){target="_blank"} .


De volgende instructies en beperkingen zijn van toepassing:

* Een profiel dat voor meerdere leveringen is bedoeld, wordt slechts eenmaal geteld.
* Profielen die in het kader van de sociale marketing op X (Twitter) zijn geselecteerd, worden niet in aanmerking genomen als actieve profielen.
* De telling is gebaseerd op de ontvankelijke primaire sleutel. Als een profiel aanwezig is in twee verschillende tabellen voor ontvangers, kan het daarom twee keer worden geteld als een actief profiel.

## Privacy en toestemming{#privacy-and-consent}

Adobe Campaign is een krachtig instrument voor het verzamelen en verwerken van grote hoeveelheden gegevens, waaronder persoonlijke informatie en gevoelige gegevens. Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en gevoelige informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

Leer hoe te om privacy en toestemming in [ Adobe Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=nl-NL){target="_blank"} te beheren .

