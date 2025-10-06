---
product: campaign
title: Een voorstel toevoegen op een webpagina
description: Meer informatie over het toevoegen van een aanbieding op een webpagina
feature: Interaction, Offers
role: User, Admin
exl-id: 1eb0775a-5da9-4a27-aa7b-339372748f9c
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '1454'
ht-degree: 0%

---

# Een voorstel toevoegen op een webpagina{#add-an-offer-in-web}

Om de motor van de Aanbieding in een Web-pagina te roepen, neem direct een vraag aan een code van JavaScript in de pagina op. Deze vraag keert de aanbiedingsinhoud in een gericht element terug.

Het script dat URL aanroept ziet er als volgt uit:

```
<script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=" type="text/javascript"></script>
```

De &quot;**env**&quot;parameter ontvangt de interne naam van het levende milieu gewijd aan anonieme interactie.

Om een aanbieding te presenteren, moeten wij een milieu en een aanbiedingsruimte in Adobe Campaign creëren, dan de pagina van HTML vormen.

In de volgende gebruiksgevallen worden de mogelijke opties voor het integreren van aanbiedingen via JavaScript beschreven.

## Optie 1: HTML-modus {#html-mode}

### Een anonieme aanbieding presenteren {#presenting-an-anonymous-offer}

**Stap 1: Bereid de motor van de Aanbieding voor**

1. Open de Adobe Campaign-interface en bereid een anonieme omgeving voor.
1. Maak een aanbiedingsruimte die is gekoppeld aan de anonieme omgeving.
1. Maak een aanbieding en geef deze weer in verband met de aanbiedingsruimte.

**Stap 2: Werk de inhoud van de pagina van HTML** bij

De HTML-pagina moet een element met een @id-kenmerk bevatten met de waarde van de interne naam van de gemaakte aanbiedingsruimte (&quot;i_internal name space&quot;). Het aanbod zal in dit element door Interaction worden opgenomen.

In ons voorbeeld ontvangt het kenmerk @id de waarde &quot;i_SPC12&quot;, waarbij &quot;SPC12&quot; de interne naam is van de eerder gemaakte aanbiedingsruimte:

```
<div id="i_SPC12"></div>
```

In ons voorbeeld is de URL voor het aanroepen van het script als volgt (&quot;OE3&quot; is de interne naam van de live omgeving):

```
<script id="interactionProposalScript" src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" type="text/javascript"></script>
```

>[!CAUTION]
>
>De tag `<script>` mag niet zelfsluitend zijn.

Deze statische vraag zal automatisch een dynamische vraag produceren die alle parameters bevat nodig door de motor van de Aanbieding.

Dit gedrag laat u verscheidene aanbiedingsruimten op de zelfde pagina gebruiken, die door één enkele vraag aan de motor van de Aanbieding worden beheerd.

**Stap 3: Toon de resultaten in de pagina van HTML**

De inhoud van de aanbiedingsweergave wordt door de aanbiedingsengine aan de HTML-pagina geretourneerd:

```
<div id="banner_header">
 <div id="i_SPC12">
   <table>
    <tbody>
        <tr>
            <td><h3>Fly to Japan!</h3></td>
        </tr>
        <tr>
            <td><img width="150px" src="https://instance.adobe.org/res/Track/874fdaf72ddc256b2d8260bb8ec3a104.jpg"></td>
            <td>
            <p>Discover Japan for 2 weeks at an unbelievable price!!</p>
            <p><b>2345 Dollars - All inclusive</b></p>
        </td>
        </tr>
    </tbody>
    </table>
 </div>
<script src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" id="interactionProposalScript" type="text/javascript"></script>
</div>
```

### Een geïdentificeerde aanbieding presenteren {#presenting-an-identified-offer}

