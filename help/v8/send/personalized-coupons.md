---
product: campaign
title: Gepersonaliseerde coupons
description: Leer hoe u gepersonaliseerde coupons maakt en invoegt
feature: Personalization
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 182939bb-7aff-4667-bda9-c5d48be3b946
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 1%

---

# Gepersonaliseerde coupons{#personalized-coupons}

Door coupons toe te voegen aan uw leveringen kunnen uw ontvangers meer waarde krijgen voor producten en services. Met de module Campagne-coupon kunt u een set coupons maken die u naar verwachting aan toekomstige marketingaanbiedingen wilt toevoegen. Als u klaar bent om een levering te maken, wijst u de toepasselijke coupons toe. Aangezien coupons geldig zijn voor een bepaalde periode, wordt een toegewezen coupon op unieke wijze gekoppeld aan het bijbehorende leveringsbericht. Bovendien bevestigt Campaign dat er voldoende coupons zijn voor het aantal berichten voordat de levering wordt verzonden.

>[!AVAILABILITY]
>
>Couponbeheer is niet beschikbaar in Campaign v8 in de context van een implementatie voor bedrijven (FFDA). Leer meer in [ documentatie van de Campagne v8 ](../architecture/enterprise-deployment.md).

Couponbeheer is afhankelijk van een pakket dat moet worden geïnstalleerd. Controleer **[!UICONTROL Administration > Configuration > Package management > Installed packages.]** om te bevestigen dat u Coupon-beheer hebt

Coupongegevens kunnen worden geïmporteerd en geëxporteerd in CSV- en XML-indeling. [Meer informatie](../../platform/using/get-started-data-import-export.md).

## Een coupon maken {#creating-a-coupon}

In de module Coupon Management hebt u twee opties voor het maken van coupons:

* **Anoniem**: Een generische coupon voor uitgezochte ontvangers of lijsten van ontvangers.
* **Individueel**: Een gepersonaliseerde coupon voor uitgezochte ontvangers.

Voordat u de onderstaande stappen uitvoert, moet u weten welk type coupon u wilt maken.

1. Ga in de Campagnestructuur naar **[!UICONTROL Resources > Campaign management > Coupons]** .

   ![](assets/deliv_coup_01.png)

1. Klik op de knop **[!UICONTROL New]**.
1. Voer in het veld **[!UICONTROL Label]** de naam van de coupon in. Er wordt automatisch een unieke code ingevoerd in **[!UICONTROL Coupon code]** . U kunt de code behouden of een nieuwe invoeren.

   ![](assets/deliv_coup_02.png)

