---
title: Soorten publiek en profielkenmerken delen en synchroniseren met Adobe Experience Platform
description: Leer hoe u het publiek en de profielkenmerken van Adobe Experience Platform kunt synchroniseren met Campagne
feature: Experience Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: ea37b72efd03afb212c060f809b6ba077b996701
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Soorten publiek delen en synchroniseren met Adobe Experience Platform {#gs-ac-aep}

Met de Adobe Campaign Managed Cloud Service Destination and Source-connectors kunt u Adobe Campaign en Adobe Experience Platform naadloos integreren. Met deze integratie kunt u:

* Adobe Experience Platform-publiek naar Adobe Campaign sturen en bezorgings- en trackinglogboeken terugsturen naar Adobe Experience Platform voor analysedoeleinden;
* Breng Adobe Experience Platform-profielkenmerken naar Adobe Campaign en zorg dat er een synchronisatieproces is ingesteld zodat deze regelmatig kunnen worden bijgewerkt.

## Adobe Experience Platform-publiek naar campagne sturen {#audiences}

De belangrijkste stappen voor het verzenden van een Adobe Experience Platform-publiek naar Adobe Campaign en het terugsturen van bezorgings- en trackinglogboeken zijn als volgt:

* Een Adobe Campaign Managed Cloud Services gebruiken **Doelverbinding** om segmenten van het Experience Platform naar Adobe Campaign te verzenden:

   1. Open de catalogus met Adobe Experience Platform-doelen en maak een nieuwe **[!UICONTROL Adobe Campaign Managed Cloud Services]** verbinding.
   1. Geef informatie over de instantie Campagne die u wilt gebruiken en kies **[!UICONTROL Audience sync]** als het synchronisatietype.

      ![](assets/aep-audience-sync.png){width="800" align="center"}

   1. Selecteer de segmenten die u wilt doorsturen naar Adobe Campaign.
   1. Vorm de attributen die u in het publiek wilt uitvoeren.
   1. Zodra de stroom is gevormd, zal het geselecteerde publiek voor activering in Adobe Campaign beschikbaar zijn.

      ![](assets/aep-destination.png){width="800" align="center"}

  Gedetailleerde informatie over hoe te om de bestemming te vormen is beschikbaar in [Adobe Campaign Managed Cloud Services-verbindingsdocumentatie](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en){target="_blank"}

* Een Adobe Campaign Managed Cloud Services gebruiken **Bronverbinding** om Adobe Campaign-leverings- en trackinglogboeken naar Adobe Experience Platform te verzenden:

  Hiertoe configureert u een nieuwe Adobe Campaign Managed Cloud Services **Bronverbinding** om Campagne-gebeurtenissen in Adobe Ervaring Platform in te voeren. Verstrek details over de instantie van de Campagne en het te gebruiken schema, selecteer een dataset waar de gegevens zouden moeten worden opgenomen, dan vormen de gebieden om terug te winnen. [Leer hoe u een Adobe Campaign Managed Cloud Services-bronverbinding maakt](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}

## Profielkenmerken synchroniseren tussen Adobe Experience Platform en Adobe Campaign {#profile}

Als u Adobe Campaign met Adobe Experience Platform verbindt, kunt u extra profielkenmerken invoeren die zijn gekoppeld aan een profiel op Adobe Experience Platform en een synchronisatieproces uitvoeren zodat deze worden bijgewerkt in de Adobe Campaign-database.

Stel bijvoorbeeld dat u waarden voor opt-in en opt-out vastlegt in Adobe Experience Platform. Met deze verbinding kunt u deze waarden overbrengen naar Adobe Campaign en een synchronisatieproces uitvoeren zodat ze regelmatig worden bijgewerkt.

>[!NOTE]
>
>Synchronisatie van profielkenmerken is beschikbaar voor profielen die al aanwezig zijn in de Adobe Campaign-database.

De belangrijkste stappen voor het synchroniseren van Adobe Experience Platform-profielkenmerken met Adobe Campaign zijn:

1. Open de catalogus met Adobe Experience Platform-doelen en maak een nieuwe **[!UICONTROL Adobe Campaign Managed Cloud Services]** verbinding.
1. Geef informatie over de instantie Campagne die u wilt gebruiken en kies **[!UICONTROL Profile sync (Update only)]** als het synchronisatietype.

   ![](assets/aep-profile-sync.png){width="800" align="center"}

1. Selecteer de segmenten die de profielen aangeven die u wilt bijwerken naar de Adobe Campaign-database.
1. Configureer de profielkenmerken die u in Adobe Campaign wilt bijwerken.
1. Zodra de stroom is gevormd, zullen de geselecteerde profielattributen met Adobe Campaign worden gesynchroniseerd en voor alle profielen bijgewerkt die door de segmenten worden gericht die in de bestemming worden gevormd.

Gedetailleerde informatie over hoe te om de bestemming te vormen is beschikbaar in [Adobe Campaign Managed Cloud Services-verbindingsdocumentatie](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en){target="_blank"}