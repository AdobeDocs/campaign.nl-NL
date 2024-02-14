---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 2f8cee4522efb59782a568334fc1300fc39d559f
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 2%

---

# Nieuwste release{#latest-release}

Adobe Campaign wordt regelmatig bijgewerkt. Deze regelmatige frequentie van updates is bedoeld om de nieuwste en beste in uw handen te krijgen, uw omgeving veilig te houden en uw ervaring met ons product te verbeteren. Adobe raadt alle klanten ten zeerste aan een upgrade uit te voeren naar de nieuwste versie. Meer informatie over campagneversies en aanbevelingen [op deze pagina](upgrades.md).

Als Beheerde gebruiker van Cloud Servicen, wordt uw instantie bevorderd door Adobe met elke nieuwe versie. Adobe zal contact met u opnemen en uw omgevingen upgraden. Campagne-clientconsole **moet worden geüpgraded naar dezelfde versie** als Campagneservers. Leer hoe u uw clientconsole in deze [page](../start/connect.md#upgrade-ac-console).

Als klant moet u er bovendien voor zorgen dat u de meest recente ondersteunde versies van de systemen gebruikt die in de [Compatibiliteitsmatrix](compatibility-matrix.md).


## Release 8.6.1 {#release-8-6-1}

_14 feb. 2024_


### Nieuwe functies {#new-8-6-1}

* Vanaf deze release hebt u toegang tot de nieuwe **Gebruikersinterface Campagne Web**, beschikbaar via de centrale Adobe Experience Cloud-omgeving. Experience Cloud is de geïntegreerde familie van digitale marketingtoepassingen, producten en diensten van de Adobe. Via de intuïtieve interface hebt u snel toegang tot uw cloudtoepassingen, productfuncties en services. Leer hoe u verbinding maakt met Adobe Experience Cloud en toegang krijgt tot de Adobe Campaign Web Interface [op deze pagina](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 kan nu worden geïntegreerd met **Adobe Experience Manager as a Cloud Service**, waarbij het ontwerpen uitsluitend beschikbaar is via de Adobe Campaign Web User Interface. [Meer informatie](../connect/ac-aem.md)

* U kunt nu uw **Adobe Experience Manager Assets-bibliotheek** naast uw Experience Cloud Assets, zelfs als het Integration with the Adobe Experience Cloud package op uw Adobe Campaign-exemplaar is geïnstalleerd. [Meer informatie](../connect/ac-aem.md#assets-library)

### Algemene verbeteringen {#improvements-8-6-1}

* Campagne v8.6 zorgt voor verbeterde doorvoer voor **e-mailvolgindicatoren voor leveringen**. Met onze geoptimaliseerde processen wordt de opname- en computertijd minder lang en kunt u de belangrijkste indicatoren voor de levering veel sneller controleren.


### Leverbaarheid-updates {#deliverability-8-6-1}

* Tegen februari 2024 verzendt een bedrijf meer dan 5000 e-mailberichten via Google of Yahoo! zal moeten beginnen gebruikend een authentificatietechnologie die als op domein-gebaseerde Rapportering en Conformiteit van de Authentificatie van het Bericht (DMARC) wordt bekend. Zorg ervoor dat DMARC-record is ingesteld voor alle subdomeinen die u gebruikt met Adobe Campaign. [Meer informatie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=nl){target="_blank"}

* Vanaf 1 juni 2024, Google en Yahoo! afzenders moeten voldoen aan lijst-abonnement met één klik. Adobe Campaign biedt nu ondersteuning voor deze optie. [Meer informatie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Oplossingen {#fixes-8-6-1}

De volgende kwesties zijn in deze release vastgelegd: NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-6387, NEO-632 94, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-6 1199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, O-50488, NEO-47789