---
title: Bekende beperkingen voor campagne v8
description: Bekende beperkingen
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: e41816003958c3373e92d5ea82240fd7ceda5857
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 1%

---

# Bekende beperkingen

Bekende beperkingen identificeren mogelijkheden, architectuur, of processen die niet door deze versie van het product worden gesteund, of die niet correct met het interoperate. Controleer deze beperkingen zorgvuldig.

Voor Adobe Campaign v8 gelden de volgende beperkingen:

* Adobe Campaign v8 is niet beschikbaar voor on-premise/hybride implementaties - alleen vrijgegeven als Adobe Managed Cloud Service.
* Bestaande klanten kunnen niet migreren van een bestaande Adobe Campaign-omgeving naar Adobe Campaign v8
* Geen tweerichtingsgegevensreplicatie: replicatie vindt alleen plaats vanuit de lokale Campagne-database naar de Cloud-database
* Opgegeven mogelijkheden [in deze sectie](capability-matrix.md#gs-unavailable-features) zijn niet beschikbaar in de huidige versie van Campagne v8
* Sommige niet-beschikbare of verwijderde functies zijn nog steeds zichtbaar in de gebruikersinterface
* De mechanismen voor abonnementen (opt-in) en het opzeggen (opt-out) en Mobile-registratie zijn asynchrone processen. De verzoeken worden verwerkt elk uur door een specifieke technische werkschema. [Meer informatie](../config/replication.md#tech-wf)
* Duplicaten moeten handmatig door eindgebruikers worden afgehandeld. [Meer informatie](../dev/keys.md)
* Adobe Campaign v8 biedt geen ondersteuning voor uitgebreide doorvoer op API- en webtoepassingen. Neem contact op met Adobe voor hulp bij specifieke behoeften.
* In de optimalisatiemodule voor Adobe Campaign-campagnes wordt geen rekening gehouden met geplande leveringen in de regels voor de druktypologie. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=en#setting-the-period).