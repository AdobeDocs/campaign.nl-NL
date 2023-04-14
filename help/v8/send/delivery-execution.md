---
title: Uitvoering van Transactieberichten
description: Meer informatie over uitvoering en bewaking van transactiemeldingen
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 1%

---


# Uitvoering van levering {#delivery-execution}

Zodra de verrijking volledig is en een leveringsmalplaatje met de gebeurtenis verbonden is, wordt de levering verzonden van de uitvoeringsinstantie.

>[!NOTE]
>
>De transactieberichten worden voorrang gegeven boven om het even welke andere levering.

Alle leveringen worden gegroepeerd in de **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** map.

Standaard worden ze in submappen gesorteerd op leveringsmaand. Deze sortering kan worden gewijzigd in de eigenschappen van de berichtsjabloon.

## Transactionele berichtbewaking {#transactional-message-monitoring}

Om uw transactieberichten te controleren, controleer [leveringslogs](send.md).

De transactionele leveringen die van de uitvoeringsinstantie worden verzonden worden gesynchroniseerd terug naar de controleinstantie door een technisch werkschema (**[!UICONTROL Message Center execution instance]**) dat elk uur loopt.

>[!NOTE]
>
>De leveringenwekelijkse accumulatie van de gebeurtenissen op basis van de meest recente update van de gebeurtenis en niet op de aanmaakdatum van de gebeurtenis. Daarom wanneer het halen van transactioneel overseinenleveringslogboeken van de controleinstantie, levert identiteitskaart verbonden aan elke identiteitskaart van het leveringslogboek kan in tijd veranderen aangezien het logboek wordt bijgewerkt (bijvoorbeeld, wanneer een binnenkomende stuit voor de gebeurtenis wordt ontvangen).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
