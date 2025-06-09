---
product: campaign
title: Aan de slag met campagnetypen
description: Leer hoe te vormen en campagnetypologieën uitvoeren
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 15%

---

# Aan de slag met campagnetypen{#about-campaign-typologies}

**Optimalisering van de Campagne** is de module van Adobe Campaign die u laat controleren, filtreren en controleren het verzenden van leveringen. Om conflicten tussen campagnes te vermijden kan Adobe Campaign diverse combinaties testen door specifieke beperkingsregels toe te passen. Dit garandeert dat de verzonden berichten voldoen aan de behoeften en verwachtingen van klanten en het communicatiebeleid van het bedrijf.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#typologies-video)

>[!NOTE]
>
>Afhankelijk van uw aanbieding kan de optimalisatie van de campagne worden opgenomen of een invoegtoepassing. Controleer hiervoor uw licentieovereenkomst.

## Typologieregels en typologieën {#typology-rules}

Campagne wordt standaard geleverd met ingebouwde typologieën en typologische regels.

Een typologie is een set verificatieregels die tijdens de leveringsanalyse op alle berichten worden toegepast.

Een campagneretypologie kan verschillende typologische regels bevatten, maar een levering kan slechts naar één typologie verwijzen.

De ingebouwde typologische regels en typologieën zijn beschikbaar in de map **[!UICONTROL Administration > Campaign management > Typology management]** van de Campagneverkenner.

Voor elke typologie kunt u met het tabblad **[!UICONTROL Rules]** de toe te passen typologische regels toevoegen, verwijderen of bekijken.

![](assets/campaign_opt_rules_tab.png)

Zodra zij zijn gecreeerd, worden de typologische regels gegroepeerd in campagne **typologies** die in leveringen van verwijzingen worden voorzien. [Meer informatie](#apply-typologies).


De campagne komt met een reeks standaard **Filtrerend** en **3} regels van de Controle {:**

* **het Filtreren** regels worden gebruikt om een deel van het doel uit te sluiten dat op criteria wordt gebaseerd. [Meer informatie](filtering-rules.md).
* **de regels van de Controle** laten u de geldigheid van berichten controleren alvorens zij worden verzonden. [Meer informatie](control-rules.md).

Het toe:voegen-op van de Optimalisering van de Campagne verstrekt twee extra types van **typologieregels**:

* **Druk** regels die u marketing moeheid laten controleren. [Meer informatie](pressure-rules.md).
* **de regels van de Capaciteit** die u ladingen laten beperken om optimale verwerkingsvoorwaarden te waarborgen. [Meer informatie](consistency-rules.md#controlling-capacity).


>[!NOTE]
>
>Als u de **module van de Interactie** gebruikt om aanbiedingen te beheren, kunt u **presentatie van de Aanbieding** typologische regels ook tot stand brengen om de stroom van aanbiedingsvoorstellen te controleren gebruikend presentatieregels. [Meer informatie](../../v8/interaction/interaction-offer.md#offer-presentation).


## Belangrijke stappen voor het maken en gebruiken van typologieën {#apply-typologies}

Volg onderstaande stappen om een typologie voor uw leveringen te maken en te gebruiken:

1. Maak typologische regels en maak een typologie om ernaar te verwijzen.
De gedetailleerde stappen worden vermeld in de volgende sectie:

   * [Filterregels](filtering-rules.md)
   * [Controleregels](control-rules.md)
   * [Drukregels](pressure-rules.md)
   * [Capaciteitsregels](consistency-rules.md)

1. Vorm uw levering om de typologie te gebruiken u creeerde. [Meer informatie](apply-rules.md#apply-a-typology-to-a-delivery).
1. Test en controleer het gedrag door campagnesimulaties. [Meer informatie](campaign-simulations.md).

Tijdens de voorbereiding van de levering worden ontvangers uitgesloten wanneer aan het criterium wordt voldaan. U kunt logboeken controleren om toezicht te houden op uitsluitingen.

De gebruiksgevallen van de steekproef op druktypologische regels zijn beschikbaar in [ deze pagina ](pressure-rules.md#use-cases-on-pressure-rules).

## Zelfstudievideo&#39;s {#typologies-video}

### Vermoeidheidsbeheer instellen met behulp van typologische regels

In deze video wordt uitgelegd hoe u vermoeidheidsbeheer in Adobe Campaign kunt implementeren door gebruik te maken van typologische regels.

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### Vermoeidheidsbeheer instellen met behulp van vooraf gedefinieerde filters

Moeheidsbeheer bepaalt de frequentie en de hoeveelheid van de berichten om de ontvangers niet te overspoelen. Als u niet de module van de campagnoptimalisering in uw campagneinstantie hebt, kunt u een vooraf bepaald filter vormen dat de doelbevolking door het aantal ontvangen berichten zal filtreren
In deze video wordt uitgelegd hoe u vermoeidheidsbeheer in Adobe Campaign kunt implementeren met behulp van filters.

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
