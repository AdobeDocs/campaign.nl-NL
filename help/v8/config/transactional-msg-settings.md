---
title: Campagne Transactionele overseinenmontages
description: Campagne Transactionele overseinenmontages
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 5%

---

# Transactionele berichtinstellingen

Transactioneel overseinen (het Centrum van het Bericht) is een module van de Campagne die voor het beheren van teweeggebrachte berichten wordt ontworpen. Meer informatie over Transactieberichten in [deze sectie](../send/transactional.md).

Begrijp transactie overseinenarchitectuur in [deze pagina](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support) om het Transactionele overseinen van de Campagne in uw milieu te installeren en te vormen.

## Machtigingen definiëren

Als u nieuwe gebruikers wilt maken voor de uitvoering van Message Center-berichten die worden gehost op Adobe Cloud, dient u contact op te nemen met de klantenservice van Adobe. De gebruikers van het Centrum van het bericht zijn specifieke exploitanten die specifieke toestemmingen vereisen om tot omslagen &quot;In real time gebeurtenissen&quot; (nmsRtEvent) toegang te hebben.

## Schema-extensies

Alle schemauitbreidingen die op de schema&#39;s worden gemaakt door worden gebruikt [Technische workflows voor Message Center](#technical-workflows) op of controle of uitvoeringsinstanties moeten op de andere instanties worden gedupliceerd die door de module van het de transactiemelding van Adobe Campaign worden gebruikt.

## Transactie-pushmeldingen verzenden

Indien gecombineerd met [Mobiele toepassingskanaalmodule](../send/push.md)kunt u transactiemeldingen uitvoeren via meldingen op mobiele apparaten.

Als u pushmeldingen over transacties wilt verzenden, moet u de volgende configuraties uitvoeren:

1. Installeer de **Mobiel App-kanaal** verpakken op de controle en uitvoeringsinstanties.

   >[!CAUTION]
   >
   >Controleer uw licentieovereenkomst voordat u een nieuw ingebouwd pakket voor de campagne installeert.

1. Repliceer de **Mobiele toepassing** en de bijbehorende mobiele toepassingen op de uitvoeringsinstanties.

Bovendien moet de gebeurtenis de volgende elementen bevatten:

* De mobiele apparaat-id: **registrationId** voor Android en **deviceToken** voor iOS. Deze ID vertegenwoordigt het &quot;adres&quot;dat het bericht wordt verzonden naar.
* De koppeling naar de mobiele toepassing of integratietoets (**uuid**) waarmee u verbindingsgegevens kunt ophalen die specifiek zijn voor de toepassing.
* Het kanaal waarnaar de melding wordt verzonden (**wishedChannel**): 41 voor iOS en 42 voor Android.
* Alle andere verpersoonlijkingsgegevens.

Hieronder ziet u een voorbeeld van een gebeurtenisconfiguratie voor het verzenden van pushmeldingen over transacties:

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
