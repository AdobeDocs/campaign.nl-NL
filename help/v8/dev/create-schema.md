---
product: Adobe Campaign
title: Nieuw schema maken in campagne
description: Leer hoe u een nieuw schema maakt in Campagne
source-git-commit: 99a1381a0d5cef38eb708dbe6e3e8029e6ff3953
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# Nieuw schema maken{#create-new-schema}

Als u de schema&#39;s wilt bewerken, maken en configureren, klikt u op het knooppunt **[!UICONTROL Administration > Configuration > Data schemas]** van de Adobe Campaign-clientconsole.

>[!NOTE]
>
>Ingebouwde gegevensschema&#39;s kunnen alleen worden verwijderd door een beheerder van uw Adobe Campaign-console.

![](assets/schema_navtree.png)

Op het tabblad **[!UICONTROL Edit]** wordt de XML-inhoud van een schema weergegeven:

![](assets/schema_edition.png)

>[!NOTE]
>
>Met het besturingselement &#39;Naam&#39; kunt u de schemasleutel invoeren die bestaat uit de naam en naamruimte. De kenmerken &quot;name&quot; en &quot;namespace&quot; van het hoofdelement van het schema worden automatisch bijgewerkt in de XML-bewerkingszone van het schema. Sommige naamruimten zijn alleen intern. [Meer informatie](schemas.md#reserved-namespaces).

Het **[!UICONTROL Preview]** lusje produceert automatisch het uitgebreide schema:

![](assets/schema_edition2.png)

>[!NOTE]
>
>Wanneer het bronschema wordt opgeslagen, wordt het genereren van het uitgebreide schema automatisch gestart.

Als u de volledige structuur van een schema moet controleren, kunt u **[!UICONTROL Preview]** tabel gebruiken. Als het schema is uitgebreid, zult u al zijn uitbreidingen dan kunnen visualiseren. Als aanvulling, toont **[!UICONTROL Documentation]** lusje alle schemakenmerken en elementen, en hun eigenschappen (SQL Gebied, type/lengte, etiket, beschrijving). Het tabblad **[!UICONTROL Documentation]** is alleen van toepassing op gegenereerde schema&#39;s.

## Hoofdlettergebruik: een contracttabel {#example--creating-a-contract-table} maken

In het volgende voorbeeld, creeert u een nieuwe lijst voor **contracten** in het gegevensbestand. In deze tabel kunt u voor elk contract de voor- en achternaam en het e-mailadres van de houder en de medehouder opslaan.

Hiervoor moet u het schema van de tabel maken en de databasestructuur bijwerken om de bijbehorende tabel te genereren. De gedetailleerde stappen worden hieronder vermeld.

1. Bewerk het knooppunt **[!UICONTROL Administration > Configuration > Data schemas]** van de Adobe Campaign-structuur en klik op **[!UICONTROL New]**.
1. Kies de optie **[!UICONTROL Create a new table in the data template]** en klik **[!UICONTROL Next]**.

   ![](assets/create_new_schema.png)

1. Geef een naam voor de tabel en een naamruimte op.

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >Standaard worden schema&#39;s die door gebruikers worden gemaakt, opgeslagen in de naamruimte &#39;cus&#39;. Voor meer op dit, verwijs naar [Identificatie van een schema](extend-schema.md#identification-of-a-schema).

1. Maak de inhoud van de tabel. Wij adviseren gebruikend de specifieke medewerker om ervoor te zorgen geen montages ontbreken. Klik hiertoe op de knop **[!UICONTROL Insert]** en kies het type instelling dat u wilt toevoegen.

   ![](assets/create_new_content.png)

1. Definieer de instellingen voor de tabel met contracten.

   Als beste praktijken, creeer de lijst in het gegevensbestand van de Wolk door het `dataSource="nms:extAccount:ffda"` attribuut toe te voegen. Dit kenmerk wordt standaard toegevoegd bij het maken van een nieuwe tabel.

   ```
   <srcSchema created="YYYY-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" lastModified="YYYY-MM-DD HH:MM:SS.TZ"
           mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

   Voeg het type van contractopsomming toe.

   ```
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png" label="Contracts" labelSingular="Contract" AA-MM-DD HH:MM:SS.TZ"mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <enumeration basetype="byte" name="typeContract">
         <value label="Home" name="home" value="0"/>
         <value label="Car" name="car" value="1"/>
         <value label="Health" name="health" value="2"/>
         <value label="Pension fund" name="pension fund" value="2"/>
      </enumeration>
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

1. Sla het schema op en klik op het tabblad **[!UICONTROL Structure]** om de structuur te genereren:

   ![](assets/configuration_structure.png)

1. Werk de databasestructuur bij om de tabel te maken waarnaar het schema wordt gekoppeld. Raadpleeg [deze sectie](update-database-structure.md) voor meer informatie.

