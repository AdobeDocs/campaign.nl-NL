---
title: Campagne v8 guardrails
description: Campagne v8 guardrails
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 2%

---

# Productgeleiders{#guardrails}

De rechten, de productbeperkingen en de prestatiesbegeleiding worden vermeld in [&#x200B; Adobe Campaign Managed Cloud Services pagina van de productbeschrijving &#x200B;](https://helpx.adobe.com/nl/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Hieronder vindt u aanvullende instructies en beperkingen wanneer u [!DNL Adobe Campaign] gebruikt.

De begeleiding en de beperkingen identificeren mogelijkheden, architectuur, of processen die niet door deze versie van het product worden gesteund, of die niet correct met het interoperate. Controleer deze beperkingen zorgvuldig.

* Adobe Campaign v8 is niet beschikbaar voor on-premise/hybride implementaties - alleen vrijgegeven als Adobe Managed Cloud Service
* Er is geen automatische migratie naar Adobe Campaign v8 beschikbaar voor bestaande klanten
* In de context van een [&#x200B; plaatsing van de Onderneming (FFDA) &#x200B;](../architecture/enterprise-deployment.md), wordt geen bidirectionele gegevensreplicatie verstrekt: de replicatie gebeurt slechts van het lokale gegevensbestand van de Campagne aan het gegevensbestand van de Wolk
* De mogelijkheden die [&#x200B; in deze sectie &#x200B;](v7-to-v8.md#gs-unavailable-features) worden vermeld zijn niet beschikbaar in de huidige Campagne v8 bouwstijl
* Sommige niet-beschikbare of verwijderde functies zijn nog steeds zichtbaar in de gebruikersinterface
* In de context van een [&#x200B; plaatsing van de Onderneming (FFDA) &#x200B;](../architecture/enterprise-deployment.md), abonnement (opt-in) en unsubscription (opt-out) mechanismen, en de Mobiele registratie zijn asynchrone processen. De verzoeken worden verwerkt elk uur door een specifieke technische werkschema. [Meer informatie](../architecture/replication.md#tech-wf)
* In de context van een [&#x200B; plaatsing van de Onderneming (FFDA) &#x200B;](../architecture/enterprise-deployment.md), moeten de duplicaten manueel door eind-gebruikers worden behandeld. [Meer informatie](../architecture/keys.md)
* Adobe Campaign v8 biedt geen ondersteuning voor uitgebreide doorvoer op API- en webtoepassingen - neem bij specifieke behoeften contact op met Adobe voor hulp
* In de context van een [&#x200B; plaatsing van de Onderneming (FFDA) &#x200B;](../architecture/enterprise-deployment.md), houdt de module van de Optimalisering van de Campagne van Adobe Campaign geen rekening met geplande leveringen in de regels van de druktypologie. Leer meer in [&#x200B; deze pagina &#x200B;](../../automation/campaign-opt/pressure-rules.md)