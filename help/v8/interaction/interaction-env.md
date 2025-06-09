---
title: Werken met omgevingen met interactie tussen campagnes
description: Leer hoe u omgevingen kunt maken voor interactie met campagnes
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# Werken met omgevingen{#work-with-environments}

## Live- en ontwerpomgevingen{#live-design-environments}

De interactie werkt met twee soorten aanbiedingsmilieu&#39;s:

* **[!UICONTROL Design]** biedt omgevingen die aanbiedingen bevatten die worden bewerkt en kunnen worden gewijzigd. Deze aanbiedingen zijn niet door de goedkeuringscyclus geweest en niet geleverd aan contacten.
* **[!UICONTROL Live]** biedt omgevingen die goedgekeurde aanbiedingen bevatten terwijl deze aan contactpersonen worden aangeboden. De aanbiedingen in deze omgeving zijn alleen-lezen.

![](assets/offer_environments_overview_001.png)

Elke **[!UICONTROL Design]** -omgeving is gekoppeld aan een **[!UICONTROL Live]** -omgeving. Wanneer een aanbieding is voltooid, worden de inhoud en de subsidiabiliteitsregels ervan onderworpen aan een goedkeuringscyclus. Zodra deze cyclus is voltooid, wordt de betreffende aanbieding automatisch opgesteld aan het **[!UICONTROL Live]** milieu. Vanaf dat moment is het beschikbaar voor levering.

Campagne wordt standaard geleverd met een **[!UICONTROL Design]** -omgeving en een **[!UICONTROL Live]** -omgeving die eraan gekoppeld zijn. Beide milieu&#39;s worden pre-gevormd om de [ ingebouwde ontvankelijke lijst ](../dev/datamodel.md#ootb-profiles) te richten.

>[!NOTE]
>
>Om ontvankelijke lijst te richten, moet u de medewerker van de doelafbeelding gebruiken om de milieu&#39;s tot stand te brengen. [Meer informatie](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Leveringsmanagers kunnen alleen de **[!UICONTROL Live]** -omgeving en de hefboomfuncties bekijken om deze te leveren. Aanbiedingsmanagers kunnen de **[!UICONTROL Design]** -omgeving weergeven en gebruiken en de **[!UICONTROL Live]** -omgeving weergeven. [Meer informatie](interaction-operators.md)

## Een omgeving maken voor anonieme interacties{#create-an-offer-environment}

Door gebrek, komt de Campagne met een ingebouwde milieu om de ontvankelijke lijst (geïdentificeerde aanbiedingen) te richten. Als u een andere tabel als doel wilt instellen, bijvoorbeeld anonieme profielen die uw website bezoeken voor binnenkomende interacties, moet u de configuratie bijwerken.

Volg de onderstaande stappen:

1. Blader naar **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]** , klik met de rechtermuisknop op de doeltoewijzing die u wilt gebruiken en selecteer **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]** .

   ![](assets/offer_env_anonymous_001.png)

1. Klik op **[!UICONTROL Next]** , selecteer de optie **[!UICONTROL Generate a storage schema for propositions]** en klik op **[!UICONTROL Save]** .

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Als de optie al is ingeschakeld, schakelt u deze uit en controleert u deze opnieuw.

1. Adobe Campaign maakt twee omgevingen - **[!UICONTROL Design]** en **[!UICONTROL Live]** - met doelgegevens uit de eerder ingeschakelde doeltoewijzing. Het milieu wordt preconfigured met het richten informatie.

Als u **[!UICONTROL Visitor]** mapping hebt geactiveerd, wordt het vak **[!UICONTROL Environment dedicated to incoming anonymous interactions]** automatisch ingeschakeld op het tabblad **[!UICONTROL General]** van de omgeving.

Met deze optie kunt u anonieme interactiespecifieke functies activeren, vooral wanneer u omgevingen configureert die spaties bieden. U kunt opties ook vormen die u toestaan om van een &quot;geïdentificeerd&quot;milieu aan een &quot;anonieme&quot;milieu over te schakelen.

U kunt bijvoorbeeld een koppeling maken tussen een ontvankelijke omgeving en een aanbiedingsruimte (geïdentificeerd contact) die overeenkomt met een bezoekersomgeving (niet-geïdentificeerd contact). Op deze manier worden verschillende aanbiedingen ter beschikking gesteld van de contactpersoon, afhankelijk van het feit of deze contactpersoon al dan niet wordt geïdentificeerd. Voor meer op dit, verwijs naar [ Creërend aanbiedingsruimten ](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>Voor meer informatie over anonieme interactie op een binnenkomend kanaal, verwijs naar [ Anonieme interactie ](anonymous-interactions.md).
