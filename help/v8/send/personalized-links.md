---
title: Gepersonaliseerde koppelingen bijhouden
description: Leer hoe u persoonlijke koppelingen kunt bijhouden in e-mails
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 1%

---

# Gepersonaliseerde koppelingen bijhouden {#tracking-personalized-links}

De koppelingen in e-mailinhoud die personalisatie bevatten, moeten specifiek worden gesynchroniseerd om te worden bijgehouden.

Met JavaScript in e-mailinhoud (HTML of Text) kunt u dynamische inhoud genereren en verzenden naar de ontvangers, met twee beperkingen:

* Het script heeft niet rechtstreeks toegang tot de database (SQL-functie en API-functies zijn niet beschikbaar).
* Adobe Campaign moet URL&#39;s kunnen detecteren zodat koppelingen kunnen worden bijgehouden.

## Voorverwerkingsinstructies {#pre-processing-instructions}

U kunt specifieke voorbewerkingsinstructies toevoegen om de URL te scripten en bij te houden. Deze instructies moeten in JavaScript worden geschreven en met `<%@` beginnen.

Bijvoorbeeld:

```
<%@ value object="myObject" xpath="@myField" %>
```

Deze instructie haalt de waarde van het veld `myField` op uit het object `myObject` .

## URL-detectie {#url-detection}

Voor het volgen opsporing, bedt Adobe Campaign [&#x200B; Tidy &#x200B;](https://www.html-tidy.org/) in om de bron van HTML te ontleden en het patroon te ontdekken. Alle URL&#39;s van de inhoud worden weergegeven zodat ze afzonderlijk kunnen worden bijgehouden. Adobe Campaign gebruikt Tidy opnieuw om de URL (`http://myurl.com`) te vervangen door een URL die naar de Adobe Campaign-omleidingsserver wijst.

In de eerste inhoud bijvoorbeeld: `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>` wordt voor een bepaalde ontvanger vervangen door: `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`

Waarbij:

* &quot;h&quot; betekent HTML-inhoud (of &quot;t&quot; voor tekstinhoud).
* 617791 is de bericht-id / wideLog-id (hexadecimaal).
* 71ffa3 is NmsDelivery ID (hexadecimaal).
* 71ffa8 is de (hexadecimale) NmsTrackingUrl-id.
* p1, p2, enzovoort, zijn alle parameters die in de URL moeten worden vervangen.

### Voorbeeld van niet-detectie {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>` werkt en verzendt de feitelijke inhoud van de webpagina via e-mail naar de ontvangers. Maar geen van de koppelingen wordt bijgehouden. De reden hiervoor is dat de MTA `"<%=getURL(..."` voor elke e-mail uitvoert alvorens te verzenden. Het kan voor elke ontvanger verschillend zijn, zodat kan Adobe Campaign niet de URLs voor het volgen kennen en hen een markeringsidentiteitskaart toewijzen.

Wanneer de te downloaden pagina voor alle ontvangers het zelfde is, is de beste praktijken:

```
<%@ include url="http://mynewsletter.com" %>
```

In dat geval wordt de pagina tijdens de analyse gedownload, voordat de traceringsdetectie wordt uitgevoerd. Zo kan Adobe Campaign de koppelingen detecteren, een tag-id toewijzen en bijhouden.

### Aanbevolen patroon {#recommended-pattern}

Na het verwerken van `<%@` instructies moet de URL die moet worden bijgehouden de volgende syntaxis hebben:

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>Alle andere patronen worden niet ondersteund door Adobe en moeten worden vermeden om potentiële veiligheidstekortkomingen te voorkomen.

## URL-parameters {#url-parameters}

Om ervoor te zorgen dat gepersonaliseerde URL&#39;s correct worden bijgehouden, moet u de functie `escapeUrl()` of de aangewezen coderingsmethode voor de parameters in uw URL&#39;s gebruiken.

**Voorbeeld:**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

Zo zorgt u ervoor dat de gepersonaliseerde parameter correct wordt gecodeerd en bijgehouden door Adobe Campaign.

## Herhaling met `<%@ foreach %>` {#foreach}

Met de instructie `<%@ foreach %>` kunt u meerdere arrays objecten doorlopen die in de levering zijn geladen om afzonderlijke koppelingen bij te houden die betrekking hebben op de objecten.

### Syntaxis

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**Parameters:**

* **`object`**: naam van het object waarvan moet worden begonnen (doorgaans een extra scriptobject, maar dit kan een levering zijn)
* **`xpath`** (optioneel): XPath van de verzameling dat moet worden doorlopen. Standaard is &quot;.&quot;, wat betekent dat het object de array is die moet worden doorlopen
* **`index`** (optioneel): als xpath niet &quot;.&quot; en object is een array zelf, itemindex van object (begint bij 0)
* **`item`** (optioneel): naam van een nieuw object dat toegankelijk is met `<%@ value %>` in de foreach-lus. Standaard is de naam van de koppeling in het schema

### Voorbeeld

Laad in de leveringseigenschappen/personalisatie een array met artikelen en een tabel met de relatie tussen ontvanger en artikelen.

U kunt koppelingen naar deze artikelen weergeven met afzonderlijke tracking:

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

Op deze manier kan Adobe Campaign bijhouden welk specifiek artikel door elke ontvanger is aangeklikt, in plaats van alleen te controleren of op een artikelkoppeling is geklikt.

## Best practices {#best-practices}

* Altijd de functie `escapeUrl()` gebruiken voor dynamische URL-parameters
* Gebruik `<%@ foreach %>` wanneer u afzonderlijke items in verzamelingen moet bijhouden
* Test het volgen alvorens uw levering te verzenden om ervoor te zorgen dat alle verbindingen correct werken
* Controleren of gepersonaliseerde koppelingen correct zijn opgemaakt in de leveringsinhoud
* Controleer de volgende logboeken om te bevestigen dat de gepersonaliseerde parameters correct worden gevangen

## Verwante onderwerpen {#related-topics}

* [Leer hoe u bijgehouden koppelingen kunt configureren](tracked-links.md)
* [Leer hoe u opties voor het bijhouden van URL&#39;s configureert](url-tracking.md)
* [Leer hoe u verpersoonlijkingsvelden kunt toevoegen](personalization-fields.md)

