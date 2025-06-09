---
title: Gegevensreplicatie
description: Technische workflows en gegevensreplicatie
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: b8f774ce507cff67163064b6bd1341b31512c08f
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 2%

---


# Gegevensreplicatie {#wf-data-replication}

## Beginsel

In de context van een [ plaatsing van de Onderneming (FFDA) ](enterprise-deployment.md), zorgt de gegevensreplicatie ervoor dat de twee gegevensbestanden, het lokale gegevensbestand van de Campagne (PostgreSQL) en het gegevensbestand van de Wolk ([!DNL Snowflake]), in parallel operationeel zijn en in real time gesynchroniseerd blijven.

De Cloud-database ([!DNL Snowflake]) is geoptimaliseerd voor het verwerken van grote gegevensbatches, zoals het bijwerken van 1 miljoen adressen. Ondertussen, is het lokale gegevensbestand van de Campagne (PostgreSQL) geschikter voor individuele of kleine volumeverrichtingen, als het bijwerken van één enkel zaadadres. De synchronisatie komt automatisch en transparant op de achtergrond voor, die ervoor zorgt dat gegevens in Lokale gegevensbestand van de Campagne (PostSQL) in het gegevensbestand van de Wolk ([!DNL Snowflake]) in real time worden gedupliceerd, die beide gegevensbestanden houden gesynchroniseerd. De synchronisatie van gegevens impliceert schema&#39;s en lijsten, en gegevens.

