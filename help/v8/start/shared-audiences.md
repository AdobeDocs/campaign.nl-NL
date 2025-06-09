---
title: Soorten publiek delen met Adobe Experience Cloud-oplossingen
description: Leer hoe u publiek kunt delen met Adobe Experience Cloud-oplossingen
feature: Audiences
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Soorten publiek delen met Adobe Experience Cloud-oplossingen{#shared-audiences}


Optie 1: AEP-bronnen en -doelen

Optie 2: Adobe People/AAM

U kunt **Adobe Campaign** met **de kerndienst van de Mensen** of Adobe Audience Manager integreren. Dan kunt u:

* Importeer gedeelde soorten publiek/segmenten van verschillende Adobe Experience Cloud-oplossingen naar Adobe Campaign. Soorten publiek kan via lijsten in Adobe Campaign worden geïmporteerd.

* Exportlijsten in de vorm van een gedeeld publiek in Adobe Experience Cloud. Deze doelgroepen kunnen worden gebruikt in de verschillende Adobe Experience Cloud-oplossingen die u gebruikt. Soorten publiek kunnen worden geëxporteerd nadat het doel is bereikt in een workflow met behulp van een toegewijde **[!UICONTROL Update shared audience]** -activiteit.

Deze integratie ondersteunt twee typen Adobe Experience Cloud-id&#39;s:

* **identiteitskaart van de Bezoeker**: dit type van herkenningsteken brengt de bezoekers van Adobe Experience Cloud met de ontvangers van Adobe Campaign in overeenstemming.
* **Verklaarde identiteitskaart**: dit type van herkenningsteken brengt alle soorten gegevens met elementen van het gegevensbestand van Adobe Campaign in overeenstemming. Het wordt in Adobe Campaign vertegenwoordigd als een vooraf gedefinieerde afstemmingssleutel.

  >[!NOTE]
  >
  > De verklaarde gegevensbron van identiteitskaart kan nu ook met de dienstintegratie van de Kern van Mensen worden gebruikt.
  >
  >Als u de de dienstintegratie van de Kern van Mensen gebruikt en de integratie van Audience Manager wilt toevoegen, zult u de hulp van een consultant van Adobe Audience Manager nodig hebben om te vermijden verlies van alle verzamelde identiteitskaart- syncs wanneer het overgaan aan het gebruiken van deze Gedeclareerde gegevensbron van identiteitskaart in een context van Adobe Audience Manager.

Zie:

[ documentatie van Adobe Audience Manager ](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=nl-NL){target="_blank"}

[ de Centrale Gids van Componenten van de Interface van Adobe Experience Cloud ](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=nl-NL){target="_blank"}
