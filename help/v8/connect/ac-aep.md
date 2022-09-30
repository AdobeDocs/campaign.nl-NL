---
title: Werken met campagne en Adobe Experience Platform
description: Leer hoe u kunt werken met Campagne en Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Werken met campagne en Adobe Experience Platform

De Adobe Campaign Managed Cloud Service bestemmings en bronschakelaars staan naadloze integratie tussen Adobe Campaign en Adobe Experience Platform toe:

* Gebruiken **Verbinding met Adobe Campaign Managed Cloud Sources** de segmenten van het Experience Platform ter activering naar Adobe Campaign te sturen;

   ![](assets/aep-destination.png)

* Gebruiken **Adobe Campaign Managed Cloud Destination-connector** om Adobe Campaign-leverings- en trackinglogboeken naar Adobe Experience Platform te verzenden.

   ![](assets/aep-logs.png)

De stappen voor het configureren van deze integratie in Adobe Experience Platform zijn als volgt:

1. Configureer een nieuwe Adobe Campaign Managed Cloud Services-doelverbinding om een segment/publiek te activeren en die gegevens naar Adobe Campaign te verzenden.

   Verstrek details op de instantie van de Campagne aan gebruik, uitgezochte segmenten voor de bestemming dan vormen de attributen u naar Campagne wilt uitvoeren.

   [Leer hoe u een Adobe Campaign Managed Cloud Services-doelverbinding maakt](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Vorm een nieuwe Adobe Campaign Managed Cloud Services bronverbinding om de gebeurtenissen van de Campagne in Adobe te nemen Ervaren Platform.

   Verstrek details over de instantie van de Campagne en het te gebruiken schema, selecteer een dataset waar de gegevens zouden moeten worden opgenomen, dan vormen de gebieden om terug te winnen.

   [Leer hoe u een Adobe Campaign Managed Cloud Services-bronverbinding maakt](https://www.adobe.com/go/sources-campaign-ui-en)
