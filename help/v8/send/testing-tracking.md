---
title: Testen van berichten
description: Leer hoe je berichten kunt testen voordat je leveringen worden verzonden
feature: Monitoring
role: User
level: Beginner
exl-id: 16ad36b7-c13e-4b77-86ca-41c9ef174172
source-git-commit: edbe7ab49a628436dfb4d27ae17122917d7371e9
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 0%

---

# Testen van berichten {#testing-tracking}

Voordat u de levering naar het volledige publiek verzendt, is het van essentieel belang dat u de functie voor bijhouden test om te controleren of alle koppelingen correct werken en dat de gegevens worden bijgehouden. Met dit verificatieproces kunt u eventuele problemen met het bijhouden van koppelingen opsporen en verhelpen voordat uw campagne live gaat. Zo voorkomt u potentiële problemen met het omleiden van koppelingen, het volgen van het laden van pixels of het verzamelen van gegevens.

Door het testen kunt u:

* Controleer of alle koppelingen in uw bericht correct zijn bijgehouden en correct zijn omgeleid
* Bevestig dat de koppeling naar de spiegelpagina werkt en wordt bijgehouden
* Zorg ervoor dat de volgende pixels correct worden geladen voor open tracking
* Controleren of gepersonaliseerde parameters in URL&#39;s correct worden vastgelegd
* Controleren of de technische workflow voor bijhouden gegevens correct verwerkt

U kunt het bijhouden van wijzigingen op spiegelpagina&#39;s, e-maillogboeken en koppelingen testen door de onderstaande stappen uit te voeren:

## Stap 1: Maak een testlevering {#create-test-delivery}

