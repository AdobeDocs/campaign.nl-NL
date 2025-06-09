---
title: Filtercampagne-schema's
description: Leer hoe u campagnereschema's kunt filteren
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Filterschema&#39;s{#filter-schemas}

## Systeemfilters {#system-filters}

U kunt de schematoegang tot specifieke gebruikers, afhankelijk van hun toestemmingen filtreren. De filters van het systeem laten u lezen beheren en schrijven toestemmingen van entiteiten die in schema&#39;s worden gedetailleerd, gebruikend **readAccess** en **writeAccess** parameters.

>[!NOTE]
>
>Deze beperking geldt alleen voor niet-technische gebruikers: een technische gebruiker met gerelateerde machtigingen of met behulp van een workflow kan gegevens ophalen en bijwerken.

* **readAccess**: verleent read slechts toegang tot schemagegevens.

  **Waarschuwing** - Alle verbonden lijsten moeten met de zelfde beperking worden geplaatst. Deze configuratie kan van invloed zijn op prestaties.

* **writeAccess**: verleent schrijftoegang tot schemagegevens.

Deze filters zijn ingegaan op het belangrijkste **element** niveau van de schema&#39;s en, zoals aangetoond in de volgende voorbeelden, kunnen worden gevormd om toegang te beperken.

* SCHRIJFmachtigingen beperken

  Hier, wordt de filter gebruikt om SCHRIJVEN toestemmingen op het schema voor exploitanten zonder de toestemming van het BEHEER toe te staan. Dit betekent dat alleen beheerders schrijfmachtigingen hebben voor entiteiten die in dit schema worden beschreven.

  ```
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* Rechten voor LEZEN EN SCHRIJVEN beperken:

  Hier, wordt de filter gebruikt om zowel LEZEN als SCHRIJVEN toestemmingen op het schema voor alle exploitanten toe te staan. Slechts de **interne** rekening, die door de uitdrukking &quot;$ (loginId) wordt vertegenwoordigd!=0&quot;, heeft deze toestemmingen.

  ```
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  Mogelijke **expr** kenmerkwaarden die worden gebruikt om de voorwaarde te bepalen zijn WAAR of VALS.

>[!NOTE]
>
>Als er geen filter is opgegeven, hebben alle operatoren lees- en schrijfmachtigingen voor het schema.

## Ingebouwde schema&#39;s beschermen

Door gebrek, zijn de ingebouwde schema&#39;s slechts toegankelijk met SCHRIJVEN toestemmingen voor exploitanten met de rechten van het BEHEER:

* ncm:publiceren
* nl:controleren
* nms:kalender
* xtk:builder
* xtk:verbindingen
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusie
* xtk:afbeelding
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk:navtree
* xtk:operatorGroup
* xtk:package
* xtk:queryDef
* xtk:resourceMenu
* xtk:rights
* xtk:schema
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:tekenreeksen
* xtk:xslt

>[!CAUTION]
>
>LEES en SCHRIJF toestemmingen voor **xtk:sessionInfo** schema zijn slechts toegankelijk door de interne rekening van een instantie van Adobe Campaign.

## Systeemfilters van ingebouwde schema&#39;s wijzigen

Ingebouwde schema&#39;s zijn beveiligd om compatibiliteitsproblemen met oudere versies te voorkomen. Adobe raadt u aan de standaardschemaparameters niet te wijzigen om optimale veiligheid te garanderen.

In specifieke gevallen moet u echter mogelijk de systeemfilters van de ingebouwde schema&#39;s wijzigen. Volg onderstaande stappen om dit te doen:

1. Maak een extensie voor het ingebouwde schema of open een bestaande extensie.
1. Voeg een onderliggend element **`<sysfilter name="<filter name>" _operation="delete"/>`** toe in het hoofdelement om het filter onder het zelfde in het ingebouwde schema te negeren.
1. U kunt een nieuwe filter toevoegen, zoals die in de [ de filters van het Systeem ](#system-filters) sectie wordt gedetailleerd.
