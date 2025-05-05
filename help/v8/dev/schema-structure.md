---
title: Campagneschemastructuur
description: Campagneschemastructuur
feature: Schema Extension, Configuration, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: 9c4a9e71-3fc8-4b4e-8782-0742bbeaf426
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '1394'
ht-degree: 1%

---

# Schemastructuur{#schema-structure}

De basisstructuur van een `<srcschema>` is als volgt:

```
<srcSchema>
    <enumeration>
        ...          //definition of enumerations
    </enumeration>
   
    <element>         //definition of the root <element>    (mandatory)

        <compute-string/>  //definition of a compute-string
        <key>
            ...        //definition of keys
        </key>
        <sysFilter>
            ...           //definition of filters
        </sysFilter>
        <attribute>
            ...             //definition of fields
        </attribute>
    
            <element>           //definition of sub-<element> 
                  <attribute>           //(collection, links or XML)
                  ...                         //and additional fields
                  </attribute>
                ...
            </element>
      
    </element> 

        <methods>                 //definition of SOAP methods
            <method>
                ...
            </method>
            ...
    </methods>  
          
</srcSchema>
```

Het document van XML van een gegevensschema moet het **`<srcschema>`** wortelelement met de **naam** en **namespace** attributen bevatten om de schemanaam en zijn namespace te bevolken.

```
<srcSchema name="schema_name" namespace="namespace">
...
</srcSchema>
```

Laten we de volgende XML-inhoud gebruiken om de structuur van een gegevensschema te illustreren:

```
<recipient email="John.doe@aol.com" created="AAAA/DD/MM" gender="1"> 
  <location city="London"/>
</recipient>
```

Met het bijbehorende gegevensschema:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email"/>
    <attribute name="created"/>
    <attribute name="gender"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

## Beschrijving {#description}

Het punt van ingang van het schema is zijn belangrijkste element. Het is gemakkelijk te identificeren omdat het de zelfde naam zoals het schema heeft, en het zou het kind van het wortelelement moeten zijn. De beschrijving van de inhoud begint met dit element.

In ons voorbeeld wordt het hoofdelement vertegenwoordigd door de volgende regel:

```
<element name="recipient">
```

Met de elementen **`<attribute>`** en **`<element>`** die volgen op het hoofdelement kunt u de locaties en namen van de gegevensitems in de XML-structuur definiëren.

In ons voorbeeldschema zijn de volgende:

```
<attribute name="email"/>
<attribute name="created"/>
<attribute name="gender"/>
<element name="location">
  <attribute name="city"/>
</element>
```

De volgende regels moeten in acht worden genomen:

* Elk **`<element>`** en **`<attribute>`** moeten door naam via het **naam** attribuut worden geïdentificeerd.

  >[!CAUTION]
  >
  >De naam van het element moet beknopt zijn, bij voorkeur in het Engels, en alleen geoorloofde tekens bevatten in overeenstemming met de XML-naamgevingsregels.

* Alleen **`<element>`** -elementen kunnen **`<attribute>`** -elementen en **`<element>`** -elementen in de XML-structuur bevatten.
* Een **`<attribute>`** -element moet een unieke naam binnen een **`<element>`** hebben.
* Het gebruik van **`<elements>`** in gegevensreeksen met meerdere regels wordt aanbevolen.

## Datatypen {#data-types}

Het gegevenstype is ingegaan via het **type** attribuut in **`<attribute>`** en **`<element>`** elementen.

Een gedetailleerde lijst is beschikbaar in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html#configuring-campaign-classic){target="_blank"} .

Wanneer dit attribuut niet bevolkt is, **koord** is het standaardgegevenstype tenzij het element kindelementen bevat. Als het, wordt het gebruikt slechts om de elementen hiërarchisch te structureren (**`<location>`** element in ons voorbeeld).

De volgende gegevenstypen worden ondersteund in schema&#39;s:

