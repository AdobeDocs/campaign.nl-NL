---
product: campaign
title: Aanbiedingen voor anonieme profielen presenteren (binnenkomende interactie)
description: Meer informatie over voorstellen voor anonieme profielen
exl-id: b7a04360-f8c6-4c69-9594-2b44d3f819b7
source-git-commit: 81e46ab0f33a72a7442c6c8e0111cf5c830447ce
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Anonieme interacties{#anonymous-interactions}

## Omgeving voor anonieme interacties {#environment-for-anonymous-interactions}

Standaard Campagne **Interactie** wordt geleverd met een vooraf geconfigureerde omgeving om de ingebouwde ontvangende tabel (geïdentificeerde aanbiedingen) als doel in te stellen. Als u een andere lijst, een bezoekerslijst voor anonieme aanbiedingen of een douane ontvankelijke lijst bijvoorbeeld moet richten, moet u de tovenaar van de doelafbeelding gebruiken om het milieu tot stand te brengen. [Meer informatie over omgevingen](interaction-env.md).

Wanneer u een anonieme omgeving maakt via de wizard voor het maken van toewijzingen, **[!UICONTROL Environment dedicated to incoming anonymous interactions]** wordt automatisch ingeschakeld in de omgeving **[!UICONTROL General]** tab.

De **[!UICONTROL Targeting dimension]** wordt automatisch voltooid. Standaard is dit een koppeling naar de bezoekerstabel.

De **[!UICONTROL Visitor folder]** wordt weergegeven. Het is automatisch voltooid om een koppeling te maken naar de **[!UICONTROL Visitors]** map. In dit veld kunt u kiezen waar bezoekersprofielen worden opgeslagen.

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>Als u verschillende soorten bezoekers wilt filteren, bijvoorbeeld in het geval van anonieme aanbiedingen die voor een of meer merken worden aangeboden, moet u een omgeving voor elk merk maken, en een **[!UICONTROL Visitors]** typemap voor elke omgeving.

## Catalogus aanbieden voor anonieme interacties {#offer-catalog-for-anonymous-interactions}

Net als uitgaande interacties worden inkomende interacties georganiseerd in een aanbiedingencatalogus die bestaat uit categorieën en aanbiedingen.

Als u categorieën en spaties wilt maken, past u hetzelfde proces toe als voor bepaalde bezoekers. Zie [Een aanbiedingencategorie maken](interaction-offer-catalog.md#creating-offer-categories) en [Een aanbiedingsomgeving maken](interaction-env.md#creating-an-offer-environment)).

## Anonieme bezoekers {#anonymous-visitors}

Wanneer anonieme bezoekers verbinding maken, kunnen ze een cookie-identificatieproces ondergaan. Deze impliciete herkenning is gebaseerd op de browsergeschiedenis van de bezoeker.

Tijdens deze stap, wordt een vergelijking gemaakt tussen de gegevens die door de koekjes en die in uw gegevensbestand worden teruggekregen. In sommige gevallen worden bezoekers erkend (ze worden dan impliciet geïdentificeerd), in andere gevallen worden ze niet herkend (en blijven dus anoniem).

Om deze analyse, voor de aanbiedingsruimte in werking te stellen, controleer **[!UICONTROL Implicitly identify the individual based on their browser history]** optie.

![](assets/identification_anonymous_visitors.png)

## Niet-geïdentificeerde anonieme bezoekers verwerken {#processing-unidentified-anonymous-visitors}

Als een anonieme bezoeker na analyse niet wordt geïdentificeerd, kunt u zijn gegevens opslaan in een bepaalde ruimte. Op deze manier kunt u voorstellen doen die specifiek op dit type bezoeker zijn gericht en die overeenkomen met de opgegeven typologische regels.

Als er geen element is dat u toestaat om een contact te identificeren, of als u geen geïdentificeerde aanbieding aan een contact wilt voorstellen dat impliciet kan worden geïdentificeerd, kunt u verkiezen om een reserve op een anonieme milieu uit te voeren.

Om dit te doen, controleer **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]** en geeft u vervolgens de omgeving op die aan deze niet-geïdentificeerde bezoekers in de **[!UICONTROL Linked anonymous space]** wanneer u een aanbiedingsruimte opgeeft.

![](assets/anonymous_to_anonymous_environment.png)
