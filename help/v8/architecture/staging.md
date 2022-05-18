---
title: Stapelmechanisme voor campagne-API
description: Stapelmechanisme voor campagne-API
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Stapelmechanisme voor campagne-API

In de context van een [Implementatie van ondernemingen (FFDA)](enterprise-deployment.md)Wat betreft de prestaties (latentie en gelijktijdige uitvoering) wordt het gebruik van ononderbroken unitaire oproepen niet aanbevolen. Batchbewerking heeft altijd de voorkeur. Om de prestaties te verbeteren, worden API&#39;s voor inname omgeleid naar de lokale database.

De het opvoeren van de campagne capaciteit wordt toegelaten door gebrek op sommige ingebouwde schema&#39;s. Wij kunnen het op om het even welk douaneschema ook toelaten. Staging mechanisme in een notendop:

* De structuur van het gegevensschema wordt gedupliceerd in de lokale het opvoeren lijst
* Nieuwe API&#39;s die zijn toegewezen aan gegevensinvoer vloeien rechtstreeks over naar de lokale staging-tabel. [Meer informatie](new-apis.md)
* Een geplande workflow activeert elk uur en synchroniseert gegevens weer naar de Cloud Database. [Meer informatie](replication.md)

Sommige ingebouwde schema&#39;s zijn standaard gefaseerd, zoals nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

API&#39;s voor Campaign Classic v7 zijn nog steeds beschikbaar, maar kunnen niet profiteren van dit nieuwe staging-mechanisme: API-aanroepen gaan rechtstreeks naar de Cloud-database. Adobe raadt u aan zoveel mogelijk gebruik te maken van het nieuwe mechanisme voor het opslaan van bestanden om de algehele druk en latentie op de Campagne Cloud-database te verminderen.

>[!CAUTION]
>
>* Met dit nieuwe mechanisme is de gegevenssynchronisatie voor kanaaloptout, abonnementen, abonnementen of mobiele registratie nu **asynchroon**.
>
>* Staging is alleen van toepassing op schema&#39;s die zijn opgeslagen in de cloud-database. Laat het opvoeren op herhaalde schema&#39;s niet toe. Schakel Staging niet in voor lokale schema&#39;s. Staging niet inschakelen in een schema met werkstadia
>


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

   ![](../assets/do-not-localize/glass.png) Meer informatie over het maken van aangepaste schema&#39;s vindt u in [deze pagina](../dev/create-schema.md).

1. Sla de databasestructuur op en werk deze bij.  [Meer informatie](../dev/update-database-structure.md)

1. Laat het opvoeren mechanisme in de schemadefinitie toe door toe te voegen **autoStg=&quot;true&quot;** parameter.

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
