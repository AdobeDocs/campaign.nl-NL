---
title: Abonnementen en abonnementen beheren in Campagne
description: Leer hoe u inschrijvingen en uitschrijvingen beheert in Campaign v8.
feature: Subscriptions
role: User
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: 08e04f3642320df94d719a415e878e3a26d2e00f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 3%

---

# Abonnementen en abonnementen beheren {#optin-optout}

Met Adobe Campaign kunt u informatieservices zoals nieuwsbrieven maken en controleren en abonnementen op deze services beheren. Verschillende diensten kunnen parallel worden gedefinieerd, bijvoorbeeld: gespecialiseerde nieuwsbrieven voor bepaalde productcategorieën, thema&#39;s of gebieden van een website, abonnementen op verschillende typen waarschuwingsberichten en realtime meldingen.

Leer hoe te om de informatiedienst tot stand te brengen, nieuwsbrief te verzenden en opt-in en opt-out in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=nl-NL){target="_blank"} te beheren 

Als u een profiel wilt abonneren (aanmelden) op een service, zijn de volgende opties beschikbaar:

* Voeg de service handmatig toe aan het profiel van de ontvanger. Klik hiertoe op het tabblad **[!UICONTROL Subscriptions]** van het profiel van de ontvanger op **[!UICONTROL Add]** en selecteer de desbetreffende informatieservice.

  ![](assets/subscribe-to-a-service.png)

  Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=nl-NL#deliveries-tab){target="_blank"} 

* Schrijf automatisch een reeks ontvangers aan de dienst in. De lijst met ontvangers kan afkomstig zijn van een filterbewerking, een groep, een map, een importbewerking of een directe handmatige selectie. Als u zich op deze ontvangers wilt abonneren, selecteert u de profielen en klikt u met de rechtermuisknop. Selecteer **[!UICONTROL Actions > Subscribe selection to a service...]**.

  ![](assets/subscribe-selection.png)

  Selecteer de desbetreffende service en start de bewerking.

  ![](assets/subscribe-confirm.png)

  Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=nl-NL#deliveries-tab){target="_blank"} 


* Importeer ontvangers en meld ze automatisch aan bij een informatieservice. Selecteer hiertoe de desbetreffende service in de laatste stap van de wizard Importeren.

  Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=nl-NL#step-5---additional-step-when-importing-recipients){target="_blank"} .

* Gebruik een webformulier zodat ontvangers zich op een service kunnen abonneren.

  ![](assets/opt-in-webapp.png)

  Campagne wordt geleverd met een standaardwebformulier voor het beheren van aanmeldingsgegevens. U kunt het personaliseren en de profielgegevens in kaart brengen.

  ![](assets/web-app.png)

  Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=nl-NL#create-a-subscription--form-with-double-opt-in){target="_blank"} .


* Maak een doelworkflow en gebruik een **[!UICONTROL Subscription service]** -activiteit.

  ![](assets/wf-subscription.png)

  Leer meer in [ deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/subscription-services.html?lang=nl-NL){target="_blank"} .

Als u een profiel wilt afmelden bij een service, kunt u het volgende doen:

**Handmatig unsubscription**

* Koppeling of webformulier voor gepersonaliseerd abonnement
* Handmatige verwijdering van een informatiedienst
* Handmatige verwijdering van ontvangers van een bepaalde abonnementsservice

**Automatisch unsubscription**

* Geef een maximumduur voor de informatiedienst op: ontvangers worden automatisch afgemeld wanneer de geldigheidsperiode is verlopen. Deze periode wordt opgegeven op het tabblad Bewerken van de service-eigenschappen. Het wordt uitgedrukt in dagen.
* Stel een workflow voor abonnementen in voor een populatie.

Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=nl-NL#unsubscribing-a-recipient-from-a-service){target="_blank"} .


>[!CAUTION]
>
>In de context van een [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), zijn de abonnementen en de unsubscriptions **asynchrone** processen. Aanvragen om te weigeren of te weigeren worden elk uur verwerkt. [Meer informatie](../architecture/new-apis.md#sub-apis)

<!--
You can also enable your delivery recipients to forward messages to a friend. To do this, insert the relevant links into your delivery. You may then track this sharing process as well as the number of visits to the concerned pages. 

For more on this capability, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=nl-NL#viral-marketing--forward-to-a-friend){target="_blank"}
-->