* **koord**: karakterkoord. Voorbeelden: een voornaam, een stad, enz.

  De grootte kan via het **lengte** attribuut (facultatieve, standaardwaarde &quot;255&quot;) worden gespecificeerd.

* **boolean**: Van Boole gebied. Voorbeeld van mogelijke waarden: true/false, 0/1, ja/nee enz.
* **byte**, **kort**, **lang**: gehelen (1 byte, 2 bytes, 4 bytes). Voorbeelden: leeftijd, rekeningnummer, aantal punten, enz.
* **dubbel**: dubbel-precisie drijvende puntaantal. Voorbeelden: een prijs, een tarief enz.
* **datum**, **datetime**: data en data + tijden. Voorbeelden: geboortedatum, aankoopdatum enz.
* **datetimenotz**: datum + tijd zonder gegevens van de tijdzone.
* **timespan**: duur. Voorbeeld: anciënniteit.
* **memo**: lange tekstgebieden (veelvoudige lijnen). Voorbeelden: een beschrijving, een opmerking enz.
* **uuid**: &quot;uniqueidentifier&quot;gebieden

  >[!NOTE]
  >
  >Om a **uuid** gebied te bevatten, moet de &quot;newuid ()&quot;functie met zijn standaardwaarde worden toegevoegd en worden voltooid.

Hier is ons voorbeeldschema met de ingevoerde types:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email" type="string" length="80"/>
    <attribute name="created" type="datetime"/>
    <attribute name="gender" type="byte"/>
    <element name="location">
      <attribute name="city" type="string" length="50"/>
   </element>
  </element>
</srcSchema>
```

## Properties {#properties}

De **`<elements>`** - en **`<attributes>`** -elementen van het gegevensschema kunnen met verschillende eigenschappen worden verrijkt. U kunt een label vullen om het huidige element te beschrijven.

### Labels en beschrijvingen {#labels-and-descriptions}

* Het **etiket** bezit laat u een korte beschrijving ingaan.

  >[!NOTE]
  >
  >Het label is gekoppeld aan de huidige taal van de instantie.

  **Voorbeeld**:

  ```
  <attribute name="email" type="string" length="80" label="Email"/>
  ```

  Het label kan worden weergegeven op het invoerformulier voor de Adobe Campaign-clientconsole:

  ![](assets/schema_label.png)

* Het **desc** bezit laat u een lange beschrijving ingaan.

  De beschrijving is te zien vanaf het invoerformulier in de statusbalk van het hoofdvenster van de Adobe Campaign-clientconsole.

  >[!NOTE]
  >
  >De beschrijving is gekoppeld aan de huidige taal van de instantie.

  **Voorbeeld**:

  ```
  <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
  ```

### Standaardwaarden {#default-values}

Het **gebrek** bezit laat u een uitdrukking bepalen die een standaardwaarde op inhoudsverwezenlijking terugkeert.

De waarde moet een expressie zijn die compatibel is met XPath-taal. Raadpleeg [deze sectie](#reference-with-xpath) voor meer informatie.

**Voorbeeld**:

* Huidige datum: **default= &quot;GetDate ()&quot;**
* Teller: **default=&quot;&#39;FRM&#39;+CounterValue (&#39;myCounter&#39;)&quot;**

  In dit voorbeeld, wordt de standaardwaarde geconstrueerd gebruikend de aaneenschakeling van een koord en roepend de **functie CounterValue** met een vrije tellernaam. Het geretourneerde getal wordt bij elke invoeging met één verhoogd.

  >[!NOTE]
  >
  >In de Adobe Campaign-clientconsole wordt het knooppunt **[!UICONTROL Administration>Counters]** gebruikt om tellers te beheren.

Als u een standaardwaarde aan een veld wilt koppelen, kunt u de opdracht `<default>  or  <sqldefault>   field.  </sqldefault> </default>`

`<default>`: hiermee kunt u het veld vooraf vullen met een standaardwaarde wanneer u entiteiten maakt. De waarde wordt geen standaard SQL-waarde.

`<sqldefault>`: hiermee kunt u een toegevoegde waarde krijgen wanneer u een veld maakt. Deze waarde wordt weergegeven als een SQL-resultaat. Tijdens een schema-update worden alleen de nieuwe records beïnvloed door deze waarde.

### Opsommingen {#enumerations}

#### Vrije opsomming {#free-enumeration}

Het **userEnum** bezit laat u een vrije opsomming bepalen om de waarden te memoriseren en te tonen die via dit gebied zijn ingegaan. De syntaxis is als volgt:

**userEnum= &quot;naam van opsomming&quot;**

De naam die aan de opsomming wordt gegeven kan vrij worden gekozen en met andere gebieden worden gedeeld.

Deze waarden worden weergegeven in een vervolgkeuzelijst van het invoerformulier:

![](assets/schema_user_enum.png)

>[!NOTE]
>
>In de Adobe Campaign-clientconsole wordt het knooppunt **[!UICONTROL Administration > Enumerations]** gebruikt om opsommingen te beheren.

#### Opsomming instellen {#set-enumeration}

Het **enum** bezit laat u een vaste opsomming bepalen die wordt gebruikt wanneer de lijst van mogelijke waarden vooraf gekend is.

Het **enum** attribuut verwijst naar de definitie van een opsommingsklasse die in het schema buiten het belangrijkste element wordt bevolkt.

Met opsommingen kan de gebruiker een waarde in een vervolgkeuzelijst selecteren in plaats van de waarde in te voeren in een gewoon invoerveld:

![](assets/schema_enum.png)

Voorbeeld van een opsommingsdeclaratie in het gegevensschema:

```
<enumeration name="gender" basetype="byte" default="0">    
  <value name="unknown" label="Not specified" value="0"/>    
  <value name="male" label="male" value="1"/>   
  <value name="female" label="female" value="2"/>   
