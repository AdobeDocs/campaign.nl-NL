---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3bc247ba81de3de56c26bdf8fa9b8aa5ea91fb2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---

# Laatste versies {#latest-release}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met Campagne v8 (console) **&#x200B;**&#x200B;komen meest recente versies. Leer meer over de versies, versies, en verbeteringen van de Campagne in [&#x200B; deze pagina &#x200B;](upgrades.md). Andere versies worden vermeld in de sectie Vorige releases van deze documentatie.

## Release 8.8.2 {#release-8-8-2}

_9 okt, 2025_

>[!AVAILABILITY]
>
>Deze versie is in **Beperkte Beschikbaarheid** (LA).

### Nieuwe functies {#features-8-8-2}

Het **nieuwe SMS verzenden schakelaar** is nu beschikbaar voor [&#x200B; Plaatsingen FFDA van de Campagne &#x200B;](../architecture/enterprise-deployment.md). Verwijs naar de [&#x200B; gedetailleerde documentatie &#x200B;](../send/sms/sms.md).

Deze versie wordt ook geleverd met een set functies die beschikbaar zijn in de gebruikersinterface van Campagne Web:

* [&#x200B; de Verrijking van het Profiel in Transactionele Berichten &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=nl-NL){target="_blank"}
* [&#x200B; Meertalige Mogelijkheden voor Transactioneel Overseinen, de Berichten van de Duw en SMS &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=nl-NL){target="_blank"}

Verwijs naar UI van het Web van de Campagne [&#x200B; versienota&#39;s &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=nl-NL){target="_blank"}

### Oplossingen {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* Probleem verholpen waarbij de workflow voor het opschonen van databases kon mislukken. (NEO-87949)
* Probleem verholpen met Distributed Marketing waarbij geen trackinggegevens werden geregistreerd voor gezamenlijke campagneleveringen. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* Probleem verholpen waarbij de personalisatie in fragmenten niet correct werkte. (NEO-88161)
* Probleem verholpen na het migreren naar de nieuwe ODBC-connector voor opnieuw toewijzen, wat ertoe kan leiden dat de activiteit van de gesplitste workflow met SQL-fouten mislukt. (NEO-87466)
* Probleem verholpen waarbij onjuiste aantallen uitsluitingen in workflows konden worden veroorzaakt. (NEO-89207)
* Probleem verholpen waarbij onjuiste klikindicatoren voor pushberichten konden worden veroorzaakt. (NEO-89503)
* Probleem verholpen waarbij de SMS-leveringslogs niet correct werden bijgewerkt, waardoor een juiste statusrapportage in Adobe Campaign werd voorkomen. (NEO-88479)
* Probleem verholpen waarbij Franse aanhalingstekens onjuist werden geconverteerd naar Engelse aanhalingstekens in bezorginhoud. (NEO-89631)
* Probleem verholpen waarbij de Real-Time Server in plaats daarvan een onjuiste antwoordcode voor ongeldige IMS-tokens heeft geretourneerd. (NEO-87428)
* Probleem verholpen waarbij de leveringsstatistieken voor e-mail en SMS niet volledig opnieuw werden berekend, wat tot onjuiste succesindicatoren leidde. (NEO-88106)
* Probleem verholpen met de nieuwe SMS-verzendende connector waarbij leveringslogboeken ten onrechte de leveringsstatus voor een kleine subset berichten toewezen. (NEO-89581)
* Probleem verholpen met de nieuwe SMS-verzendende connector, waarbij de gegevens over geslaagde levering van T-Mobile niet correct werden bijgewerkt op zowel de marketing- als de midserver. (NEO-89850)
* Oplossing voor een synchronisatieprobleem tussen de Real-Time en Marketing-instanties dat tot ontbrekende trackinglogbestanden en onjuiste rapportage leidde. (NEO-90247)
* Probleem verholpen met een workflowverrijking die fouten kan veroorzaken bij het selecteren van velden in twee opeenvolgende 1-N koppelingen in aangepaste schema&#39;s. (NEO-87682)

