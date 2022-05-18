---
title: Filtercampagne-schema's
description: Leer hoe u campagnereschema's kunt filteren
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Filterschema&#39;s{#filter-schemas}

## Systeemfilters {#system-filters}

U kunt de schematoegang tot specifieke gebruikers, afhankelijk van hun toestemmingen filtreren. Met systeemfilters kunt u de lees- en schrijfmachtigingen beheren van entiteiten die in schema&#39;s zijn beschreven, met **readAccess** en **writeAccess** parameters.

>[!NOTE]
>
>Deze beperking geldt alleen voor niet-technische gebruikers: een technische gebruiker met verwante machtigingen of met behulp van een workflow kan gegevens ophalen en bijwerken .

* **readAccess**: biedt alleen-lezen toegang tot schemagegevens.

   **Waarschuwing** - Alle gekoppelde tabellen moeten met dezelfde beperking worden ingesteld. Deze configuratie kan van invloed zijn op prestaties.

* **writeAccess**: biedt schrijftoegang tot schemagegevens.

Deze filters worden ingevoerd bij de hoofdmap **element** niveau van de regelingen en, zoals in de volgende voorbeelden wordt getoond, kan worden gevormd om toegang te beperken.

* SCHRIJFmachtigingen beperken

   Hier, wordt de filter gebruikt om SCHRIJVEN toestemmingen op het schema voor exploitanten zonder de toestemming van het BEHEER toe te staan. Dit betekent dat alleen beheerders schrijfmachtigingen hebben voor entiteiten die in dit schema worden beschreven.

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* Rechten voor LEZEN EN SCHRIJVEN beperken:

   Hier, wordt de filter gebruikt om zowel LEZEN als SCHRIJVEN toestemmingen op het schema voor alle exploitanten toe te staan. Alleen de **internal** account, weergegeven door de expressie &quot;$(loginId)!=0&quot;, heeft deze toestemmingen.

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   Mogelijk **expr** de kenmerkwaarden die worden gebruikt om de voorwaarde te definiëren, zijn TRUE of FALSE.

>[!NOTE]
>
>Als er geen filter is opgegeven, hebben alle operatoren lees- en schrijfmachtigingen voor het schema.

## Protect ingebouwde schema&#39;s

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
>Rechten voor LEZEN en SCHRIJVEN voor de **xtk:sessionInfo** schema&#39;s zijn alleen toegankelijk via de interne account van een Adobe Campaign-exemplaar.

## Systeemfilters van ingebouwde schema&#39;s wijzigen

Ingebouwde schema&#39;s zijn beveiligd om compatibiliteitsproblemen met oudere versies te voorkomen. Adobe raadt u aan de standaardschemaparameters niet te wijzigen om optimale veiligheid te waarborgen.

In specifieke gevallen moet u echter mogelijk de systeemfilters van de ingebouwde schema&#39;s wijzigen. Volg onderstaande stappen om dit te doen:

1. Maak een extensie voor het ingebouwde schema of open een bestaande extensie.
1. Een onderliggend element toevoegen **`<sysfilter name="<filter name>" _operation="delete"/>`** in het hoofdelement om het filter onder het zelfde in het ingebouwde schema te negeren.
1. U kunt een nieuw filter toevoegen, zoals wordt beschreven in het dialoogvenster [Systeemfilters](#system-filters) sectie.