1. Maak een nieuwe e-maillevering die wordt gebruikt voor het testen. [&#x200B; leren hoe te om een levering &#x200B;](../start/create-message.md) tot stand te brengen
1. Ontwerp uw e-mailinhoud met koppelingen die u wilt bijhouden. [&#x200B; Leer over het ontwerp van e-mailinhoud &#x200B;](defining-the-email-content.md)
1. Voeg een het verpersoonlijkingsblok van de spiegelpagina in de e-mailinhoud toe. [&#x200B; Leer over verpersoonlijkingsblokken &#x200B;](personalization-blocks.md)

   ![](assets/mirror-page-insert.png)

1. Geef de gebruiker op die de e-mail zal ontvangen. Aangezien deze gebruiker het e-mailbericht moet openen en op de koppelingen moet klikken die het bevat, moet u een adres voor de testontvanger selecteren dat u beheert. [&#x200B; leer over testprofielen &#x200B;](../audiences/test-profiles.md)

## Stap 2: Verzend de testlevering {#send-test}

1. Controleer of Tekstspatiëring is ingeschakeld in de leveringsinstellingen:
   * Open de **[!UICONTROL Properties]** van de levering
   * Ga naar de sectie **[!UICONTROL Tracking & Images]**
   * Controleer of **[!UICONTROL Activate tracking]** is ingeschakeld
   * Controleer of **[!UICONTROL Opens tracking]** is ingeschakeld als u de openingen wilt bijhouden

   ![](assets/s_ncs_user_email_del_tracking_param.png)

[Meer informatie over opties voor het bijhouden van URL&#39;s](url-tracking.md)

1. Verzend de levering aan uw testontvanger. [&#x200B; Leer over het verzenden van leveringen &#x200B;](configure-and-send.md)

## Stap 3: functionaliteit voor bijhouden controleren {#verify-tracking}

1. Nadat u het e-mailbericht hebt ontvangen, opent u het en klikt u op de koppeling naar de spiegelpagina. [&#x200B; leren over spiegelpagina&#39;s &#x200B;](mirror-page.md)
1. Klik op verschillende koppelingen in de e-mail om trackinggegevens te genereren.
1. Nadat u correct naar de spiegelpagina wordt omgeleid, heb toegang tot de **[!UICONTROL Administration > Production > Technical workflows]** omslag. [&#x200B; Leer over werkschema&#39;s &#x200B;](../config/workflows.md)
1. Open de **[!UICONTROL Tracking]** -workflow.
1. Start de workflow of klik met de rechtermuisknop op de **[!UICONTROL Scheduler]** -activiteit en selecteer **[!UICONTROL Execute pending task now]** .
1. Wacht ongeveer 30 seconden op de werkstroom om de volgende logboeken te verwerken.
1. Selecteer het tabblad **[!UICONTROL Audit]** van de workflow. Zorg ervoor dat ten minste één logrecord voor bijhouden is gevonden. Klik op **[!UICONTROL Refresh]** als er geen nieuwe logbestanden worden weergegeven.

1. Controleren of trackinglogboeken in de levering zijn ingevoerd:
   * Ga terug naar je levering
   * Selecteer de tab **[!UICONTROL Tracking]**
   * Controleer of de lijst met trackinglogbestanden wordt weergegeven met de geklikte URL&#39;s en andere volggebeurtenissen

   ![](assets/s_ncs_user_delivery_tracking_tab.png)

## Stap 4: Het tabblad voor het bijhouden van ontvangers controleren {#check-recipient-tracking}

1. Ga naar de profielpagina van de ontvanger u voor de test gebruikte. [&#x200B; leer over het bekijken profielen &#x200B;](../audiences/view-profiles.md)
   * De profielpagina van de ontvanger bevindt zich standaard in de map **[!UICONTROL Profiles and Targets > Recipients]** .

1. Selecteer het tabblad **[!UICONTROL Tracking]**. [&#x200B; Leer meer over het volgen logboeken &#x200B;](tracking-logs.md)

   ![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

1. Controleer of de volgende records worden weergegeven:
   * De waarde **[!UICONTROL Mirror Page]** in de kolom **[!UICONTROL Type]**
   * **[!UICONTROL Open]** -waarden in de kolom **[!UICONTROL Type]** voor e-mail wordt geopend
   * **[!UICONTROL Email click]** waarden in de kolom **[!UICONTROL Type]** voor koppelingsklikken

## Test voor bijhouden van problemen {#troubleshooting-tracking-test}

Als de trackinglogboeken niet worden weergegeven:

1. **de leveringsmontages van de Controle**: Ga naar de levering en toegang tot zijn **[!UICONTROL Properties]** om ervoor te zorgen dat zowel **[!UICONTROL Activate tracking]** als **[!UICONTROL Opens tracking]** opties worden gecontroleerd. [&#x200B; Leer meer over URL het volgen opties &#x200B;](url-tracking.md)

1. **verifieer het Volgen werkschema**: Zorg ervoor het **[!UICONTROL Tracking]** technische werkschema zonder fouten loopt. [&#x200B; Leer over het volgen werkschemaoplossen &#x200B;](tracking-logs.md#check-tracking-workflow)

1. **het formaat van de Controle URL**: Verifieer dat uw URLs correct geformatteerd en ingesloten in afbakeningen is. [&#x200B; Leer meer over het vormen van bijgehouden verbindingen &#x200B;](tracked-links.md)

1. **e-mailcliëntgedrag van het Overzicht**: Sommige e-mailcliënten kunnen het volgen pixel blokkeren of verbindingen wijzigen. Test het met verschillende e-mailclients. [&#x200B; Leer over levering beste praktijken &#x200B;](../start/delivery-best-practices.md)

1. **wacht op verwerking**: De het Volgen werkschemalooppas per uur door gebrek. Als u het handmatig activeert, moet u voldoende tijd toestaan voor de verwerking voordat u de resultaten controleert. [&#x200B; Leer meer over het volgen logboeken &#x200B;](tracking-logs.md)

## Verwante onderwerpen {#related-topics}

* [Leer hoe u bijgehouden koppelingen kunt configureren](tracked-links.md)
* [Leer hoe u logbestanden voor bijhouden kunt openen](tracking-logs.md)
* [Trackingrapporten begrijpen](../reporting/delivery-reports.md#tracking-indicators)

