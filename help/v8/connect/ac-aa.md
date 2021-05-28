---
solution: Campaign v8
product: Adobe Campaign
title: Werken met campagne en Adobe Analytics
description: Leer hoe u kunt werken met Campagne en Adobe Analytics
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 2%

---

# Werken met campagne en Adobe Analytics


## Adobe Analytics Connector

U kunt Adobe Analytics-connectors configureren om campagne en analyse te integreren.

Met Adobe Analytics Connector kunnen Adobe Campaign en Adobe Analytics communiceren via de **Web Analytics-connectors** add-on. Deze integratie deelt gegevens van Analytics aan Campagne als segmenten met betrekking tot gebruikersgedrag na een e-mail. Omgekeerd verzendt het programma indicatoren en kenmerken van e-mailcampagnes die door Adobe Campaign worden geleverd aan Adobe Analytics - Gegevensconnector.

Met Adobe Analytics Connector kan Adobe Campaign het internetpubliek meten (Web Analytics). Dankzij deze integratie kan Adobe Campaign na een marketingcampagne gegevens over het gedrag van bezoekers van een of meer sites herstellen en (na analyse) hermarketingcampagnes voeren om deze in kopers om te zetten. Omgekeerd, laten de analytische hulpmiddelen van het Web Adobe Campaign toe om indicatoren en campagneattributen aan hun platforms door te sturen.

De actievelden voor elk gereedschap zijn als volgt:

* **Adobe Analytics**

   * markeert de e-mailcampagnes die met Adobe Campaign zijn gestart
   * bespaart ontvankelijk gedrag, op de plaats zij na het klikken van campagne e-mail, in de vorm van segmenten doorbladeden. Segmenten houden verband met verlaten producten (bekeken maar niet toegevoegd aan het winkelwagentje of aangeschaft), aankopen of winkelen.

* **Adobe Campaign**

   * verzendt de indicatoren en campagnerekenmerken naar de schakelaar, die hen aan het analytische hulpmiddel van het Web terugstuurt
   * herstelt en analyseert segmenten
   * leidt tot een hermarketing campagne

Meer informatie over Adobe Campaign en Adobe Analytics vindt u op [deze pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html)

[!DNL :speech_balloon:]  Als gebruiker van Beheerde Cloud Services,  [contacteer ](../start/campaign-faq.md#support) Adobe om de Verbinding van Gegevens van Adobe Analytics met Campagne te integreren.


## Experience Cloud Triggers

U kunt Experience Cloud Triggers gebruiken om gegevens tussen Adobe Campaign en Adobe Analytics te verbinden gebruikend de pijpleiding. De pijplijn haalt de acties van de gebruiker of trekkers van uw website terug. Een achterlating van een winkelwagen is een voorbeeld van een trigger. Triggers worden in Adobe Campaign verwerkt om e-mails in bijna real-time te verzenden.

Meer informatie over Adobe Campaign en Experience Cloud Triggers vindt u op [deze pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en).

[!DNL :speech_balloon:]  Als Beheerde gebruiker van Cloud Services,  [contacteer ](../start/campaign-faq.md#support) Adobe om de trekkers van Experience Cloud met Campagne uit te voeren.
