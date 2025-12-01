---
title: De database opvragen met queryDef
description: Leer hoe u queryDef- en NLWS-methoden gebruikt om query's uit te voeren op de Campagne-database
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
source-git-commit: ceab90331fab0725962a2a98f338ac3dc31a2588
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 0%

---

# De database opvragen met queryDef {#query-database-api}

[!DNL Adobe Campaign] biedt krachtige JavaScript-methoden voor interactie met de database via `queryDef` en het `NLWS` -object. Met deze op SOAP gebaseerde methoden kunt u gegevens laden, maken, bijwerken en zoeken met JSON, XML of SQL.

>[!NOTE]
>
>Deze documentatie behandelt gegevensgeoriënteerde APIs voor het vragen van het gegevensbestand programmatically. Voor REST APIs, verwijs naar [&#x200B; begonnen wordt met REST APIs &#x200B;](api/get-started-apis.md). Voor het visuele vraaggebouw, verwijs naar [&#x200B; Werk met de vraagredacteur &#x200B;](../start/query-editor.md).

## Wat is NLWS? {#what-is-nlws}

`NLWS` (Neolane Web Services) is het algemene JavaScript-object dat wordt gebruikt voor toegang tot de op SOAP gebaseerde API-methoden van [!DNL Adobe Campaign] . Schema&#39;s zijn eigenschappen van het `NLWS` -object, zodat u programmatisch kunt communiceren met campagneentiteiten.

Volgens de [&#x200B; documentatie van JSAPI van de Campagne &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=nl-NL){target="_blank"}, &quot;zijn de schema&#39;s &quot;NLWS&quot;globale voorwerpen.&quot; De syntaxis voor toegang tot schemamethoden volgt dit patroon:

```javascript
NLWS.<namespace><SchemaName>.<method>()
```

**Voorbeelden:**

* `NLWS.nmsRecipient` - Toegang tot methoden voor het ontvangende schema (`nms:recipient`)
* `NLWS.nmsDelivery` - Toegang tot methoden voor het leveringsschema (`nms:delivery`)
* `NLWS.xtkQueryDef` - Toegang tot queryDef-methoden om query&#39;s uit te voeren op de database

Veelvoorkomende API-methoden zijn:

* `load(id)` - Een entiteit met de id laden. [Meer informatie](https://experienceleague.adobe.com/developer/campaign-api/api/f-load.html?lang=nl-NL){target="_blank"}
* `create(data)` - Een nieuwe entiteit maken
* `save()` - Wijzigingen in een entiteit opslaan

**Voorbeeld van officiële documentatie:**

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

>[!NOTE]
>
>**Alternatieve syntaxis:** voor achterwaartse verenigbaarheid, kunt u ook de syntaxis van kleine letters namespace in sommige documentatie (b.v., `nms.recipient.create()`, `xtk.queryDef.create()`) zien. Beide syntaxis werkt, maar `NLWS` is de standaard die wordt beschreven in de officiële JSAPI-referentie voor campagne.

## Vereisten {#prerequisites}

Voordat u de methoden queryDef en NLWS gebruikt, moet u bekend zijn met:

* JavaScript
* [!DNL Adobe Campaign] gegevensmodel en -schema&#39;s
* XPath-expressies voor navigeren door schema-elementen

**Begrijpend het de gegevensmodel van de Campagne:**

Adobe Campaign wordt geleverd met een vooraf gedefinieerd gegevensmodel dat bestaat uit tabellen die zijn gekoppeld in een Cloud-database. De basisstructuur omvat:

* **Ontvankelijke lijst** (`nmsRecipient`) - Belangrijkste lijst die marketing profielen opslaat
* **lijst van de Levering** (`nmsDelivery`) - slaat leveringsacties en malplaatjes met parameters op voor het uitvoeren van leveringen
* **Logs lijsten** - de uitvoeringslogboeken van de opslag:
   * `nmsBroadLogRcp` - Leveringslogboeken voor alle berichten die naar ontvangers worden verzonden
   * `nmsTrackingLogRcp` - Logboeken bijhouden voor reacties van ontvangers (wordt geopend, er wordt geklikt)
* **Technische lijsten** - de systeemgegevens van de opslag zoals exploitanten (`xtkGroup`), zittingen (`xtkSessionInfo`), werkschema&#39;s (`xtkWorkflow`)

Om tot schemabeschrijvingen in de interface van de Campagne toegang te hebben, doorblader aan **Beleid > Configuratie > de schema&#39;s van Gegevens**, selecteer een middel, en klik de **Documentatie** tabel.

## Methoden van het entiteitsschema {#entity-schema-methods}

Elk schema in [!DNL Adobe Campaign] (bijvoorbeeld `nms:recipient` , `nms:delivery` ) wordt geleverd met methoden die toegankelijk zijn via het `NLWS` -object. Deze methodes verstrekken een geschikte manier om met gegevensbestandentiteiten in wisselwerking te staan.

### Statische methoden {#static-methods}

Statische SOAP-methoden worden benaderd door een methode aan te roepen voor het object dat het schema vertegenwoordigt. `NLWS.xtkWorkflow.PostEvent()` roept bijvoorbeeld een statische methode aan.

### Niet-statische methoden {#non-static-methods}

Als u niet-statische SOAP-methoden wilt gebruiken, moet u eerst een entiteit ophalen met de methoden `load` of `create` in de desbetreffende schema&#39;s. Leer meer in de [&#x200B; documentatie van JSAPI van de Campagne &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html?lang=nl-NL){target="_blank"}.

### Entiteiten laden, opslaan en maken {#load-save-create}

**Laad een entiteit door identiteitskaart en werk het bij:**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**creeer een ontvanger gebruikend JSON:**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**creeer een ontvanger gebruikend XML:**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## Overzicht van QueryDef {#querydef-overview}

Het `xtk:queryDef` -schema biedt methoden om databasequery&#39;s te maken en uit te voeren. Met `NLWS.xtkQueryDef.create()` kunt u query&#39;s samenstellen met JSON- of XML-syntaxis.

**Beschikbare verrichtingen:**

* `select` - Meerdere records ophalen
* `get` - Eén record ophalen (SQL `LIMIT 1`)
* `getIfExists` - Eén record ophalen, null retourneren als deze niet is gevonden
* `count` - Records tellen die aan de criteria voldoen

Leer meer over methodes queryDef in de [&#x200B; documentatie van JSAPI van de Campagne &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html?lang=nl-NL){target="_blank"}.

## Query uitvoeren met JSON {#query-json}

Gebruik `NLWS.xtkQueryDef.create()` om query&#39;s samen te stellen met JSON-syntaxis. Met de bewerking `get` wordt één record opgehaald (SQL `LIMIT 1` ), terwijl `select` meerdere records ophaalt.

**krijg één enkele ontvanger:**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**Gebruik `getIfExists` om uitzonderingen te vermijden:**

Als de record mogelijk niet bestaat, gebruikt u `operation: "getIfExists"` in plaats van `get` om uitzonderingen te voorkomen:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## Meerdere records selecteren {#select-multiple}

Gebruik de bewerking `select` om meerdere records op te halen. U kunt voorwaarden, opdracht geven tot, en grenzen toevoegen.

**de werkschema&#39;s van de Vraag met filters en het opdracht geven tot:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**de leveringen van de Vraag met de syntaxis van XML:**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>**de grenzen van het Resultaat:** De campagne beperkt automatisch vraagresultaten om geheugenkwesties te verhinderen:
>* Standaardlimiet varieert per context (doorgaans 200-10.000 records)
>* Gebruik `lineCount` om het maximale aantal resultaten expliciet in te stellen
>* Voor grote datasets (>1000 verslagen), gebruik werkschema&#39;s in plaats van queryDef. Workflows zijn ontworpen om miljoenen rijen efficiënt te verwerken.

Leer meer over [&#x200B; ExecuteQuery &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html?lang=nl-NL){target="_blank"} en [&#x200B; vraag beste praktijken &#x200B;](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}.

## Overgangsgegevens van querywerkstroom {#workflow-transition-data}

Wanneer u werkt met JavaScript-activiteiten in workflows, kunt u query&#39;s uitvoeren op gegevens van binnenkomende overgangen met `vars.targetSchema` en `vars.tableName` .

**de ontvankelijke gegevens van de Vraag van een werkschemaovergang:**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>Gebruik altijd geparameteriiseerde query&#39;s met `$(sz)` voor tekenreeksen en `$(l)` voor gehele getallen om SQL-injectiekwetsbaarheden te voorkomen. Leer meer in de [&#x200B; documentatie van JSAPI van de Campagne &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html?lang=nl-NL){target="_blank"}.

## Records tellen {#count-records}

Gebruik `Count(@id)` met een alias om records te tellen.

**Aantal lopende hypothesen:**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**Telling met veelvoudige voorwaarden:**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Verdeling van waarden {#distribution-values}

Hiermee wordt de verdeling van waarden voor een bepaald veld opgehaald. Dit is handig voor het analyseren van gegevenspatronen.

**Distributie van landcodes:**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## Opsommingen query met analyse {#analyze-enumerations}

De optie `analyze` retourneert gebruikersvriendelijke namen voor opsommingswaarden. In plaats van alleen numerieke waarden retourneert Campaign ook de tekenreekswaarde en het label met de achtervoegsels &quot;Naam&quot; en &quot;Label&quot;.

**levering van de Vraag afbeelding met opsommingsanalyse:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:deliveryMapping",
    operation: "get",
    select: {
      node: [
        {expr: "@id"},
        {expr: "@name"},
        {expr: "[storage/@exclusionType]", analyze: true}  // Analyze enumeration
      ]
    },
    where: {
      condition: [{expr: "@name='mapRecipient'"}]
    }
  }
});

var mapping = query.ExecuteQuery();

// Result includes:
// - exclusionType: 2 (numeric value)
// - exclusionTypeName: "excludeRecipient" (string value)
// - exclusionTypeLabel: "Exclude recipient" (display label)
logInfo("Type: " + mapping.$exclusionType);
logInfo("Name: " + mapping.$exclusionTypeName);
logInfo("Label: " + mapping.$exclusionTypeLabel);
```

Leer meer over [&#x200B; analyseer optie &#x200B;](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#the-analyze-option){target="_blank"}.

## Paginering {#pagination}

Gebruik `lineCount` en `startLine` om door grote resultaatsets te pagineren.

**wint verslagen in pagina&#39;s terug:**

```javascript
// Get records 3 and 4 (skip first 2)
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    lineCount: 2,     // Number of records per page
    startLine: 2,     // Starting position (0-indexed)
    select: {
      node: [
        {expr: "@id"},
        {expr: "@email"}
      ]
    },
    orderBy: {
      node: [{expr: "@id"}]  // Critical: Always use orderBy for pagination
    }
  }
});

