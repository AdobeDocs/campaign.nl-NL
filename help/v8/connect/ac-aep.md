---
title: Werken met campagne en Adobe Experience Platform
description: Leer hoe u kunt werken met Campagne en Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Werken met campagne en Adobe Experience Platform

De Adobe Campaign Managed Cloud Service Destination and Source connectors staan naadloze integratie tussen Adobe Campaign en Adobe Experience Platform toe.

* Gebruiken **Adobe Campaign Managed Cloud Services-bestemming** verbinding om Experience Platform segmenten naar Adobe Campaign te verzenden voor activering

   ![](assets/aep-destination.png)

* Gebruiken **Adobe Campaign Managed Cloud Services-bron** verbinding voor het verzenden van Adobe Campaign-bezorgings- en trackingslogbestanden naar Adobe Experience Platform

   ![](assets/aep-logs.png)

De stappen voor het configureren van deze integratie in Adobe Experience Platform zijn als volgt:

1. Configureer een nieuwe Adobe Campaign Managed Cloud Services-bestemmingsverbinding om een segment/publiek te activeren en die gegevens naar Adobe Campaign te verzenden.

   Verstrek details op de instantie van de Campagne aan gebruik, uitgezochte segmenten voor de bestemming dan vormen de attributen u naar Campagne wilt uitvoeren.

   [Leer hoe u een Adobe Campaign Managed Cloud Services-doelverbinding maakt](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configureer een nieuwe Adobe Campaign Managed Cloud Services Source-verbinding om Campagnegebeurtenissen in Adobe Experience Platform in te voeren.

   Verstrek details over de instantie van de Campagne en het te gebruiken schema, selecteer een dataset waar de gegevens zouden moeten worden opgenomen, dan vormen de gebieden om terug te winnen.

   [Leer hoe u een Adobe Campaign Managed Cloud Services-bronverbinding maakt](https://www.adobe.com/go/sources-campaign-ui-en)
