---
product: Adobe Campaign
title: Stapelmechanisme voor campagne-API
description: Stapelmechanisme voor campagne-API
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 3%

---

# Stapelmechanisme voor campagne-API

Met de Campaign Cloud-database worden algemene aanroepen niet aanbevolen vanwege de prestaties (latentie en gelijktijdige uitvoering). Batchbewerking heeft altijd de voorkeur. Om optimale prestaties van APIs te waarborgen, blijft de Campagne API vraag op het lokale gegevensbestandniveau behandelen.

Het het opvoeren van de campagne mechanisme is beschikbaar voor zowel ingebouwde als douanetabel en brengt de volgende voordelen:

* De structuur van het gegevensschema wordt herhaald in de lokale het opvoeren lijst
* Nieuwe API&#39;s voor inname vloeien rechtstreeks over naar de testtabel. [Meer informatie](new-apis.md)
* Een geplande workflow activeert elk uur en synchroniseert gegevens weer naar de Cloud Database. [Meer informatie](../config/replication.md).

Sommige ingebouwde schema&#39;s zijn standaard gefaseerd, zoals nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

API&#39;s voor Campaign Classic v7 zijn nog steeds beschikbaar, maar kunnen niet profiteren van dit nieuwe staging-mechanisme: API-aanroepen gaan rechtstreeks naar de Cloud-database. Adobe raadt u aan zoveel mogelijk gebruik te maken van het nieuwe mechanisme voor het opslaan van bestanden om de algehele druk en latentie op de Campagne Cloud-database te verminderen.

>[!CAUTION]
>
>Met dit nieuwe mechanisme is gegevenssynchronisatie voor abonnementen, abonnementen of mobiele registratie nu **asynchroon**.


## Implementatiestappen{#implement-staging}

Voer de volgende stappen uit om het staging-mechanisme voor campagnes op een specifieke tabel toe te passen:

1. Maak een aangepast voorbeeldschema voor de Campagne Cloud-database. Geen plaatsing ingeschakeld in deze stap.

   ```
   <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

   [!DNL :bulb:] Meer informatie over het maken van aangepaste schema&#39;s vindt u op  [deze pagina](create-schema.md).

1. Sla de databasestructuur op en werk deze bij.  [Meer informatie](update-database-structure.md)

1. Laat het het opvoeren mechanisme in de schemadefinitie toe door **autoStg=&quot;waar&quot;** parameter toe te voegen.

   ```
   <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

1. Sla de wijziging op. Er is een nieuw staging-schema beschikbaar. Dit is een lokale kopie van het oorspronkelijke schema.

   ![](assets/staging-mechanism.png)

1. Werk de databasestructuur bij. De testtabel wordt gemaakt in de lokale database van Campagne.
