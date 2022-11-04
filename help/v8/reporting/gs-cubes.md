---
title: Aan de slag met Adobe Campaign-analyserapporten
description: Leer hoe u kubussen maakt
feature: Reporting
role: Data Engineer
level: Beginner
source-git-commit: bd39a18178edec2730707f0323a19c9d1c80cd76
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 13%

---

# Aan de slag met analyserapporten van campagne {#gs-cube}

Adobe Campaign wordt geleverd met een intuïtief hulpprogramma voor gegevensverkenning voor het maken van dynamische rapporten.

Gebruik de mogelijkheden voor marketinganalyses om gegevens te analyseren en te meten, statistieken te berekenen, het maken en berekenen van rapporten te vereenvoudigen en te optimaliseren. U kunt rapporten creëren en doelpopulaties bouwen en hen opslaan in lijsten die in Adobe Campaign voor het richten of segmenteren van taken kunnen worden gebruikt.

U kunt de mogelijkheden van databaseverkenning en -analyse uitbreiden terwijl het voor eindgebruikers gemakkelijker wordt om rapporten en tabellen te configureren. Alles wat gebruikers moeten doen is een bestaande (volledig geconfigureerde) kubus selecteren bij het maken van hun rapport of tabel om berekeningen, metingen en statistieken te verwerken.

De kubussen worden gebruikt voor het produceren van bepaalde ingebouwde rapporten, met inbegrip van [leveringsrapporten](delivery-reports.md) (levering het volgen, klikt, opent, etc.).

>[!CAUTION]
>
>In een [[!DNL Snowflake] Implementatie van FDA (standaard)](../architecture/fda-deployment.md)Op kubussen gebaseerde rapporten mogen alleen worden gebruikt voor gegevensvolumes onder 5 miljoen feitenlijnen.


Zodra kubussen zijn gemaakt en geconfigureerd, worden ze gebruikt in vakken voor rapportquery’s en webapplicaties. Ze kunnen worden gebruikt en bewerkt binnen draaitabellen.

Met de module Campagne Marketing Analytics kunt u:

1. Kubussen en indicatoren maken

   * gegevens samenvoegen en opslaan in een werktabel om indicatoren vooraf te berekenen op basis van gebruikersbehoeften;
   * het gegevensvolume te verminderen dat betrokken is bij de verschillende berekeningen die voor rapporten en vragen worden gebruikt, zodat de berekeningstijden van de indicatoren aanzienlijk worden geoptimaliseerd;
   * de toegang tot gegevens te vereenvoudigen, gebruikers in staat te stellen gegevens (al dan niet vooraf geaggregeerd) afhankelijk van verschillende afmetingen te manipuleren.

   Raadpleeg voor meer informatie hierover [Indicatoren maken](cube-indicators.md).

1. Draaitabellen maken en gegevens verkennen

   * berekende gegevens, geconfigureerde maatregelen verkennen;
   * de gegevens selecteren die moeten worden weergegeven, alsmede de weergavemodus;
   * de gebruikte maatregelen en indicatoren aanpassen;
   * bieden interactieve analysehulpmiddelen aan gebruikers met een niet-technische achtergrond.

   Raadpleeg voor meer informatie hierover [Kubussen gebruiken om gegevens te verkennen](cube-tables.md).

1. Bouw een vraag gebruikend gegevens die in een kubus worden berekend en worden samengevoegd.
1. Identificeer populaties en verwijs hen in lijsten.

## Terminologie {#terminology}

De specifieke termijnen wanneer het werken met kubussen worden hieronder vermeld.

* **Kubus** - Een kubus is een weergave van multidimensionale informatie: het biedt eindgebruikers structuren die ontworpen zijn voor interactieve gegevensanalyse .

* **Feitentabel/schema** - De feitenlijst (of het feitenschema) bevat de ruwe of elementaire gegevens waarop de analyses zullen worden gebaseerd. Dit zijn hoofdzakelijk grote volumelijsten (misschien met verbonden lijsten) met potentieel lange berekeningen. Een feitentabel kan bijvoorbeeld: de omroeptabel, de aankooptabel, enz.

* **Dimension** - Met Dimension kunt u gegevens segmenteren in groepen: zodra zij zijn gecreëerd , dienen de afmetingen als analysecentra . In de meeste gevallen zullen voor een bepaalde dimensie verschillende niveaus worden vastgesteld. Voor een tijdsdimensie zijn de niveaus bijvoorbeeld maanden, dagen, uren, minuten, enzovoort. Deze reeks niveaus vertegenwoordigt de dimensiehiërarchie en laat diverse niveaus van gegevensanalyse toe.

* **Binding** - Voor sommige velden kunt u binden aan groepswaarden definiëren en het gemakkelijker maken om informatie te lezen. Binding wordt toegepast op niveaus. Wij adviseren dat u het binden bepaalt wanneer er een mogelijkheid van vele verschillende waarden is.

* **Meetlat** - De meest voorkomende maatregelen zijn som, gemiddelde, maximum, minimum, standaardafwijking enz. De maatregelen kunnen worden berekend: zo is het aanvaardingspercentage van een aanbieding bijvoorbeeld de verhouding tussen het aantal ingediende aanbiedingen en het aantal aanvaarde inschrijvingen .
