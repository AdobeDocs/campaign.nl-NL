---
title: Campagne Transactionele overseinenmontages
description: Campagne Transactionele overseinenmontages
feature: Transactional Messaging
role: Admin, Developer
level: Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 4%

---

# Transactionele berichtinstellingen {#mc-settings}

Transactioneel overseinen (het Centrum van het Bericht) is een module van de Campagne die voor het beheren van teweeggebrachte berichten wordt ontworpen. Leer meer over Transactioneel overseinen in [ deze sectie ](../send/transactional.md).

Begrijp transactie overseinenarchitectuur in [ deze pagina ](../architecture/architecture.md#transac-msg-archi).


>[!NOTE]
>
>Als Beheerde gebruiker van de Diensten van de Wolk, [ contacteer Adobe ](../start/campaign-faq.md#support) om het Transactionele overseinen van de Campagne in uw milieu te installeren en te vormen.

## Machtigingen definiëren {#mc-permissions}

Neem contact op met uw Adobe Transition Manager als u nieuwe gebruikers wilt maken voor Message Center-uitvoeringsinstanties die worden gehost op Adobe Cloud. De gebruikers van het Centrum van het bericht zijn specifieke exploitanten die specifieke toestemmingen om tot omslagen &quot;Real time gebeurtenissen&quot;(nmsRtEvent) vereisen toegang te hebben.

## Schema-extensies  {#mc-schema-ext}

Alle schemauitbreidingen die op de schema&#39;s worden gemaakt door [ technische werkschema&#39;s van het Centrum van het Bericht ](#technical-workflows) op of controle of uitvoeringsinstanties worden gebruikt moeten op de andere instanties worden gedupliceerd die door de module van het de transactiemelding van Adobe Campaign worden gebruikt.

## Transactie-pushmeldingen verzenden {#mc-transactional-push}

Wanneer gecombineerd met [ Mobiele module van het toepassingskanaal ](../send/push.md), laat het transactionele overseinen u toe om transactionele berichten door berichten op mobiele apparaten te duwen.

Als u pushmeldingen over transacties wilt verzenden, moet u de volgende configuraties uitvoeren:

1. Installeer het **Mobiele pakket van het Kanaal van de App** op de controle en uitvoeringsinstanties.

   >[!CAUTION]
   >
   >Controleer uw licentieovereenkomst voordat u een nieuw, ingebouwd pakket voor de campagne installeert.

1. Herhaal de **Mobiele toepassings** dienst en de bijbehorende mobiele toepassingen op de uitvoeringsinstanties.

Bovendien moet de gebeurtenis de volgende elementen bevatten:

* Mobiele apparatenidentiteitskaart: **registrationId** voor Android en **deviceToken** voor iOS. Deze ID vertegenwoordigt het &quot;adres&quot;dat het bericht wordt verzonden naar.
* De verbinding aan de mobiele toepassing of de integratiesleutel (**uuid**) die u verbindingsinformatie specifiek voor de toepassing laat terugwinnen.
* Het kanaal waarnaar het bericht zal worden verzonden (**wishedChannel**): 41 voor iOS en 42 voor Android.
* Alle andere verpersoonlijkingsgegevens.

Hieronder ziet u een voorbeeld van een gebeurtenisconfiguratie voor het verzenden van pushmeldingen over transacties:

```xml
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
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

De ontruiming van de gebeurtenis wordt uitgevoerd automatisch door het **technische werkschema van de Opschoonmaakbeurt van het 0&rbrace; Gegevensbestand.** Dit werkschema zuiveert de gebeurtenissen die op de uitvoeringsinstanties en de gebeurtenissen worden ontvangen en worden opgeslagen die op een controleinstantie worden gearchiveerd.

Gebruik de pijlen zoals aangewezen om de zuiveringsmontages voor de **Gebeurtenissen** (op een uitvoeringsinstantie) en **Gearchiveerde gebeurtenissen** (op een controleinstantie) te veranderen.


## Technische workflows {#technical-workflows}

U moet ervoor zorgen dat de technische werkschema&#39;s op uw controle en uitvoeringsinstanties zijn begonnen alvorens om het even welke transactionele berichtmalplaatjes op te stellen.

Deze werkschema&#39;s kunnen dan van het **Beleid > de Productie > het Centrum van het Bericht** omslag worden betreden.

### Workflows voor besturingsinstanties {#control-instance-workflows}

In de besturingsinstantie moet u één archiveringsworkflow maken voor elke **[!UICONTROL Message Center execution instance]** externe account. Klik op de knop **[!UICONTROL Create the archiving workflow]** om de workflow te maken en te starten.

### Workflows voor uitvoeringsinstanties {#execution-instance-workflows}

In de uitvoeringsinstantie(s) moet u de volgende technische workflows starten:

* **[!UICONTROL Processing batch events]** (interne naam: **[!UICONTROL batchEventsProcessing]** ): met deze workflow kunt u batchgebeurtenissen in een wachtrij onderbreken voordat ze aan een berichtsjabloon zijn gekoppeld.
* **[!UICONTROL Processing real time events]** (interne naam: **[!UICONTROL rtEventsProcessing]** ): met deze workflow kunt u real-time gebeurtenissen in een wachtrij onderbreken voordat deze aan een berichtsjabloon worden gekoppeld.
* **[!UICONTROL Update event status]** (interne naam: **[!UICONTROL updateEventStatus]** ): met deze workflow kunt u een status aan de gebeurtenis toewijzen.

  Mogelijke gebeurtenisstatussen zijn:

   * **[!UICONTROL Pending]**: de gebeurtenis bevindt zich in de wachtrij. Er is nog geen berichtsjabloon aan toegewezen.
   * **[!UICONTROL Pending delivery]**: de gebeurtenis bevindt zich in de wachtrij, er is een berichtsjabloon toegewezen aan de gebeurtenis en deze wordt verwerkt door de levering.
   * **[!UICONTROL Sent]**: deze status wordt gekopieerd uit de leveringslogboeken. Dit betekent dat de levering is verzonden.
   * **[!UICONTROL Ignored by the delivery]**: deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is genegeerd.
   * **[!UICONTROL Delivery failed]**: deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is mislukt.
   * **[!UICONTROL Event not taken into account]** : de gebeurtenis kan niet worden gekoppeld aan een berichtsjabloon. De gebeurtenis wordt niet verwerkt.
