---
title: Send emails with Adobe Campaign
description: Aan de slag met e-mails in Campagne
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 3%

---

# E-mails ontwerpen en verzenden

Email deliveries let you send personalized emails to the target population.

![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Create your first email delivery

Maak persoonlijke en contextafhankelijke e-mails die consistent zijn met de rest van de klantervaring.

![](assets/new-email-content.png)


In het volgende voorbeeld leert u hoe u een e-maillevering ontwerpt in Adobe Campaign die gepersonaliseerde gegevens, koppelingen naar een externe URL en een koppeling naar de spiegelpagina bevat.

1. **De levering maken**

   To create a new delivery, browse to the **Campaigns** tab, click **Deliveries** and click the **Create** button above the list of existing deliveries.

   ![](assets/delivery_step_1.png)

1. **Selecteer de sjabloon**

   Selecteer een leveringssjabloon en geef uw levering een naam. Deze naam is alleen zichtbaar voor gebruikers van de Adobe Campaign-console en niet voor uw ontvangers. Deze kop wordt echter wel weergegeven in uw lijst met leveringen. Klik op **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Uw inhoud importeren**

   Klik op de knop **Bron** om uw HTML-inhoud te plakken.

   ![](assets/paste-content.png)


1. **Je bericht personaliseren**


   * Voeg de eerste en laatste namen van uw ontvangers toe

      Als u de voor- en achternamen van de doelprofielen wilt invoegen in de inhoud van het bericht, plaatst u de cursor op de plaats waar u deze wilt invoegen en klikt u op het laatste pictogram op de werkbalk. Klik vervolgens op **[!UICONTROL Include]** en selecteert u **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      Blader naar het tabblad Voorbeeld om de personalisatie te controleren door een ontvanger te selecteren.

      ![](assets/perso-check.png)

   * Een bijgehouden koppeling invoegen

      Als u ontvangers voor levering via een afbeelding of tekst naar een extern adres wilt sturen, selecteert u de gewenste ontvanger en klikt u op de knop **[!UICONTROL Add a link]** in de werkbalk.

      Voer de URL voor de koppeling in het dialoogvenster **URL** veld met de volgende notatie **https://www.myURL.com**, bevestig vervolgens.

      ![](assets/add-a-link.png)

   * Een spiegelpagina toevoegen

      To allow your recipients to view your delivery content in a web browser, add a link to the mirror page of your message.

      Plaats de cursor op de plaats waar u deze koppeling wilt invoegen, klik op het laatste pictogram op de werkbalk en klik vervolgens op **[!UICONTROL Include]** en selecteert u **[!UICONTROL link to mirror page]**.
   Als de inhoud gereed is, klikt u op **Opslaan**: het wordt nu weergegeven in uw lijst met leveringen, in de **[!UICONTROL Campaigns > Deliveries]** tab. Uw eerste e-maillevering is gereed. U moet nu het publiek definiëren, de levering valideren en verzenden.


Learn more in these sections of Campaign Classic v7 documentation:

* Een e-mail ontwerpen in Campagne
   ![](../assets/do-not-localize/book.png) [Learn how to design an email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* E-mailinhoud importeren
   ![](../assets/do-not-localize/book.png) [Use case: Create a workflow to load a delivery content](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* Create and use an email template
   ![](../assets/do-not-localize/book.png) [Meer informatie over e-mailsjablonen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* Selecteer het publiek van uw e-mail
   ![](../assets/do-not-localize/book.png) [Leer hoe u de doelpopulatie definieert](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* Een levering valideren en proefdrukken verzenden
   ![](../assets/do-not-localize/book.png) [Belangrijke stappen om een levering te valideren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* Toevoegen [zaadadressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## Test and validate your emails

De campagne biedt verschillende manieren om uw e-mails te testen en te valideren voordat u ze naar uw publiek stuurt.

![](../assets/do-not-localize/book.png) [Apply best practices listed in Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

U kunt:

* Logboeken voor leveringsanalyse controleren
* Verzend proeven
* Seedadressen toevoegen
* Controlegroepen gebruiken
* E-mailrendering controleren

![](../assets/do-not-localize/book.png) [Meer informatie in de Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## Uw e-mailberichten controleren

Zodra verzonden, controleer uw leveringsstatus in het dashboard van de Levering en toegangsleveringslogboeken en rapporten om berichten te bevestigen correct werden verzonden.

![](../assets/do-not-localize/book.png) [Meer informatie in de Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)
