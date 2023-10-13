---
title: Soorten publiek delen met Adobe Experience Cloud-oplossingen
description: Leer hoe u publiek kunt delen met Adobe Experience Cloud-oplossingen
feature: Audiences
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 5%

---

# Soorten publiek delen met Adobe Experience Cloud-oplossingen{#shared-audiences}


Optie 1: AEP-bronnen en -bestemmingen

Optie 2: Personen/AAM Adoben

U kunt **Adobe Campaign** with **Personenkern-service** of Adobe Audience Manager. Dan kunt u:

* Importeer gedeelde soorten publiek/segmenten van verschillende Adobe Experience Cloud-oplossingen naar Adobe Campaign. Soorten publiek kan via lijsten in Adobe Campaign worden geïmporteerd.

* Exportlijsten in de vorm van een gedeeld publiek in Adobe Experience Cloud. Deze doelgroepen kunnen worden gebruikt in de verschillende Adobe Experience Cloud-oplossingen die u gebruikt. Soorten publiek kunnen worden geëxporteerd nadat het doelpubliek zich in een workflow heeft gericht, met behulp van een toegewezen publiek **[!UICONTROL Update shared audience]** activiteit.

Deze integratie ondersteunt twee typen Adobe Experience Cloud-id&#39;s:

* **Bezoeker-id**: dit type id zorgt ervoor dat Adobe Experience Cloud-bezoekers overeenkomen met Adobe Campaign-ontvangers.
* **Opgegeven id**: dit type id zorgt ervoor dat alle typen gegevens overeenkomen met elementen uit de Adobe Campaign-database. Het wordt in Adobe Campaign vertegenwoordigd als een vooraf gedefinieerde afstemmingssleutel.

  >[!NOTE]
  >
  > De gegevensbron Declared ID kan nu ook worden gebruikt met de integratie van de People-kernservice.
  >
  >Als u de de dienstintegratie van de Kern van Mensen gebruikt en de integratie van de Audience Manager wilt toevoegen, zult u de hulp van een consultant van Adobe Audience Manager nodig hebben om te vermijden verlies van alle verzamelde syncs van identiteitskaart wanneer het overgaan aan het gebruiken van deze Gedeclareerde gegevensbron van identiteitskaart in een context van Adobe Audience Manager.

Zie:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html)
