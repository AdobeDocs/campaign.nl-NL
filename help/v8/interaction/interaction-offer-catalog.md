---
title: Catalogus aanbieding voor campagneinteractie
description: Leer hoe u een aanbiedingencatalogus maakt
feature: Interaction, Offers
role: Developer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 1%

---

# Een aanbiedingencatalogus maken

Als **manager van de Aanbieding**, bent u verantwoordelijk voor het creëren van de aanbiedingscatalogus.

Een aanbiedingscatalogus is gekoppeld aan één bestaande omgeving. Aanbiedingen in deze catalogus kunnen alleen worden gekoppeld aan de ruimten die in dezelfde omgeving zijn opgegeven.

Alvorens uw aanbiedingen tot stand te brengen, moet u een [&#x200B; milieu &#x200B;](interaction-env.md) eerst specificeren dat alle kenmerken (geschiktheid, beperkingen op het doel, presentatieregels) van een reeks aanbiedingen bevat, die in categorieën, evenals de lijst van hun ruimten wordt gesorteerd.

## Aanbiedingscategorieën maken{#creating-offer-categories}

De aanbieding is ingedeeld in categorieën/subcategorieën. Categorieën worden gemaakt in de **[!UICONTROL Design]** -omgeving en worden automatisch geïmplementeerd in de **[!UICONTROL Live]** -omgeving (d.w.z. beschikbaar gesteld) wanneer de aanbiedingen die ze bevatten, worden goedgekeurd. De **[!UICONTROL Design]** -omgeving bevat een standaardcategorie voor het ontvangen van alle aanbiedingen. U kunt subcategorieën maken om een hiërarchie toe te voegen aan de catalogusaanbiedingen.

Voor elke categorie, kunt u **toelatingsdata** bepalen, die de periode is waarin de aanbiedingen in de categorie aan hun doel kunnen worden voorgesteld. U kunt ook het gewicht van een categorie aanpassen om voorrang te geven aan de aanbiedingspresentatie.

Ga als volgt te werk om een nieuwe categorie te maken:

1. Ga naar de map **[!UICONTROL Offer catalog]** .

   ![](assets/offer_cat_create_001.png)

1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Create a new "Offer category" folder]** in de vervolgkeuzelijst.

   ![](assets/offer_cat_create_002.png)

1. Geef de categorie een nieuwe naam. U kunt het label later bewerken met het tabblad **[!UICONTROL General]** .

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >Herhaal deze stappen om zoveel categorieën te maken als nodig is.

   Daarna kunt u zo nodig:

   * Wijs toelatingsdatums toe vanaf het tabblad **[!UICONTROL Eligibility]** .

     ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** om filters op het aanbiedingsdoel toe te passen.

   * Een overzicht van de geschiktheidsregels. Klik op de koppeling **[!UICONTROL Schedule and eligibility rules of the offer]** om deze weer te geven.

## Een terugvalcategorie toevoegen

Om ervoor te zorgen dat alle ontvangers een voorstel voor een aanbod ontvangen, is het mogelijk systematisch een of meerdere categorieën aanbiedingen in de aanbevelingen op te nemen.

Deze terugvalaanbiedingen moeten een laag (maar niet-nulgewicht) gewicht hebben, zodat ze alleen in aanmerking worden genomen als er geen aanbiedingen met een hoger gewicht in aanmerking komen.

Bovendien mag er geen presentatieregel worden toegepast op deze aanbiedingen om ervoor te zorgen dat deze altijd in de aanbevelingen worden opgenomen. Dit betekent dat de ontvanger tijdens een voorstel ten minste één bod van deze categorie zal ontvangen als er geen aanbod met een hoger gewicht beschikbaar is.

Volg onderstaande stappen om een fallback-categorie op te nemen in de aanbevelingen:

1. Blader naar de catalogus met aanbiedingen.
1. Klik op de tab **[!UICONTROL Eligibility]** en selecteer de optie **[!UICONTROL Always include this category in the recommendations]** .
1. Klik op **[!UICONTROL Save]**.

   ![](assets/offer_cat_default_001.png)
