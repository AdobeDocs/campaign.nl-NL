---
title: Filtercampagne-schema's
description: Leer hoe u campagnereschema's kunt filteren
source-git-commit: e0faeda87d5b84309524a72d9f021c381ac4619e
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Filterschema&#39;s{#filter-schemas}

## Systeemfilters {#system-filters}

U kunt de schematoegang tot specifieke gebruikers, afhankelijk van hun toestemmingen filtreren. Met systeemfilters kunt u de lees- en schrijfmachtigingen beheren van entiteiten die in schema&#39;s worden beschreven, met behulp van de parameters **readAccess** en **writeAccess**.

>[!NOTE]
>
>Deze beperking geldt alleen voor niet-technische gebruikers: een technische gebruiker met verwante machtigingen of met behulp van een workflow kan gegevens ophalen en bijwerken .

* **readAccess**: biedt alleen-lezen toegang tot schemagegevens.

   **Waarschuwing** : alle gekoppelde tabellen moeten met dezelfde beperking zijn ingesteld. Deze configuratie kan van invloed zijn op prestaties.

* **writeAccess**: biedt schrijftoegang tot schemagegevens.

Deze filters zijn ingegaan op het belangrijkste **element** niveau van de schema&#39;s en, zoals aangetoond in de volgende voorbeelden, kunnen worden gevormd om toegang te beperken.

* SCHRIJFmachtigingen beperken

   Hier, wordt de filter gebruikt om SCHRIJVEN toestemmingen op het schema voor exploitanten zonder de toestemming van het BEHEER toe te staan. Dit betekent dat alleen beheerders schrijfmachtigingen hebben voor entiteiten die in dit schema worden beschreven.

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* Rechten voor LEZEN EN SCHRIJVEN beperken:

   Hier, wordt de filter gebruikt om zowel LEZEN als SCHRIJVEN toestemmingen op het schema voor alle exploitanten toe te staan. Alleen de **internal**-account, vertegenwoordigd door de expressie &quot;$(loginId)!=0&quot;, heeft deze toestemmingen.

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   Mogelijke **expr** kenmerkwaarden die worden gebruikt om de voorwaarde te definiëren, zijn TRUE of FALSE.

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
>De LEZEN en SCHRIJVEN toestemmingen voor het **xtk:sessionInfo** schema zijn slechts toegankelijk door de interne rekening van een instantie van Adobe Campaign.

## Systeemfilters van ingebouwde schema&#39;s wijzigen

Ingebouwde schema&#39;s zijn beveiligd om compatibiliteitsproblemen met oudere versies te voorkomen. Adobe raadt u aan de standaardschemaparameters niet te wijzigen om optimale veiligheid te waarborgen.

In specifieke gevallen moet u echter mogelijk de systeemfilters van de ingebouwde schema&#39;s wijzigen. Volg onderstaande stappen om dit te doen:

1. Maak een extensie voor het ingebouwde schema of open een bestaande extensie.
1. Voeg een kindelement **`<sysfilter name="<filter name>" _operation="delete"/>`** in het belangrijkste element toe om de filter onder het zelfde in het ingebouwde schema te negeren.
1. U kunt een nieuw filter toevoegen, zoals beschreven in de sectie [Systeemfilters](#system-filters).
