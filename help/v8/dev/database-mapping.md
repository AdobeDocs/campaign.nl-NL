---
title: Toewijzing van Campagne-database
description: Toewijzing van Campagne-database
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# Databasetoewijzing{#database-mapping}

De SQL-toewijzing van ons voorbeeldschema geeft het volgende XML-document:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## Beschrijving {#description}

Het hoofdelement van het schema is niet langer **`<srcschema>`**, maar **`<schema>`**.

Dit neemt ons aan een ander type van document, dat automatisch van het bronschema wordt geproduceerd, eenvoudig die als schema wordt bedoeld. Dit schema wordt gebruikt door de Adobe Campaign-toepassing.

De SQL-namen worden automatisch bepaald op basis van de naam en het type van het element.

De SQL-naamgevingsregels zijn als volgt:

* tabel: samenvoeging van de naamruimte en naam van het schema

  In ons voorbeeld wordt de naam van de tabel ingevoerd via het hoofdelement van het schema in het dialoogvenster **sqltable** kenmerk:

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* field: naam van het element voorafgegaan door een voorvoegsel gedefinieerd volgens type (&#39;i&#39; voor geheel getal, &#39;d&#39; voor dubbel, &#39;s&#39; voor tekenreeks, &#39;ts&#39; voor datums, enz.)

  De veldnaam wordt ingevoerd via het dialoogvenster **sqlname** kenmerk voor elk type **`<attribute>`** en **`<element>`**:

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>SQL-namen kunnen worden overgeladen uit het bronschema. Hiertoe vult u de kenmerken &quot;sqltable&quot; of &quot;sqlname&quot; op het desbetreffende element in.

Het SQL-script voor het maken van de tabel die wordt gegenereerd op basis van het uitgebreide schema ziet er als volgt uit:

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

De beperkingen voor het SQL-veld zijn als volgt:

* geen null-waarden in numerieke velden en datumvelden
* numerieke velden worden geïnitialiseerd naar 0

## XML-velden {#xml-fields}

Standaard wordt elk type **`<attribute>`** en **`<element>`** element wordt in kaart gebracht op een SQL gebied van de lijst van het gegevensschema. U kunt echter naar dit veld verwijzen in XML in plaats van naar SQL, wat betekent dat de gegevens worden opgeslagen in een geheugenveld (&quot;mData&quot;) van de tabel dat de waarden van alle XML-velden bevat. De opslag van deze gegevens is een XML-document dat de schemastructuur in acht neemt.

Als u een veld in XML wilt vullen, voegt u de opdracht **xml** kenmerk met de waarde &quot;true&quot; aan het betrokken element.

**Voorbeelden**

* Veld voor opmerkingen met meerdere regels:

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* Beschrijving van de gegevens in HTML-formaat:

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  Met het type &quot;html&quot; kunt u de HTML-inhoud opslaan in een CDATA-tag en een speciale controle voor het bewerken van HTML weergeven in de Adobe Campaign-clientinterface.

Met XML-velden kunt u velden toevoegen zonder dat u de fysieke structuur van de database hoeft te wijzigen. Een ander voordeel is dat u minder bronnen gebruikt (grootte die is toegewezen aan SQL-velden, beperking van het aantal velden per tabel, enzovoort).
