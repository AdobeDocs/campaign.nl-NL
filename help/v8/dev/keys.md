---
product: Adobe Campaign
title: 'Belangrijk beheer in campagne '
description: Aan de slag met sleutelbeheer
source-git-commit: 40b38168a3704f171f1f389e2d232e6a2c6f1d85
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Belangrijk beheer en eenheid {#key-management}

In Campagne v8 is de primaire sleutel een Universally Unique IDentifier (UUID), die een tekenreeks op tekens is. Om deze UUID tot stand te brengen, moet het belangrijkste element van het schema **autouuid** en **Automatische Auto** attributen bevatten die aan **true** worden geplaatst.

Adobe-campagne v8 wordt geleverd met Snowflake als de kerndatabase. De verdeelde architectuur van het gegevensbestand van Snowflake verstrekt geen mechanismen om de eenheid van een sleutel binnen een lijst te beheren: eindgebruikers zijn verantwoordelijk voor het waarborgen van consistentie van sleutels binnen de Adobe Campaign-database.

Om de consistentie van relationele databases te behouden, is het verplicht duplicaten van sleutels, en met name van primaire sleutels, te voorkomen. Duplicaten op primaire sleutels leiden tot problemen met de werkstroomactiviteiten voor gegevensbeheer, zoals Query, Verzoening, Update en meer.

Adobe Campaign stelt krachtige hulpmiddelen voor gegevensbeheer voor om de gegevens te combineren, ervoor te zorgen dat gegevens worden ingevoegd of bijgewerkt afhankelijk van de aanwezigheid ervan in de database (Afstemming) en duplicaten te verwijderen voordat gegevens worden ingevoerd (Deduplicatie). Als beste praktijken, adviseert Adobe het goedkeuren van een [Detect](#detect-duplicates) en [Correct](#correct-duplicates) strategie als deel van uw algemeen proces van het Beheer van Gegevens, voor het geval dat de gedupliceerde sleutels in het gegevensbestand zijn geladen.

## Duplicaten detecteren{#detect-duplicates}

Campagne wordt geleverd met een nieuwe hulplijn die automatisch gedupliceerde UUID&#39;s uit een publiek verwijdert tijdens de voorbereiding van de levering. Dit nieuwe mechanisme voorkomt dat er een fout optreedt bij het voorbereiden van een levering.

Als eindgebruiker, kunt u deze informatie in de Logboeken van de Levering controleren: sommige ontvangers kunnen van het hoofddoel worden uitgesloten vanwege een gedupliceerde sleutel. In dat geval wordt de volgende waarschuwing weergegeven: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/delivery-log-duplicates.png)

Wanneer dit gebeurt, kunt u een werkschema tot stand brengen om de dubbele sleutels te identificeren. Vervolgens kunt u deze toetsen corrigeren. Volg onderstaande stappen om dit te doen:

1. Maak een nieuwe workflow.

   ![](assets/new-wf.png)

1. Een **Query**-activiteit toevoegen
1. Selecteer de tabel **Ontvanger**

   ![](assets/add-query-on-rcp.png)

1. Voeg een **Deduplicatie** activiteit toe en dedupliceer op de primaire sleutel (UUID). Houd slechts één duplicaat en controleer **Generate Complement** optie om een uitgaande overgang voor duplicaten tot stand te brengen.

   ![](assets/deduplicate.png)

1. Sla de duplicaten op in een lijst met behulp van een List-updateactiviteit.

   ![](assets/list-update.png)

U hebt nu rechtstreeks vanuit de lijst toegang tot de gedupliceerde ontvangers. Zelfs als de overgang slechts een van de gedupliceerde rijen bevat, worden alle duplicaten in de lijst geregistreerd.


## Duplicaten corrigeren{#correct-duplicates}

Voor het corrigeren van duplicaten moeten klanten Campagnegegevens bijwerken. Het type actie is sterk gebonden aan de aard van de duplicaten en de implementatie. Er kunnen meerdere gevallen optreden waarvoor een andere mitigatiestrategie nodig is (verwijderen, samenvoegen of bijwerken).

>[!IMPORTANT]
>
>Met dubbele primaire sleutels kunt u geen ingebouwde workflowactiviteiten gebruiken om een specifieke rij te selecteren of bij te werken. Wegens gedupliceerde UUID, zal gegevensdeduplicatie ontbreken en kan uw gegevensbestandintegriteit beïnvloeden. Daarom wordt het ten zeerste aanbevolen duplicaten te corrigeren.

Bijvoorbeeld:

* **Case 1**  - Gedupliceerde ontvangers met dezelfde UUID en dezelfde profielgegevens (zelfde e-mail, voornaam, enz.) : de ontvangers zien er als &quot;echte&quot; duplicaten uit en de verzachting zou kunnen zijn om slechts één van de duplicaten te verwijderen.
Een andere manier zou kunnen zijn om informatie van één ontvanger in andere te verenigen.

* **Case 2**  - Gedupliceerde ontvangers met dezelfde UUID maar andere profielgegevens (andere e-mail, voornaam, enz.):
Nu lijkt het of er verschillende profielen zijn en dat u beide wilt behouden in de Campagne-database. Dit betekent dat we liever alleen een van de duplicaten bijwerken die een nieuwe UUID genereren. [Meer weten in dit voorbeeld](#deduplicate-sample)?

Afhankelijk van uw verzachtingsstrategie kunt u altijd een query uitvoeren op de lijst in een andere workflow en de update toepassen op basis van uw behoefte. Neem contact op met Adobe voor meer informatie.

### Deduplicatiemonster{#deduplicate-sample}

Bij gedupliceerde ontvangers kunt u beide records in de Campagne-database bewaren. In dat geval moet u een van de UUID&#39;s bijwerken met een nieuwe UUID.

Zo kunt u een SQL updatequery op het Gegevensbestand van de Wolk in werking stellen u **SQL gegevensbeheer** werkschemaactiviteit gebruiken en de volgende SQL update uitvoeren:

```sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

Zodra de geselecteerde rij met nieuwe UUID wordt bijgewerkt dan kunt u de bijgewerkte rij van de interface controleren en opmerken UUID zoals verwacht is bijgewerkt. U kunt ook duplicaten in de database detecteren door de workflow [Detecteren van duplicaten uit te voeren, zoals hier wordt uitgelegd](#detect-duplicates).
