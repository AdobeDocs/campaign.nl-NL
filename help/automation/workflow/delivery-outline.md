---
product: campaign
title: Overzicht van levering
description: Meer informatie over de workflowactiviteit van het overzicht van de levering
feature: Workflows, Targeting Activity
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 1%

---

# Overzicht van levering{#delivery-outline}

De **leveringsoverzicht** Hiermee kunt u een omtrek gebruiken in een campagneworkflow. De contouren moeten vooraf in de campagne zijn gemaakt.

Om de activiteit te vormen, moet u eenvoudig het overzicht selecteren u evenals de geplande contactdatum houdt van. U kunt het filtreren regels toevoegen door typologieën of typologieregels toe te voegen.

## Voorbeeld: Een voorstel invoegen via een leveringsoverzicht {#example--inserting-an-offer-via-a-delivery-outline}

De **leveringsoverzicht** activiteit, beschikbaar in de campagnewerkschema&#39;s, laat u aanbiedingen voorstellen presenteren die in een leveringsoverzicht van de huidige lopende campagne van verwijzingen worden voorzien.

>[!NOTE]
>
>De **Interactie** pakket moet zijn geïnstalleerd.

1. Voeg in een workflow een overzichtsactiviteit toe voordat u een leveringsactiviteit toevoegt.
1. Geef in de overzichtsactiviteit van de levering de omtrek op die u wilt gebruiken.
1. Vul de beschikbare velden in op basis van uw levering.
1. Er zijn twee mogelijke gevallen:

   * Als je de aanbiedingsengine wilt bellen, kun je de **[!UICONTROL Restrict the number of propositions selected]** doos. Geef de aanbiedingsruimte en het aantal voorstellen op dat in de levering wordt weergegeven.

      De aanbiedingsmotor zal rekening houden met het gewicht van de aanbieding en de subsidiabiliteitsregels.

   * Als u niet de doos controleert, zullen alle aanbiedingen in het leveringsoverzicht worden voorgesteld zonder een vraag aan de aanbiedingsmotor te maken.

   In de voorvertoning wordt rekening gehouden met het aantal aanbiedingen dat in de levering is opgegeven. Bij het uitvoeren van een workflow wordt rekening gehouden met het nummer dat is opgegeven in het leveringsoverzicht.

   ![](assets/int_compo_offre_wf1.png)
