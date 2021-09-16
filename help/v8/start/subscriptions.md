---
title: Abonnementen en abonnementen beheren in Campagne
description: Leer hoe u abonnementen en abonnementen beheert in Campagne v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# Abonnementen en abonnementen beheren{#optin-optout}

Met Adobe Campaign kunt u informatieservices zoals nieuwsbrieven maken en controleren en abonnementen op deze services beheren. Verschillende diensten kunnen parallel worden gedefinieerd, bijvoorbeeld: gespecialiseerde nieuwsbrieven voor bepaalde productcategorieën, thema&#39;s of gebieden van een website, abonnementen op verschillende soorten waarschuwingsberichten en real-time meldingen. Raadpleeg Abonnementen beheren.

↗️ Leer hoe te om een informatiedienst tot stand te brengen, nieuwsbrief te verzenden en opt-in en opti-out in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target=&quot;_blank&quot; te beheren

Als u een profiel wilt abonneren (aanmelden) op een service, zijn de volgende opties beschikbaar:

* Voeg de service handmatig toe aan het profiel van de ontvanger: om dit te doen, van **[!UICONTROL Subscriptions]** lusje van hun profiel, klik **[!UICONTROL Add]** en selecteer de betrokken informatiedienst.

   ![](assets/subscribe-to-a-service.png)

   ↗️ meer informatie in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}

* Schrijf automatisch een reeks ontvangers aan de dienst in. De lijst met ontvangers kan afkomstig zijn van een filterbewerking, een groep, een map, een importbewerking of een directe handmatige selectie. Als u zich op deze ontvangers wilt abonneren, selecteert u de profielen en klikt u met de rechtermuisknop. Selecteer **[!UICONTROL Actions > Subscribe selection to a service...]**.

   ![](assets/subscribe-selection.png)

   Selecteer de desbetreffende service en start de bewerking.

   ![](assets/subscribe-confirm.png)

   ↗️ meer informatie in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target=&quot;_blank&quot;}


* Importeer ontvangers en meld ze automatisch aan bij een informatieservice. Selecteer hiertoe de desbetreffende service in de laatste stap van de wizard Importeren.

   ↗️ meer informatie in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients){target=&quot;_blank&quot;}

* Gebruik een webformulier zodat ontvangers zich op een service kunnen abonneren.

   ![](assets/opt-in-webapp.png)

   Campagne wordt geleverd met een standaardwebformulier voor het beheren van aanmeldingsgegevens. U kunt het personaliseren en de profielgegevens in kaart brengen.

   ![](assets/web-app.png)

   ↗️ meer informatie in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in){target=&quot;_blank&quot;}


* Maak een doelworkflow en gebruik een **[!UICONTROL Subscription service]**-activiteit.

   ![](assets/wf-subscription.png)

   ↗️ meer informatie in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter){target=&quot;_blank&quot;}

Als u een profiel wilt afmelden bij een service, kunt u het volgende doen:

**Handmatige uitschrijving**

* Koppeling of webformulier voor gepersonaliseerd abonnement
* Handmatige verwijdering van een informatiedienst
* Handmatige verwijdering van ontvangers van een bepaalde abonnementsservice

**Automatisch uitschakelen**

* Geef een maximumduur voor de informatiedienst op: de ontvangers worden automatisch afgemeld wanneer de geldigheidsperiode is verlopen . Deze periode wordt opgegeven op het tabblad Bewerken van de service-eigenschappen. Het wordt uitgedrukt in dagen.
* Stel een workflow voor abonnementen in voor een populatie.

↗️ meer informatie in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service){target=&quot;_blank&quot;}


>[!CAUTION]
>
>Abonnementen en abonnementen zijn **asynchrone** processen. Aanvragen om te weigeren of te weigeren worden elk uur verwerkt. [Meer informatie](../dev/new-apis.md#sub-apis)

U kunt uw leveringsontvangers ook toelaten om berichten aan een vriend door:sturen. Om dit te doen, neem de relevante verbindingen in uw levering op. U kunt dit deelproces dan volgen evenals het aantal bezoeken aan de betrokken pagina&#39;s.

↗️ Voor meer op dit vermogen, verwijs naar [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend){target=&quot;_blank&quot;
