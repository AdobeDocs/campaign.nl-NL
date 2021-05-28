---
solution: Campaign v8
product: Adobe Campaign
title: Operatoren voor Campagne-interactie
description: Beheerders van aanbiedingen maken
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# Live- en ontwerpomgevingen{#live-design-environments}

De interactie werkt met twee soorten aanbiedingsmilieu&#39;s:

* **[!UICONTROL Design]** bieden omgevingen aan die aanbiedingen bevatten die worden bewerkt en kunnen worden gewijzigd. Deze aanbiedingen zijn niet door de goedkeuringscyclus geweest en niet geleverd aan contacten.
* **[!UICONTROL Live]** bieden omgevingen aan die goedgekeurde aanbiedingen bevatten terwijl deze aan contactpersonen worden aangeboden. De aanbiedingen in deze omgeving zijn alleen-lezen.

![](assets/offer_environments_overview_001.png)

Elke **[!UICONTROL Design]**-omgeving is gekoppeld aan een **[!UICONTROL Live]**-omgeving. Wanneer een aanbieding is voltooid, worden de inhoud en de subsidiabiliteitsregels ervan onderworpen aan een goedkeuringscyclus. Zodra deze cyclus volledig is, wordt de betrokken aanbieding automatisch opgesteld aan het **[!UICONTROL Live]** milieu. Vanaf dat moment is het beschikbaar voor levering.

Campagne wordt standaard geleverd met een **[!UICONTROL Design]**-omgeving en een **[!UICONTROL Live]**-omgeving die eraan is gekoppeld. Beide milieu&#39;s worden pre-gevormd om [ingebouwde ontvankelijke lijst](../dev/datamodel.md#ootb-profiles) te richten.

>[!NOTE]
>
>Om ontvankelijke lijst te richten, moet u de medewerker van de doelafbeelding gebruiken om de milieu&#39;s tot stand te brengen. [Meer informatie](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Leveringsmanagers kunnen alleen de **[!UICONTROL Live]**-omgeving en de hefboomfuncties bekijken om deze te leveren. De managers van de aanbieding kunnen het **[!UICONTROL Design]** milieu bekijken en gebruiken, en het **[!UICONTROL Live]** milieu bekijken. [Meer informatie](interaction-operators.md).

## Een aanbiedingsomgeving maken {#creating-an-offer-environment}

Door gebrek, komt de Campagne met een ingebouwde milieu om de ontvankelijke lijst (geïdentificeerde aanbiedingen) te richten. Volg onderstaande stappen om een andere tabel als doel in te stellen:

1. Blader naar **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**, klik met de rechtermuisknop op de doelafbeelding die u wilt gebruiken en selecteer **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. Klik **[!UICONTROL Next]**, selecteer **[!UICONTROL Generate a storage schema for propositions]** optie en klik **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Als de optie al is ingeschakeld, schakelt u deze uit en controleert u deze opnieuw.

1. Adobe Campaign maakt twee omgevingen - **[!UICONTROL Design]** en **[!UICONTROL Live]** - met doelinformatie uit de eerder ingeschakelde doeltoewijzing. Het milieu wordt preconfigured met het richten informatie.
