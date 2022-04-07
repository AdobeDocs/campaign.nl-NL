---
title: Belangrijk beheer in campagne
description: Aan de slag met sleutelbeheer
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: 2d0b40e49afdfd71e8bb5c3f0b1d569a715420b2
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Sleutelbeheer en eenheid {#key-management}

In Campagne v8 is de primaire sleutel een Universally Unique IDentifier (UUID), die een tekenreeks op tekens is. Als u deze UUID wilt maken, moet het hoofdelement van het schema het volgende bevatten: **autouuid** en **automatische** kenmerken ingesteld op **true**.

Adobe Campaign v8 wordt geleverd met Snowflake als de kerndatabase. De verdeelde architectuur van het gegevensbestand van Snowflake verstrekt geen mechanismen om de eenheid van een sleutel binnen een lijst te beheren: eindgebruikers zijn verantwoordelijk voor het waarborgen van consistentie van sleutels binnen de Adobe Campaign-database.

Om de consistentie van relationele databases te behouden, is het verplicht duplicaten van sleutels, en met name van primaire sleutels, te voorkomen. Duplicaties op primaire sleutels leiden tot problemen met de werkstroomactiviteiten voor gegevensbeheer, zoals **Query**, **Verzoening**, **Gegevens bijwerken** en meer.

Adobe beveelt aan een [Detecteren](#detect-duplicates) en [Juist](#correct-duplicates) strategie als onderdeel van uw algemene proces voor gegevensbeheer, in het geval dat dubbele sleutels in de database zijn geladen.

## Duplicaten detecteren{#detect-duplicates}

Campagne wordt geleverd met een nieuwe hulplijn die automatisch gedupliceerde UUID&#39;s uit een publiek verwijdert tijdens de voorbereiding van de levering. Dit nieuwe mechanisme voorkomt dat er een fout optreedt bij het voorbereiden van een levering.

>[!CAUTION]
>
>Gedupliceerde toetsen zijn niet beperkt tot UUID&#39;s. Dit kan gebeuren in combinatie met id&#39;s, inclusief aangepaste sleutels die in aangepaste tabellen zijn gemaakt.

Als eindgebruiker, kunt u deze informatie in de leveringslogboeken controleren: sommige ontvangers kunnen van het hoofddoel worden uitgesloten vanwege een gedupliceerde sleutel. In dat geval wordt de volgende waarschuwing weergegeven: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/delivery-log-duplicates.png)

Wanneer dit gebeurt, kunt u een werkschema tot stand brengen om de dubbele sleutels te identificeren. Vervolgens kunt u deze toetsen corrigeren. Volg onderstaande stappen om dit te doen:

1. Maak een nieuwe workflow.

   ![](assets/new-wf.png)

1. Voeg een **Query** activiteit
1. Selecteer **Ontvanger** table

   ![](assets/add-query-on-rcp.png)

1. Voeg een **Deduplicatie** activiteit en dedupliceren op de primaire sleutel (UUID). Houd slechts één duplicaat en controleer de  **Complement genereren** optie om een uitgaande overgang te maken voor de duplicaten.

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

* **Zaak 1** - Gedupliceerde ontvangers met dezelfde UUID en dezelfde profielgegevens (zelfde e-mail, voornaam, enz.) : de ontvangers zien er als &quot;echte&quot; duplicaten uit en de verzachting zou kunnen zijn om slechts één van de duplicaten te verwijderen.
Een andere manier zou kunnen zijn om informatie van één ontvanger in andere te verenigen.

* **Zaak 2** - Gedupliceerde ontvangers met dezelfde UUID maar andere profielgegevens (andere e-mail, voornaam enz.): Nu lijkt het of er verschillende profielen zijn en dat u beide wilt behouden in de Campagne-database. Dit betekent dat we liever alleen een van de duplicaten bijwerken die een nieuwe UUID genereren. [Meer informatie in dit voorbeeld](#deduplicate-sample).

Afhankelijk van uw verzachtingsstrategie kunt u altijd een query uitvoeren op de lijst in een andere workflow en de update toepassen op basis van uw behoefte. Neem contact op met Adobe voor meer informatie.

### Voorbeeld van deduplicatie{#deduplicate-sample}

Bij gedupliceerde ontvangers kunt u beide records in de Campagne-database bewaren. In dat geval moet u een van de UUID&#39;s bijwerken met een nieuwe UUID.

Zo kunt u een SQL-updatequery uitvoeren op de Cloud Database met de opdracht **SQL-gegevensbeheer** workflowactiviteit en voer de volgende SQL-update uit:

```sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

Zodra de geselecteerde rij met nieuwe UUID wordt bijgewerkt dan kunt u de bijgewerkte rij van de interface controleren en opmerken UUID zoals verwacht is bijgewerkt. U kunt ook duplicaten in de database detecteren door de opdracht **Duplicaten detecteren** werkstroom [zoals hier uitgelegd](#detect-duplicates).
