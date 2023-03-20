---
title: Voorwaardelijke content
description: Leer hoe u voorwaardelijke inhoud maakt
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 10%

---


# Voorwaardelijke content maken{#conditional-content}

Door voorwaardelijke-contentvelden te configureren kunt u geavanceerde personalisaties maken. Volledige tekstblokken en/of afbeeldingen worden vervangen wanneer aan een bepaalde voorwaarde wordt voldaan.


## Voorwaarden in een e-mail gebruiken {#conditions-in-an-email}

In het onderstaande voorbeeld leert u hoe u een bericht maakt dat dynamisch is gepersonaliseerd op basis van de stad en interesses van de ontvanger.

* Wijzig het bericht afhankelijk van de plaats van de ontvanger.
* De inhoud van de aanbieding aanpassen aan de belangen van de afnemer.

Voer de volgende stappen uit om voorwaardelijke inhoud te maken op basis van de waarde van een veld:

1. Open een bestaande levering of maak een nieuwe e-maillevering.
1. Klik in de e-mailinhoudeditor op het pictogram voor aanpassen en selecteer **[!UICONTROL Conditional content > If]**.

   ![Een voorwaarde invoegen](assets/condition-insert.png)

   De verpersoonlijkingselementen worden opgenomen in het berichtlichaam. U moet hen nu vormen.

1. De parameters van de **indien** expressie.

   * Selecteer het eerste element van de expressie. **`<FIELD>`** en klikt u op het pictogram voor aanpassen om dit te vervangen door het testveld.
   * Vervangen **`<VALUE>`** met de waarde van het veld waarvoor aan de voorwaarde wordt voldaan. Deze waarde moet tussen aanhalingstekens staan.
   * Geef de inhoud op die moet worden ingevoegd wanneer aan de voorwaarde wordt voldaan. Dit kan tekst, een afbeelding, een formulier, een hypertekstkoppeling enzovoort zijn.

   ![Voorwaarde in een e-mail](assets/condition-in-email.png)

1. Klik op de knop **[!UICONTROL Preview]** om de inhoud van het bericht weer te geven op basis van de geadresseerde van de levering. Selecteer een ontvanger waarvoor de voorwaarde waar is om de inhoud te controleren. Selecteer vervolgens een andere ontvanger waarvoor deze onwaar is en probeer het opnieuw.

U kunt andere gevallen toevoegen en verschillende inhoud definiëren op basis van de waarden van een of meer velden. Om dit te doen, gebruik **[!UICONTROL Conditional content > Else]** en **[!UICONTROL Conditional content > Else if]**. Deze expressies zijn op dezelfde manier geconfigureerd als de **indien** expressie.

>[!CAUTION]
>
>De **%> &lt;%** tekens moeten worden verwijderd nadat ze zijn toegevoegd **Else** en **Anders indien** voorwaarden.


## Hoofdlettergebruik: een meertalige e-mail maken {#creating-multilingual-email}

In het onderstaande voorbeeld leert u hoe u een meertalige e-mail maakt. De inhoud wordt in de ene of de andere taal weergegeven, afhankelijk van de voorkeurstaal van de ontvanger.

1. Maak een e-mail en selecteer de doelpopulatie. In dit voorbeeld wordt de voorwaarde voor het weergeven van de ene versie of de andere gebaseerd op de **Taal** waarde van het profiel van de ontvanger. Deze waarden zijn ingesteld op **NL**, **FR**, **ES**.
1. Klik in de HTML-inhoud van de e-mail op de knop **[!UICONTROL Source]** kunt u de volgende code plakken en op Tab drukken:

   ```
   <% if (language == "EN" ) { %>
   <DIV id=en-version>Hello <%= recipient.firstName %>,</DIV>
   <DIV>Discover your new offers!</DIV>
   <DIV><a href="https://www.adobe.com/products/en">www.adobe.com/products/en</A></FONT></DIV><%
    } %>
   <% if (language == "FR" ) { %>
   <DIV id=fr-version>Bonjour <%= recipient.firstName %>,</DIV>
   <DIV>Découvrez nos nouvelles offres !</DIV>
   <DIV><a href="https://www.adobe.com/products/fr">www.adobe.com/products/fr</A></DIV><%
    } %>
    <% if (language == "ES" ) { %>
   <DIV id=es-version><FONT face=Arial>
   <DIV>Olà <%= recipient.firstName %>,</DIV>
   <DIV>Descubra nuestros nuevas ofertas !</DIV>
   <DIV><a href="https://www.adobe.com/products/es">www.adobe.com/products/es</A></DIV>
   <% } %>
   ```

1. E-mailinhoud testen in het dialoogvenster **[!UICONTROL Preview]** door ontvangers met verschillende voorkeurstalen te selecteren.

   >[!NOTE]
   >
   >Aangezien er geen alternatieve versie is gedefinieerd in de e-mailinhoud, moet u de doelpopulatie filteren voordat u de e-mail verzendt.

## Video over zelfstudie {#conditionnal-content-video}

Deze video laat zien hoe u voorwaardelijke content aan een levering kunt toevoegen, bijvoorbeeld aan een meertalige nieuwsbrief.

>[!VIDEO](https://video.tv.adobe.com/v/335682?quality=12)

