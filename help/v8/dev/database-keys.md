---
title: Sleutelbeheer in Campagne-database
description: Belangrijk beheer in Adobe Campaign-schema's begrijpen
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: cf1f5cfc-172f-44ec-ac97-804d15f9d628
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Sleutelbeheer {#management-of-keys}

Elke tabel die aan een gegevensschema is gekoppeld, moet ten minste één sleutel bevatten voor het identificeren van een record in een tabel.

Een sleutel wordt verklaard van het belangrijkste element van het gegevensschema.

```sql
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Een sleutel wordt een &#39;primaire sleutel&#39; genoemd wanneer deze de eerste sleutel in het schema is die moet worden ingevuld, of als deze het kenmerk `internal` bevat dat op &#39;true&#39; is ingesteld.

Een toets kan naar een of meer velden in de tabel verwijzen.

**Voorbeeld**:

* Een sleutel toevoegen aan het e-mailadres en de plaats:

  ```sql
  <srcSchema name="recipient" namespace="cus">
    <element name="recipient">
      <key name="email">
        <keyfield xpath="@email"/> 
        <keyfield xpath="location/@city"/> 
      </key>
  
      <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
      <element name="location" label="Location">
        <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
      </element>
    </element>
  </srcSchema>
  ```

  Het gegenereerde schema:

  ```sql
  <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
    <element name="recipient" sqltable="CusRecipient">    
     <key name="email">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="location/@city"/>    
     </key>    
  
     <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
     <element label="Location" name="location">      
       <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
     </element>  
    </element>
  </schema>
  ```

* Een primaire of interne sleutel toevoegen aan het naamveld &quot;id&quot;:

  ```sql
  <srcSchema name="recipient" namespace="cus">
    <element name="recipient">
      <key name="id" internal="true">
        <keyfield xpath="@id"/> 
      </key>
  
      <key name="email">
        <keyfield xpath="@email"/> 
      </key>
  
      <attribute name="id" type="long" label="Identifier"/>
      <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
    </element>
  </srcSchema>
  ```

  Het gegenereerde schema:

  ```sql
  <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
    <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
        <keyfield xpath="@email"/>    
      </key>  
  
      <key internal="true" name="id">      
       <keyfield xpath="@id"/>    
      </key>    
  
      <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
    </element>
  </schema>
  ```

## Primaire sleutel - Id{#primary-key}

In de context van een [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), is de primaire sleutel van de lijsten van Adobe Campaign a **universeel Unieke identiteitskaart (UUID)** auto-geproduceerd door de gegevensbestandmotor. De sleutelwaarde is uniek in het volledige gegevensbestand. De inhoud van de toets wordt automatisch gegenereerd bij het invoegen van de record.

**Voorbeeld**

In het onderstaande voorbeeld declareren we een incrementele sleutel in het bronschema:

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

Het gegenereerde schema:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

Naast de definitie van de sleutel, is een numeriek gebied genoemd &quot;id&quot;toegevoegd aan het uitgebreide schema om de auto-geproduceerde primaire sleutel te bevatten.

>[!CAUTION]
>
>Bij het maken van de tabel wordt automatisch een record met de primaire sleutel ingesteld op 0 ingevoegd. Deze record wordt gebruikt om buitenste verbindingen te voorkomen, die niet effectief zijn op volumetabellen. Door gebrek, worden alle buitenlandse sleutels geïnitialiseerd met waarde 0 zodat een resultaat altijd kan zijn teruggekeerd op de verbinding wanneer het gegevenspunt niet bevolkt is.
