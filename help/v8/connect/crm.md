---
title: Werken met campagne en uw CRM
description: Leer hoe te met Campagne en uw CRM werken
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 19%

---

# Sluit uw CRM aan Campagne aan {#gs-crm}

Adobe Campaign biedt verschillende CRM-connectoren waarmee u uw Adobe Campaign-platform kunt koppelen aan systemen van derden. Deze CRM-connectoren laten u toe om contactpersonen, accounts, aankopen, enzovoort, te synchroniseren. Ze zorgen ervoor dat uw applicatie eenvoudig kan worden geïntegreerd met verschillende externe en zakelijke applicaties.

Deze schakelaars laten snelle en gemakkelijke gegevensintegratie toe: Adobe Campaign verstrekt een specifieke medewerker voor het verzamelen van en het selecteren van uit de lijsten beschikbaar in CRM. Dit garandeert tweerichtingssynchronisatie om ervoor te zorgen dat de data altijd up-to-date zijn in alle systemen.

Belangrijkste voordelen zijn:

* Consistent overseinen tussen verkoop &amp; marketing: de integratie van Adobe Campaign met uw CRM geeft zowel systeemtoegang tot klant insight als e-mailmarketing geschiedenis die alle berichten aan de klant toestaat om het zelfde verenigbare overseinen te delen.

* Holistische weergave van alle perspectiefgegevens en klantgegevens: door Adobe Campaign te integreren met uw CRM, is het mogelijk om e-mailmarketinggeschiedenis te delen en te openen voor elk contact vanuit het CRM-systeem.

* Activeer uw CRM-gegevens op elk kanaal: met contactgegevens die zijn gesynchroniseerd met Adobe Campaign, kunnen communicatie via elk online of offline kanaal worden verzonden met Campagne, waaronder mobiele push, in-app, e-mail of direct mail.


>[!NOTE]
>
>Deze eigenschap is beschikbaar in Adobe Campaign door het **specifieke pakket 1&rbrace; van de schakelaars van CRM**.

## Compatibele systemen {#compatible-crm-systems-and-limitations}

De gesteunde CRM en de versies zijn gedetailleerd in de matrijs van de Verenigbaarheid van de Campagne [&#128279;](../start/compatibility-matrix.md).

>[!CAUTION]
>
> Campagne CRM-connectors werken alleen met een beveiligde URL (https).

## Implementatiestappen {#crm-implementation-steps}

Leer geleidelijke procedure om Campagne en Microsoft Dynamics in [ te verbinden deze pagina ](ac-ms-dyn.md).

Leer geleidelijke procedure om Campagne en Salesforce.com in [ te verbinden deze pagina ](ac-sfdc.md).

Gegevenssynchronisatie tussen Adobe Campaign en de CRM wordt uitgevoerd via een specifieke workflowactiviteit. Bouw uw werkschema&#39;s om synchronisatie tussen Campagne en uw CRM te automatiseren. U kunt een werkschema tot stand brengen dat de contacten via Microsoft Dynamics invoert, hen synchroniseert met de bestaande gegevens van Adobe Campaign, dubbele contacten schrapt, en dan het gegevensbestand van Adobe Campaign bijwerkt. Meer informatie vindt u [op deze pagina](crm-data-sync.md).
