---
title: Werken met campagne en Adobe Experience Platform
description: Leer hoe u kunt werken met Campagne en Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Werken met campagne en Adobe Experience Platform

De Adobe Campaign Managed Cloud Service Destination and Source connectors staan naadloze integratie tussen Adobe Campaign en Adobe Experience Platform toe.

* Een Adobe Campaign Managed Cloud Services gebruiken **Doelverbinding** om Experience Platforms segmenten naar Adobe Campaign te sturen voor activering:

  Hiertoe configureert u een nieuwe Adobe Campaign Managed Cloud Services **Doelverbinding** om een segment/publiek te activeren en die gegevens naar Adobe Campaign te verzenden. Verstrek details op de instantie van de Campagne aan gebruik, uitgezochte segmenten voor de bestemming dan vormen de attributen u naar Campagne wilt uitvoeren. [Leer hoe u een Adobe Campaign Managed Cloud Services-doelverbinding maakt](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* Een Adobe Campaign Managed Cloud Services gebruiken **Bronverbinding** om Adobe Campaign-leverings- en trackinglogboeken naar Adobe Experience Platform te verzenden:

  Hiertoe configureert u een nieuwe Adobe Campaign Managed Cloud Services **Bronverbinding** om Campagne-gebeurtenissen in Adobe Ervarend Platform in te nemen. Verstrek details over de instantie van de Campagne en het te gebruiken schema, selecteer een dataset waar de gegevens zouden moeten worden opgenomen, dan vormen de gebieden om terug te winnen. [Leer hoe u een Adobe Campaign Managed Cloud Services-bronverbinding maakt](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
