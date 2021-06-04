---
product: Adobe Campaign
title: Bekende beperkingen voor campagne v8
description: Bekende beperkingen
feature: Overzicht
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: cf00895f988514fc029d0060d7404bdef0c8b30e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 2%

---

# Bekende beperkingen

Bekende beperkingen identificeren mogelijkheden, architectuur, of processen die niet door deze versie van het product worden gesteund, of die niet correct met het interoperate. Controleer deze beperkingen zorgvuldig.

Voor Adobe Campaign v8 gelden de volgende beperkingen:

* Adobe Campaign v8 is niet beschikbaar voor on-premise/hybride implementaties - alleen vrijgegeven als Adobe Managed Cloud Service.
* Bestaande klanten kunnen niet migreren van een bestaande Adobe Campaign-omgeving naar Adobe Campaign v8
* Geen tweerichtingsgegevensreplicatie: replicatie vindt alleen plaats vanuit de lokale Campagne-database naar de Cloud-database
* De mogelijkheden die [in deze sectie](capability-matrix.md#gs-unavailable-features) worden vermeld zijn niet beschikbaar in de huidige Campagne v8 bouwstijl
* Sommige niet-beschikbare of verwijderde functies zijn nog steeds zichtbaar in de gebruikersinterface
* De mechanismen Abonnement (opt-in) en Abonnement (opt-out) en Mobiele registratie zijn asynchrone processen. De verzoeken worden verwerkt elk uur door een specifieke technische werkschema. [Meer informatie](../config/replication.md#tech-wf)
* Duplicaten moeten handmatig door eindgebruikers worden afgehandeld. [Meer informatie](../dev/keys.md)
* Adobe Campaign v8 biedt geen ondersteuning voor uitgebreide doorvoer op API- en webtoepassingen. Neem contact op met Adobe voor hulp bij specifieke behoeften.