var recipients = query.ExecuteQuery();
```

>[!CAUTION]
>
>**Paginering vereist orderBy:** Zonder een `orderBy` clausule, zijn de vraagresultaten niet gewaarborgd om in een verenigbare orde te zijn. Volgende aanroepen kunnen verschillende pagina&#39;s of dubbele records retourneren. Neem altijd een `orderBy` op wanneer u paginering gebruikt.

Leer meer over [&#x200B; paginering &#x200B;](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#pagination){target="_blank"}.

## Dynamische queryconstructie {#dynamic-queries}

Bouw vragen dynamisch door voorwaarden programmatically toe te voegen.

**voegt voorwaarden aan een bestaande vraag toe:**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**bouwt uitgezocht en waar clausules in lijnen:**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Geavanceerde queryDef-methoden {#advanced-methods}

Buiten `ExecuteQuery()` biedt queryDef verschillende gespecialiseerde methoden voor geavanceerde gebruiksgevallen.

### BuildQuery - SQL genereren zonder uitvoeren {#build-query}

Gebruik `BuildQuery()` om de SQL-instructie te genereren zonder deze uit te voeren. Dit is nuttig voor het zuiveren, registreren, of het overgaan van vragen aan externe systemen.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

Leer meer over [&#x200B; BuildQuery &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html?lang=nl-NL){target="_blank"}.

### BuildQueryEx - SQL ophalen met indelingstekenreeks {#build-query-ex}

`BuildQueryEx()` retourneert zowel de SQL-query als een indelingstekenreeks die compatibel is met de functie `sqlSelect()` .

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

Leer meer over [&#x200B; BuildQueryEx &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html?lang=nl-NL){target="_blank"}.

### Alles selecteren - Alle velden toevoegen om te selecteren {#select-all}

De methode `SelectAll()` voegt automatisch alle velden van het schema toe aan de selectieclausule, zodat u niet elk veld handmatig hoeft weer te geven.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

Leer meer over [&#x200B; SelectAll &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html?lang=nl-NL){target="_blank"}.

### Bijwerken - Update-records voor massa {#mass-update}

Met de methode `Update()` kunt u massa-updates uitvoeren op records die voldoen aan uw querycriteria zonder elke record afzonderlijk te laden.

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>De updates van de massa beïnvloeden alle verslagen die de waar clausule aanpassen. Test altijd waar de voorwaarden met een uitgezochte vraag eerst om te verifiëren welke verslagen zullen worden beïnvloed.

Leer meer over [&#x200B; Update &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html?lang=nl-NL){target="_blank"}.

### GetInstanceFromModel - Query-sjablooninstanties {#get-instance-from-model}

Gebruik `GetInstanceFromModel()` om gegevens op te halen uit instanties die zijn gemaakt van sjablonen.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

Leer meer over [&#x200B; GetInstanceFromModel &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html?lang=nl-NL){target="_blank"}.

## Batchbewerkingen {#batch-operations}

Verwerk meerdere records in batch om de prestaties te verbeteren.

**de etiketten van de updatelevering van de Partij:**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## Onbewerkte SQL-uitvoering {#raw-sql}

Voor complexe bewerkingen kunt u onbewerkte SQL rechtstreeks uitvoeren.

**Uitvoeren geparametereerde SQL:**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

**Vraag met sqlSelect:**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>Wanneer u onbewerkte SQL gebruikt:
>
>* Gebruikersinvoer altijd valideren en ontsmetten
>* Gebruik geparametereerde query&#39;s met `$(sz)` , `$(l)` , `$(dt)` enz.
>* Ben zich bewust van de verschillen tussen de lokale en wolkengegevensbestanden in [&#x200B; plaatsingen FFDA &#x200B;](../architecture/enterprise-deployment.md)

## Best practices {#best-practices}

Bij het werken met queryDef- en NLWS-methoden:

* **werkschema&#39;s van het Gebruik voor grote datasets** - QueryDef wordt niet ontworpen voor de verwerking van high-volume gegevens. Voor datasets met meer dan 1.000 verslagen, gebruikwerkschema&#39;s die miljoenen rijen efficiënt kunnen behandelen. Leer meer in de [&#x200B; documentatie van SDK van de Campagne &#x200B;](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* **Gebruik de parameters bepaalde vragen** - gebruik altijd gebonden parameters (`$(sz)`, `$(l)`) met `sqlExec` om SQL injectie te verhinderen
* **vastgestelde expliciete grenzen** - Gebruik `lineCount` om resultaatgrootte te controleren. De standaardlimieten van de campagne variëren per context (200-10.000 records)
* **Gebruik orderBy met paginering** - omvat altijd een `orderBy` clausule wanneer het gebruiken `startLine` en `lineCount` om verenigbare paginering te verzekeren
* **getIfExists van het Gebruik** - Gebruik `operation: "getIfExists"` wanneer de verslagen niet zouden kunnen bestaan om uitzonderingen te vermijden
* **Analyseer van het Gebruik voor opsommingen** - voeg `analyze: true` toe om knopen te selecteren om gebruikersvriendelijke opsommingsnamen en etiketten te krijgen
* **optimaliseer vragen** - voeg aangewezen `where` voorwaarden toe om resultaatreeksen te beperken
* **verwerking van de Partij** - de veelvoudige verslagen in partijen verwerken om geheugenkwesties en onderbrekingen te vermijden
* **bewustzijn FFDA** - In [&#x200B; de plaatsingen van de Onderneming (FFDA) &#x200B;](../architecture/enterprise-deployment.md), ben zich ervan bewust dat [!DNL Campaign] met twee gegevensbestanden werkt



## Praktische gebruiksgevallen {#use-cases}

### Foutopsporing en logboekquery&#39;s {#debug-queries}

Gebruik `BuildQuery()` om de gegenereerde SQL te inspecteren voordat deze wordt uitgevoerd:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### Een record dupliceren met SelectAll {#duplicate-record}

Met `SelectAll()` kunt u alle velden kopiëren tijdens het dupliceren van records:

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### Valideren vóór update van massa {#validate-mass-update}

Altijd de betreffende records voorvertonen voordat u massa-updates uitvoert:

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## Overzicht van de querydefinitiesyntaxis {#querydef-reference}

Volledige structuur van het object `queryDef` :

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## Verwante onderwerpen {#related-topics}

* [Aan de slag met campagne-API&#39;s](api.md)
* [&#x200B; Campagne JavaScript SDK - de Vraag API &#x200B;](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* [&#x200B; queryDef API Verwijzing &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html?lang=nl-NL){target="_blank"}
* [&#x200B; de documentatie van JSAPI van de Campagne &#x200B;](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=nl-NL){target="_blank"}
* [Werken met schema&#39;s](schemas.md)
* [Werken met de query-editor](../start/query-editor.md)

