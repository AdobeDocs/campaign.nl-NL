---
product: campaign
title: Aan de slag met campagnetypen
description: Leer hoe te vormen en campagnetypologieën uitvoeren
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 7fe079c5473fa164405753c2be6cc8be16329f58
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 16%

---

# Aan de slag met campagnetypen{#about-campaign-typologies}

**Campagne optimaliseren** Dit is de Adobe Campaign-module waarmee u het verzenden van leveringen kunt beheren, filteren en controleren. Om conflicten tussen campagnes te vermijden kan Adobe Campaign diverse combinaties testen door specifieke beperkingsregels toe te passen. Dit garandeert dat de verzonden berichten voldoen aan de behoeften en verwachtingen van klanten en het communicatiebeleid van het bedrijf.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#typologies-video)

>[!NOTE]
>
>Afhankelijk van uw aanbieding kan de optimalisatie van de campagne worden opgenomen of een invoegtoepassing. Controleer hiervoor uw licentieovereenkomst.

## Typologische regels en typologieën {#typology-rules}

Campagne wordt standaard geleverd met ingebouwde typologieën en typologische regels.

Een typologie is een set verificatieregels die tijdens de leveringsanalyse op alle berichten worden toegepast.

Een campagneretypologie kan verschillende typologische regels bevatten, maar een levering kan slechts naar één typologie verwijzen.

De ingebouwde typologische regels en typologieën zijn beschikbaar in de **[!UICONTROL Administration > Campaign management > Typology management]** knooppunt van Campagneverkenner.

Voor elke typologie wordt **[!UICONTROL Rules]** kunt u de toe te passen typologische regels toevoegen, verwijderen of bekijken.

![](assets/campaign_opt_rules_tab.png)

Als ze eenmaal zijn gemaakt, worden de typologische regels gegroepeerd in campagne **typologieën** waarnaar in leveringen wordt verwezen. [Meer informatie](#apply-typologies).


Campagne wordt geleverd met een set standaardinstellingen **Filteren** en **Control** regels:

* **Filteren** regels worden gebruikt om een deel van de doelstelling op basis van criteria uit te sluiten . [Meer informatie](filtering-rules.md).
* **Control** de regels laten u de geldigheid van berichten controleren alvorens zij worden verzonden. [Meer informatie](control-rules.md).

De invoegtoepassing Campagne optimaliseren biedt twee extra typen **typologieregels**:

* **Druk** regels die u in staat stellen om vermoeidheid bij het in de handel brengen te beheersen. [Meer informatie](pressure-rules.md).
* **Capaciteit** regels waarmee u de belasting kunt beperken om optimale verwerkingsomstandigheden te garanderen. [Meer informatie](consistency-rules.md#controlling-capacity).


>[!NOTE]
>
>Als u het **Interactie** kunt u ook **Presentatie aanbieden** typologieregels om de stroom van voorstellen te controleren met behulp van presentatieregels. [Meer informatie](../../v8/interaction/interaction-offer.md#offer-presentation).


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

Er zijn gevallen van monstergebruik voor de druktypologische regels beschikbaar in: [deze pagina](pressure-rules.md#use-cases-on-pressure-rules).

## Tutorialvideo’s {#typologies-video}

### Vermoeidheidsbeheer instellen met behulp van typologische regels

In deze video wordt uitgelegd hoe u vermoeidheidsbeheer in Adobe Campaign kunt implementeren door gebruik te maken van typologische regels.

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### Vermoeidheidsbeheer instellen met behulp van vooraf gedefinieerde filters

Moeheidsbeheer bepaalt de frequentie en de hoeveelheid van de berichten om de ontvangers niet te overspoelen. Als u niet de module van de campagneroptimalisering in uw campagneinstantie hebt, kunt u een vooraf bepaald filter vormen dat de doelbevolking door het aantal ontvangen berichten zal filtreren Deze video verklaart hoe te om vermoeidheidsbeheer in Adobe Campaign uit te voeren door filters te gebruiken.

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
