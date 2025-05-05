---
title: Campagne v8 guardrails
description: Campagne v8 guardrails
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 1%

---

# Productgeleiders{#guardrails}

De rechten, de productbeperkingen en de prestatiegaranties worden vermeld in [Adobe Campaign Managed Cloud Services-productbeschrijvingspagina](https://helpx.adobe.com/nl/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Hieronder vindt u aanvullende instructies en beperkingen bij het gebruik [!DNL Adobe Campaign].

De begeleiding en de beperkingen identificeren mogelijkheden, architectuur, of processen die niet door deze versie van het product worden gesteund, of die niet correct met het interoperate. Controleer deze beperkingen zorgvuldig.

* Adobe Campaign v8 is niet beschikbaar voor on-premise/hybride implementaties - alleen vrijgegeven als Adobe Managed Cloud Service
* Er is geen automatische migratie naar Adobe Campaign v8 beschikbaar voor bestaande klanten
* In de context van een [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md), er is geen bidirectionele gegevensreplicatie beschikbaar: replicatie vindt alleen plaats vanuit de lokale Campagne-database naar de Cloud-database
* Opgegeven mogelijkheden [in deze sectie](v7-to-v8.md#gs-unavailable-features) zijn niet beschikbaar in de huidige versie van Campagne v8
* Sommige niet-beschikbare of verwijderde functies zijn nog steeds zichtbaar in de gebruikersinterface
* In de context van een [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md), de mechanismen voor abonnementen (opt-in) en abonnementen (opt-out) en mobiele registratie zijn asynchrone processen. De verzoeken worden verwerkt elk uur door een specifieke technische werkschema. [Meer informatie](../architecture/replication.md#tech-wf)
* In de context van een [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md)duplicaten moeten handmatig door de eindgebruikers worden afgehandeld. [Meer informatie](../architecture/keys.md)
* Adobe Campaign v8 biedt geen ondersteuning voor uitgebreide doorvoer op API- en webtoepassingen - neem contact op met de Adobe voor hulp bij specifieke behoeften
* In de context van een [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md)In de Adobe Campaign Campagne Optimization module wordt geen rekening gehouden met geplande leveringen in de druktypologische regels. Meer informatie in [deze pagina](../../automation/campaign-opt/pressure-rules.md)