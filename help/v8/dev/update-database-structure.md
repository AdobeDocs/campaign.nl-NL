---
title: De databasestructuur bijwerken
description: De databasestructuur bijwerken
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%

---

# De databasestructuur bijwerken{#updating-the-database-structure}

Om de wijzigingen toe te passen die aan de schema&#39;s worden aangebracht, lanceer de de updatetovenaar van het Gegevensbestand. Deze assistent is toegankelijk via **[!UICONTROL Tools > Advanced > Update database structure]** . Het controleert of de fysieke structuur van het gegevensbestand zijn logische beschrijving aanpast en de SQL updatescripts uitvoert.

![](assets/schema_update.png)

De modules in het gegevensbestand worden automatisch bevolkt en geactiveerd.

![](assets/schema_update_select2.png)

Voer de stappen uit en bekijk het SQL-script voor de update van de database:

![](assets/schema_update2.png)

>[!NOTE]
>
>Dit bevindt zich in een bewerkingsveld en kan worden gewijzigd om SQL-code te verwijderen of toe te voegen.

Start vervolgens de database-update:

![](assets/schema_update3.png)
