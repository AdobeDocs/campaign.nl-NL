---
title: Catalogus aanbieding voor campagneinteractie
description: Leer hoe u een aanbiedingencatalogus maakt
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 1%

---

# Een aanbiedingencatalogus maken

Als **Aanbiedingsmanager**, bent u verantwoordelijk voor het maken van de aanbiedingencatalogus.

Een aanbiedingscatalogus is gekoppeld aan één bestaande omgeving. Aanbiedingen in deze catalogus kunnen alleen worden gekoppeld aan de ruimten die in dezelfde omgeving zijn opgegeven.

Voordat u uw aanbiedingen maakt, moet u eerst een [milieu](interaction-env.md) die alle kenmerken (subsidiabiliteit, beperkingen van het doel, presentatieregels) van een reeks aanbiedingen bevat, uitgesplitst in categorieën, alsmede de lijst van de ruimten waarin zij voorkomen.

## Aanbiedingscategorieën maken{#creating-offer-categories}

De aanbieding is ingedeeld in categorieën/subcategorieën. De categorieën worden gecreeerd in **[!UICONTROL Design]** en automatisch in de **[!UICONTROL Live]** milieu (d.w.z. beschikbaar gesteld) wanneer de aanbiedingen die zij bevatten, worden goedgekeurd. De **[!UICONTROL Design]** omgeving bevat een standaardcategorie voor het ontvangen van alle aanbiedingen. U kunt subcategorieën maken om een hiërarchie toe te voegen aan de catalogusaanbiedingen.

Voor elke categorie kunt u definiëren **toelatingsdata**, de periode waarin de aanbiedingen in de categorie aan hun doel kunnen worden voorgelegd. U kunt ook het gewicht van een categorie aanpassen om voorrang te geven aan de aanbiedingspresentatie.

Ga als volgt te werk om een nieuwe categorie te maken:

1. Browser naar de **[!UICONTROL Offer catalog]** map.

   ![](assets/offer_cat_create_001.png)

1. Klikken met rechtermuisknop en selecteren **[!UICONTROL Create a new "Offer category" folder]** in de vervolgkeuzelijst.

   ![](assets/offer_cat_create_002.png)

1. Geef de categorie een nieuwe naam. U kunt het label later bewerken met de **[!UICONTROL General]** tab.

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >Herhaal deze stappen om zoveel categorieën te maken als nodig is.

   Daarna kunt u zo nodig:

   * Toepassingsdata toewijzen vanaf de **[!UICONTROL Eligibility]** tab.

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Edit query]** om filters op het aanbiedingsdoel toe te passen.

   * Een overzicht van de subsidiabiliteitsregels. Klik op de knop **[!UICONTROL Schedule and eligibility rules of the offer]** koppeling.

## Een terugvalcategorie toevoegen

Om ervoor te zorgen dat alle ontvangers een voorstel voor een aanbod ontvangen, is het mogelijk systematisch een of meerdere categorieën aanbiedingen in de aanbevelingen op te nemen.

Deze terugvalaanbiedingen moeten een laag (maar niet-nulgewicht) gewicht hebben, zodat ze alleen in aanmerking worden genomen als er geen aanbiedingen met een hoger gewicht in aanmerking komen.

Bovendien mag er geen presentatieregel worden toegepast op deze aanbiedingen om ervoor te zorgen dat deze altijd in de aanbevelingen worden opgenomen. Dit betekent dat de ontvanger tijdens een voorstel ten minste één bod van deze categorie zal ontvangen als er geen aanbod met een hoger gewicht beschikbaar is.

Volg onderstaande stappen om een fallback-categorie op te nemen in de aanbevelingen:

1. Blader naar de catalogus met aanbiedingen.
1. Klik op de knop **[!UICONTROL Eligibility]** en selecteert u de **[!UICONTROL Always include this category in the recommendations]** optie.
1. Klik op **[!UICONTROL Save]**.

   ![](assets/offer_cat_default_001.png)