Om een aanbieding aan een geïdentificeerd contact voor te stellen, is het proces gelijkaardig zoals gedetailleerd [ in deze sectie ](#presenting-an-anonymous-offer).

In de inhoud van de Web-pagina, moet u het volgende manuscript toevoegen dat de contact tijdens de vraag aan de motor van de Aanbieding zal identificeren:

```
<script type="text/javascript">
  interactionTarget = <contact_identifier>;
</script>
```

1. Ga naar de aanbiedingsruimte die door de webpagina wordt aangeroepen, klik op **[!UICONTROL Advanced parameters]** en voeg een of meer identificatietoetsen toe.

   ![](assets/interaction_htmlmode_001.png)

   In dit voorbeeld is de identificatiesleutel samengesteld omdat deze zowel op de e-mail als op de naam van de ontvanger is gebaseerd.

1. Tijdens de Web-pagina vertoning, laat de manuscriptevaluatie u ontvankelijke identiteitskaart op de motor van de Aanbieding overgaan. Als de id een samenstelling heeft, worden de toetsen weergegeven in dezelfde volgorde als in de geavanceerde instellingen en worden ze van elkaar gescheiden door een |.

   In het volgende voorbeeld heeft de contactpersoon zich aangemeld bij de website en is de contactpersoon door zijn e-mail en naam herkend tijdens het aanroepen naar de engine voor voorstellen.

   ```
   <script type="text/javascript">
     interactionTarget = myEmail|myName;
   </script>
   ```

### Een HTML-renderfunctie gebruiken {#using-an-html-rendering-function}

Als u de representatie van de HTML-aanbieding automatisch wilt genereren, kunt u een renderfunctie gebruiken.

1. Ga naar de aanbiedingsruimte en klik op **[!UICONTROL Edit functions]** .
1. Selecteer **[!UICONTROL Overload the HTML rendering function]**.
1. Ga naar het tabblad **[!UICONTROL HTML rendering]** en voeg de variabelen die overeenkomen met de velden die voor de aanbiedingsinhoud zijn gedefinieerd, in de aanbiedingsruimte in.

   ![](assets/interaction_htmlmode_002.png)

   In dit voorbeeld wordt de aanbieding weergegeven in de vorm van een banner op een webpagina en bestaat deze uit een klikbare afbeelding en een titel die overeenkomen met de velden die zijn gedefinieerd in de inhoud van de aanbieding.

## Optie 2: XML-modus {#xml-mode}

### Een voorstel presenteren {#presenting-an-offer}

De module van de Interactie van de campagne **** laat u een knoop van XML aan de pagina terugkeren van HTML die de motor van de Aanbieding omhoog roept. Dit XML-knooppunt kan worden verwerkt door functies die aan de kant van de klant moeten worden ontwikkeld.

De vraag aan de motor van de Aanbieding kijkt als dit:

```
<script type="text/javascript" id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=&cb="></script>
```

* De &quot;**env**&quot;parameter ontvangt de interne naam van het levende milieu.

* De &quot;**cb**&quot;parameter ontvangt de naam van de functie die de knoop van XML zal lezen die door de motor is teruggekeerd die (callback) proposition(s) bevat. Deze parameter is optioneel.

* De &quot;**t**&quot;parameter ontvangt de waarde van het doel, slechts voor een geïdentificeerde interactie. Deze parameter kan ook met de **interactionTarget** variabele worden overgegaan. Deze parameter is optioneel.

* De &quot;**c**&quot;parameter ontvangt de lijst van interne namen van de categorieën. Deze parameter is optioneel.

* De &quot;**de**&quot;parameter ontvangt de lijst van thema&#39;s. Deze parameter is optioneel.

* De &quot;**gctx**&quot;parameter ontvangt globale vraaggegevens (context) aan de volledige pagina. Deze parameter is optioneel.

Het geretourneerde XML-knooppunt ziet er als volgt uit:

```
<propositions>
 <proposition id="" offer-id="" weight="" rank="" space="" div=""> //proposition identifiers
   ...XML content defined in Adobe Campaign...
 </proposition>
 ...
</propositions>
```

In het onderstaande gebruiksgeval worden de configuraties beschreven die in Adobe Campaign moeten worden uitgevoerd om de XML-modus in te schakelen en wordt vervolgens het resultaat van de aanroep naar de engine op de HTML-pagina weergegeven.

1. **creeer een milieu en een aanbiedingsruimte**

   Voor meer bij het creëren van een milieu, verwijs naar [ deze pagina ](interaction-env.md).

   Voor meer bij het creëren van een aanbiedingsruimte, verwijs naar [ deze pagina ](interaction-offer-spaces.md).

1. **breid het aanbiedingsschema uit om nieuwe gebieden toe te voegen**

   In dit schema worden de volgende velden gedefinieerd: Titel nummer 2 en prijs.

   De naam van het schema in het voorbeeld is **focus:offer**

   ```
   <srcSchema _cs="Marketing offers (cus)" created="2013-01-18 17:14:20.762Z" createdBy-id="0"
              desc="" entitySchema="xtk:srcSchema" extendedSchema="nms:offer" img="nms:offer.png"
              label="Marketing offers" labelSingular="Marketing offers" lastModified="2013-01-18 15:20:18.373Z"
              mappingType="sql" md5="F14A7AA009AE1FCE31B0611E72866AC3" modifiedBy-id="0"
              name="offer" namespace="cus" xtkschema="xtk:srcSchema">
     <createdBy _cs="Administrator (admin)"/>
     <modifiedBy _cs="Administrator (admin)"/>
     <element img="nms:offer.png" label="Marketing offers" labelSingular="Marketing offer"
              name="offer">
       <element label="Content" name="view">
         <element label="Price" name="price" type="long" xml="true"/>
         <element label="Title 2" name="title2" type="string" xml="true"/>
   
         <element advanced="true" desc="Price calculation script." label="Script price"
                  name="price_jst" type="CDATA" xml="true"/>
         <element advanced="true" desc="Title calculation script." label="Script title"
                  name="title2_jst" type="CDATA" xml="true"/>
       </element>
     </element>
   </srcSchema>
   ```

   >[!CAUTION]
   >
   >Elk element moet tweemaal worden gedefinieerd. CDATA-typeelementen (&quot;_jst&quot;) kunnen personalisatievelden bevatten.
   >
   >Vergeet niet de databasestructuur bij te werken.

   U kunt het aanbiedingsschema uitbreiden om nieuwe velden toe te voegen in batch- en eenheidsmodus en in elke gewenste indeling (tekst, HTML en XML).

1. **breid de aanbiedingsformule uit om nieuwe gebieden uit te geven en een bestaand gebied** te wijzigen

   Bewerk de **Aanbieding (nsm)** inputvorm.

   Voeg in de sectie Weergaven de twee nieuwe velden in met de volgende inhoud:

   ```
   <input label="Title 2" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="title2_jst">
        <form label="Edit title 2" name="editForm" nothingToSave="true">
            <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizeTitle2">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizeTitle2"/>
            </container>
            </input>
        </form>
    </input>
    <input nolabel="true" type="edit" xpath="title2_jst"/>
    <input label="Price" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="price_jst">
        <form label="Edit price" name="editForm" nothingToSave="true">
        <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizePrice">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizePrice"/>
            </container>
        </input>
        </form>
    </input>
    <input colspan="2" label="Prix" nolabel="true" type="number" xpath="price_jst"/>
   ```

   Opmerking toevoegen aan het doel-URL-veld:

   ![](assets/interaction_xmlmode_form_001.png)

   >[!CAUTION]
   >
   >De velden van het formulier ( `<input>` ) moeten verwijzen naar de CDATA-typeelementen die zijn gedefinieerd in het gemaakte schema.

   De rendering in het formulier met aanbiedingsweergaven ziet er als volgt uit:

   ![](assets/interaction_xmlmode_form.png)

   De velden **[!UICONTROL Title 2]** en **[!UICONTROL Price]** zijn toegevoegd en het veld **[!UICONTROL Destination URL]** wordt niet meer weergegeven.

1. **Een aanbieding maken**

   Voor meer bij het creëren van aanbiedingen, verwijs naar [ deze pagina ](interaction-offer.md).

   In het volgende gebruiksgeval wordt de aanbieding als volgt vermeld:

   ![](assets/interaction_xmlmode_offer.png)

1. **keur de aanbieding** goed

   Goedkeuren of laten goedkeuren door iemand anders, dan activeren op de aanbiedingsruimte die bij de laatste stap is gecreëerd, zodat deze beschikbaar wordt gesteld in de gekoppelde live omgeving.

1. **vraag van de Motor en resultaat op de pagina van HTML**

   De oproep aan de engine voor voorstellen op de HTML-pagina ziet er als volgt uit:

   ```
   <script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=OE7&cb=alert" type="text/javascript">
   ```

   De waarde van de &quot;**env**&quot;parameter is de interne naam van het levende milieu.

   De waarde van de &quot;**cb**&quot;parameter is de naam van de functie die de knoop van XML moet interpreteren die door de motor is teruggekeerd. In ons voorbeeld opent de aangeroepen functie een modaal venster (alert() functie).

   Het XML-knooppunt dat door de Offer-engine wordt geretourneerd, ziet er als volgt uit:

   ```
   <propositions>
    <proposition id="a28002" offer-id="10322005" weight="1" rank="1" space="SPC14" div="i_SPC14">
     <xmlOfferView>
      <title>Travel to Russia</title>
      <price>3456</price>
      <description>Discover this vacation package!INCLUDES 10 nights. FEATURES buffet breakfast daily. BONUS 5th night free.</description>
      <image>
       <path>https://myinstance.com/res/Track/ae1d2113ed732d58a3beb441084e5960.jpg</path>
       <alt>Travel to Russia</alt>
      </image>
     </xmlOfferView>
    </proposition>
   </propositions>
   ```

### Een renderfunctie gebruiken {#using-a-rendering-function-}

Het is mogelijk een XML-renderfunctie te gebruiken om een aanbiedingspresentatie te maken. Deze functie wijzigt het XML-knooppunt dat tijdens het aanroepen van de Offertenengine naar de HTML-pagina wordt geretourneerd.

1. Ga naar de aanbiedingsruimte en klik op **[!UICONTROL Edit functions]** .
1. Selecteer **[!UICONTROL Overload the XML rendering function]**.
1. Ga naar de tab **[!UICONTROL XML rendering]** en voeg de gewenste functie in.

   De functie kan er als volgt uitzien:

   ```
   function (proposition) {
     delete proposition.@id;
     proposition.@newAttribute = "newValue";
   } 
   ```

![](assets/interaction_xmlmode_001.png)

## SOAP-integratie instellen

De SOAP-webservices die voor het beheer van aanbiedingen worden aangeboden, verschillen van de services die gewoonlijk in Adobe Campaign worden gebruikt. U hebt toegang tot deze bestanden via de interactie-URL die in de vorige sectie is beschreven. U kunt nu aanbiedingen voor een bepaalde contactpersoon presenteren of bijwerken.

### Voorstel {#offer-proposition}

Voor een aanbiedingsvoorstel via SOAP, voeg het **nms :proposition #Propose** bevel toe dat door de volgende parameters wordt gevolgd:

* **targetId**: primaire sleutel van de ontvanger (kan een samengestelde sleutel zijn).
* **maxCount**: specificeert het aantal aanbiedingsvoorstellen voor het contact.
* **context**: laat u contextinformatie in het ruimteschema toevoegen. Als het gebruikte schema **nms:interaction** is, **`<empty>`** zou moeten worden toegevoegd.
* **categorieën**: specificeert de categorie(ën) de aanbiedingen moeten tot behoren.
* **thema&#39;s**: specificeert de thema(s) die de aanbieding(en) moeten behoren tot.
* **uuid**: waarde van het permanente koekje van Adobe Campaign (&quot;uuid230&quot;).
* **nli**: waarde van het de zittingskoekje van Adobe Campaign (&quot;ongeldig&quot;).
* **noProp**: gebruik de &quot;ware&quot;waarde om voorsteltoevoeging te deactiveren.

>[!NOTE]
>
>De **targetId** en **maxCount** montages zijn verplicht. De andere zijn optioneel.

Als antwoord op de vraag, zal de dienst van SOAP de volgende parameters terugkeren:

* **interactionId**: identiteitskaart van de interactie.
* **voorstellen**: Het element van XML, bevat de lijst van voorstellen, elk met hun eigen identiteitskaart en vertegenwoordiging van HTML.

### Aanbieding bijwerken {#offer-update}

Voeg het **nms :interaction #UpdateStatus** bevel aan URL toe, die door deze parameters wordt gevolgd:

* **voorstel**: koord van karakters, bevat het propositie identiteitskaart die als output tijdens een aanbiedingsvoorstel wordt gegeven. Verwijs naar [ voorstel van de Aanbieding ](#offer-proposition).
* **status**: koordtype, specificeert het de nieuwe status van de aanbieding. De mogelijke waarden zijn vermeld in **propositionStatus** [ opsomming ](../config/enumerations.md), in het **nms:common** schema. Bijvoorbeeld, uit-van-de-doos, beantwoordt aantal 3 aan **Toegelaten** status.
* **context**: Het element van XML, laat u contextinformatie in het ruimteschema toevoegen. Als het gebruikte schema **nms:interaction** is, **`<empty>`** zou moeten worden toegevoegd.

### Voorbeeld met een SOAP-aanroep {#example-using-a-soap-call}

Hier volgt een voorbeeld van code voor een SOAP-aanroep:

```
<%
  var space = request.parameters.sp
  var cnx = new HttpSoapConnection(
    "https://" + request.serverName + ":" + request.serverPort + "/interaction/" + env + "/" + space,
    "utf-8",
    HttpSoapConnection.SOAP_12)
  var session = new SoapService(cnx, "nms:interaction")
  var action = request.parameters.a
  if( action == undefined )
    action = 'propose'

  try
  {
    switch( action )
    {
    case "update":
      var proposition = request.parameters.p
      var status      = request.parameters.st
      session.addMethod("UpdateStatus", "nms:interaction#UpdateStatus",
       ["proposition", "string",
        "status",      "string",
        "context",     "NLElement"],
       [])
      session.UpdateStatus(proposition, status, <undef/>)
      var redirect = request.parameters.r
      if( redirect != undefined )
        response.sendRedirect(redirect)
      break;

    case "propose":
      var count = request.parameters.n
      var target = request.parameters.t
      var categorie = request.parameters.c
      var theme = request.parameters.th
      var layout = request.parameters.l
      if( count == undefined )
        count = 1
      session.addMethod("Propose", "nms:proposition#Propose",
       ["targetId",      "string",
        "maxCount",      "string",
         "categories",    "string",
         "themes",        "string",
        "context",       "NLElement"],
       ["interactionId", "string",
        "propositions",  "NLElement"])
      response.setContentType("text/html")
      var result = session.Propose(target, count, category, theme, <empty/>)
      var props = result[1]
  %><table><tr><%
      for each( var propHtml in props.proposition.*.mdSource )
      {
        %><td><%=propHtml%></td><%
      }
  %></tr></table><%
      break;
    }
  }
  catch( e )
  {
  }
  %>
```
