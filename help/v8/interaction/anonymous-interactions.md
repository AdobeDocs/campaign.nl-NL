---
product: campaign
title: Aanbiedingen voor anonieme profielen presenteren (binnenkomende interactie)
description: Meer informatie over het presenteren van voorstellen voor anonieme profielen
feature: Interaction, Offers
role: User, Admin
exl-id: b7a04360-f8c6-4c69-9594-2b44d3f819b7
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Anonieme interacties {#anonymous-interactions}

## Omgeving voor anonieme interacties {#environment-for-anonymous-interactions}

Door gebrek, komt de module van de Interactie van de Campagne **met een pre-gevormd milieu om de ingebouwde ontvankelijke lijst (geïdentificeerde aanbiedingen) te richten.** Als u een andere lijst, een bezoekerslijst voor anonieme aanbiedingen of een douane ontvankelijke lijst bijvoorbeeld moet richten, moet u de tovenaar van de doelafbeelding gebruiken om het milieu tot stand te brengen. [&#x200B; leer meer over milieu&#39;s &#x200B;](interaction-env.md).

Wanneer u via de wizard voor het maken van toewijzingen een anonieme omgeving maakt, wordt het selectievakje **[!UICONTROL Environment dedicated to incoming anonymous interactions]** automatisch ingeschakeld op het tabblad **[!UICONTROL General]** van de omgeving.

**[!UICONTROL Targeting dimension]** wordt automatisch voltooid. Standaard is dit een koppeling naar de bezoekerstabel.

Het veld **[!UICONTROL Visitor folder]** wordt weergegeven. De koppeling naar de map **[!UICONTROL Visitors]** wordt automatisch voltooid. In dit veld kunt u kiezen waar bezoekersprofielen worden opgeslagen.

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>Als u verschillende soorten bezoekers wilt filteren, bijvoorbeeld in het geval van anonieme aanbiedingen die voor een of meer merken worden aangeboden, moet u een omgeving voor elk merk en een map van het type **[!UICONTROL Visitors]** voor elke omgeving maken.

## Catalogus aanbieden voor anonieme interacties {#offer-catalog-for-anonymous-interactions}

Net als uitgaande interacties worden inkomende interacties georganiseerd in een aanbiedingencatalogus die bestaat uit categorieën en aanbiedingen.

Als u categorieën en spaties wilt maken, past u hetzelfde proces toe als voor bepaalde bezoekers. Verwijs naar [&#x200B; creeer een aanbiedingscategorie &#x200B;](interaction-offer-catalog.md#creating-offer-categories) en [&#x200B; creeer een aanbiedingsmilieu &#x200B;](interaction-env.md#creating-an-offer-environment)).

## Anonieme bezoekers {#anonymous-visitors}

Wanneer anonieme bezoekers verbinding maken, kunnen ze een cookie-identificatieproces ondergaan. Deze impliciete herkenning is gebaseerd op de browsergeschiedenis van de bezoeker.

Tijdens deze stap, wordt een vergelijking gemaakt tussen de gegevens die door de koekjes en die in uw gegevensbestand worden teruggekregen. In sommige gevallen worden bezoekers erkend (ze worden dan impliciet geïdentificeerd), in andere gevallen worden ze niet herkend (en blijven dus anoniem).

Als u deze analyse wilt uitvoeren, schakelt u voor de aanbiedingsruimte de optie **[!UICONTROL Implicitly identify the individual based on their browser history]** in.

![](assets/identification_anonymous_visitors.png)

## Niet-geïdentificeerde anonieme bezoekers verwerken {#processing-unidentified-anonymous-visitors}

Als een anonieme bezoeker na analyse niet wordt geïdentificeerd, kunt u zijn gegevens opslaan in een bepaalde ruimte. Op deze manier kunt u voorstellen doen die specifiek op dit type bezoeker zijn gericht en die overeenkomen met de opgegeven typologische regels.

Als er geen element is dat u toestaat om een contact te identificeren, of als u geen geïdentificeerde aanbieding aan een contact wilt voorstellen dat impliciet kan worden geïdentificeerd, kunt u verkiezen om een reserve op een anonieme milieu uit te voeren.

Hiervoor controleert u **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]** en geeft u vervolgens de omgeving op die is toegewezen aan deze niet-geïdentificeerde bezoekers in **[!UICONTROL Linked anonymous space]** wanneer u een aanbiedingsruimte opgeeft.

![](assets/anonymous_to_anonymous_environment.png)
