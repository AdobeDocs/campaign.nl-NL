---
title: Een koppeling toevoegen aan de spiegelpagina
description: Leer hoe u een koppeling naar de spiegelpagina maakt
feature: Email
role: User
level: Beginner
source-git-commit: 2c35b169725b5300940260124a4b559eb44ffe43
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# De pagina E-mailspiegel{#mirror-page}

De spiegelpagina is een online versie van uw e-mail.

Hoewel de meeste e-mailclients afbeeldingen zonder problemen renderen, kunnen bepaalde voorinstellingen om beveiligingsredenen voorkomen dat afbeeldingen worden weergegeven. Gebruikers kunnen naar de spiegelpagina van een e-mailbericht bladeren, bijvoorbeeld als ze problemen ondervinden met het renderen of als ze afbeeldingen proberen te bekijken in hun Postvak IN. Het wordt ook aanbevolen om een onlineversie aan te bieden om toegankelijkheidsredenen of om sociaal delen aan te moedigen.

De spiegelpagina die door Adobe Campaign wordt gegenereerd, bevat alle aanpassingsgegevens.

![](assets/mirror-page-link.png)


## Een koppeling toevoegen aan de spiegelpagina{#link-to-mirror-page}

Het invoegen van een koppeling naar de spiegelpagina is een goede gewoonte. Deze koppeling kan bijvoorbeeld &#39;Deze e-mail weergeven in uw browser&#39; zijn en bevindt zich vaak in de kop- of voettekst van een e-mail.

In Adobe Campaign kunt u een koppeling naar de spiegel in de e-mailinhoud invoegen met behulp van de toegewezen **verpersoonlijkingsblok**. Standaard wordt de spiegelpagina alleen gegenereerd als de koppeling is ingevoegd in de inhoud van het bericht.

De ingebouwde **Koppelen aan spiegelpagina** het verpersoonlijkingsblok neemt de volgende code in uw e-mailinhoud op: `<%@ include view='MirrorPage' %>`.

<!--For more on personalization blocks insertion, refer to [Personalization blocks](personalization-blocks.md).-->

## Pagina genereren spiegelen{#mirror-page-generation}

Standaard wordt de spiegelpagina automatisch gegenereerd door Adobe Campaign als de e-mailinhoud niet leeg is en als deze een koppeling naar de spiegelpagina bevat (ook wel de koppeling Mirror genoemd).

U kunt de generatiemodus van de spiegel voor e-mail bepalen. De opties zijn beschikbaar in de leveringseigenschappen. U kunt deze opties als volgt openen:

1. Bladeren naar de **[!UICONTROL Validity]** tabblad van de e-maileigenschappen.
1. In de **Paginabeheer spiegelen** sectie, controleren **[!UICONTROL Mode]** vervolgkeuzelijst.

![](assets/mirror-page-generation.png)

Naast de standaardmodus zijn de volgende opties beschikbaar:

* **[!UICONTROL Force the generation of the mirror page]**: Gebruik deze wijze om de spiegelpagina te produceren zelfs als geen verbinding aan de spiegelpagina in de levering wordt opgenomen.
* **[!UICONTROL Do not generate the mirror page]**: Gebruik deze modus om te voorkomen dat een spiegelpagina wordt gegenereerd, zelfs als de koppeling aanwezig is in de levering.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: gebruik deze optie om toegang tot de inhoud van de spiegelpagina, met verpersoonlijkingsgegevens, in het venster van het leveringslogboek toe te laten. Deze spiegelpagina openen: zodra de levering is verzonden, opent u deze en bladert u naar de bijbehorende **[!UICONTROL Delivery]** tab. Selecteer een ontvanger en klik op de knop **[!UICONTROL Display the mirror page for this message...]** koppeling. De spiegelpagina wordt weergegeven in een nieuw tabblad.

