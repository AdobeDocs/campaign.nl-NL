---
title: Een koppeling toevoegen aan de spiegelpagina
description: Leer hoe u de koppeling naar de spiegel toevoegt en beheert
feature: Email
role: User
level: Beginner
source-git-commit: e2aaf80a5a0d74161152fabe8ea157d31923ee19
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# Koppeling maken naar de spiegelpagina{#mirror-page}

## Over de spiegelpagina{#about-mirror-page}

De spiegelpagina is een online versie van uw e-mail.

Hoewel de meeste e-mailclients afbeeldingen zonder problemen renderen, kunnen bepaalde voorinstellingen om beveiligingsredenen voorkomen dat afbeeldingen worden weergegeven. Gebruikers kunnen naar de spiegelpagina van een e-mailbericht bladeren, bijvoorbeeld als ze problemen ondervinden met het renderen of als ze afbeeldingen proberen te bekijken in hun Postvak IN. Het wordt ook aanbevolen om een onlineversie aan te bieden om toegankelijkheidsredenen of om sociaal delen aan te moedigen.

De spiegelpagina die door Adobe Campaign wordt gegenereerd, bevat alle aanpassingsgegevens.

![voorbeeld van spiegelkoppeling](assets/mirror-page-link.png){width="500" align="left"}

## Een koppeling toevoegen aan de spiegelpagina{#link-to-mirror-page}

Het invoegen van een koppeling naar de spiegelpagina is een goede gewoonte. Deze koppeling kan bijvoorbeeld &#39;Deze e-mail weergeven in uw browser&#39; of &#39;Deze online lezen&#39; zijn. Deze bevindt zich vaak in de kop- of voettekst van de e-mail.

In Adobe Campaign kunt u een koppeling naar de spiegel in de e-mailinhoud invoegen met behulp van de toegewezen **verpersoonlijkingsblok**. De ingebouwde **Koppelen aan spiegelpagina** het verpersoonlijkingsblok neemt de volgende code in uw e-mailinhoud op: `<%@ include view='MirrorPage' %>`.

![](assets/mirror-page-insert.png){width="500" align="left"}


<!--For more on personalization blocks insertion, refer to [Personalization blocks](personalization-blocks.md).-->

## Pagina genereren spiegelen{#mirror-page-generation}

Standaard wordt de spiegelpagina automatisch gegenereerd door Adobe Campaign als de e-mailinhoud niet leeg is en als deze een koppeling naar de spiegelpagina bevat (ook wel de koppeling Mirror genoemd).

U kunt de generatiemodus van de spiegel voor e-mail bepalen. De opties zijn beschikbaar in de leveringseigenschappen. U kunt deze opties als volgt openen:

1. Bladeren naar de **[!UICONTROL Validity]** tabblad van de e-maileigenschappen.
1. In de **Paginabeheer spiegelen** sectie, controleren **[!UICONTROL Mode]** vervolgkeuzelijst.

![](assets/mirror-page-generation.png){width="500" align="left"}

Naast de standaardmodus zijn de volgende opties beschikbaar:

* **[!UICONTROL Force the generation of the mirror page]**: Gebruik deze wijze om de spiegelpagina te produceren zelfs als geen verbinding aan de spiegelpagina in de levering wordt opgenomen.
* **[!UICONTROL Do not generate the mirror page]**: Gebruik deze modus om te voorkomen dat een spiegelpagina wordt gegenereerd, zelfs als de koppeling aanwezig is in de levering.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: als de koppeling naar de spiegelpagina niet aanwezig is in de e-mailinhoud, gebruikt u deze optie om toegang tot de inhoud van de spiegelpagina in te schakelen, in het venster van het leveringslogboek, zoals hieronder beschreven.

## De spiegelpagina voor een ontvanger controleren{#mirror-page-access}

U kunt tot de inhoud van de spiegelpagina voor een specifieke ontvanger van een levering, met verpersoonlijkingsgegevens toegang hebben.

Deze spiegelpagina openen:

1. Nadat de levering is verzonden, opent u deze en bladert u naar de betreffende **[!UICONTROL Delivery]** tab.

1. Selecteer een ontvanger en klik op de knop **[!UICONTROL Display the mirror page for this message...]** koppeling.

   ![](assets/mirror-page-display.png){width="500" align="left"}

   De spiegelpagina wordt weergegeven in een speciaal scherm, met verpersoonlijkingsgegevens voor de geselecteerde ontvanger.

