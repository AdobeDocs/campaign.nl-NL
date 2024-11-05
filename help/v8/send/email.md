---
title: E-mails verzenden met Adobe Campaign
description: Ga aan de slag met e-mails in Adobe Campaign. Stuur gepersonaliseerde e-mails naar een doelgroep.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: cf292ecd7d30862d7d195536ecc5be709fe037b3
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 5%

---

# E-mails ontwerpen en verzenden

Met e-mailleveringen kunt u persoonlijke e-mails sturen naar de doelgroep. [Meer informatie](../send/send.md)

Leer zeer belangrijke stappen om een levering in [ tot stand te brengen en te vormen deze pagina ](../start/create-message.md).

## Uw eerste e-maillevering maken

Maak persoonlijke en contextafhankelijke e-mails die consistent zijn met de rest van de klantervaring.

![](assets/new-email-content.png)


In het volgende voorbeeld leert u hoe u een e-maillevering ontwerpt in Adobe Campaign die gepersonaliseerde gegevens, koppelingen naar een externe URL en een koppeling naar de spiegelpagina bevat.

1. **creeer de levering**

   Om een nieuwe levering tot stand te brengen, doorblader aan het **lusje van Campagnes**, klik **Leveringen** en klik **creeer** knoop boven de lijst van bestaande leveringen.

   ![](assets/delivery_step_1.png)

1. **selecteer het malplaatje**

   Selecteer een leveringssjabloon en geef uw levering een naam. Deze naam is alleen zichtbaar voor gebruikers van de Adobe Campaign-console en niet voor uw ontvangers. Deze kop wordt echter wel weergegeven in uw lijst met leveringen. Klik op **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **de Invoer uw inhoud**

   Klik het **Source** lusje om uw inhoud van de HTML te kleven.

   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >Om prestatieproblemen te voorkomen, mogen afbeeldingen in e-mailberichten niet groter zijn dan 100 kB.

1. **Personaliseer uw bericht**

   * Voeg de eerste en laatste namen van uw ontvangers toe

     Als u de eerste en laatste namen van de doelprofielen in de inhoud van het bericht wilt invoegen, plaatst u de cursor op de plaats waar u deze wilt invoegen, klikt u op het laatste pictogram op de werkbalk, klikt u op **[!UICONTROL Include]** en selecteert u **[!UICONTROL Greetings]** .

     ![](assets/include-greetings.png)

     Blader naar het tabblad Voorvertoning om de personalisatie te controleren door een ontvanger te selecteren.

     ![](assets/perso-check.png)

     Leer meer over verpersoonlijkingsopties in [ deze sectie ](personalize.md).

   * Een bijgehouden koppeling invoegen

     Als u ontvangers voor levering via een afbeelding of tekst naar een extern adres wilt sturen, selecteert u de afbeelding of tekst en klikt u op het pictogram **[!UICONTROL Add a link]** op de werkbalk.

     Ga URL voor de verbinding op het **URL** gebied in gebruikend het volgende formaat **https://www.myURL.com**, dan bevestig.

     ![](assets/add-a-link.png)

   * Een spiegelpagina toevoegen

     Om uw ontvangers toe te staan om uw leveringsinhoud in Webbrowser te bekijken, voeg een verbinding aan de [ spiegelpagina ](mirror-page.md) van uw bericht toe.

     Plaats de cursor op de plaats waar u deze koppeling wilt invoegen, klik op het laatste pictogram op de werkbalk en klik vervolgens op **[!UICONTROL Include]** en selecteer **[!UICONTROL link to mirror page]** .

     Leer meer over het beheren van de spiegelpagina in [ deze sectie ](mirror-page.md#link-to-mirror-page).

1. U kunt aanvullende parameters voor uw e-mail definiëren, zoals het verzenden van een kopie van uw berichten naar een BBC-adres, het wijzigen van de berichtindeling, het instellen van een specifieke codering, enzovoort. Lees meer in [deze sectie](email-parameters.md).

1. Zodra de inhoud klaar is, klik **sparen**: het zal nu in uw lijst van leveringen, in het **[!UICONTROL Campaigns > Deliveries]** lusje worden getoond.

Uw eerste e-maillevering is gereed. U moet nu het publiek definiëren, de levering valideren en verzenden.

Leer hoe te om een e-mailinhoud in dit [ gebruiksgeval ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html) in te voeren {target="_blank"}.

Meer informatie vindt u in de volgende secties:

<!--[Design an email in Campaign]-->
* [Een e-mailsjabloon maken en gebruiken](../send/create-templates.md)
* [Selecteer het publiek van uw e-mail](../audiences/gs-audiences.md)
* [Een levering valideren en proefdrukken verzenden](preview-and-proof.md)
* [De levering configureren en verzenden](configure-and-send.md)

## Uw e-mails testen en valideren

De campagne biedt verschillende manieren om uw e-mails te testen en te valideren voordat u ze naar uw publiek stuurt. Leer hoe te om uw e-mailinhoud in [ te voorproef en te testen deze sectie ](../send/preview-and-proof.md).

U kunt:

* [Proefdrukken verzenden](preview-and-proof.md)
* [Seedadressen toevoegen](../audiences/test-profiles.md)
* [Logboeken voor leveringsanalyse controleren](delivery-analysis.md)

