---
title: Aan de slag met Adobe Campaign-analyserapporten
description: Leer hoe u kubussen maakt
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 13%

---

# Aan de slag met analyserapporten van campagne {#gs-cube}

Adobe Campaign wordt geleverd met een intuïtief hulpprogramma voor gegevensverkenning voor het maken van dynamische rapporten.

Gebruik de mogelijkheden voor marketinganalyses om gegevens te analyseren en te meten, statistieken te berekenen, het maken en berekenen van rapporten te vereenvoudigen en te optimaliseren. U kunt rapporten creëren en doelpopulaties bouwen en hen opslaan in lijsten die in Adobe Campaign voor het richten of segmenteren van taken kunnen worden gebruikt.

U kunt de mogelijkheden van databaseverkenning en -analyse uitbreiden terwijl het voor eindgebruikers gemakkelijker wordt om rapporten en tabellen te configureren. Alles wat gebruikers moeten doen is een bestaande (volledig geconfigureerde) kubus selecteren bij het maken van hun rapport of tabel om berekeningen, metingen en statistieken te verwerken.

De kubussen worden gebruikt voor het produceren van bepaalde ingebouwde rapporten, met inbegrip van [ leveringsrapporten ](delivery-reports.md) (levering het volgen, klikt, opent, enz.).

Zodra kubussen zijn gemaakt en geconfigureerd, worden ze gebruikt in vakken voor rapportquery’s en webapplicaties. Ze kunnen worden gebruikt en bewerkt binnen draaitabellen.

Met de module Campagne Marketing Analytics kunt u:

1. Kubussen en indicatoren maken

   * gegevens samenvoegen en opslaan in een werktabel om indicatoren vooraf te berekenen op basis van gebruikersbehoeften;
   * het gegevensvolume te verminderen dat betrokken is bij de verschillende berekeningen die voor rapporten en vragen worden gebruikt, zodat de berekeningstijden van de indicatoren aanzienlijk worden geoptimaliseerd;
   * de toegang tot gegevens te vereenvoudigen, gebruikers in staat te stellen gegevens (al dan niet vooraf geaggregeerd) afhankelijk van verschillende afmetingen te manipuleren.

   Voor meer op dit, verwijs naar [ creeer indicatoren ](cube-indicators.md).

1. Draaitabellen maken en gegevens verkennen

   * berekende gegevens, geconfigureerde maatregelen verkennen;
   * de gegevens selecteren die moeten worden weergegeven, alsmede de weergavemodus;
   * de gebruikte maatregelen en indicatoren aan te passen;
   * bieden interactieve analysehulpmiddelen aan gebruikers met een niet-technische achtergrond.

   Voor meer op dit, verwijs naar [ kubussen van het Gebruik om gegevens ](cube-tables.md) te onderzoeken.

1. Bouw een vraag gebruikend gegevens die in een kubus worden berekend en worden samengevoegd.
1. Identificeer populaties en verwijs hen in lijsten.

## Terminologie {#terminology}

De specifieke termijnen wanneer het werken met kubussen worden hieronder vermeld.

* **kubus** - een kubus is een vertegenwoordiging van multidimensionele informatie: het voorziet eind - gebruikers van structuren die voor interactieve gegevensanalyse worden ontworpen.

* **lijst/schema van het Fact** - de feitenlijst (of feitenschema) bevat de ruwe of elementaire gegevens waarop de analyses zullen worden gebaseerd. Dit zijn hoofdzakelijk grote volumelijsten (misschien met verbonden lijsten) met potentieel lange berekeningen. Een tabel met feiten kan bijvoorbeeld de volgende zijn: de tabel voor het uitzenden, de tabel voor aankopen, enzovoort.

* **Dimension** - de Afmetingen laten u gegevens in groepen segmenteren: zodra zij zijn gecreeerd, dienen de afmetingen als analysegassen. In de meeste gevallen zullen voor een bepaalde dimensie verschillende niveaus worden vastgesteld. Voor een tijdsdimensie zijn de niveaus bijvoorbeeld maanden, dagen, uren, minuten, enzovoort. Deze reeks niveaus vertegenwoordigt de dimensiehiërarchie en laat diverse niveaus van gegevensanalyse toe.

* **Bindend** - voor sommige gebieden, kunt u het binden aan groepswaarden bepalen en het gemakkelijker maken om informatie te lezen. Binding wordt toegepast op niveaus. Wij adviseren dat u het binden bepaalt wanneer er een mogelijkheid van vele verschillende waarden is.

* **Maatregel** - de frequentste maatregelen zijn som, gemiddelde, maximum, minimum, standaardafwijking etc. De maatregelen kunnen worden berekend: het aanvaardingspercentage van een aanbieding is bijvoorbeeld de verhouding tussen het aantal ingediende aanbiedingen en het aantal aanvaarde inschrijvingen.