1. Kies **[!UICONTROL Start date]** en **[!UICONTROL End date]** om de periode in te stellen waarin de coupon geldig is.
1. Kies Anonieme of Individuele in **[!UICONTROL Coupon type]** .

   **[!UICONTROL Anonymous coupons]** : een anonieme coupon is identiek voor alle ontvangers. Bevestig dat Anoniem in het **type van Coupon** menu wordt geselecteerd en **sparen** klikt om de coupon te produceren.

   **[!UICONTROL Individual coupons]** : Een afzonderlijke coupon kan verder worden gepersonaliseerd met extra couponcodes. Er wordt bijvoorbeeld een afzonderlijke coupon gemaakt voor verkoop in een winkel voor sportapparatuur. De lijst van ontvangers is echter lang en zij delen niet hetzelfde enthousiasme voor één enkele sport. U kunt codenamen toevoegen voor de afzonderlijke coupon op basis van een sport (bijvoorbeeld voetbal, voetbal, honkbal, enz.) en elke code naar de desbetreffende ontvangers sturen.

   1. Als u Individueel kiest, wordt linksonder een nieuw tabblad, Coupons, weergegeven. Ga naar de tab **[!UICONTROL Coupons]** en klik op **[!UICONTROL Add]** .
   1. Voer een unieke code voor de afzonderlijke coupon in als u hierom wordt gevraagd door het pop-upvenster.
   1. Klik op **[!UICONTROL Save]** om de coupon te genereren.

   Voor meer details over het lusje van Coupons, zie [ individuele coupons ](#configuring-individual-coupons) vormen.

   >[!NOTE]
   >
   >Individuele coupons kunnen bulksgewijs worden ingevoerd. Voor details betreffende het invoeren en het uitvoeren, verwijs naar [ deze sectie ](../../platform/using/get-started-data-import-export.md).

### Afzonderlijke coupons configureren {#configuring-individual-coupons}

![](assets/deliv_coup_03.png)

Het tabblad Coupons is alleen beschikbaar voor afzonderlijke coupons. Nadat een coupon is gekoppeld aan een levering, geeft het tabblad Coupons de volgende details:

* **[!UICONTROL Status]** : beschikbaarheid van coupon.
* **[!UICONTROL Redeemed on]** : De datum waarop de coupon wordt afgelost.
* **[!UICONTROL Channel]** : het kanaal dat wordt gebruikt om de coupon te verzenden.
* **[!UICONTROL Address]** : De e-mailadressen van de ontvangers.

De waarden voor **[!UICONTROL status]** , **[!UICONTROL channel]** en **[!UICONTROL address]** worden automatisch voltooid. De waarden voor **[!UICONTROL redeemed on]** worden echter niet hersteld door Campagne. U kunt deze gegevens invullen door een bestand te importeren dat de gegevens voor het inwisselen van coupons bevat.

## Een coupon invoegen in een e-maillevering {#inserting-a-coupon-into-an-email-delivery}

In het onderstaande voorbeeld wordt de levering gemaakt op de startpagina. Voor gedetailleerde instructies op hoe te om een levering tot stand te brengen, verwijs naar [ deze sectie ](about-email-channel.md). U kunt ook een coupon toevoegen aan een levering in een workflow.

1. Ga naar **[!UICONTROL Campaigns]** en kies **[!UICONTROL Deliveries]** .
1. Klik op **[!UICONTROL Create]**.

   ![](assets/deliv_coup_04.png)

1. Typ een naam in **[!UICONTROL Label]** en klik op **[!UICONTROL Continue]** .
1. Klik op **[!UICONTROL To]** om ontvangers toe te voegen.
1. Klik op **[!UICONTROL Add]** om ontvangers voor de levering te kiezen. Nadat u de ontvangers hebt geselecteerd, klikt u op **[!UICONTROL Ok]** om terug te keren naar de levering.

   ![](assets/deliv_coup_05.png)

1. Voer een onderwerp in en voeg inhoud toe aan het bericht.

   ![](assets/deliv_coup_06.png)

1. Klik in de werkbalk op **[!UICONTROL Properties]** en kies de tab **[!UICONTROL Advanced]** .
1. Klik op het mappictogram voor **[!UICONTROL Coupon management]** .

   ![](assets/deliv_coup_07.png)

1. Kies de coupon en klik op **[!UICONTROL Ok]** . Klik nogmaals op **[!UICONTROL Ok]** .

   ![](assets/deliv_coup_08.png)

1. Klik op het bericht om aan te geven waar u de coupon wilt plaatsen.

   ![](assets/deliv_coup_09.png)

1. Klik op het verpersoonlijkingspictogram om een van de volgende opties te kiezen op basis van het type coupon:

   * Anonieme coupon: **[!UICONTROL Coupon > Coupon code]**

     ![](assets/deliv_coup_10.png)

   * Afzonderlijke coupon: **[!UICONTROL Coupon value > Coupon code]**

     ![](assets/deliv_coup_11.png)

     De coupon wordt in het bericht ingevoegd als code in plaats van de naam die u hebt toegewezen. De code wordt gebruikt binnen het de gegevensmodel van het Mob van de Campagne.

   ![](assets/deliv_coup_12.png)

1. Voer een test uit om de naam te bevestigen die u aan de coupon hebt toegewezen. Ga naar de tab **[!UICONTROL Preview]** en klik op **[!UICONTROL Test personalization]** . Kies een ontvanger voor de test.

   ![](assets/deliv_coup_13.png)

   Na de test moet de coupon worden weergegeven als de toegewezen naam in plaats van als de code.

   ![](assets/deliv_coup_14.png)

1. Klik in de werkbalk op **[!UICONTROL Send]** (linksboven) en kies hoe u de levering wilt verzenden.

   ![](assets/deliv_coup_15.png)

1. Klik op **[!UICONTROL Analyze]**. Als het analyselogboek bevestigt dat er genoeg coupons voor alle ontvangers zijn, klikt u op **[!UICONTROL Confirm delivery]** om het te verzenden.

   ![](assets/deliv_coup_16.png)

>[!NOTE]
>
>Voor instructies op hoe te om ontoereikende coupons voor een levering te beheren, zie [ ontoereikende coupons beheren ](#managing-insufficient-coupons)

Bevestig dat de levering succesvol was:

1. Ga naar **[!UICONTROL Explorer > Resources > Campaign management > Coupons]** .
1. Klik op de tab **[!UICONTROL Deliveries]** .

   ![](assets/deliv_coup_17.png)

   De status wordt gelezen als **[!UICONTROL Finished]** voor een geslaagde levering.

>[!NOTE]
>
>Door gebrek, gebruikt de module van het couponbeheer een **nms:recipient** lijst. [Meer informatie](../../configuration/using/about-data-model.md#default-recipient-table).
>
>Leer hoe te om een douane ontvankelijke lijst [ in deze pagina ](../../configuration/using/about-custom-recipient-table.md) te gebruiken.

## Onvoldoende coupons beheren {#managing-insufficient-coupons}

De leveringsanalyse stopt als er minder coupons zijn dan berichten. In dat geval kunt u meer coupons importeren of het aantal berichten beperken. Volg de onderstaande instructies als u het aantal berichten wilt beperken.

1. Ga naar het venster E-maillevering.
1. Klik op **[!UICONTROL To]**.
1. Ga in **[!UICONTROL Select target]** naar de tab **[!UICONTROL Exclusions]** .

   ![](assets/deliv_coup_18.png)

1. Klik in de sectie met uitsluitingsinstellingen op **[!UICONTROL Edit]** .
1. Voer het aantal berichten in dat u wilt verzenden **[!UICONTROL Limit delivery to...messages]** en klik op **[!UICONTROL Ok]** . U kunt de levering verzenden.

   ![](assets/deliv_coup_19.png)

>[!NOTE]
>
>Als u een beperkt aantal coupons beheert, kunt u de levering splitsen op basis van uw criteria. Het is een goede optie als u coupons naar een bepaalde populatie wilt sturen zonder het doel te beperken.
