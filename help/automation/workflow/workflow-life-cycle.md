---
product: campaign
title: Levenscyclus van workflow
description: Meer informatie over de levenscyclus van een workflow
feature: Workflows
exl-id: 4356b90c-9d7c-49ef-88cd-716b2ccdb7f0
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 2%

---

# Levenscyclus van workflow {#workflow-life-cycle}



De workflowcyclus bestaat uit drie hoofdstappen.

* **Wordt bewerkt**

   Dit is de eerste ontwerpfase: Als er een nieuwe workflow wordt gemaakt, wordt de status ervan bewerkt. De workflow wordt nog niet door de server afgehandeld en kan zonder risico worden gewijzigd.

* **Gestart**

   Zodra de eerste ontwerpfase is voltooid, kan de workflow worden gestart. In deze fase, wordt de instantie behandeld door de server en de individuele taken worden uitgevoerd. De workflow kan nog steeds met bepaalde voorzorgen worden aangepast.

* **Voltooid**

   Een workflow is &#39;voltooid&#39; wanneer er geen taken meer worden uitgevoerd of wanneer een operator de instantie expliciet heeft gestopt.

De **Start** en **Aflevering** activiteiten worden beschreven terwijl de **Goedkeuring** activiteit knippert in de onderstaande workflow.

![](assets/new-workflow-6.png)

Dit betekent dat de eerste twee activiteiten met succes zijn uitgevoerd en dat de goedkeuring bezig is, d.w.z. dat zij is gecreëerd maar nog niet is voltooid.

De tekens **574 - OK** weergegeven boven de overgang na de overgang **Aflevering** de activiteit houdt in dat de voorbereiding van de levering gericht is op 574 ontvangers en dat de bewerking met succes is voltooid. Deze informatie, die aan de overgangen wordt toegevoegd wanneer zij worden uitgevoerd, wordt berekend door de activiteiten die gegevens verwerken.

De workflow wordt gestart en er wordt gewacht op een operator die behoort tot de groep die in het dialoogvenster **Goedkeuring** activiteiten om een besluit te nemen. De tot de groep behorende exploitanten die een e-mailadres of mobiel telefoonnummer hebben, worden op de hoogte gesteld.

Het beheer van de exploitant wordt in dit hoofdstuk nader toegelicht.

Raadpleeg voor meer informatie over hoe u uw workflows kunt controleren [deze sectie](monitor-workflow-execution.md).
