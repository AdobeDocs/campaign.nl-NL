---
solution: Campaign v8
product: Adobe Campaign
title: Werken met campagne-schema's
description: Aan de slag met schema's
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 4%

---

# Werken met schema&#39;s{#gs-ac-schemas}

De fysieke en logische structuur van de data die in de applicatie worden overgedragen, wordt in XML beschreven. Het volgt een grammatica specifiek voor Adobe Campaign, genoemd a **schema**.

Een schema is een XML-document dat is gekoppeld aan een databasetabel. De code definieert de gegevensstructuur en beschrijft de SQL-definitie van de tabel:

* De naam van de tabel
* Velden
* Koppelingen met andere tabellen

Hierin wordt ook de XML-structuur beschreven die wordt gebruikt om gegevens op te slaan:

* Elementen en kenmerken
* Hiërarchie van elementen
* Element- en kenmerktypen
* Standaardwaarden
* Labels, beschrijvingen en andere eigenschappen.

Met schema&#39;s kunt u een entiteit in de database definiëren. Er is een schema voor elke entiteit.

Adobe Campaign past gegevensschema&#39;s toe op:

* Definieer hoe het gegevensobject in de toepassing wordt gekoppeld aan onderliggende databasetabellen.
* Definiëren van koppelingen tussen de verschillende dataobjecten in de Campaign-applicatie.
* Definiëren en beschrijven van de afzonderlijke velden die in elk object zijn opgenomen.

Raadpleeg [deze sectie](datamodel.md) voor een beter begrip van geïntegreerde tabellen en hun interactie voor campagnes.

>[!CAUTION]
>
>Sommige ingebouwde schema&#39;s van de Campagne hebben een bijbehorend schema op het gegevensbestand van de Wolk. Deze schema&#39;s worden geïdentificeerd door **Xxl** namespace en moeten niet worden gewijzigd of worden uitgebreid.

## Syntaxis van schema&#39;s {#syntax-of-schemas}

Het hoofdelement van het schema is **`<srcschema>`**. Het bevat de **`<element>`** en **`<attribute>`** subelementen.

Het eerste **`<element>`** subelement valt samen met de wortel van de entiteit.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>Het hoofdelement van de entiteit heeft dezelfde naam als het schema.

![](assets/schema_and_entity.png)

Met de **`<element>`**-tags worden de namen van entiteitselementen gedefinieerd. **`<attribute>`** tags in het schema de namen definiëren van de kenmerken in de  **`<element>`** tags waaraan ze zijn gekoppeld.

## Identificatie van een schema {#identification-of-a-schema}

Een gegevensschema wordt geïdentificeerd door zijn naam en zijn namespace.

Met een naamruimte kunt u een set schema&#39;s groeperen op interessegebied. De naamruimte **cus** wordt bijvoorbeeld gebruikt voor klantspecifieke configuratie (**klanten**).

>[!CAUTION]
>
>Standaard moet de naam van de naamruimte beknopt zijn en alleen toegestane tekens bevatten, in overeenstemming met XML-naamgevingsregels.
>
>Id&#39;s mogen niet beginnen met numerieke tekens.

## Gereserveerde naamruimten {#reserved-namespaces}

Bepaalde naamruimten zijn gereserveerd voor beschrijvingen van de systeementiteiten die vereist zijn voor de werking van de Adobe Campaign-toepassing. De volgende naamruimte **mag niet worden gebruikt** om een nieuw schema te identificeren, in een combinatie van hoofdletters en kleine letters:

* **xxl**: gereserveerd voor Cloud-databaseschema&#39;s
* **xtk**: gereserveerd voor platformsysteemgegevens
* **nl**: uitsluitend bestemd zijn voor het algemene gebruik van de aanvraag
* **nms**: gereserveerd voor leveringen (ontvanger, levering, volgen, enz.)
* **ncm**: gereserveerd voor inhoudsbeheer
* **temp**: gereserveerd voor tijdelijke regelingen
* **crm**: gereserveerd voor integratie van CRM-connectors

De identificatiesleutel van een schema is een tekenreeks die is opgebouwd met behulp van de naamruimte en de naam gescheiden door een dubbele punt. bijvoorbeeld: **nms:ontvanger**.

## Campagne-schema&#39;s maken of uitbreiden {#create-or-extend-schemas}

Als u een veld of ander element wilt toevoegen aan een van de kerngegevensschema&#39;s in Campagne, zoals de ontvangende tabel (nms:ontvanger), moet u dat schema uitbreiden.

[!DNL :bulb:] Voor meer op dit, verwijs naar  [breid een schema](extend-schema.md) uit.

Als u een geheel nieuw type gegevens wilt toevoegen dat niet bestaat in Adobe Campaign (bijvoorbeeld een contracttabel), kunt u rechtstreeks een aangepast schema maken.

[!DNL :bulb:] Raadpleeg  [Een nieuw schema](create-schema.md) maken voor meer informatie.

![](assets/schemaextension_1.png)


Nadat u een schema hebt gemaakt of uitgebreid om in te werken, kunt u het beste de XML-inhoudselementen definiëren in dezelfde volgorde als hieronder.

## Opsommingen {#enumerations}

Opsommingen worden eerst gedefinieerd, vóór het hoofdelement van het schema. Hiermee kunt u waarden in een lijst weergeven om de keuzes te beperken die de gebruiker voor een bepaald veld heeft.

Voorbeeld:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

