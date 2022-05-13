---
title: Bekende beperkingen voor campagne v8
description: Bekende beperkingen
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 1%

---

# Bekende beperkingen

Bekende beperkingen identificeren mogelijkheden, architectuur, of processen die niet door deze versie van het product worden gesteund, of die niet correct met het interoperate. Controleer deze beperkingen zorgvuldig.

Voor Adobe Campaign v8 gelden de volgende beperkingen:

* Adobe Campaign v8 is niet beschikbaar voor on-premise/hybride implementaties - alleen vrijgegeven als Adobe Managed Cloud Service.
* Bestaande klanten kunnen niet migreren van een bestaande Adobe Campaign-omgeving naar Adobe Campaign v8
* In de context van een [Implementatie van ondernemingen (FFDA)](../architecture/enterprise-deployment.md)Er is geen bidirectionele gegevensreplicatie beschikbaar: replicatie vindt alleen plaats vanuit de lokale Campagne-database naar de Cloud-database
* Opgegeven mogelijkheden [in deze sectie](capability-matrix.md#gs-unavailable-features) zijn niet beschikbaar in de huidige versie van Campagne v8
* Sommige niet-beschikbare of verwijderde functies zijn nog steeds zichtbaar in de gebruikersinterface
* In de context van een [Implementatie van ondernemingen (FFDA)](../architecture/enterprise-deployment.md), de mechanismen voor abonnementen (opt-in) en abonnementen (opt-out) en mobiele registratie zijn asynchrone processen. De verzoeken worden verwerkt elk uur door een specifieke technische werkschema. [Meer informatie](../architecture/replication.md#tech-wf)
* Duplicaten moeten handmatig door eindgebruikers worden afgehandeld. [Meer informatie](../architecture/keys.md)
* Adobe Campaign v8 biedt geen ondersteuning voor uitgebreide doorvoer op API- en webtoepassingen. Neem contact op met Adobe voor hulp bij specifieke behoeften.
* In de Adobe Campaign Campagne Optimization module wordt geen rekening gehouden met geplande leveringen in de druktypologische regels. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=en#setting-the-period).