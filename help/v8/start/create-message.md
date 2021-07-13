---
product: Adobe Campaign
title: Aan de slag met berichten
description: Aan de slag met berichten
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 3%

---

# Aan de slag met berichten{#gs-ac-audiences}

Met Adobe Campaign kunt u kanaalcampagnes verzenden, waaronder e-mails, SMS, pushmeldingen en directe mails, en de doeltreffendheid van deze campagnes meten aan de hand van verschillende speciale rapporten. Deze berichten worden ontworpen en verzonden door leveringen, en kunnen voor elke ontvanger worden gepersonaliseerd.

De kernfuncties omvatten het richten, het bepalen en het personaliseren van berichten, de uitvoering van mededelingen, en de bijbehorende operationele rapporten. Het belangrijkste functionele toegangspunt is de leveringsmedewerker. Dit toegangspunt leidt tot meerdere mogelijkheden die door Adobe Campaign worden gedekt.

Leer belangrijke stappen om levering in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html) tot stand te brengen.

Adobe Campaign v8 wordt geleverd met de volgende leveringskanalen:

* **E-mailkanaal**: Met e-mailleveringen kunt u persoonlijke e-mails sturen naar de doelgroep. Meer informatie vindt u op [deze pagina](../send/email.md).

* **Direct-mailkanaal**: met direct mail kunt u een extractiebestand genereren dat gegevens over de doelpopulatie bevat.  Meer informatie op [deze pagina](../send/direct-mail.md)

* **Mobiel kanaal**: Met leveringen op mobiele kanalen kunt u persoonlijke SMS naar de doelgroep sturen.  Meer informatie op [deze pagina](../send/sms.md)

* **Mobiel toepassingskanaal**: Met levering voor mobiele apps kunt u meldingen verzenden naar iOS- en Android-systemen.  Meer informatie op [deze pagina](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Geef op hoe berichten moeten worden verzonden

Nadat u het bericht hebt gemaakt en de inhoud ervan hebt ontworpen en getest, kunt u kiezen hoe u het bericht wilt verzenden. De campagne biedt een reeks mogelijkheden aan:

* Handmatig berichten verzenden naar het hoofddoel

   ![](assets/send-email.png)

   ↗️ leer hoe te om berichten in [Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html){target=&quot;_blank&quot; te verzenden

* Verzend berichten verbonden aan een [marketing campagne](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   ↗️ leren hoe te om berichten in de context van een campagne in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html){target=&quot;_blank&quot;} te verzenden

* Berichten verzenden via een [workflow](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   ↗️ leren hoe u e-mailleveringen kunt automatiseren in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html){target=&quot;_blank&quot;}

* [Berichten ](../send/transactional.md) activeren van een gebeurtenis ↗️  [Gebruik hoofdletters/kleine letters: leren hoe u een transactie-e-mail met een bijlage](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=en) verzendt {target=&quot;_blank&quot;}

* Uw berichten plannen

   ![](assets/schedule-send.png)

   ↗️ [Gebruik hoofdletters/kleine letters: leer hoe programma en verzend a verjaardag e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?){target=&quot;_blank&quot;}


## Aanpassing toevoegen

Berichten die door Adobe Campaign worden geleverd, kunnen op verschillende manieren worden gepersonaliseerd.

U kunt:

* Dynamische personalisatievelden invoegen.
↗️ Leer hoe te om verpersoonlijkingsgebieden in [Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html){target=&quot;_blank&quot; te gebruiken
* Vooraf gedefinieerde personalisatieblokken invoegen.
↗️ leer wat een verpersoonlijkingsblok is en hoe te om het in [Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html){target=&quot;_blank&quot; te gebruiken
* Voorwaardelijke content maken.
↗️ leren hoe u voorwaardelijke inhoud kunt invoegen in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html){target=&quot;_blank&quot;

## Transactieberichten verzenden

Transactioneel overseinen (het Centrum van het Bericht) is de module van de Campagne die voor het beheren van trekkerberichten wordt ontworpen.

?? Meer informatie over de mogelijkheid van transactieberichten vindt u in [deze sectie](../dev/architecture.md#transac-msg-archi)

?? De stappen voor het configureren en verzenden van transactieberichten worden beschreven in [deze pagina](../send/transactional.md)

↗️ ontdekt dit vermogen in een gebruiksgeval van begin tot eind in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html){target=&quot;_blank&quot;}

## Logbestanden voor aflevering en bijhouden

Het controleren van uw leveringen nadat deze zijn verzonden, is een belangrijke stap om ervoor te zorgen dat uw marketingcampagnes efficiënt zijn en uw klanten bereiken. U kunt controleren na het verzenden van een levering, evenals begrijpen hoe de leveringsmislukkingen en quarantines worden beheerd.

↗️ Leer hoe te om uw leveringen in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target=&quot;_blank&quot; te controleren


**Verwante** onderwerpen in Campaign Classic v7 documentatie:

↗️ [Best practices voor levering](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html){target=&quot;_blank&quot;}

↗️ [Een e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html){target=&quot;_blank&quot; testen en verzenden

↗️ [Proofs verzenden](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
