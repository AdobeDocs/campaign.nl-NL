---
title: Aan de slag met berichten
description: Aan de slag met berichten
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 4%

---

# Aan de slag met berichten{#gs-ac-audiences}

Met Adobe Campaign kunt u kanaalcampagnes verzenden, waaronder e-mails, SMS, pushmeldingen en directe mails, en de doeltreffendheid van deze campagnes meten aan de hand van verschillende speciale rapporten. Deze berichten worden ontworpen en verzonden door leveringen, en kunnen voor elke ontvanger worden gepersonaliseerd.

De kernfuncties omvatten het richten, het bepalen en het personaliseren van berichten, de uitvoering van mededelingen, en de bijbehorende operationele rapporten. Het belangrijkste functionele toegangspunt is de leveringsmedewerker. Dit toegangspunt leidt tot meerdere mogelijkheden die door Adobe Campaign worden gedekt.

Leer de belangrijkste stappen om een levering te maken in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html).

Adobe Campaign v8 wordt geleverd met de volgende leveringskanalen:

* **E-mailkanaal**: Met e-mailleveringen kunt u persoonlijke e-mails sturen naar de doelgroep. Meer informatie in [deze pagina](../send/email.md).

* **Direct mailkanaal**: met direct mail kunt u een extractiebestand genereren dat gegevens over de doelpopulatie bevat.  Meer informatie in [deze pagina](../send/direct-mail.md)

* **Mobiel kanaal**: Met leveringen op mobiele kanalen kunt u persoonlijke SMS naar de doelgroep sturen.  Meer informatie in [deze pagina](../send/sms.md)

* **Mobiel toepassingskanaal**: Met levering voor mobiele apps kunt u meldingen verzenden naar iOS- en Android-systemen.  Meer informatie in [deze pagina](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Geef op hoe berichten moeten worden verzonden{#gs-send-msg}

Nadat u het bericht hebt gemaakt en de inhoud ervan hebt ontworpen en getest, kunt u kiezen hoe u het bericht wilt verzenden. De campagne biedt een reeks mogelijkheden aan:

* Handmatig berichten verzenden naar het hoofddoel

   ![](assets/send-email.png)

   Leer hoe berichten worden verzonden in [deze sectie](../send/send.md)

* Berichten verzenden die zijn gekoppeld aan een [marketingcampagne](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   Leer hoe u berichten kunt verzenden in het kader van een campagne in [deze sectie](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html)

* Berichten verzenden via een [werkstroom](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   Leer hoe u e-mailleveringen kunt automatiseren in [deze pagina](../../automation/workflow/delivery.md)

* [Berichten activeren](../send/transactional.md) van een gebeurtenis

* Uw berichten plannen

   ![](assets/schedule-send.png)

[Hoofdlettergebruik: leren plannen en een verjaardagsbericht verzenden](../../automation/workflow/send-a-birthday-email.md)


## Aanpassing toevoegen{#personalization}

Berichten die door Adobe Campaign worden geleverd, kunnen op verschillende manieren worden gepersonaliseerd. [Meer informatie over personalisatiemogelijkheden](../send/personalize.md)

U kunt:

* Dynamische personalisatievelden invoegen. [Meer informatie](../send/personalization-fields.md)
* Vooraf gedefinieerde aanpassingsblokken invoegen. [Meer informatie](../send/personalization-blocks.md)
* Voorwaardelijke content maken. [Meer informatie](../send/conditions.md)

## Transactieberichten verzenden{#gs-transac-messages}

Transactioneel overseinen (het Centrum van het Bericht) is de module van de Campagne die voor het beheren van trekkerberichten wordt ontworpen.

![](../assets/do-not-localize/glass.png) Meer informatie over de mogelijkheid van transactieberichten vindt u in [deze sectie](../architecture/architecture.md#transac-msg-archi)

![](../assets/do-not-localize/glass.png) De stappen om transactieberichten te vormen en te verzenden zijn gedetailleerd in [deze pagina](../send/transactional.md)

![](../assets/do-not-localize/book.png) Ontdek deze mogelijkheid in een gebruiksgeval van begin tot eind [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html){target="_blank"}

## Logbestanden voor aflevering en bijhouden{#gs-tracking-logs}

Het controleren van uw leveringen nadat deze zijn verzonden, is een belangrijke stap om ervoor te zorgen dat uw marketingcampagnes efficiënt zijn en uw klanten bereiken. U kunt controleren na het verzenden van een levering, evenals begrijpen hoe de leveringsmislukkingen en quarantines worden beheerd.

![](../assets/do-not-localize/book.png) Leer hoe u uw leveringen kunt controleren in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target="_blank"}

