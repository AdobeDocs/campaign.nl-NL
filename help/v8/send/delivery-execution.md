---
title: Transactieberichten verzenden en controleren
description: Leer hoe u transactieberichten kunt verzenden en controleren
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Transactieberichten verzenden en controleren {#delivery-execution}

## Berichten verzenden{#send-transactional-msg}

Zodra de verrijking volledig is en een leveringsmalplaatje met de gebeurtenis verbonden is, wordt de levering verzonden van de uitvoeringsinstantie.

>[!NOTE]
>
>De transactieberichten worden voorrang gegeven boven om het even welke andere levering.

Alle leveringen worden gegroepeerd in de **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** map.

Standaard worden ze in submappen gesorteerd op leveringsmaand. Dit kan in de eigenschappen van het berichtmalplaatje worden veranderd.

## Monitorberichten {#monitor-transactional-msg}

Om uw transactieberichten te controleren, controleer [leveringslogs](send.md).

De transactionele leveringen die van de uitvoeringsinstantie worden verzonden worden gesynchroniseerd terug naar de controleinstantie door een technisch werkschema (**[!UICONTROL Message Center execution instance]**) dat elk uur loopt.

>[!NOTE]
>
>De leveringenwekelijkse accumulatie van de gebeurtenissen op basis van de meest recente update van de gebeurtenis en niet op de aanmaakdatum van de gebeurtenis. Daarom wanneer het halen van transactioneel overseinenleveringslogboeken van de controleinstantie, levert identiteitskaart verbonden aan elke identiteitskaart van het leveringslogboek kan in tijd veranderen aangezien het logboek wordt bijgewerkt (bijvoorbeeld, wanneer een binnenkomende stuit voor de gebeurtenis wordt ontvangen).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## Rapportage{#reporting-transactional-msg}

Adobe Campaign biedt verschillende rapporten waarmee u de activiteit en het vloeiend functioneren van uitvoeringsinstanties kunt beheren.

Deze rapporten van het Centrum van Bericht kunnen van **[!UICONTROL Reports]** tabblad van het dialoogvenster **besturingsinstantie**.

![](assets/mc-reports.png)

### Gebeurtenisgeschiedenis van Message Center {#history-events}

De **[!UICONTROL Message Center event history]** het rapport toont een overzicht van de de moduleactiviteit van het Centrum van het Bericht, d.w.z. het aantal gebeurtenissen die als transactionele berichten worden verwerkt en geleverd.

Wanneer het rapport wordt geopend, valt de informatie die door gebrek wordt getoond met het tarief van met succes verzonden transactieberichten. Als u meer niveaus wilt weergeven, kunt u de verschillende knooppunten openen en de cursor op het juiste niveau plaatsen om deze te selecteren.

U kunt de gegevens voor elk gebeurtenistype, per tijdsperiode bekijken. De **[!UICONTROL Events]** de kolom beantwoordt aan het aantal gebeurtenissen die per controleinstantie worden ontvangen. Het aantal gebeurtenissen dat in gepersonaliseerde transactionele berichten wordt omgezet is gedetailleerd in **[!UICONTROL Sent]** kolom.


### Verwerkingstijd van het Berichtencentrum {#processing-time}

De **[!UICONTROL Message Center processing time]** het rapport toont de belangrijkste indicatoren met betrekking tot de echte tijdrij. Dit rapport is ook toegankelijk via de **[!UICONTROL Monitoring]** op de besturingsinstantie.

![](assets/mc-processing-time-report.png)

U kunt ervoor kiezen om algemene statistieken of statistieken met betrekking tot een bepaalde uitvoeringsinstantie weer te geven. U kunt de gegevens ook filteren op kanaal en over een bepaalde periode.

De indicatoren die worden weergegeven in het **[!UICONTROL Indicators over the period]** de sectie wordt berekend over de geselecteerde periode:

* **[!UICONTROL Average queuing time]**: de gemiddelde tijd die met succes gebeurtenissen gebruikte in het Centrum van het Bericht verwerkte. Alleen de verwerkingstijd wordt in aanmerking genomen.
* **[!UICONTROL Average message sending time (s)]**: de gemiddelde tijd die met succes gebeurtenissen gebruikte in het Centrum van het Bericht verwerkte. Alleen de levertijd van de mta wordt in aanmerking genomen.
* **[!UICONTROL Average processing time (s)]**: de gemiddelde tijd die met succes gebeurtenissen gebruikte in het Centrum van het Bericht verwerkte. De berekening neemt de verwerkingstijd in aanmerking en de tijd die de gegevens verzenden.
* **[!UICONTROL Maximum number of queued events]**: maximumaantal gebeurtenissen aanwezig in de rij van het Centrum van het Bericht op om het even welk bepaald ogenblik.
* **[!UICONTROL Minimum number of queued events]**: minimumaantal gebeurtenissen aanwezig in de rij van het Centrum van het Bericht op om het even welk bepaald ogenblik.
* **[!UICONTROL Average number of queued events]**: gemiddeld aantal gebeurtenissen aanwezig in de rij van het Centrum van het Bericht op om het even welk bepaald ogenblik.

>[!NOTE]
>
>De drempelwaarden voor de waarschuwings- (oranje) en waarschuwingsindicator (rood) kunnen worden geconfigureerd in de implementatiewizard van Adobe Campaign. Zie [Monitordrempels](#thresholds).



### Serviceniveau van het Berichtencentrum {#service-level}

De **[!UICONTROL Message Center service level]** het rapport toont de leveringsstatistieken met betrekking tot transactiemeldingen evenals de uitsplitsing van fouten. U kunt op een fouttype klikken om de details ervan weer te geven.

Dit rapport is ook toegankelijk via de **[!UICONTROL Monitoring]** op de besturingsinstantie.

U kunt ervoor kiezen om algemene statistieken of statistieken met betrekking tot een bepaalde uitvoeringsinstantie weer te geven. U kunt de gegevens ook filteren op kanaal en over een bepaalde periode.

De indicatoren die worden weergegeven in het **[!UICONTROL Indicators over the period]** de sectie wordt berekend over de geselecteerde periode:

* **[!UICONTROL Incoming (throughput event/h)]**: gemiddeld aantal gebeurtenissen per uur dat is ingevoerd in de wachtrij van het Berichtencentrum.
* **[!UICONTROL Incoming (event vol)]**: Aantal gebeurtenissen ingegaan in de rij van het Centrum van het Bericht.
* **[!UICONTROL Outgoing (throughput msg/h)]**: gemiddeld uuraantal succesvolle uitgaande gebeurtenissen van het Centrum van het Bericht (verzonden door een levering).
* **[!UICONTROL Outgoing (msg vol)]**: Aantal succesvolle uitgaande gebeurtenissen van het Centrum van het Bericht (verzonden door een levering).
* **[!UICONTROL Average sending time (seconds)]**: gemiddelde tijd die in het Centrum van het Bericht voor met succes verwerkte gebeurtenissen wordt doorgebracht. De berekening neemt de verwerkingstijd in aanmerking en de tijd die de gegevens verzenden.
* **[!UICONTROL Error rate]**: Het aantal gebeurtenissen met fouten in vergelijking met het aantal gebeurtenissen dat de wachtrij van het Berichtencentrum is binnengekomen. Met de volgende fouten wordt rekening gehouden: het verpletteren van fout, verlopen gebeurtenis (gebeurtenis die in de rij te lang is geweest), leveringsfout, genegeerd door de levering (quarantaine, enz.).

>[!NOTE]
>
>De drempelwaarden voor de waarschuwings- (oranje) en waarschuwingsindicator (rood) kunnen worden geconfigureerd in de implementatiewizard van Adobe Campaign. Zie [Monitordrempels](#thresholds).

### Drempels controleren {#thresholds}

U kunt de waarschuwings (oranje) en waakzame (rode) drempels van de indicatoren vormen die in **Serviceniveau van Message Center** en **Verwerkingstijd van Message Center** rapporten.

Volg de onderstaande stappen om dit te doen:

1. Open de implementatiewizard op de **uitvoeringsinstantie** en blader naar de **[!UICONTROL Message Center]** pagina.
1. Gebruik de pijlen om de drempels te veranderen.

   ![](assets/mc-thresholds.png)
