---
product: campaign
title: Campagne maken met webcomponenten en versie 100 in Chrome Firefox- en Edge-browsers
description: Webcomponenten en versie 100 van de campagne in Chrome, Firefox, en browsers van Edge
hide: true
hidefromtoc: true
exl-id: 912ad71e-2b23-4b16-b5f9-47d547fc83d5
source-git-commit: 8f58db2b00f2fc98afd737f20411f829dd24c78a
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%

---

# Browserversie van 3 cijfers heeft invloed op webcomponenten voor campagnes {#version-100}

Google en Mozilla waarschuwen dat Chrome en Firefox sommige websites kunnen verbreken vanwege hun aanstaande versies van 3 cijfers.

Chrome v100 wordt geplaatst voor versie op **29 Maart, 2022**, en Firefox v100 op **3 Mei, 2022**.

Microsoft heeft Edge v100 eerder uitgebracht in maart 2022.

De wijziging in het versienummer van 2 naar 3 cijfers kan problemen veroorzaken bij het bezoeken van websites die niet zijn voorbereid voor deze wijziging. Sommige webpagina&#39;s worden mogelijk niet meer correct weergegeven in deze nieuwe browserversies.

De compatibiliteit van belangrijke websites is van tevoren getest. Als er problemen zijn met sites die niet kunnen worden opgelost voordat deze versies worden uitgebracht, hebben bedrijven back-upplannen die klaar zijn om ervoor te zorgen dat de sites niet worden beïnvloed.

Mogelijke problemen of verlies van functionaliteit op de website komen voort uit de userAgent-tekenreeks die browsers verzenden naar websites die u bezoekt: de userAgent is een tekenreeks die door de browser naar de website wordt verzonden om de site te laten weten welke browser en versie u gebruikt, en de bijbehorende technologie. Wanneer uw browser een verzoek naar een website verzendt, identificeert het zich met het koord van de gebruikersagent alvorens het de gevraagde inhoud terugwint. De gegevens in de tekenreeks van de gebruikersagent helpen de website de inhoud te leveren in een indeling die geschikt is voor uw browser. De versie van de gebruikersagent wordt verhoogd zodat deze overeenkomt met het versienummer van de browser. Het verplaatsen van 2 naar 3 cijfers kan problemen veroorzaken.

## Heb je invloed op?{#version-100-impact}

Adobe raadt u aan uw Campagne-webtoepassingen, waaronder webformulieren en enquêtes, te testen om ervoor te zorgen dat deze nog steeds goed werken met deze nieuwe browserversies.

Deze aanbeveling is van toepassing op alle webtoepassingen, en vooral als u JavaScript-code hebt opgenomen.

U moet dit controleren bij alle browsers, mobiel en bureaublad.

## Hoe kan ik testen?{#version-100-test}

U kunt uw browsers vormen om de versie nu als 100 te melden, dan om het even welke kwesties te melden en te verbeteren u tegenkomt.

Met deze instellingen stuurt de browser de tekenreeks new userAgent naar websites om aan te geven dat de browser versie 100 is. Als u problemen ondervindt met uw webformulieren, moet u een bug voor de browsereditor maken. Overweeg deze webformulieren opnieuw samen te stellen voordat deze updates algemeen beschikbaar zijn.

### Testen met Firefox 100{#test-firefox-100}

Als u uw webpagina&#39;s wilt testen met Mozilla Firefox 100, kunt u de volgende wijziging van de gebruikersagent in uw webapps simuleren door de tekenreeks van de gebruikersagent handmatig te wijzigen.

1. Open Firefox, voer `about:config` in op de adresbalk en druk op Enter.
1. Zoeken naar `general.useragent.override` .
1. Selecteer &#39;String&#39; en klik op het plusteken (+).

   ![](assets/do-not-localize/force-user-agent-firefox.png)

1. Voer de volgende tekst in het veld in:

   ```
   Mozilla/5.0 (Windows NT 10.0; rv:100.0) Gecko/20100101 Firefox/100.0
   ```

1. Klik op het blauwe vinkje om de instelling op te slaan.
1. Sluit de browser en start deze opnieuw.

Als u de standaardversie van de gebruikersagent wilt herstellen, gaat u gewoon terug naar `about:config` en zoekt u nogmaals naar `general.useragent.override` -instelling.  Klik in dat geval op het prullenbakpictogram om de instelling te verwijderen en de browser opnieuw te starten.

### Testen met Chrome 100{#test-chrome-100}

Als u de Google Chrome 100-gebruikersagent wilt testen op uw eigen webapps, kunt u deze test inschakelen door de volgende stappen uit te voeren:

1. Open Chrome, typ `chrome://flags` op de adresbalk en druk op Enter.
1. Zoek `Force major version to 100 in User-Agent` in het zoekveld en schakel het in zoals hieronder wordt weergegeven.

   ![](assets/do-not-localize/force-user-agent-chrome.png)

1. Start de browser opnieuw.
1. Sluit de tab `chrome://flags` .

Als u de standaardversie van de gebruikersagent wilt herstellen, volgt u dit proces en wijzigt u de instelling van de markering in `Default` en start u de browser opnieuw.


### Testen met Microsoft Edge 100{#test-ms-edge-100}

Vanaf versie 97 kunnen siteeigenaars deze versie emuleren door de experimentatiemarkering `#force-major-version-to-100` in `edge://flags` in te schakelen.

1. Open Microsoft Edge, typ `edge://flags` op de adresbalk en druk op Enter.
1. Zoek naar `force-major-version-to-100` gebied, en laat het zoals hieronder getoond toe.

   ![](assets/do-not-localize/force-user-agent-edge.png)

1. Start de browser opnieuw.
1. Sluit de tab `edge://flags` .

Als u de standaardversie van de gebruikersagent wilt herstellen, volgt u dit proces en wijzigt u de instelling van de markering in `Default` en start u de browser opnieuw.
