---
product: Adobe Campaign
title: E-mails verzenden met Adobe Campaign
description: Aan de slag met e-mails in Campagne
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 3%

---

# E-mails ontwerpen en verzenden

Met e-mailleveringen kunt u persoonlijke e-mails sturen naar de doelgroep.

↗️ Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Uw eerste e-maillevering maken

Maak persoonlijke en contextafhankelijke e-mails die consistent zijn met de rest van de klantervaring.

![](assets/new-email-content.png)


In het volgende voorbeeld leert u hoe u een e-maillevering ontwerpt in Adobe Campaign die gepersonaliseerde gegevens, koppelingen naar een externe URL en een koppeling naar de spiegelpagina bevat.

1. **De levering maken**

   Als u een nieuwe levering wilt maken, bladert u naar het tabblad **Campagnes**, klikt u op **Leveringen** en klikt u op de knop **Maken** boven de lijst met bestaande leveringen.

   ![](assets/delivery_step_1.png)

1. **Selecteer de sjabloon**

   Selecteer een leveringssjabloon en geef uw levering een naam. Deze naam is alleen zichtbaar voor gebruikers van de Adobe Campaign-console en niet voor uw ontvangers. Deze kop wordt echter wel weergegeven in uw lijst met leveringen. Klik op **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Uw inhoud importeren**

   Klik op het tabblad **Bron** om uw HTML-inhoud te plakken.

   ![](assets/paste-content.png)


1. **Je bericht personaliseren**


   * Voeg de eerste en laatste namen van uw ontvangers toe

      Als u de eerste en laatste naam van de doelprofielen in de inhoud van het bericht wilt invoegen, plaatst u de cursor op de plaats waar u deze wilt invoegen en klikt u op het laatste pictogram op de werkbalk. Klik vervolgens op **[!UICONTROL Include]** en selecteer **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      Blader naar het tabblad Voorbeeld om de personalisatie te controleren door een ontvanger te selecteren.

      ![](assets/perso-check.png)

   * Een bijgehouden koppeling invoegen

      Als u ontvangers voor levering via een afbeelding of tekst naar een extern adres wilt sturen, selecteert u de afbeelding of tekst en klikt u op het pictogram **[!UICONTROL Add a link]** op de werkbalk.

      Voer de URL voor de koppeling in het veld **URL** in met de volgende notatie **https://www.myURL.com** en bevestig vervolgens de URL.

      ![](assets/add-a-link.png)

   * Een spiegelpagina toevoegen

      Als u wilt dat de ontvangers de inhoud van de levering in een webbrowser kunnen bekijken, voegt u een koppeling toe naar de spiegelpagina van het bericht.

      Plaats de cursor op de plaats waar u deze koppeling wilt invoegen en klik op het laatste pictogram op de werkbalk. Klik vervolgens op **[!UICONTROL Include]** en selecteer **[!UICONTROL link to mirror page]**.
   Als de inhoud gereed is, klikt u op **Opslaan**: het wordt nu weergegeven in uw lijst met leveringen op het tabblad **[!UICONTROL Campaigns > Deliveries]**. Uw eerste e-maillevering is gereed. U moet nu het publiek definiëren, de levering valideren en verzenden.


Meer informatie vindt u in de volgende secties van de Campaign Classic v7-documentatie:

* Een e-mail ontwerpen in Campagne
↗️ [Leer hoe u een e-mail ontwerpt](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* E-mailinhoud importeren
↗️ [Gebruik hoofdletters/kleine letters: Een workflow maken om een leveringsinhoud te laden](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* Een e-mailsjabloon maken en gebruiken
↗️ [Meer informatie over e-mailsjablonen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* Selecteer het publiek van uw e-mail
↗️ [Leer hoe u de doelpopulatie definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* Een levering valideren en proefdrukken verzenden
↗️ [Leer belangrijke stappen om een levering te bevestigen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* [zaadadressen toevoegen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## Uw e-mails testen en valideren

De campagne biedt verschillende manieren om uw e-mails te testen en te valideren voordat u ze naar uw publiek stuurt.

↗️ [Beste praktijken toepassen die in Campaign Classic v7 documentatie worden vermeld](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

U kunt:

* Logboeken voor leveringsanalyse controleren
* Verzend proeven
* Seedadressen toevoegen
* Controlegroepen gebruiken
* E-mailrendering controleren

↗️ [Meer informatie in Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## Uw e-mailberichten controleren

Zodra verzonden, controleer uw leveringsstatus in het dashboard van de Levering en toegangsleveringslogboeken en rapporten om berichten te bevestigen correct werden verzonden.

↗️ [Meer informatie in Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

