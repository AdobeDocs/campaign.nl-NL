---
title: Berichten plaatsen op X (Twitter) met Adobe Campaign
description: Leer hoe u de Adobe Campaign Social Marketing-module kunt gebruiken om berichten op X (voorheen bekend als Twitter) te plaatsen en directe berichten naar uw volgers te verzenden
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 1%

---


# Berichten plaatsen op X (Twitter) met Adobe Campaign {#post-tw-messages}

Adobe Campaign wordt geleverd met een **Sociale marketing** -module waarmee u via X (voorheen bekend als Twitter) kunt communiceren met uw klanten en vooruitzichten.

Zodra de integratie wordt gevormd, kunt u:

* Verzend directe berichten naar uw volgers
* Plaatsen op uw X-account
* Verzamel nieuwe contacten door de profielgegevens terug te krijgen, die u toelaat om het richten campagnes uit te voeren en, waar mogelijk, om kanaalstrategieën uit te voeren. Voor deze handeling is toestemming van de gebruiker vereist.


De configuratiestappen om uw X-account te integreren met Adobe Campaign worden beschreven in [deze pagina](../connect/ac-tw.md).

## Een X-bericht maken en publiceren {#publish-on-tw}

Voer de onderstaande stappen uit om een bericht op uw X-account te plaatsen:

1. Een X-levering maken

   Maak een nieuwe levering op basis van de **[!UICONTROL Tweet (twitter)]** leveringssjabloon.

   ![](assets/tw-new-delivery.png)

1. Selecteer het hoofddoel

   Selecteer de account(s) waarnaar je berichten wilt verzenden.

   ![](assets/tw-define-target.png)

   1. Klik op de koppeling **[!UICONTROL To]**.
   1. Klik op de knop **[!UICONTROL Add]**.
   1. Selecteer **[!UICONTROL A Twitter account]**.
   1. In de **[!UICONTROL Folder]** , selecteert u de servicemap die de X-account bevat. Selecteer vervolgens de X-account waarnaar u de tweet wilt verzenden.

