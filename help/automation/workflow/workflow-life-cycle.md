---
product: campaign
title: Levenscyclus van workflow
description: Meer informatie over de levenscyclus van een workflow
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 4356b90c-9d7c-49ef-88cd-716b2ccdb7f0
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 2%

---

# Levenscyclus van workflow {#workflow-life-cycle}



De workflowcyclus bestaat uit drie hoofdstappen.

* **wordt uitgegeven**

  Dit is de eerste ontwerpfase: als er een nieuwe workflow wordt gemaakt, wordt de status ervan bewerkt. De workflow wordt nog niet door de server afgehandeld en kan zonder risico worden gewijzigd.

* **Begonnen**

  Zodra de eerste ontwerpfase is voltooid, kan de workflow worden gestart. In deze fase, wordt de instantie behandeld door de server en de individuele taken worden uitgevoerd. De workflow kan nog steeds met bepaalde voorzorgen worden aangepast.

* **Voltooid**

  Een werkstroom is &#39;voltooid&#39; wanneer er geen taken meer worden uitgevoerd of wanneer een operator de instantie expliciet heeft gestopt.

Bijvoorbeeld, worden het **Begin** en **Levering** activiteiten geschetst terwijl de **5&rbrace; activiteit van de Goedkeuring &lbrace;in het werkschema hieronder knippert.**

![](assets/new-workflow-6.png)

Dit betekent dat de eerste twee activiteiten met succes zijn uitgevoerd en dat de goedkeuring in uitvoering is, d.w.z. dat zij is gecreëerd maar nog niet is voltooid.

De karakters **574 - O.K.** getoond boven de overgang na de **activiteit van de Levering** betekent dat de leveringsvoorbereiding 574 ontvangers heeft gericht en dat de verrichting met succes werd voltooid. Deze informatie, die aan de overgangen wordt toegevoegd wanneer zij worden uitgevoerd, wordt berekend door de activiteiten die gegevens verwerken.

Het werkschema is begonnen en wacht op een exploitant die tot de groep behoort die in de **wordt gespecificeerd van de Goedkeuring** activiteit om een besluit te nemen. De operatoren die tot de groep behoren en een e-mailadres of mobiel nummer hebben, worden op de hoogte gesteld.

Voor meer op hoe te om u werkschema&#39;s te controleren, verwijs naar [ deze sectie ](monitor-workflow-execution.md).
