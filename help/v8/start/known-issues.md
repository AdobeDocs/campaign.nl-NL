---
title: Bekende problemen in de campagne v8
description: Bekende problemen in de nieuwste campagnerelease
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 099d14ace04df1b98e03be283a6436f49f535958
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Bekende problemen{#known-issues}

Deze pagina bevat een lijst met bekende problemen die zijn geïdentificeerd in het dialoogvenster **nieuwste release Campagne v8**. Bovendien worden de beperkingen die bij Campagne v8 worden geleverd, vermeld [op deze pagina](known-limitations.md).


>[!NOTE]
>
>Adobe publiceert deze lijst met bekende problemen naar eigen goeddunken. Het is gebaseerd op het aantal klantenrapporten, de strengheid, en de tijdelijke beschikbaarheid. Als een probleem dat u tegenkomt niet in de lijst voorkomt, voldoet het mogelijk niet aan de criteria voor publicatie op deze pagina.

## Probleem met gegevensbronactiviteit wijzigen {#issue-1}

### Beschrijving

De **Gegevensbron wijzigen** De activiteit ontbreekt wanneer het overbrengen van gegevens van lokale gegevensbestand van de Campagne aan Snowflake wolkengegevensbestand. Wanneer het schakelen van richtingen, kan de activiteit kwesties produceren.

### Reproductiestappen

1. Maak verbinding met de clientconsole en maak een workflow.
1. Voeg een **Query** en **Gegevensbron wijzigen** activiteit.
1. Definieer een query op het tabblad **email**, wat een tekenreeks is.
1. Voer de workflow uit en klik met de rechtermuisknop op de overgang om de populatie weer te geven: de e-mailrecords worden vervangen door `****`.
1. Controleer de workflowlogboeken: de **Gegevensbron wijzigen** activiteit interpreteert deze verslagen als numerieke waarden.

### Workaround

Om de gegevens te hebben die van de de wolkengegevensbestand van Snowflake naar de lokale gegevensbestand van de Campagne en terug naar Snowflake worden overgebracht, moet u twee verschillende gebruiken **Gegevensbron wijzigen** activiteiten.

### Interne referentie

Referentie: NEO-45549


## Actie voor het laden van gegevens (bestand) is mislukt. Bestand wordt geüpload naar de server {#issue-2}

### Beschrijving

Het uploaden van bestanden naar de Campagneserver stopt bij 100% voortgang maar eindigt nooit.

### Reproductiestappen

1. Maak verbinding met de clientconsole en maak een workflow.
1. Voeg een **Gegevens laden (bestand)** activiteit en vorm het.
1. Selecteer **Uploaden op server** optie.
1. Selecteer het bestand op uw lokale computer.
1. Klikken **Uploaden**

### Workaround

Geen

### Interne referentie

Referentie: NEO-47269