1. Proofingdoel selecteren

   De **[!UICONTROL Target of the proofs]** kunt u het X-account definiëren dat voor testleveringen moet worden gebruikt voordat de uiteindelijke levering plaatsvindt.

   Zoals in het [configuratiestappen](../connect/ac-tw.md#tw-test-account), moet u een privé testX rekening tot stand brengen die aan het verzenden van proeven wordt gewijd.

   >[!NOTE]
   >
   >Als u voor al uw leveringen dezelfde X-testaccount gebruikt, kunt u het proefdrukdoel opslaan in het dialoogvenster **[!UICONTROL Tweet]** leveringssjabloon, toegankelijk via **[!UICONTROL Resources > Templates > Delivery templates]** knooppunt. Het proefdrukdoel wordt dan standaard ingevoerd voor elke nieuwe levering.

1. De inhoud van je bericht definiëren

   Voer de inhoud van je advertentie in in het dialoogvenster **[!UICONTROL Content]** tab.

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Bij het plaatsen op X gelden de beperkingen:
   >
   >* Het bericht mag niet langer zijn dan 140 tekens.
   >* HTML-indeling wordt niet ondersteund.
   >

1. Je advertentie bekijken

   Bladeren in het dialoogvenster **[!UICONTROL Preview]** om de weergave van uw advertentie te controleren.

   ![](assets/tw-delivery-preview.png)

   1. Klik op de knop **[!UICONTROL Preview]** tab.
   1. Klik op de knop **[!UICONTROL Test personalization]** vervolgkeuzelijst en selecteert u **[!UICONTROL Service]**.
   1. In de **[!UICONTROL Folder]** , selecteert u de servicemap die uw X-account bevat.

1. Een proef verzenden

   Voordat u uw tweet publiceert, moet u controleren of de publicatie is gevalideerd door een bewijs van uw publicatie te verzenden. U kunt dan een exacte weergave van de publicatie op een persoonlijke X-testpagina krijgen.

1. Bericht verzenden

   1. Als de inhoud is goedgekeurd, klikt u op de knop **[!UICONTROL Send]** knop.
   1. Selecteren **[!UICONTROL Deliver as soon as possible]** en klik op de knop **[!UICONTROL Analyze]** knop.
   1. Controleer het resultaat als de analyse is voltooid.
   1. Klikken **[!UICONTROL Confirm delivery]** en klik vervolgens op **[!UICONTROL Yes]**.

## Directe berichten verzenden naar volgers {#direct-tw-messages}

De **[!UICONTROL Synchronize Twitter accounts]** de technische werkstroom herstelt de lijst van X volgers zodat u hen directe berichten kunt verzenden. [Meer informatie](../connect/ac-tw.md#synchro-tw-accounts)

Volg onderstaande stappen om directe berichten naar uw volgers te verzenden:

1. Een X-levering maken op basis van de **[!UICONTROL Tweet (Direct Message)]** ingebouwde leveringssjabloon.

1. Selecteer het hoofddoel

   ![](assets/tw-dm-define-target.png)

   1. Selecteer de **[!UICONTROL To]** en de **[!UICONTROL Add]** knop.

   1. Kies een doeltype

      * Selecteren **[!UICONTROL Twitter subscribers]** om een rechtstreeks bericht naar al uw volgers te sturen.

      * Selecteren **[!UICONTROL Filter conditions]** om een vraag te bepalen en zijn resultaat te bekijken. Leer hoe u een filter maakt in [deze sectie](../audiences/create-filters.md#advanced-filters).

1. Selecteer het proefdrukdoel in het menu **[!UICONTROL Target of the proofs]** tab: deze account ontvangt het bewijs van je directe bericht.

   Zoals in het [configuratiestappen](../connect/ac-tw.md#tw-test-account), moet u een privé testX rekening tot stand brengen die aan het verzenden van proeven wordt gewijd.


   >[!NOTE]
   >
   >Als u al uw directe-berichtproefdrukken naar dezelfde X-account wilt verzenden, kunt u het proefdrukdoel opslaan in het dialoogvenster **[!UICONTROL Tweet (Direct Message)]** leveringssjabloon, toegankelijk via **[!UICONTROL Resources > Templates > Delivery templates]** knooppunt.

1. Voer de inhoud van het bericht in het dialoogvenster **[!UICONTROL Content]** tab.

   ![](assets/tw-dm-content.png)

   Velden voor persoonlijke voorkeur kunnen op dezelfde manier worden gebruikt als voor e-mailleveringen, bijvoorbeeld om de naam van de volgende persoon toe te voegen aan de hoofdtekst van het bericht. Meer informatie in [deze sectie](../send/personalize.md).

1. Een voorbeeld van uw bericht bekijken

   Bladeren in het dialoogvenster **[!UICONTROL Preview]** om de weergave van uw advertentie te controleren.

   ![](assets/tw-dm-preview.png)

   1. Klik op de knop **[!UICONTROL Preview]** tab.
   1. Klik op de knop **[!UICONTROL Test personalization]** vervolgkeuzelijst en selecteert u **[!UICONTROL Visitor Subscription]**.
   1. Kies een X-account waarmee u de voorvertoning wilt testen.

1. Een proef verzenden

   Voordat u uw bericht verzendt, moet u controleren of het is gevalideerd door [het verzenden van een bewijs naar een testaccount](../send/preview-and-proof.md): u kunt dan een exacte weergave van het bericht op een persoonlijke X-account ophalen en de inhoud en personalisatie controleren.

1. Het directe bericht verzenden

   1. Als de inhoud is goedgekeurd, klikt u op de knop **[!UICONTROL Send]** knop.
   1. Selecteren **[!UICONTROL Deliver as soon as possible]** en klik op de knop **[!UICONTROL Analyze]** knop.
   1. Controleer het resultaat als de analyse is voltooid.
   1. Klikken **[!UICONTROL Confirm delivery]** en klik vervolgens op **[!UICONTROL Yes]**.

>[!CAUTION]
>
>U kunt niet meer dan 250 directe berichten per dag verzenden. Als u wilt voorkomen dat deze drempelwaarde wordt overschreden, kunt u in golven leveren. Raadpleeg voor meer informatie hierover [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target="_blank"}.


## Gegevens voor bijhouden van toegang {#tw-tracking}

Ingebouwd **[!UICONTROL Tweet]** leveringssjabloon; reeksspatiëring is standaard ingeschakeld.

Trackinggegevens kunnen worden weergegeven in de leveringsrapporten en in de **[!UICONTROL Edit > Tracking]** tabblad van de levering en de service.

De volgende configuratie is het zelfde als voor een e-maillevering. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html){target="_blank"}.

