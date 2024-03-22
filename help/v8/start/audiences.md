---
title: Werken met doelgroepen in campagne
description: Werken met doelgroepen in campagne
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 14%

---

# Werken met doelgroepen in campagne{#gs-ac-audiences}

Profielen zijn contactpersonen die zijn opgeslagen in de Campagne-database.

In Adobe Campaign: **ontvangers** Dit zijn de standaardprofielen die worden gebruikt voor het verzenden van leveringen (e-mails, SMS, enz.). De ontvangende gegevens die in het gegevensbestand worden opgeslagen laten u toe om het doel te filtreren dat om het even welke bepaalde levering zal ontvangen en verpersoonlijkingsgegevens in uw leveringsinhoud toe te voegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.

Leer profielen en publiek importeren, bijwerken en beheren [in deze sectie](../audiences/gs-audiences.md).

## Lijsten maken{#create-lists}

Een lijst is een statische reeks contacten die in leveringsacties kunnen worden gericht of tijdens de invoer of een andere werkschemaactie worden bijgewerkt. Bijvoorbeeld, kan een populatie die uit het gegevensbestand via een vraag wordt gehaald als lijst worden opgeslagen.

Leer hoe u lijsten maakt en beheert in [deze pagina](../audiences/create-audiences.md).

## De database filteren{#filter-the-database}

Met de filterconfiguratie kunt u gegevens uit een lijst selecteren **[!UICONTROL dynamically]**: Wanneer de gegevens worden gewijzigd, worden de gefilterde gegevens bijgewerkt. U kunt uw eigen filters maken of de ingebouwde filters gebruiken om een doelgroep te definiëren.

Leer hoe u filters kunt maken en beheren in [deze pagina](../audiences/create-filters.md).

## Een publiek maken in een workflow

Het richten kan door een combinatie vragen in een grafische opeenvolging in een werkschema worden gecreeerd. U kunt een publiek maken dat afhankelijk van uw vereisten als doelgroep wordt gebruikt. Als u de werkstroomeditor wilt weergeven, klikt u op de knop **[!UICONTROL Targeting and workflows]** in het campagnedashboard.

Leer hoe u een publiek kunt maken in een campagneworkflow in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html){target="_blank"}.


## Actieve profielen {#active-profiles}

Een actief profiel is een profiel waarmee klanten de afgelopen twaalf maanden via een willekeurig kanaal hebben geprobeerd te communiceren. De licentiemetriek is gebaseerd op actieve profielen. Meer informatie in [Adobe Campaign-productbeschrijving](https://helpx.adobe.com/nl/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

U kunt het aantal actieve profielen op uw instantie direct van het Controlebord van de Campagne controleren. Raadpleeg voor meer informatie de [Documentatie van het regelpaneel](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}.

>[!CAUTION]
>
>* Een profiel dat voor meerdere leveringen is bedoeld, wordt slechts eenmaal geteld.
>
>* Profielen die in het kader van de sociale marketing op X (Twitter) zijn geselecteerd, worden niet in aanmerking genomen als actieve profielen.

## Privacy en toestemming{#privacy-and-consent}

Adobe Campaign is een krachtig instrument voor het verzamelen en verwerken van grote hoeveelheden gegevens, waaronder persoonlijke informatie en gevoelige gegevens. Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en gevoelige informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

Leer hoe u privacy en toestemming beheert in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target="_blank"}.

**Verwante onderwerpen**

* [Een campagnerespecifieke workflow ontwerpen en uitvoeren](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html){target="_blank"}

* [Leer hoe u het publiek van een campagne kunt selecteren](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html){target="_blank"}

* [Aan de slag met workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html){target="_blank"}
