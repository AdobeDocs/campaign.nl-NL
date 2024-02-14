---
title: Bestaande profielen weergeven in campagne
description: Leer hoe u contactgegevens kunt openen in Campagne
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: b5574ba2d9fa520b701f7af4e34862304b825a66
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 2%

---

# Bestaande profielen weergeven{#view-profiles}

Bladeren naar **[!UICONTROL Profiles and targets]** om toegang te krijgen tot ontvangers die zijn opgeslagen in de Adobe Campaign-database.

Op deze pagina kunt u [nieuwe ontvanger maken](create-profiles.md), bewerkt u een bestaande ontvanger en opent u de profieldetails.

![](assets/profiles-and-targets.png)

Voor geavanceerdere profielbewerkingen opent u de Campagne vanuit de **[!UICONTROL Explorer]** koppeling op de startpagina van Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>Het ingebouwde scherm Ontvanger wordt bepaald door een schema van XML en zijn bijbehorende vorm. Het XML-schema wordt opgeslagen in het **[!UICONTROL Administration > Configuration > Data schemas]** knooppunt van de Adobe Campaign Explorer-boomstructuur. Alleen deskundige gebruikers kunnen wijzigingen aanbrengen in deze schema&#39;s.
>

## Een profiel bewerken{#edit-a-profiles}

Selecteer een profiel om details op een nieuw tabblad weer te geven.

![](assets/edit-a-profile.png)

De gegevens over profielen worden gegroepeerd in tabbladen. Deze tabbladen en hun inhoud zijn afhankelijk van uw specifieke instellingen en geïnstalleerde pakketten.

Voor een standaard ingebouwde ontvanger hebt u toegang tot de volgende tabbladen:

* **[!UICONTROL General]** voor alle algemene profielgegevens. Het bevat met name de achternaam, voornaam, e-mailadres, e-mailnotatie, enz.

  Op dit tabblad wordt ook het dialoogvenster **opt-out** markering voor het profiel: wanneer de **[!UICONTROL No longer contact (by any channel)]** is geselecteerd, bevindt het profiel zich op lijst van gewezen personen. Deze informatie wordt toegevoegd aan de contactgegevens als de ontvanger bijvoorbeeld op een koppeling voor niet-abonnementen in een nieuwsbrief heeft geklikt. Deze ontvanger is niet meer gericht op enig kanaal (e-mail, direct mail, enz.). Raadpleeg [deze pagina](../send/quarantines.md) voor meer informatie.

* **Contactgegevens**, die het directe-mailadres van het geselecteerde profiel bevat.

  U kunt in dit scherm de kwaliteitsindex van het adres controleren, en hoeveel fouten het adres bevat. Deze informatie wordt rechtstreeks door de direct-mailprovider gebruikt, op basis van het aantal fouten dat tijdens eerdere leveringen is aangetroffen, en kan niet handmatig worden gewijzigd.

* **Overige**, voor specifieke velden die u naar wens kunt aanpassen en vullen.

  Gebruik de **[!UICONTROL Field properties…]** contextueel menu om de namen van de velden te wijzigen en hun indeling te definiëren.

  ![](assets/other-tab-field-properties.png)

  Voer de nieuwe instellingen hieronder in:

  ![](assets/change-field-properties.png)

  Controleer de update in de gebruikersinterface:

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >Wijzigingen gelden voor alle ontvangers.
  >


* **Abonnementen**, voor alle actieve abonnementen op services. Gebruik de **Historie** tabblad voor toegang tot details over abonnementen en abonnementen voor deze contactpersoon.

  ![](assets/subscription-tab.png)

  Meer informatie over abonnementen [in deze sectie](../start/subscriptions.md).

* **Leveringen**, voor alle leveringslogboeken voor het geselecteerde profiel. Op dit tabblad hebt u via alle kanalen toegang tot de marketinggeschiedenis van de contactpersoon: labels, datums en status van alle leveringsacties die aan het profiel zijn gericht.


* **Tekstspatiëring**, voor alle trackinglogboeken voor het geselecteerde profiel. Deze informatie wordt gebruikt om profielgedrag na leveringen te volgen. Dit tabblad geeft het cumulatieve totaal weer van alle URL&#39;s die in leveringen worden bijgehouden. De lijst is configureerbaar en bevat meestal: de URL waarop is geklikt, de datum en tijd waarop is geklikt en het document dat de URL bevatte

  Meer informatie over bijhouden [in deze sectie](../start/tracking.md).


## Actieve profielen {#active-profiles}

Een actief profiel is een profiel waarmee klanten de afgelopen twaalf maanden via een willekeurig kanaal hebben geprobeerd te communiceren. De licentiemetriek is gebaseerd op actieve profielen. Meer informatie in [Adobe Campaign-productbeschrijving](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

>[!CAUTION]
>
>* Een profiel dat voor meerdere leveringen is bedoeld, wordt slechts eenmaal geteld.
>
>* Profielen die in het kader van de sociale marketing op X (voorheen bekend als Twitter) als doel zijn geselecteerd, worden niet als actieve profielen in aanmerking genomen.

U kunt het aantal actieve profielen op uw instantie direct van het Controlebord van de Campagne controleren. Raadpleeg voor meer informatie de [Documentatie van het regelpaneel](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}.
