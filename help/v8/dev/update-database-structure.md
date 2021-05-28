---
solution: Campaign v8
product: Adobe Campaign
title: De databasestructuur bijwerken
description: De databasestructuur bijwerken
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%

---

# De databasestructuur bijwerken{#updating-the-database-structure}

Om de wijzigingen toe te passen die aan de schema&#39;s worden aangebracht, lanceer de de updatetovenaar van het Gegevensbestand. Deze assistent is toegankelijk via **[!UICONTROL Tools > Advanced > Update database structure]**. Het controleert of de fysieke structuur van het gegevensbestand zijn logische beschrijving aanpast en de SQL updatescripts uitvoert.

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