Wanneer u velden definieert, kunt u deze opsomming als volgt gebruiken:

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>U kunt door de gebruiker beheerde opsommingen ook gebruiken (gewoonlijk onder **[!UICONTROL Administration]** > **[!UICONTROL Platform]**) om de waarden voor een bepaald veld op te geven. Dit zijn in feite globale opsommingen, en een betere keus als uw opsomming buiten het specifieke schema kan worden gebruikt u binnen werkt.

## Toetsen {#keys}

Elke lijst moet minstens één sleutel hebben, en vaak wordt het automatisch gevestigd in het belangrijkste element van het schema door **@autouuid=true** attributen te gebruiken die aan &quot;waar&quot;worden geplaatst.

De primaire sleutel kan ook worden bepaald gebruikend het **internal** attribuut.

Voorbeeld:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

In dit voorbeeld, in plaats van het laten **@autouuid** attribuut een standaard primaire sleutel tot stand brengen genoemd &quot;id&quot;wij specificeren onze eigen &quot;huishoudenId&quot;primaire sleutel.

>[!CAUTION]
>
>Wanneer het creëren van een nieuw schema of tijdens een schemauitbreiding, moet u de zelfde primaire zeer belangrijke opeenvolgingswaarde (@pkSequence) voor het volledige schema houden.

[!DNL :bulb:] Meer informatie over toetsen vindt u in  [deze sectie](database-mapping.md#management-of-keys).

## Attributen (velden) {#attributes--fields-}

Met kenmerken kunt u de velden definiëren waaruit het gegevensobject bestaat. U kunt de **[!UICONTROL Insert]** knoop in de toolbar van de schemageditie gebruiken om lege attributenmalplaatjes in uw XML te laten vallen waar uw curseur is. Meer informatie vindt u in [deze sectie](create-schema.md).

![](assets/schemaextension_2.png)

De volledige lijst met kenmerken is beschikbaar in de `<attribute>`-elementsectie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). Hier volgen enkele van de meer gebruikte kenmerken: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **a13/>,**@length **,**@name **,**@notNull **,**@required **,**@ref 23/>, **@xml**, **@type**.****

[!DNL :arrow_upper_right:] Voor meer informatie over elk attribuut, verwijs naar de beschrijving van Attributen in  [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### Voorbeelden {#examples}

Voorbeeld van het definiëren van een standaardwaarde:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Voorbeeld van het gebruik van een gemeenschappelijk kenmerk als een sjabloon voor een veld dat ook als verplicht is gemarkeerd:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Voorbeeld van een berekend veld dat is verborgen met het kenmerk **@advanced**:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Voorbeeld van een XML-veld dat ook is opgeslagen in een SQL-veld en dat het kenmerk **@dataPolicy** heeft.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Hoewel de meeste kenmerken volgens een 1-1-cardinaliteit aan een fysiek veld van de database zijn gekoppeld, is dit niet het geval voor de XML-velden of de berekende velden.\
>Een XML-veld wordt opgeslagen in een memoveld (&quot;mData&quot;) van de tabel.\
>Een gegevens verwerkt gebied nochtans wordt gecreeerd dynamisch telkens als een vraag wordt begonnen, bestaat het daarom slechts in de toepassingslaag.

## Koppelingen {#links}

De verbindingen zijn enkele laatste elementen in het belangrijkste element van uw schema. Ze definiëren hoe alle verschillende schema&#39;s in uw instantie op elkaar betrekking hebben.

De verbindingen worden verklaard in het schema dat **buitenlandse sleutel** van de lijst bevat waaraan het wordt verbonden.

Er zijn drie soorten kardinaliteit: 1-1, 1-N, en N-N. Het is het type 1-N dat door gebrek wordt gebruikt.

### Voorbeelden {#examples-1}

Een voorbeeld van een verbinding 1-N tussen de ontvankelijke lijst (out-of-the-box schema) en een lijst van douanetransacties:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

Een voorbeeld van een 1-1 verbinding tussen een douaneschema &quot;Auto&quot;(in &quot;cus&quot;namespace) en de ontvankelijke lijst:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

Voorbeeld van een externe verbinding tussen de ontvankelijke lijst en een lijst van adressen die op het e-mailadres en niet een primaire sleutel wordt gebaseerd:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

Hier komt &#39;xpath-dst&#39; overeen met de primaire sleutel in het doelschema en &#39;xpath-src&#39; komt overeen met de externe sleutel in het bronschema.

## Audit trail {#audit-trail}

Eén handig element dat u onder aan het schema wilt opnemen, is een element tracking (audittrail).

In het onderstaande voorbeeld kunt u velden opnemen die betrekking hebben op de aanmaakdatum, de gebruiker die de gegevens heeft gemaakt, de datum en de auteur van de laatste wijziging voor alle gegevens in de tabel:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## De databasestructuur bijwerken {#updating-the-database-structure}

Nadat de wijzigingen zijn voltooid en opgeslagen, moeten alle wijzigingen die van invloed kunnen zijn op de SQL-structuur worden toegepast op de database. Om dit te doen, gebruik de medewerker van de gegevensbestandupdate.

![](assets/schemaextension_3.png)

Raadpleeg [deze sectie](update-database-structure.md) voor meer informatie.

>[!NOTE]
>
>Wanneer de wijzigingen niet de gegevensbestandstructuur beïnvloeden, moet u enkel schema&#39;s regenereren. Selecteer hiertoe de schema&#39;s die u wilt bijwerken, klik met de rechtermuisknop en kies **[!UICONTROL Actions > Regenerate selected schemas...]**.

