---
product: Adobe Campaign
title: E-mails verzenden met Adobe Campaign
description: Aan de slag met e-mails in Campagne
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: 5762e58aafb11932d0e28d87df84704974c09564
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# E-mails ontwerpen en verzenden

Met e-mailleveringen kunt u persoonlijke e-mails sturen naar de doelgroep.

[!DNL :arrow_upper_right:] Meer informatie vindt u in de  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Uw eerste e-maillevering maken

Maak persoonlijke en contextafhankelijke e-mails die consistent zijn met de rest van de klantervaring.

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [Leer hoe u een e-maillevering kunt maken in Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html)


In het volgende voorbeeld leert u hoe u in Adobe Campaign een e-maillevering ontwerpt die gepersonaliseerde gegevens, koppelingen naar een externe URL, een koppeling naar de spiegel en een koppeling naar een webformulier bevat.

1. De levering maken

   Als u een nieuwe levering wilt maken, bladert u naar het tabblad **Campagnes**, klikt u op **Leveringen** en klikt u op de knop **Maken** boven de lijst met bestaande leveringen.

   ![](assets/delivery_step_1.png)

1. Selecteer de sjabloon

   Selecteer een leveringssjabloon en geef uw levering een naam. Deze naam is alleen zichtbaar voor gebruikers van de Adobe Campaign-console en niet voor uw ontvangers. Deze kop wordt echter wel weergegeven in uw lijst met leveringen. Klik op **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. Uw inhoud importeren

   Klik op het tabblad **Bron** om uw HTML-inhoud te plakken.

   ![](assets/paste-content.png)


1. Je bericht personaliseren


   * De eerste en tweede naam van de ontvangers weergeven

      Als u de eerste en tweede naam van de ontvangers wilt invoegen in een tekstveld in de aflevering, klikt u op het gekozen tekstveld en plaatst u de cursor op de gewenste positie. Klik op het eerste pictogram op de pop-upwerkbalk en klik vervolgens op **[!UICONTROL Personalization block]**. Selecteer **[!UICONTROL Greetings]** en klik vervolgens op **[!UICONTROL OK]**.

   * Een koppeling invoegen in een afbeelding

      Als u ontvangers voor levering via een afbeelding naar een extern adres wilt sturen, klikt u op de desbetreffende afbeelding om de pop-upwerkbalk weer te geven. Plaats de cursor op het eerste pictogram en klik vervolgens op **[!UICONTROL Link to an external URL]**.

      Voer de URL voor de koppeling in het veld **URL** in met de volgende notatie **https://www.myURL.com** en bevestig vervolgens de URL.

      U kunt de koppeling op elk gewenst moment wijzigen met de sectie rechts van het venster.

   * Koppelingen in tekst invoegen

      Als u een externe koppeling wilt integreren in de tekst in uw bestelling, selecteert u een stuk tekst of een blok tekst en klikt u op het eerste pictogram in de pop-upwerkbalk. Klik **[!UICONTROL Link to an external URL]**, ga het verbindingsadres in **[!UICONTROL URL]** gebied in.

      U kunt de koppeling op elk gewenst moment wijzigen met de sectie rechts van het venster.

   * Een spiegelpagina toevoegen

      Om uw ontvangers toe te staan om uw leveringsinhoud in browser van het Web te bekijken, kunt u een verbinding aan een spiegelpagina in uw levering integreren.

      Klik op het tekstveld waarin u de koppeling wilt plaatsen. Klik op het eerste pictogram op de pop-upwerkbalk, selecteer **[!UICONTROL Personalization block]** en **[!UICONTROL Link to Mirror Page (MirrorPage)]**. Klik **[!UICONTROL Save]** om te bevestigen.

   * Een koppeling naar een webtoepassing integreren

      Met de Digital Content Editor kunt u koppelingen naar webtoepassingen integreren vanuit uw Adobe Campaign-console, zoals een openingspagina of een formulierpagina.

      Selecteer een tekstveld voor de koppeling naar een webtoepassing en klik op het eerste pictogram. Kies **[!UICONTROL Link to a Web application]**, dan selecteer de gewenste toepassing door het pictogram aan het eind van **Web Application** te klikken gebied.

1. Berichten verzenden

   Wanneer de inhoud is geïntegreerd, slaat u de levering op door op **Opslaan** te klikken. Het wordt nu weergegeven in de lijst met leveringen op het tabblad **[!UICONTROL Campaigns > Deliveries]**.


## Inhoud maken en publiek selecteren

U kunt rechtstreeks in Campagne creëren of uw publiek, evenals uw e-mailinhoud invoeren. Gebruik de onderstaande koppelingen voor meer informatie:

* Een e-mail ontwerpen in Campagne
   [!DNL :arrow_upper_right:] [Leer hoe u een e-mail ontwerpt](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* E-mailinhoud importeren
   [!DNL :arrow_upper_right:] [Hoofdlettergebruik: Een workflow maken om leveringsinhoud te laden](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* Een e-mailsjabloon maken en gebruiken
   [!DNL :arrow_upper_right:] [Meer informatie over e-mailsjablonen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* Selecteer het publiek van uw e-mail
   [!DNL :arrow_upper_right:] [Leer hoe u de doelpopulatie definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* Een levering valideren en proefdrukken verzenden
   [!DNL :arrow_upper_right:] [Belangrijke stappen om een levering te valideren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* [zaadadressen toevoegen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## Uw e-mails testen en valideren

De campagne biedt verschillende manieren om uw e-mails te testen en te valideren voordat u ze naar uw publiek stuurt.

[!DNL :arrow_upper_right:] [Best practices toepassen die worden vermeld in de Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

U kunt:

* Logboeken voor leveringsanalyse controleren
* Verzend proeven
* Seedadressen toevoegen
* Controlegroepen gebruiken
* E-mailrendering controleren

[!DNL :arrow_upper_right:] [Meer informatie in de Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## Uw e-mailberichten controleren

Zodra verzonden, controleer uw leveringsstatus in het Dashboard van de Levering en de logboeken van de toegangslevering en de rapporten bevestigen berichten correct werden verzonden.

[!DNL :arrow_upper_right:] [Meer informatie in de Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

