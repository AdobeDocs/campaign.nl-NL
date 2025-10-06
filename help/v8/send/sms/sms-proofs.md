---
title: SMS-proefdrukken verzenden
description: Ontdek hoe je proefdrukken van een SMS-levering kunt verzenden
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: d2ec4d92-7f00-47c8-98e6-0613d6387de0
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Een bewijs van een SMS-levering verzenden {#sms-proof}

Adobe raadt u ten zeerste aan een validatiecyclus voor levering in te stellen. Zorg ervoor dat de inhoud is goedgekeurd voordat u deze naar het publiek stuurt.

Je kunt een bewijs voor je SMS-levering verzenden om het te valideren:

1. Klik op de knop **[!UICONTROL Send a proof]** . Er wordt een venster geopend

   ![](assets/proof_targeting.png){zoomable="yes"}

   U hebt meerdere modi om een proef te verzenden:

   * **[!UICONTROL Definition of a specific proof target]**: hiermee kunt u met filters zoeken naar de adressen in de database als het proefdrukdoel
   * **[!UICONTROL Substitution of the address]**: hiermee kunt u uw testadressen invoeren en de gegevens van de doelontvanger gebruiken om de inhoud te valideren. U kunt de vervangende adressen handmatig invoeren of selecteren in de vervolgkeuzelijst. De bijbehorende [&#x200B; opsomming &#x200B;](../../config/enumerations.md) is **[!UICONTROL Substitution address (rcpAddress)]**.
Standaard wordt vervanging willekeurig uitgevoerd, maar u kunt een specifieke ontvanger selecteren in het hoofddoel via het pictogram **[!UICONTROL Detail]** .
   * **[!UICONTROL Seed addresses]**: hiermee hebt u toegang tot zaadadressen als proefdoel. Deze adressen kunnen uit een dossier worden ingevoerd of manueel ingegaan.
   * **[!UICONTROL Specific target and Seed addresses]**: hiermee kunt u zaadadressen en adressen van ontvangers combineren.

1. Nadat u **[!UICONTROL Targeting mode]** hebt gekozen, voegt u de proefdrukadressen volgens deze optie toe

   In het onderstaande voorbeeld kiezen we **[!UICONTROL Definition of a specific proof target]** en voegen we een ontvanger toe:

   ![](assets/proof_recipient.png){zoomable="yes"}

1. Klik op de knop **[!UICONTROL Analyze]** .
Adobe Campaign voert alle controle uit alvorens de verzending van bewijs te bevestigen. Aan het einde van de analyse kan op de knop **[!UICONTROL Confirm delivery]** worden geklikt.

   ![](assets/proof_analyze.png){zoomable="yes"}

1. Klik op **[!UICONTROL Confirm delivery]** om de proefdruk van uw SMS-levering te verzenden.

Als allen op dit stadium juist is, kunt u vooruit gaan en [&#x200B; uw levering van SMS verzenden naar het publiek &#x200B;](sms-audience.md).
