---
title: Werken met doelgroepen in campagne
description: Werken met doelgroepen in campagne
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 16%

---

# Werken met doelgroepen in campagne{#gs-ac-audiences}

Profielen zijn contactpersonen die zijn opgeslagen in de Campagne-database.

In Adobe Campaign: **ontvangers** Dit zijn de standaardprofielen die worden gebruikt voor het verzenden van leveringen (e-mails, SMS, enz.). De ontvangende gegevens die in het gegevensbestand worden opgeslagen laten u toe om het doel te filtreren dat om het even welke bepaalde levering zal ontvangen en verpersoonlijkingsgegevens in uw leveringsinhoud toe te voegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.

Leer hoe u profielen en soorten publiek kunt importeren, bijwerken en beheren [in deze sectie](../audiences/gs-audiences.md).

## Lijsten maken{#create-lists}

Een lijst is een statische reeks contacten die in leveringsacties kunnen worden gericht of tijdens de invoer of een andere werkschemaactie worden bijgewerkt. Bijvoorbeeld, kan een populatie die uit het gegevensbestand via een vraag wordt gehaald als lijst worden opgeslagen.

![](../assets/do-not-localize/glass.png) Leer hoe u lijsten maakt en beheert in [deze pagina](../audiences/create-audiences.md).

## De database filteren{#filter-the-database}

Met de filterconfiguratie kunt u gegevens uit een lijst selecteren **[!UICONTROL dynamically]**: wanneer de gegevens worden gewijzigd, worden de gefilterde gegevens bijgewerkt. U kunt uw eigen filters maken of de ingebouwde filters gebruiken om een doelgroep te definiëren.

![](../assets/do-not-localize/glass.png) Leer hoe u filters kunt maken en beheren in [deze pagina](../audiences/create-filters.md).

## Een publiek maken in een workflow

Het richten kan door een combinatie vragen in een grafische opeenvolging in een werkschema worden gecreeerd. U kunt een publiek maken dat afhankelijk van uw vereisten als doelgroep wordt gebruikt. Klik op de knop **[!UICONTROL Targeting and workflows]** in het campagnedashboard.

Leer hoe u een publiek kunt maken in een campagneworkflow in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)


## Actieve profielen{#active-profiles}

Volgens uw contract wordt elk van uw campagneexemplaren voorzien van een specifiek aantal actieve profielen die voor factureringsdoeleinden worden geteld. Raadpleeg uw meest recente contract voor informatie over het aantal aangeschafte actieve profielen.

**Profiel** een informatiedossier (bv.: een record in het [Ontvangertabel](../dev/datamodel.md) of een externe tabel met een cookie-id, een klant-id, een mobiele id of andere informatie die relevant is voor een bepaald kanaal) die een eindklant, perspectief of lead vertegenwoordigt. Profielen worden als actief beschouwd als ze in de afgelopen twaalf maanden via een kanaal zijn aangewezen of meegedeeld.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

## Privacy en toestemming{#privacy-and-consent}

Adobe Campaign is een krachtig instrument voor het verzamelen en verwerken van grote hoeveelheden gegevens, waaronder persoonlijke informatie en gevoelige gegevens. Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en gevoelige informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

![](../assets/do-not-localize/book.png) Leer hoe u privacy en toestemming beheert in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target=&quot;_blank&quot;}.

**Verwante onderwerpen**

* [Een specifieke workflow voor een campagne ontwerpen en uitvoeren](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html)

* [Leer hoe u het publiek van een campagne kunt selecteren](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)

* [Aan de slag met workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)