➡️ [ ontdekt hoe de gegevensreplicatie in video ](#video) werkt

## Replicatiemodi {#modes}

De replicatie van gegevens kan op verschillende wijzen afhankelijk van het gebruiksgeval voorkomen.

* **handvatten van de replicatie op de vlucht** gevallen waar de duplicatie in real time essentieel is. Het baseert zich op specifieke technische draden om gegevens voor gebruiksgevallen zoals het creëren van een verspreiding of het bijwerken van een zaadadres onmiddellijk te herhalen.
* **Geplande replicatie** wordt gebruikt wanneer de directe synchronisatie niet wordt vereist. De geplande replicatie gebruikt specifieke [ technische werkschema&#39;s ](#workflows) die elk uur in werking stellen om gegevens, zoals typologische regels te synchroniseren.

## Replicatiebeleid

Het beleid van de replicatie bepaalt hoeveel gegevens van een lokale gegevensbestand van de Campagne (PostSQL) lijst worden herhaald. Dit beleid hangt van de grootte van de lijst en het specifieke gebruiksgeval af. Sommige tabellen hebben incrementele updates wanneer andere volledig worden gerepliceerd. Er zijn drie belangrijke soorten replicatiebeleid:

* **XS**: Dit beleid wordt gebruikt voor lijsten met vrij kleine grootte. De hele tabel wordt in één opname gerepliceerd. Met incrementele replicatie wordt voorkomen dat dezelfde gegevens herhaaldelijk worden herhaald door een tijdstempelaanwijzer te gebruiken om alleen recente wijzigingen te repliceren.
* **SingleRow**: Dit beleid herhaalt slechts één rij tegelijkertijd. Het wordt doorgaans gebruikt voor replicatie ter plekke waarbij de huidige Campagneobjecten en verwante objecten worden betrokken.
* **SomeRows**: Dit beleid wordt ontworpen voor het herhalen van een beperkte ondergroep van gegevens gebruikend vraagdefinities of filters. Het wordt gebruikt voor grotere lijsten waar de selectieve replicatie noodzakelijk is.

## Replicatiewerkstromen {#workflows}

Campagne v8 is gebaseerd op specifieke technische workflows voor het beheer van geplande gegevensreplicatie. Deze technische workflows zijn beschikbaar via het knooppunt **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** van Campagne Explorer. **zij moeten niet worden gewijzigd.**

Technische workflows voeren processen of taken uit, die regelmatig op de server worden gepland. De volledige lijst van technische werkschema&#39;s wordt gedetailleerd in [ deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=nl-NL){target="_blank"}.

De technische werkschema&#39;s die gegevensreplicatie verzekeren zijn als volgt:

| Technische workflow | Beschrijving |
|------|-----------|
| **[!UICONTROL Replicate Reference tables]** (ffdaReplicateReferenceTables) | Voert automatische replicatie van ingebouwde lijsten uit die op het lokale gegevensbestand van de Campagne (PostgreSQL) en het gegevensbestand van de Wolk ([!DNL Snowflake]) aanwezig moeten zijn. Het is gepland om elk uur uit te voeren, dagelijks. Als **lastModified** gebied bestaat, gebeurt de replicatie incrementeel, anders wordt de volledige lijst herhaald. |
| **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) | Herhaalt het opvoeren gegevens voor unitaire vraag. Het is gepland om elk uur uit te voeren, dagelijks. |
| **[!UICONTROL Deploy FFDA immediately]** (ffdaDeploy) | Voert een onmiddellijke plaatsing aan het gegevensbestand van de Wolk uit. |
| **[!UICONTROL Replicate FFDA data immediately]** (ffdaReplicate) | Repliceert de XS-gegevens voor een bepaalde externe account. |

Indien nodig kunt u de gegevenssynchronisatie handmatig starten. Om dit te doen, klik op de **Planner** activiteit met de rechtermuisknop aan en selecteer **uitvoeren hangende taak(s) nu**.

Naast het ingebouwde **technische werkschema van de Verwijzing 0&rbrace; Repliceren**, kunt u gegevensreplicatie in uw werkschema&#39;s dwingen gebruikend één van deze methodes

+++Hoe te om gegevensreplicatie te dwingen

* Voeg een specifieke **Javascript code** activiteit met de volgende code toe:

  ```
  nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
  ```

  ![](assets/jscode.png)

* Voeg een specifieke **nlmodule** activiteit met het volgende bevel toe:

  ```
  nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
  ```

  ![](assets/nlmodule.png)

+++

<br/>

>[!NOTE]
>
>De replicatie ter plekke wordt behandeld door specifieke technische draden eerder dan werkschema&#39;s. De configuratie voor deze wijze wordt beheerd in het serverConf.xml- dossier. U kunt serverConf.xml vormen om specifieke gebruiksgevallen aan te passen, zoals het verzoeken dat de lijsten XS stapsgewijs eerder dan volledig worden herhaald. Neem voor meer informatie contact op met uw Adobe-vertegenwoordiger.

## API&#39;s

APIs laat replicatie van zowel douane als uit-van-de-doosgegevens van het lokale gegevensbestand van de Campagne (PostgreSQL) aan het gegevensbestand van de Wolk ([!DNL Snowflake]) toe. Met deze API&#39;s kunt u vooraf gedefinieerde workflows omzeilen en replicatie aanpassen voor specifieke vereisten, zoals het repliceren van aangepaste tabellen.

Voorbeeld:

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="cus:recipient"/>
    </params>
);
```

## Replicatierijen

Wanneer de hoge volumes van replicatieverzoeken gelijktijdig voorkomen, kunnen de prestatieskwesties in het gegevensbestand van de Wolk ([!DNL Snowflake]) toe te schrijven aan lijst-vlakke sloten tijdens de verrichtingen van de FUSIE zich voordoen. Om dit te verlichten, gecentraliseerde verzoeken van de de groep van replicatiewerkschema&#39;s in rijen.

Elke rij wordt behandeld door een technisch werkschema, dat replicatie voor een specifieke lijst beheert, uitvoerend hangende verzoeken als één enkele verrichting van de SAMENVOEGING. Deze werkschema&#39;s worden teweeggebracht om de 20 seconden om nieuwe replicatieverzoeken te verwerken:

| Technische workflow | Beschrijving |
|------|-----------|
| **Replicate nmsDelivery rij** (ffdaReplicateQueueDelivery) | Wachtrij voor de tabel `nms:delivery` . |
| **Replicate nmsDlvExclusion rij** (ffdaReplicateQueueDlvExclusion) | Wachtrij voor de tabel `nms:dlvExclusion` . |
| **Replicate nmsDlvMidRemoteIdRel rij** (ffdaReplicateQueueDlvMidRemoteIdRel) | Wachtrij voor de tabel `nms:dlvRemoteIdRel` . |
| **Replicate nmsTrackingUrl rij** (ffdaReplicateQueueTrackingUrl) <br/>**Replicate nmsTrackingUrl rij in gelijktijdig** (ffdaReplicateQueueTrackingUrl_2) | Hiermee wordt een wachtrij geplaatst voor de tabel `nms:trackingUrl` , waarbij twee workflows worden gebruikt om de efficiëntie te verbeteren door aanvragen te verwerken op basis van verschillende prioriteiten. |

## Tutorial {#video}

In deze video worden de belangrijkste concepten beschreven van welke databases Adobe Campaign v8 gebruikt, waarom gegevens worden gerepliceerd, welke gegevens worden gerepliceerd en hoe het replicatieproces werkt.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)

De extra leerprogramma&#39;s van de Console van de Campagne v8 van de Cliënt zijn beschikbaar [ hier ](https://experienceleague.adobe.com/nl/docs/campaign-learn/tutorials/overview).