</enumeration>
```

Een opsomming wordt buiten het hoofdelement gedeclareerd via het element **`<enumeration>`** .

De opsommingseigenschappen zijn als volgt:

* **baseType**: type van gegevens verbonden aan de waarden,
* **etiket**: beschrijving van de opsomming,
* **naam**: naam van de opsomming,
* **gebrek**: standaardwaarde van de opsomming.

De opsommingswaarden worden gedeclareerd in het element **`<value>`** met de volgende kenmerken:

* **naam**: naam van de waarde die intern wordt opgeslagen,
* **etiket**: etiket dat via de grafische interface wordt getoond.

#### dbenum-opsomming {#dbenum-enumeration}

* Het **dbenum** bezit laat u een opsomming bepalen de waarvan eigenschappen aan die van het **zijn enum** bezit.

  Nochtans, slaat het **naam** attribuut intern niet de waarde op, het slaat een code op die u de betrokken lijsten zonder hun schema uit te breiden laat uitbreiden.

  De waarden worden gedefinieerd via het knooppunt **[!UICONTROL Administration>Enumerations]** .

  Deze opsomming wordt bijvoorbeeld gebruikt om de aard van campagnes op te geven.

  ![](assets/schema_dbenum.png)

### Voorbeeld {#example}

Hier volgt ons voorbeeldschema met de eigenschappen die zijn ingevuld:

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="male" value="1"/>   
    <value name="female" label="female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
    <attribute name="created" type="datetime" label="Date of creation" default="GetDate()"/>
    <attribute name="gender" type="byte" label="gender" enum="gender"/>
    <element name="location" label="Location">
      <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
   </element>
  </element>
</srcSchema>
```

## Verzamelingen {#collections}

Een verzameling is een lijst met elementen met dezelfde naam en hetzelfde hiërarchische niveau.

Het **niet verbindende** attribuut met de waarde &quot;waar&quot;laat u een inzamelingselement bevolken.

**Voorbeeld**: definitie van het **`<group>`** inzamelingselement in het schema.

