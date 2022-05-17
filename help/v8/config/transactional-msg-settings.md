---
title: Campagne Transactionele overseinenmontages
description: Campagne Transactionele overseinenmontages
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Transactionele berichtinstellingen

![](../assets/do-not-localize/speech.png)  Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support) om het Transactionele overseinen van de Campagne in uw milieu te installeren en te vormen.

![](../assets/do-not-localize/glass.png) Transactionele berichtenmogelijkheden zijn gedetailleerd in [deze sectie](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Begrijp transactie overseinenarchitectuur in [deze pagina](../dev/architecture.md).

## Machtigingen definiëren

Als u nieuwe gebruikers wilt maken voor de uitvoering van Message Center-berichten die worden gehost op Adobe Cloud, dient u contact op te nemen met de klantenservice van Adobe. De gebruikers van het Centrum van het bericht zijn specifieke exploitanten die specifieke toestemmingen vereisen om tot omslagen &quot;In real time gebeurtenissen&quot; (nmsRtEvent) toegang te hebben.

## Schema-extensies

Alle schemauitbreidingen die op de schema&#39;s worden gemaakt door worden gebruikt **Technische workflows voor Message Center** op of controle of uitvoeringsinstanties moeten op de andere instanties worden gedupliceerd die door de module van het de transactiemelding van Adobe Campaign worden gebruikt.

![](../assets/do-not-localize/book.png) Meer informatie over technische workflows in Berichtencentrum in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Transactie-pushmeldingen verzenden

In combinatie met de module Mobiele toepassingskanalen kunt u met transactiemeldingen transactionele berichten verzenden via meldingen op mobiele apparaten.

![](../assets/do-not-localize/book.png) Het mobiele toepassingskanaal wordt gedetailleerd in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

Als u pushmeldingen over transacties wilt verzenden, moet u de volgende configuraties uitvoeren:

1. Installeer de **Mobiel App-kanaal** verpakken op de controle en uitvoeringsinstanties.

   >[!CAUTION]
   >
   >Controleer uw licentieovereenkomst voordat u een nieuw ingebouwd pakket voor de campagne installeert.

1. Repliceer de **Mobiele toepassing** en de bijbehorende mobiele toepassingen op de uitvoeringsinstanties.

Campagne kan alleen transactionele pushmeldingen verzenden als de gebeurtenis de volgende elementen bevat:

* De mobiele apparaat-id: **registrationId** voor Android en **deviceToken** voor iOS. Deze ID vertegenwoordigt het &quot;adres&quot;dat het bericht zal worden verzonden naar.
* De koppeling naar de mobiele toepassing of integratietoets (**uuid**) waarmee u verbindingsgegevens kunt ophalen die specifiek zijn voor de toepassing.
* Het kanaal waarnaar de melding wordt verzonden (**wishedChannel**): 41 voor iOS en 42 voor Android.
* Andere gegevens die kunnen worden gebruikt voor personalisatie.

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
