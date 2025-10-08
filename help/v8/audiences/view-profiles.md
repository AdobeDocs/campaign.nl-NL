---
title: Bestaande profielen weergeven in campagne
description: Leer hoe u contactgegevens kunt openen in Campagne
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
version: Campaign v8, Campaign Classic v7
source-git-commit: ec1b41ccf532b044e75c69e795eabfb19a523ec2
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 2%

---

# Bestaande profielen weergeven {#view-profiles}

Blader naar **[!UICONTROL Profiles and targets]** om toegang te krijgen tot ontvangers die zijn opgeslagen in de Adobe Campaign-database.

Van deze pagina, kunt u [&#x200B; nieuwe ontvanger &#x200B;](create-profiles.md) tot stand brengen, een bestaande ontvanger uitgeven en tot zijn profieldetails toegang hebben.

![](assets/profiles-and-targets.png)

Voor geavanceerdere profielmanipulaties opent u de Campagnestructuur via de koppeling **[!UICONTROL Explorer]** op de startpagina van Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>Het ingebouwde scherm van de Ontvanger wordt bepaald door een schema van XML en zijn bijbehorende vorm. Het XML-schema wordt opgeslagen in het knooppunt **[!UICONTROL Administration > Configuration > Data schemas]** van de Adobe Campaign Explorer-boomstructuur. Alleen deskundige gebruikers kunnen wijzigingen aanbrengen in deze schema&#39;s.
>

## Een profiel bewerken {#edit-a-profiles}

Selecteer een profiel om details op een nieuw tabblad weer te geven.

![](assets/edit-a-profile.png)

De gegevens over profielen worden gegroepeerd in tabbladen. Deze tabbladen en hun inhoud zijn afhankelijk van uw specifieke instellingen en geïnstalleerde pakketten.

Voor een standaard ingebouwde ontvanger hebt u toegang tot de volgende tabbladen:

* **[!UICONTROL General]** voor alle algemene profielgegevens. Het bevat met name de achternaam, voornaam, e-mailadres, e-mailnotatie, enz.

  Dit lusje slaat ook de **opt-out** vlag voor het profiel op: wanneer de **[!UICONTROL No longer contact (by any channel)]** optie wordt geselecteerd, is het profiel op lijst van gewezen personen. Deze informatie wordt toegevoegd aan de contactgegevens als de ontvanger bijvoorbeeld op een koppeling voor niet-abonnementen in een nieuwsbrief heeft geklikt. Deze ontvanger is niet meer gericht op enig kanaal (e-mail, direct mail, enz.). Raadpleeg [deze pagina](../send/quarantines.md) voor meer informatie.

* **de informatie van het Contact**, die het directe postadres van het geselecteerde profiel bevat.

  U kunt in dit scherm de kwaliteitsindex van het adres controleren, en hoeveel fouten het adres bevat. Deze informatie wordt rechtstreeks door de direct-mailprovider gebruikt, op basis van het aantal fouten dat tijdens eerdere leveringen is aangetroffen, en kan niet handmatig worden gewijzigd.

* **Andere**, voor specifieke gebieden die afhankelijk van uw behoeften kunnen worden gepersonaliseerd en worden bevolkt.

  In het contextmenu **[!UICONTROL Field properties…]** kunt u de namen van de velden wijzigen en de indeling van de velden definiëren.

  ![](assets/other-tab-field-properties.png)

  Voer de nieuwe instellingen hieronder in:

  ![](assets/change-field-properties.png)

  Controleer de update in de gebruikersinterface:

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >Wijzigingen gelden voor alle ontvangers.
  >


* **Abonnementen**, voor alle actieve abonnementen aan de diensten. Gebruik het **lusje van de Geschiedenis** aan toegangsdetails van abonnementen en oncessies voor dit contact.

  ![](assets/subscription-tab.png)

  Leer meer over Abonnementen [&#x200B; in deze sectie &#x200B;](../start/subscriptions.md).

* **levert**, voor alle leveringslogboeken voor het geselecteerde profiel. Op dit tabblad hebt u via alle kanalen toegang tot de marketinggeschiedenis van de contactpersoon: labels, datums en status van alle leveringsacties die aan het profiel zijn gericht.


* **het Volgen**, voor alle het volgen logboeken voor het geselecteerde profiel. Deze informatie wordt gebruikt om profielgedrag na leveringen te volgen. Dit tabblad geeft het cumulatieve totaal weer van alle URL&#39;s die in leveringen worden bijgehouden. De lijst is configureerbaar en bevat meestal: de URL waarop is geklikt, de datum en tijd waarop is geklikt en het document dat de URL bevatte

  Leer meer over het Volgen [&#x200B; in deze sectie &#x200B;](../start/tracking.md).