```
<element name="group" unbound="true" label="List of groups">
  <attribute name="label" type="string" label="Label"/>
</element>
```

Met projectie van de XML-inhoud:

```
<group label="Group1"/>
<group label="Group2"/>
```

## Verwijzing met XPath {#reference-with-xpath}

De XPath-taal wordt in Adobe Campaign gebruikt om naar een element of kenmerk te verwijzen dat of dat tot een gegevensschema behoort.

XPath is een syntaxis waarmee u een knooppunt in de boomstructuur van een XML-document kunt zoeken.

Elementen worden aangeduid met hun naam en kenmerken worden aangeduid met de naam voorafgegaan door het teken &quot;@&quot;.

**Voorbeeld**:

* **@email** : hiermee selecteert u het e-mailbericht,
* **plaats/@city**: selecteert de &quot;stad&quot;attributen onder het **`<location>`** element
* **../@email**: hiermee selecteert u het e-mailadres in het bovenliggende element van het huidige element
* **groep`[1]/@label`**: selecteert het &quot;etiket&quot;attribuut dat het kind van het eerste **`<group>`** inzamelingselement is
* **groep`[@label='test1']`**: selecteert het &quot;etiket&quot;attribuut dat het kind van het **`<group>`** element is en de waarde &quot;test1&quot;bevat

>[!NOTE]
>
>Er wordt een extra beperking toegevoegd wanneer het pad een subelement kruist. In dit geval moet de volgende expressie tussen haakjes worden geplaatst:
>
>* **plaats/@city** is ongeldig; gelieve te gebruiken **`[location/@city]`**
>* **`[@email]`** en **@email** zijn gelijk
>

Het is ook mogelijk complexe expressies te definiëren, zoals de volgende rekenkundige bewerkingen:

* **@gender+1**: voegt 1 aan de inhoud van het **gender** attribuut toe,
* **@email + &#39;(&#39;+@created+&#39;)&#39;**: hiermee maakt u een tekenreeks door de waarde te nemen van het e-mailadres dat tussen haakjes aan de aanmaakdatum is toegevoegd (voor het type tekenreeks plaatst u de constante tussen aanhalingstekens).

Er zijn functies op hoog niveau toegevoegd aan de expressies om het potentieel van deze taal te verrijken.

U hebt toegang tot de lijst met beschikbare functies via een expressie-editor in de Adobe Campaign-clientconsole:

![](assets/schema_function.png)

**Voorbeeld**:

* **GetDate ()**: keert de huidige datum terug
* **Jaar (@created)**: keert het jaar van de datum in het &quot;gecreeerde&quot;attribuut terug.
* **GetEmailDomain (@email)**: keert het domein van het e-mailadres terug.

## Een tekenreeks samenstellen via de compute string {#building-a-string-via-the-compute-string}

A **verwerkt koord** is een uitdrukking van XPath die wordt gebruikt om een koord te construeren dat een verslag in een lijst vertegenwoordigt verbonden aan het schema. **verwerkt koord** wordt hoofdzakelijk gebruikt in de grafische interface om het etiket van een geselecteerd verslag te tonen.

Het **berekent koord** wordt bepaald via het **`<compute-string>`** element onder het belangrijkste element van het gegevensschema. Een **expr** attribuut bevat een uitdrukking van XPath om de vertoning te berekenen.

**Voorbeeld**: compute koord van de ontvankelijke lijst.

```
<srcSchema name="recipient" namespace="nms">  
  <element name="recipient">
    <compute-string expr="@lastName + ' ' + @firstName +' (' + @email + ')' "/>
    ...
  </element>
</srcSchema>
```

Resultaat van het gegevens verwerkte koord voor een ontvanger: **Doe John (john.doe@aol.com)**

>[!NOTE]
>
>Als het schema geen Compute koord bevat, wordt een Compute koord bevolkt door gebrek met de waarden van de primaire sleutel van het schema.
