---
title: Een koppeling toevoegen aan de spiegelpagina
description: Leer hoe u de koppeling naar de spiegel toevoegt en beheert
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 7bf3937c-484d-4404-8a9b-de7a10f5455a
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Koppeling maken naar de spiegelpagina {#mirror-page}

## Over de spiegelpagina {#about-mirror-page}

De spiegelpagina is een online versie van uw e-mail.

Hoewel de meeste e-mailclients afbeeldingen zonder problemen renderen, kunnen bepaalde voorinstellingen om beveiligingsredenen voorkomen dat afbeeldingen worden weergegeven. Gebruikers kunnen naar de spiegelpagina van een e-mailbericht bladeren, bijvoorbeeld als ze problemen ondervinden met het renderen of als ze afbeeldingen proberen te bekijken in hun Postvak IN. Het wordt ook aanbevolen om een onlineversie aan te bieden om toegankelijkheidsredenen of om sociaal delen aan te moedigen.

De spiegelpagina die door Adobe Campaign wordt gegenereerd, bevat alle aanpassingsgegevens.

![&#x200B; de steekproef van de spiegelverbinding &#x200B;](assets/mirror-page-link.png){width="600" align="left"}

## Een koppeling toevoegen aan de spiegelpagina {#link-to-mirror-page}

Het invoegen van een koppeling naar de spiegelpagina is een goede gewoonte. Deze koppeling kan bijvoorbeeld &#39;Deze e-mail weergeven in uw browser&#39; of &#39;Deze online lezen&#39; zijn. Deze bevindt zich vaak in de kop- of voettekst van de e-mail.

In Adobe Campaign, kunt u een verbinding aan de spiegelpagina in de e-mailinhoud opnemen gebruikend het specifieke **verpersoonlijkingsblok**. De ingebouwde **Verbinding aan spiegelpagina** verpersoonlijkingsblok neemt de volgende code in uw e-mailinhoud op: `<%@ include view='MirrorPage' %>`.

![](assets/mirror-page-insert.png){width="800" align="left"}


Voor meer bij het opnemen van de blokken van de verpersoonlijkingsinhoud, verwijs naar [&#x200B; de blokken van de Aanpassing &#x200B;](personalization-blocks.md).

## Het genereren van spiegel beheren {#mirror-page-generation}

Standaard wordt de spiegelpagina automatisch gegenereerd door Adobe Campaign als de e-mailinhoud niet leeg is en als deze een koppeling naar de spiegelpagina bevat (ook wel de koppeling Mirror genoemd).

U kunt de generatiemodus van de spiegel voor e-mail bepalen. De opties zijn beschikbaar in de leveringseigenschappen. U kunt deze opties als volgt openen:

1. Blader naar het tabblad **[!UICONTROL Validity]** van de e-maileigenschappen.
1. In de **sectie van het de paginanummerbeheer van de Spiegel**, controleer de **[!UICONTROL Mode]** drop down lijst.

![](assets/mirror-page-generation.png){width="800" align="left"}

Naast de standaardmodus zijn de volgende opties beschikbaar:

* **[!UICONTROL Force the generation of the mirror page]**: gebruik deze modus om de spiegelpagina te genereren, zelfs als er geen koppeling naar de spiegelpagina is ingevoegd in de levering.
* **[!UICONTROL Do not generate the mirror page]**: gebruik deze modus om te voorkomen dat een spiegelpagina wordt gegenereerd, zelfs als de koppeling aanwezig is in de levering.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: wanneer de koppeling naar de spiegelpagina niet aanwezig is in de e-mailinhoud, gebruikt u deze optie om toegang tot de inhoud van de spiegelpagina in te schakelen, in het venster van het leveringslogboek, zoals hieronder wordt beschreven.

## De spiegelpagina voor een ontvanger controleren {#mirror-page-access}

U kunt tot de inhoud van de spiegelpagina voor een specifieke ontvanger van een levering, met verpersoonlijkingsgegevens toegang hebben.

Deze spiegelpagina openen:

1. Nadat de levering is verzonden, opent u deze en bladert u naar het tabblad **[!UICONTROL Delivery]** ervan.

1. Selecteer een ontvanger en klik op de koppeling **[!UICONTROL Display the mirror page for this message...]** .

   ![](assets/mirror-page-display.png){width="800" align="left"}

   De spiegelpagina wordt weergegeven in een speciaal scherm, met verpersoonlijkingsgegevens voor de geselecteerde ontvanger.
