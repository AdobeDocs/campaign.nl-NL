---
title: Werken met campagne en uw CRM
description: Leer hoe te met Campagne en uw CRM werken
feature: Salesforce Integration, Microsoft Integration
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 17%

---

# Sluit uw CRM aan Campagne aan {#gs-crm}

Adobe Campaign biedt verschillende CRM-connectoren waarmee u uw Adobe Campaign-platform kunt koppelen aan systemen van derden. Deze CRM-connectoren laten u toe om contactpersonen, accounts, aankopen, enzovoort, te synchroniseren. Ze zorgen ervoor dat uw applicatie eenvoudig kan worden geïntegreerd met verschillende externe en zakelijke applicaties.

Deze connectors maken snelle en eenvoudige gegevensintegratie mogelijk: Adobe Campaign verstrekt een specifieke medewerker voor het verzamelen van en het selecteren van uit de lijsten beschikbaar in CRM. Dit garandeert tweerichtingssynchronisatie om ervoor te zorgen dat de data altijd up-to-date zijn in alle systemen.

Belangrijkste voordelen zijn:

* Consistent overseinen tussen verkoop en marketing: de integratie van Adobe Campaign met uw CRM verleent zowel systeemtoegang tot klanteninzicht als e-mailmarketing geschiedenis die alle berichten aan de klant toestaat om het zelfde verenigbare overseinen te delen.

* Holistische mening van alle vooruitzichten en klantengegevens: door Adobe Campaign te integreren met uw CRM, is het mogelijk om e-mailmarketinggeschiedenis te delen en te openen op elk contact vanuit het CRM-systeem.

* Activeer uw CRM-gegevens op elk kanaal: Als contactgegevens zijn gesynchroniseerd met Adobe Campaign, kunnen communicatie via elk online of offline kanaal worden verzonden met Campagne, zoals mobiele push, in-app, e-mail of direct mail.


>[!NOTE]
>
>Deze functie is beschikbaar in Adobe Campaign via de **CRM-connectors** toegewezen pakket.

## Compatibele systemen {#compatible-crm-systems-and-limitations}

Ondersteunde CRM&#39;s en versies worden in de campagne gedetailleerd weergegeven [Compatibiliteitsmatrix](../start/compatibility-matrix.md).

>[!CAUTION]
>
> Campagne CRM-connectors werken alleen met een beveiligde URL (https).

## Implementatiestappen {#crm-implementation-steps}

Leer geleidelijke procedure om Campagne en de Dynamica van Microsoft in te verbinden [deze pagina](ac-ms-dyn.md).

Leer geleidelijke procedure om Campagne en Salesforce.com in te sluiten [deze pagina](ac-sfdc.md).

Gegevenssynchronisatie tussen Adobe Campaign en de CRM wordt uitgevoerd via een specifieke workflowactiviteit. Bouw uw werkschema&#39;s om synchronisatie tussen Campagne en uw CRM te automatiseren. U kunt een werkschema tot stand brengen dat de contacten via de Dynamica van Microsoft invoert, hen synchroniseert met de bestaande gegevens van Adobe Campaign, dubbele contacten schrapt, en dan het gegevensbestand van Adobe Campaign bijwerkt. Meer informatie in [deze pagina](crm-data-sync.md).
