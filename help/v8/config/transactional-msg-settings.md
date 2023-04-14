---
title: Campagne Transactionele overseinenmontages
description: Campagne Transactionele overseinenmontages
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 6%

---

# Transactionele berichtinstellingen

![](../assets/do-not-localize/speech.png) Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support) om het Transactionele overseinen van de Campagne in uw milieu te installeren en te vormen.

![](../assets/do-not-localize/glass.png) Transactionele berichtenmogelijkheden zijn gedetailleerd in [deze sectie](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Begrijp transactie overseinenarchitectuur in [deze pagina](../architecture/architecture.md#transac-msg-archi).

## Machtigingen definiëren

Als u nieuwe gebruikers wilt maken voor de uitvoering van Message Center-berichten die worden gehost op Adobe Cloud, dient u contact op te nemen met de klantenservice van Adobe. De gebruikers van het Centrum van het bericht zijn specifieke exploitanten die specifieke toestemmingen vereisen om tot omslagen &quot;In real time gebeurtenissen&quot; (nmsRtEvent) toegang te hebben.

## Schema-extensies

Alle schemauitbreidingen die op de schema&#39;s worden gemaakt door worden gebruikt **Technische workflows voor Message Center** op of controle of uitvoeringsinstanties moeten op de andere instanties worden gedupliceerd die door de module van het de transactiemelding van Adobe Campaign worden gebruikt.

![](../assets/do-not-localize/book.png) Meer informatie over technische workflows in Berichtencentrum in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Transactie-pushmeldingen verzenden

In combinatie met de module Mobiele toepassingskanalen kunt u met transactiemeldingen transactionele berichten verzenden via meldingen op mobiele apparaten.

![](../assets/do-not-localize/book.png) Het mobiele toepassingskanaal wordt gedetailleerd in [deze sectie](../send/push.md).

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

## Drempels controleren {#monitor-thresholds}

U kunt de waarschuwingsdrempels (oranje) en waakzame drempels (rood) van de indicatoren vormen die in verschijnen **Serviceniveau van Message Center** en **Verwerkingstijd van Message Center** rapporten.

Volg de onderstaande stappen om dit te doen:

1. Open de implementatiewizard op de **uitvoeringsinstantie** en blader naar de **[!UICONTROL Message Center]** pagina.
1. Gebruik de pijlen om de drempels te veranderen.


## Gebeurtenissen opschonen {#purge-events}

U kunt de montages van de plaatsingstovenaar aanpassen om te vormen hoe lang de gegevens in het gegevensbestand moeten worden opgeslagen.

Gebeurtenissen worden automatisch door de **Database opschonen** technische workflow. Dit werkschema zuiveert de gebeurtenissen die op de uitvoeringsinstanties en de gebeurtenissen worden ontvangen en worden opgeslagen die op een controleinstantie worden gearchiveerd.

Gebruik de pijlen naar wens om de purgeerinstellingen voor de **Gebeurtenissen** (op een uitvoeringsinstantie) en **Gearchiveerde gebeurtenissen** (op een besturingsinstantie).


## Technische workflows {#technical-workflows}

U moet ervoor zorgen dat de technische werkschema&#39;s op uw controle en uitvoeringsinstanties zijn begonnen alvorens om het even welke transactionele berichtmalplaatjes op te stellen.

Deze workflows zijn vervolgens toegankelijk via de **Beheer > Productie > Berichtencentrum** map.

### Workflows voor besturingsinstanties {#control-instance-workflows}

Voor de controleinstantie, moet u één archiveringswerkschema voor elk creëren **[!UICONTROL Message Center execution instance]** externe rekening. Klik op de knop **[!UICONTROL Create the archiving workflow]** om de workflow te maken en te starten.

### Workflows voor uitvoeringsinstanties {#execution-instance-workflows}

In de uitvoeringsinstantie(s) moet u de volgende technische workflows starten:

* **[!UICONTROL Processing batch events]** (interne naam: **[!UICONTROL batchEventsProcessing]** ): met deze workflow kunt u batchgebeurtenissen in een wachtrij onderverdelen voordat deze aan een berichtsjabloon zijn gekoppeld.
* **[!UICONTROL Processing real time events]** (interne naam: **[!UICONTROL rtEventsProcessing]** ): met deze workflow kunt u real-time gebeurtenissen in een wachtrij onderverdelen voordat deze aan een berichtsjabloon zijn gekoppeld.
* **[!UICONTROL Update event status]** (interne naam: **[!UICONTROL updateEventStatus]** ): in deze workflow kunt u een status aan de gebeurtenis toewijzen.

   Mogelijke gebeurtenisstatussen zijn:

   * **[!UICONTROL Pending]**: de gebeurtenis bevindt zich in de wachtrij. Er is nog geen berichtsjabloon aan toegewezen.
   * **[!UICONTROL Pending delivery]**: de gebeurtenis is in de rij, is een berichtmalplaatje toegewezen aan het en het wordt verwerkt door de levering.
   * **[!UICONTROL Sent]**: deze status wordt gekopieerd uit de leveringslogboeken. Dit betekent dat de levering is verzonden.
   * **[!UICONTROL Ignored by the delivery]**: deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is genegeerd.
   * **[!UICONTROL Delivery failed]**: deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is mislukt.
   * **[!UICONTROL Event not taken into account]**: de gebeurtenis kon niet aan een berichtmalplaatje worden verbonden. De gebeurtenis wordt niet verwerkt.
