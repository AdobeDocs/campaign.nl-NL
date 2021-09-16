---
title: Werken met campagne en uw CRM
description: Leer hoe te met Campagne en uw CRM werken
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 22%

---

# Sluit uw CRM aan Campagne aan {#gs-crm}

Adobe Campaign biedt verschillende CRM-connectoren waarmee u uw Adobe Campaign-platform kunt koppelen aan systemen van derden. Deze CRM-connectoren laten u toe om contactpersonen, accounts, aankopen, enzovoort, te synchroniseren. Ze zorgen ervoor dat uw applicatie eenvoudig kan worden geïntegreerd met verschillende externe en zakelijke applicaties.

Deze connectors maken snelle en eenvoudige gegevensintegratie mogelijk: Adobe Campaign verstrekt een specifieke medewerker voor het verzamelen van en het selecteren van uit de lijsten beschikbaar in CRM. Dit garandeert tweerichtingssynchronisatie om ervoor te zorgen dat de data altijd up-to-date zijn in alle systemen.

>[!NOTE]
>
>Deze functie is beschikbaar in Adobe Campaign via het speciale pakket **CRM-connectors**.

## Compatibele systemen {#compatible-crm-systems-and-limitations}

Ondersteunde CRM&#39;s en versies worden beschreven in Campagne [Compatibiliteitsmatrix](../start/compatibility-matrix.md).

?? De CRM-connectors werken alleen met een beveiligde URL (https).

## Implementatiestappen {#crm-implementation-steps}

↗️ Leer geleidelijke procedure om Campagne en de Dynamica van Microsoft in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps) te verbinden

↗️ Leer geleidelijke procedure om Campagne en Salesforce in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started) aan te sluiten


Gegevenssynchronisatie tussen Adobe Campaign en de CRM wordt uitgevoerd via een specifieke workflowactiviteit. Bouw uw werkschema&#39;s om synchronisatie tussen Campagne en uw CRM te automatiseren. U kunt een werkschema tot stand brengen dat de contacten via de Dynamica van Microsoft invoert, hen synchroniseert met de bestaande gegevens van Adobe Campaign, dubbele contacten schrapt, en dan het gegevensbestand van Adobe Campaign bijwerkt.

↗️ Meer informatie in de [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)
