---
title: Voorspellingsmogelijkheden voor gebruikersbetrokkenheid
description: Leer hoe u voorspellende verzendtijd en betrokkenheidsscores kunt gebruiken
feature: Send Time Optimization
role: User
level: Intermediate
source-git-commit: fdaf107fd22f439a728f32ceb8cfc13a8c5bc1ad
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 67%

---

# Optimalisatie op korte termijn en voorspellende betrokkenheidsscoring{#optimize-message-delivery}

Dankzij AI en computerleren kunnen de Send-Time Optimization en het Predictive Engagement Scoring van Adobe Campaign open tarieven, optimale verzendtijden en waarschijnlijke prijs analyseren en voorspellen op basis van historische betrokkenheidsmetriek.

Adobe Campaign biedt twee nieuwe modellen voor het leren van machines: [Optimalisatie van de verzendtijd](#predictive-send) en [Progressieve scores voor betrokkenheid](#predictive-scoring). Deze twee modellen zijn machine-leert modellen die specifiek voor het ontwerpen en het leveren van betere klantenreizen zijn.

>[!CAUTION]
>
>Deze mogelijkheid is niet rechtstreeks beschikbaar als onderdeel van het product. Het is alleen beschikbaar voor Adobe Campaign Managed Cloud Services-klanten die Adobe Campaign Classic v7 of Adobe Campaign v8 uitvoeren.
>
>Voor de implementatie moet Adobe Consulting worden ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.


## Voorspellende optimalisatie van verzendtijd{#predictive-send}

De voorspellende voorspellingen van de Optimalisatie van de Send-Time die de beste verzendtijd voor elk ontvangend profiel voor e-mail opent of klikt en voor push-message opent. Voor elk ontvangend profiel geven de scores aan wat de beste verzendtijd is op elke weekdag en welke weekdag het geschiktst is voor verzending om de beste resultaten te bereiken.

Binnen het Predictive Send-Time Optimization model, zijn er twee submodellen:

* De voorspelbare verzendtijd voor openen is de beste tijd om een bericht naar de klant te verzenden voor een maximale kans op openen.

* De voorspelbare verzendtijd voor klikken is de beste tijd om een bericht naar de klant te verzenden voor een maximale kans op klikken


**Modelinvoer**: Leveringslogboeken, logbestanden bijhouden en profielkenmerken (niet-PII)

**Modeluitvoer**: Beste tijd om een bericht te verzenden (voor opent en klikt)

Uitvoerdetails:

* Bereken het beste tijdstip om een e-mail te verzenden voor de 7 dagen van de week met intervallen van 1 uur (bijvoorbeeld: 9:00 uur, 10:00 uur, 11:00 uur)
* Het model geeft de beste dag in de week en het beste tijdstip op die dag aan
* Elke optimale tijd wordt twee keer berekend: één keer om de openingsfrequentie te maximaliseren en één keer om de klikfrequentie te maximaliseren
* Er worden 16 velden weergegeven (14 voor weekdagen en 2 voor de hele week):
   * de beste verzendtijd voor een e-mail om klikken te optimaliseren op maandag - waarden tussen 0 en 23
   * de beste verzendtijd voor een e-mail om openen te optimaliseren op maandag - waarden tussen 0 en 23
   * ...
   * de beste verzendtijd voor een e-mail om klikken te optimaliseren op zondag - waarden tussen 0 en 23
   * de beste verzendtijd voor een e-mail om openen te optimaliseren op zondag - waarden tussen 0 en 23
   * ...
   * de beste verzenddag voor een e-mail om openen te optimaliseren voor de hele week - van maandag tot en met zondag
   * de beste verzendtijd voor een e-mail om openen te optimaliseren voor de hele week - waarden tussen 0 en 23


Optimalisatie van de verzendtijd wordt opgeslagen op profielniveau:

![](assets/sto-schema.png)


>[!NOTE]
>
>Het model heeft minstens één maand aan data nodig om significante resultaten te produceren. Deze voorspellende mogelijkheden zijn alleen van toepassing op e-mail- en pushkanalen.


## Voorspellende betrokkenheidsscore {#predictive-scoring}

Met voorspellende scores voor betrokkenheid voorspelt u de waarschijnlijkheid dat een ontvanger een bericht zal ontvangen en de kans dat hij of zij het abonnement zal opzeggen (zal opzeggen) binnen de volgende 7 dagen na het volgende e-mailbericht. De waarschijnlijkheden worden verder verdeeld in emmers op basis van het verwachte niveau van betrokkenheid bij uw inhoud: hoog, gemiddeld of laag. Deze modellen bieden de klanten ook de percentiele positie van het niet-abonnementsrisico om te begrijpen waar de rang van een bepaalde klant ten opzichte van anderen is.

Met voorspellende betrokkenheidsscore kunt u het volgende doen:

* **Een doelgroep selecteren**: met de queryactiviteit kunt u de doelgroep selecteren die u wilt aantrekken met een specifiek bericht
* **Een doelgroep uitsluiten**: met de queryactiviteit kunt u de doelgroep verwijderen voor afmelden
* **Personaliseren**: personaliseer berichten op basis van het betrokkenheidsniveau (sterk betrokken gebruikers krijgen een ander bericht dan niet-betrokken gebruikers)

Dit model gebruikt meerdere scores om het volgende aan te geven:

* **Betrokkenheidsscore voor openen/Betrokkenheidsscore voor klikken**: deze waarde geeft aan hoe waarschijnlijk het is dat een abonnee iets doet met een bepaald bericht (openen of klikken). Waarden kunnen variëren van 0,0 tot 1,0.
* **Waarschijnlijkheid van afmelding**: deze waarde geeft aan hoe waarschijnlijk het is dat de ontvanger zich voor het e-mailkanaal afmeldt op basis van één geopend bericht. Waarden kunnen variëren van 0,0 tot 1,0.
* **Retentieniveau**: met deze waarde worden gebruikers in drie niveaus ingedeeld: laag, gemiddeld en hoog. Bij een hoge waarde blijven gebruikers waarschijnlijk bij het merk, bij een lage waarde melden ze zich waarschijnlijk af.
* **Percentielwaarde voor retentie**: profielrangorde in termen van kans op afmelden. Waarden kunnen variëren van 0,0 tot 1,0. Als de percentielwaarde voor retentie bijvoorbeeld 0,953 is, is er meer kans dat deze ontvanger bij het merk blijft en minder kans dat deze zich afmeldt dan bij 95,3% van alle gebruikers.

>[!NOTE]
>
>Deze voorspellende mogelijkheden gelden alleen voor e-mailleveringen.
>
>Het model heeft minstens één maand aan data nodig om significante resultaten te produceren.

**Modelinvoer**: leveringslogboeken, trackinglogboeken en specifieke profielkenmerken

**Modeluitvoer**: een profielkenmerk dat de score en categorie van het profiel beschrijft
