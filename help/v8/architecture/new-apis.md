---
title: Nieuwe API's voor campagne v8
description: Nieuwe API's voor campagne v8
feature: Architecture, API, FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: dd822f88-b27d-4944-879c-087f68e79825
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# Specifieke API&#39;s voor campagnes van FFDA{#gs-new-api}

In de context van een [Implementatie in het kader van Enterprise (FFDA)](enterprise-deployment.md)Campagne v8 wordt geleverd met twee specifieke API&#39;s voor het beheer van gegevens tussen de lokale database van Campagne en de Cloud-database. De voorwaarden om hen te gebruiken moeten het het opvoeren mechanisme op het schema toelaten. [Meer informatie](staging.md)

* Ingestie-API: **xtk.session.ingest**

  Deze API is alleen bedoeld voor het invoegen van gegevens. [Meer informatie](#data-insert-api)

* API voor bijwerken/verwijderen van gegevens: **xtk.session.ingestExt**

  Deze API wordt gebruikt om gegevens bij te werken of te schrappen. [Meer informatie](#data-update-api)

Met een speciale ingebouwde workflow worden de gegevens in de cloud-database gesynchroniseerd.

## Gegevens invoegen{#data-insert-api}

De **xtk.session.ingest** API is alleen bestemd voor gegevensinvoer. Geen update/verwijdering.

### Invoegen zonder afstemming{#insert-no-reconciliation}

**In een workflow**

Gebruik de volgende code in een **Javascript-code** activiteit om gegevens in het gegevensbestand van de Wolk zonder aanpassing op te nemen:

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Nadat de werkstroom is uitgevoerd, wordt de testtabel op de verwachte manier ingevoerd.

**Van een SOAP-aanroep**

1. Haal het verificatietoken op.
1. Trigger de API. De lading is:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:Ingest>
           <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
           <urn:domDoc>
               <sampleTableStg
                   testcol1="Test Value 1 (from SOAP)"
                   testcol2="Test Value 2 (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:Ingest>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. UUID wordt teruggestuurd naar de reactie van de ZEEP:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Hierdoor wordt de testtabel op de verwachte manier gevoed.

![](assets/no-reconciliation.png)

### Invoegen met reconciliatie

**In een workflow**

Gebruik de volgende code in een **Javascript-code** activiteit om gegevens in het gegevensbestand van de Wolk met verenigbaarheid op te nemen:

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Nadat de werkstroom is uitgevoerd, wordt de testtabel op de verwachte manier ingevoerd.

![](assets/with-reconciliation.png)


**Van een SOAP-aanroep**

1. Haal het verificatietoken op.
1. Trigger de API. De lading is:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
     <urn:Ingest>
        <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
        <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                testcol1="Test Value 1 (from SOAP)"
                testcol2="Test Value 2 (from SOAP)"
                xtkschema="dem:sampleTableStg">
            </sampleTableStg>
        </urn:domDoc>
     </urn:Ingest>
    </soapenv:Body>
   </soapenv:Envelope>
   ```

1. In dit geval wordt UUID niet teruggestuurd naar de reactie omdat deze in de lading is opgegeven. Het antwoord is:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string"/>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Hierdoor wordt de testtabel op de verwachte manier gevoed.

## Gegevens bijwerken of verwijderen{#data-update-api}

De **xtk.session.IngestExt** API is geoptimaliseerd voor bijwerken/verwijderen van gegevens. Alleen invoegen, voorkeur **xtk.session.ingest**. Invoegen werkt of de recordsleutel zich niet in de testtabel bevindt.

### Invoegen/bijwerken

**In een workflow**

Gebruik de volgende code in een **Javascript-code** activiteit om gegevens in het gegevensbestand van de Wolk bij te werken:

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

Nadat de workflow is uitgevoerd, wordt de testtabel op de verwachte manier bijgewerkt.

![](assets/updated-data.png)

**Van een SOAP-aanroep**

1. Haal het verificatietoken op.
1. Trigger de API. De lading is:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:IngestExt>
           <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
           <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                   testcol1="Test Value E (from SOAP)"
                   testcol2="Test Value F (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:IngestExt>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. De SOAP-reactie is:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Dientengevolge, wordt het opvoeren lijst bijgewerkt zoals verwacht.

## Abonnementsbeheer {#sub-apis}

Abonnementsbeheer in campagne wordt beschreven in [deze pagina](../start/subscriptions.md).

Het invoegen van abonnements- en abonnementsgegevens is afhankelijk van de [Stapelmechanisme](staging.md) in de lokale database van Campagne. De informatie van de abonnee is tijdelijk opgeslagen in het opvoeren van lijsten in het lokale gegevensbestand, en het synchronisatiewerkschema verzendt deze gegevens van het lokale gegevensbestand naar het gegevensbestand van de Wolk. Als gevolg hiervan zijn de processen voor abonnementen en abonnementen **asynchroon**. Aanvragen om te weigeren of te weigeren worden elk uur verwerkt via een specifieke technische workflow. [Meer informatie](replication.md#tech-wf)


**Verwante onderwerpen**

* [Campaign-JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
