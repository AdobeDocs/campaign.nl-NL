---
title: E-mails verzenden met Adobe Campaign
description: Ga aan de slag met e-mails in Adobe Campaign. Stuur gepersonaliseerde e-mails naar een doelgroep.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 500de76853772313b1aac655da2f1b3562de2c55
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 4%

---

# E-mails ontwerpen en verzenden

Met e-mailleveringen kunt u persoonlijke e-mails sturen naar de doelgroep. [Meer informatie](../send/send.md)

## Uw eerste e-maillevering maken

Maak persoonlijke en contextafhankelijke e-mails die consistent zijn met de rest van de klantervaring.

![](assets/new-email-content.png)


In het volgende voorbeeld leert u hoe u een e-maillevering ontwerpt in Adobe Campaign die gepersonaliseerde gegevens, koppelingen naar een externe URL en een koppeling naar de spiegelpagina bevat.

1. **De levering maken**

   Blader naar de **Campagnes** tabblad, klikt u op **Leveringen** en klik op de knop **Maken** boven de lijst met bestaande leveringen.

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

     Blader naar het tabblad Voorvertoning om de personalisatie te controleren door een ontvanger te selecteren.

     ![](assets/perso-check.png)

     Meer informatie over verpersoonlijkingsopties vindt u in [deze sectie](personalize.md).

   * Een bijgehouden koppeling invoegen

     Als u ontvangers voor levering via een afbeelding of tekst naar een extern adres wilt sturen, selecteert u de gewenste ontvanger en klikt u op de knop **[!UICONTROL Add a link]** in de werkbalk.

     Voer de URL voor de koppeling in het dialoogvenster **URL** veld met de volgende notatie **https://www.myURL.com**, bevestig vervolgens.

     ![](assets/add-a-link.png)

   * Een spiegelpagina toevoegen

     Als u wilt toestaan dat de ontvangers uw inhoud van de levering in een webbrowser kunnen bekijken, voegt u een koppeling toe naar de [spiegelpagina](mirror-page.md) van uw bericht.

     Plaats de cursor op de plaats waar u deze koppeling wilt invoegen, klik op het laatste pictogram op de werkbalk en klik vervolgens op **[!UICONTROL Include]** en selecteert u **[!UICONTROL link to mirror page]**.

     Meer informatie over het beheren van de spiegelpagina in [deze sectie](mirror-page.md#link-to-mirror-page).

1. U kunt aanvullende parameters voor uw e-mail definiëren, zoals het verzenden van een kopie van uw berichten naar een BBC-adres, het wijzigen van de berichtindeling, het instellen van een specifieke codering, enzovoort. Meer informatie in [deze sectie](email-parameters.md).

1. Als de inhoud gereed is, klikt u op **Opslaan**: het wordt nu weergegeven in uw lijst met leveringen, in de **[!UICONTROL Campaigns > Deliveries]** tab.

Uw eerste e-maillevering is gereed. U moet nu het publiek definiëren, de levering valideren en verzenden.

Leer hoe u een e-mailinhoud importeert in deze [use case](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

Meer informatie vindt u in de volgende secties:

<!--[Design an email in Campaign]-->
* [Een e-mailsjabloon maken en gebruiken](../send/create-templates.md)
* [Selecteer het publiek van uw e-mail](../audiences/gs-audiences.md)
* [Een levering valideren en proefdrukken verzenden](preview-and-proof.md)
* [De levering configureren en verzenden](configure-and-send.md)

## Uw e-mails testen en valideren

De campagne biedt verschillende manieren om uw e-mails te testen en te valideren voordat u ze naar uw publiek stuurt. Leer hoe u uw e-mailinhoud kunt voorvertonen en testen in [deze sectie](../send/preview-and-proof.md).

U kunt:

* [Verzend proeven](preview-and-proof.md)
* [Seedadressen toevoegen](../audiences/test-profiles.md)
* [Logboeken voor leveringsanalyse controleren](delivery-analysis.md)

