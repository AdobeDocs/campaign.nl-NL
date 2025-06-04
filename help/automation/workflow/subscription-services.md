---
product: campaign
title: Lidmaatschapsservices
description: Meer informatie over de workflowactiviteiten van Subscription Services
feature: Workflows, Targeting Activity, Subscription Services Activity
version: Campaign v8, Campaign Classic v7
exl-id: 919630ed-b39f-40e5-b893-f3a203713b15
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%

---

# Lidmaatschapsservices{#subscription-services}



A **de diensten van het Abonnement** - type activiteit laat u een abonnement aan een informatiedienst voor de bevolking tot stand brengen of schrappen die in de overgang wordt gespecificeerd.

Om het te vormen, geef de activiteit uit en ga zijn etiket in, dan selecteer de uit te voeren actie (Abonnement of Unsubscription) en de dienst in kwestie, zoals in het volgende voorbeeld:

![](assets/edit_service_inscription.png)

1. Voer het label van de activiteit in.
1. Selecteer **[!UICONTROL Generate an outbound transition]** als u een overgang wilt maken aan het einde van de uitvoering.

   Over het algemeen markeert een abonnement van een doel op een informatiedienst het einde van de doelworkflow. Daarom wordt de optie niet standaard geactiveerd.

1. Klik op **[!UICONTROL Subscription]** of **[!UICONTROL Unsubscription]** als u een abonnement wilt nemen op de opgegeven populatie of dit wilt opzeggen bij de geselecteerde informatieservice.
1. Selecteer **[!UICONTROL Send a confirmation message]** om ontvangers op de hoogte te stellen van het feit dat ze zijn geabonneerd op of geen abonnement hebben op een service.

   De inhoud van dit bericht wordt gespecificeerd in een leveringsmalplaatje met betrekking tot de informatiedienst.

## Voorbeeld: abonneer een lijst met ontvangers op een nieuwsbrief {#example--subscribe-a-list-of-recipients-to-a-newsletter}

In één enkele operatie is de volgende workflow bedoeld om een lijst op te stellen van ontvangers die in aanmerking komen voor een nieuwsbrief, gericht op werkende mensen die in Parijs wonen, om hen te laten inschrijven.

Hiervoor moet u ook ontvangers uitsluiten die al zijn geabonneerd.

>[!CAUTION]
>
>Alvorens manueel ontvangers aan de dienst in te tekenen, verifieer dat deze ontvangers goedkeuren om mededelingen van u te ontvangen.

![](assets/subscription_services_example.png)

1. Voeg de volgende drie vragen toe:

   * Eén gericht op ontvangers in de leeftijd van 18 tot 60 jaar.
   * Een tweede gericht op ontvangers die in Parijs wonen.
   * Een derde gericht op ontvangers die momenteel niet aan de nieuwsbrief worden geabonneerd.

1. Voeg een doorsnedeactiviteit toe om de verschillende resultaten te verwijzen.
1. Voeg desgewenst een lijst bij om de lijst met de meest recente abonnees up-to-date te houden.
1. Voeg een activiteit van de abonnementsdiensten in, dan klik dit tweemaal om het te vormen.
1. Voer het activiteitslabel in en selecteer **[!UICONTROL Subscription]** .

   U kunt ontvangers desgewenst informeren over hun abonnement op de nieuwsbrief door het selectievakje **[!UICONTROL Send a confirmation message]** in te schakelen.

1. Selecteer de map waarin de nieuwsbrief zich bevindt en selecteer vervolgens de nieuwsbrief in de lijst die wordt weergegeven.
1. Laat **[!UICONTROL Generate outbound transition]** uitgeschakeld zodat deze activiteit het einde van de workflow markeert en klik vervolgens op **[!UICONTROL Ok]** .

Tijdens werkschemauitvoering, worden de ontvangers die aan alle drie vragen beantwoorden toegevoegd aan de lijst en aan nieuwsbrief geabonneerd.

U kunt controleren of het abonnement is gelukt door naar het tabblad **[!UICONTROL Subscription]** voor de ontvangers te gaan.

## Invoerparameters {#input-parameters}

* tableName
* schema

Elke binnenkomende gebeurtenis moet een doel specificeren dat door deze parameters wordt bepaald.
