---
title: Campagne v8 guardrails
description: Campagne v8 guardrails
feature: Overview
role: User
level: Beginner, Intermediate, Experienced
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 58fff46ba12f5c6221bbcd88a40fa0806a6c98b9
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 1%

---

# Productbegeleiding{#guardrails}

De rechten, de productbeperkingen en de prestatiegaranties worden vermeld in [Adobe Campaign Managed Cloud Services-productbeschrijving](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Hieronder vindt u aanvullende instructies en beperkingen bij het gebruik [!DNL Adobe Campaign].

De begeleiding en de beperkingen identificeren mogelijkheden, architectuur, of processen die niet door deze versie van het product worden gesteund, of die niet correct met het interoperate. Controleer deze beperkingen zorgvuldig.

* Adobe Campaign v8 is niet beschikbaar voor on-premise/hybride implementaties - alleen vrijgegeven als Adobe Beheerde Cloud Service
* Er is geen automatische migratie naar Adobe Campaign v8 beschikbaar voor bestaande klanten
* In de context van een [Implementatie van ondernemingen (FFDA)](../architecture/enterprise-deployment.md)Er is geen bidirectionele gegevensreplicatie beschikbaar: replicatie vindt alleen plaats vanuit de lokale Campagne-database naar de Cloud-database
* Opgegeven mogelijkheden [in deze sectie](v7-to-v8.md#gs-unavailable-features) zijn niet beschikbaar in de huidige versie van Campagne v8
* Sommige niet-beschikbare of verwijderde functies zijn nog steeds zichtbaar in de gebruikersinterface
* In de context van een [Implementatie van ondernemingen (FFDA)](../architecture/enterprise-deployment.md), de mechanismen voor abonnementen (opt-in) en abonnementen (opt-out) en mobiele registratie zijn asynchrone processen. De verzoeken worden verwerkt elk uur door een specifieke technische werkschema. [Meer informatie](../architecture/replication.md#tech-wf)
* Duplicaten moeten handmatig door eindgebruikers worden afgehandeld. [Meer informatie](../architecture/keys.md)
* Adobe Campaign v8 biedt geen ondersteuning voor uitgebreide doorvoer op API- en webtoepassingen - neem bij specifieke behoeften contact op met Adobe voor hulp
* In de Adobe Campaign Campagne Optimization module wordt geen rekening gehouden met geplande leveringen in de druktypologische regels. Meer informatie in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/pressure-rules.html)