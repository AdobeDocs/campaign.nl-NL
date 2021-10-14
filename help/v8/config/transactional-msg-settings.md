---
title: Campagne Transactionele overseinenmontages
description: Campagne Transactionele overseinenmontages
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Transactional messaging settings

![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to install and configure Campaign Transactional messaging in your environment.

![](../assets/do-not-localize/glass.png) Transactionele berichtenmogelijkheden worden beschreven in  [deze sectie](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Understand transactional messaging architecture in [this page](../dev/architecture.md).

## Define permissions

Als u nieuwe gebruikers wilt maken voor de uitvoering van Message Center-berichten die worden gehost op Adobe Cloud, dient u contact op te nemen met de klantenservice van Adobe. Message Center users are specific operators that require dedicated permissions to access ‘Real time events’ (nmsRtEvent) folders.

## Schema-extensies

All schema extensions made on the schemas used by **Message Center technical workflows** on either control or execution instances need to be duplicated on the other instances used by Adobe Campaign transactional messaging module.

![](../assets/do-not-localize/book.png) Meer informatie over technische workflows in het Berichtencentrum in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Transactie-pushmeldingen verzenden

In combinatie met de module Mobiele toepassingskanalen kunt u met transactiemeldingen transactionele berichten verzenden via meldingen op mobiele apparaten.

![](../assets/do-not-localize/book.png) Het kanaal van de Mobiele app is gedetailleerd in  [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

Als u pushmeldingen over transacties wilt verzenden, moet u de volgende configuraties uitvoeren:

1. Install the **Mobile App Channel** package onto the control and execution instances.

   >[!CAUTION]
   >
   >Check your license agreement before installing a new Campaign built-in package.

1. Replicate the **Mobile application** service and the associated mobile applications on the execution instances.

Campagne kan alleen transactionele pushmeldingen verzenden als de gebeurtenis de volgende elementen bevat:

* De mobiele apparaat-id: **registrationId** voor Android en **deviceToken** voor iOS. This ID represents the &quot;address&quot; that the notification will be sent to.
* De koppeling naar de mobiele toepassing of integratietoets (**uuid**) waarmee u verbindingsgegevens kunt ophalen die specifiek zijn voor de toepassing.
* The channel to which the notification will be sent (**wishedChannel**): 41 for iOS and 42 for Android.
* Other data to leverage for personalization.

Hier volgt een voorbeeld van een gebeurtenis die deze informatie bevat:

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
