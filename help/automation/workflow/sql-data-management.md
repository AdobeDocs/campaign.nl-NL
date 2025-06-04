---
product: campaign
title: SQL Data Management
description: Meer informatie over de workflowactiviteit van SQL Data Management
feature: Workflows
Role: User
level: Experienced
version: Campaign v8, Campaign Classic v7
exl-id: a1e08d57-0387-4802-b447-f6d9ad87072a
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# SQL Data Management{#sql-data-management}

De **SQL activiteit van het Beheer van Gegevens** laat u uw eigen SQL manuscripten schrijven om het werklijsten tot stand te brengen en te bevolken.

## Vereisten {#prerequisites}

Voordat u de activiteit configureert, moet u controleren of aan de volgende voorwaarden is voldaan:

* De activiteit is beschikbaar voor verre slechts gegevensbronnen.
* Het uitgaande schema moet in het gegevensbestand bestaan en met een gegevensbestand FDA worden verbonden.


## De SQL-gegevensbeheeractiviteit configureren {#configuring-the-sql-data-management-activity}

1. Geef de activiteit op **[!UICONTROL Label]** .
1. Selecteer de **[!UICONTROL External account]** die u wilt gebruiken en selecteer de **[!UICONTROL Outbound schema]** die aan deze externe account is gekoppeld.

   >[!CAUTION]
   >
   >Het uitgaande schema is vast en kan niet worden bewerkt.

1. Voeg het SQL-script toe.

   >[!CAUTION]
   >
   >Het is de verantwoordelijkheid van de SQL manuscriptschrijver om ervoor te zorgen dat het SQL manuscript functioneel is, en dat zijn verwijzingen (gebiedsnamen, enz.) in overeenstemming met het Uitgaande schema zijn.

   Als u een bestaande SQL-code wilt laden, selecteert u de optie **[!UICONTROL The SQL script is contained in an entity stored in the database]** . SQL-scripts moeten worden gemaakt en opgeslagen in het menu **[!UICONTROL Administration]** / **[!UICONTROL Configuration]** / **[!UICONTROL SQL scripts]** .

   Anders typt of kopieert u het SQL-script in het daarvoor bestemde gebied.

   ![](assets/sql_datamanagement.png)

   Met deze activiteit kunt u de volgende variabelen in het script gebruiken:

   * **activity.tableName**: SQL naam van de uitgaande het werklijst.
   * **task.innerTransitionByName (&#39;name&#39;).tableName**: SQL naam van de het werklijst die door de inkomende overgang wordt gedragen om te gebruiken (de overgang wordt geïdentificeerd door zijn naam).

     >[!NOTE]
     >
     >De waarde (&#39;name&#39;) komt overeen met het veld **[!UICONTROL Name]** van de overgangseigenschappen.

1. Als het SQL-script al opdrachten bevat om een uitgaande werktabel te maken, schakelt u de optie **[!UICONTROL Automatically create work table]** uit. Anders wordt automatisch een werktabel gemaakt zodra de workflow wordt uitgevoerd.
1. Klik op **[!UICONTROL Ok]** om de activiteitenconfiguratie te bevestigen.

De activiteit wordt nu gevormd. Het kan worden uitgevoerd in de workflow.

>[!CAUTION]
>
>Zodra de uitgevoerde activiteit, is de uitgaande telling van overgangsverslagen slechts indicatief. Deze kan variëren afhankelijk van het complexiteitsniveau van het SQL-script.
>  
>Als de activiteit opnieuw is begonnen, wordt het volledige manuscript uitgevoerd vanaf zijn begin, ongeacht het uitvoerstatus.

## SQL-scriptvoorbeelden {#sql-script-samples}

>[!NOTE]
>
>De manuscriptsteekproeven in deze sectie moeten onder PostgreSQL worden uitgevoerd.

Met het onderstaande script kunt u een werktabel maken en gegevens in dezelfde werktabel invoegen:

```
CREATE UNLOGGED TABLE <%= activity.tableName %> (
  iRecipientId INTEGER DEFAULT 0,
  sFirstName VARCHAR(100),
  sMiddleName VARCHAR(100),
  sLastName VARCHAR(100),
  sEmail VARCHAR(100)
);

INSERT INTO <%= activity.tableName %>
SELECT iRecipientId, sFirstName, sMiddleName, sLastName, sEmail
FROM nmsRecipient
GROUP BY iRecipientId, sFirstName, sMiddleName, sLastName, sEmail;
```

Met het onderstaande script kunt u een CTAS-bewerking (CREATE TABLE AS SELECT) uitvoeren en een werktabelindex maken:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT iRecipientId, sEmail, sFirstName, sLastName, sMiddleName
FROM nmsRecipient
WHERE sEmail IS NOT NULL
GROUP BY iRecipientId, sEmail, sFirstName, sLastName, sMiddleName;

CREATE INDEX ON <%= activity.tableName %> (sEmail);

ANALYZE <%= activity.tableName %> (sEmail);
```

Met het onderstaande script kunt u twee werktabellen samenvoegen:

```
CREATE TABLE <%= activity.tableName %>
AS SELECT i1.sFirstName, i1.sLastName, i2.sEmail
FROM <%= task.incomingTransitionByName('input1').tableName %> i1
JOIN <%= task.incomingTransitionByName('input2').tableName %> i2 ON (i1.id = i2.id)
```
