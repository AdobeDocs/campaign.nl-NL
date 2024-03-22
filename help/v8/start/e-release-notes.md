---
title: Opmerkingen bij de release Vroege campagne v8
description: release van Early Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 5%

---

# Vroege aanvullende informatie {#e-new-release}

Op deze pagina vindt u een beschrijving van de verbeteringen en correcties die zijn opgenomen in de volgende versie van Campagne v8. Deze inhoud kan tot de releasedatum zonder voorafgaande kennisgeving worden gewijzigd. De officiële opmerkingen bij de release zijn beschikbaar in deze [page](../start/release-notes.md).

## Release 8.6.1 {#release-8-6-1}

_14 feb. 2024_


### Nieuwe functies {#new-8-6-1}

* Vanaf deze release hebt u toegang tot de nieuwe **Gebruikersinterface Campagne Web**, beschikbaar via de centrale Adobe Experience Cloud-omgeving. Experience Cloud is de geïntegreerde familie van digitale marketingtoepassingen, producten en diensten van de Adobe. Via de intuïtieve interface hebt u snel toegang tot uw cloudtoepassingen, productfuncties en services. Leer hoe u verbinding maakt met Adobe Experience Cloud en toegang krijgt tot de Adobe Campaign Web Interface [op deze pagina](campaign-ui.md#ac-web-ui).

* De 32-bits versie van de clientconsole is nu vervangen. Vanaf 8.6 is de clientconsole alleen beschikbaar in 64 bits. De upgrade naar de 64-bits versie van de clientconsole is naadloos. Raadpleeg voor meer informatie over het upgraden van uw besturingssysteem [technote](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html){target="_blank"}.


### Algemene verbeteringen {#improvements-8-6-1}

* Campagne v8.6 zorgt voor verbeterde doorvoer voor **e-mailvolgindicatoren voor leveringen**. Met onze geoptimaliseerde processen wordt de opname- en computertijd minder lang en kunt u de belangrijkste indicatoren voor de levering veel sneller controleren.

* U kunt nu uw Campagne v8 instantie met uw Azure synapse externe gegevensbestand verbinden. Deze verbinding wordt beheerd via een nieuw extern account.

* Adobe Campaign v8 kan nu worden geïntegreerd met **Adobe Experience Manager as a Cloud Service**, waarbij het ontwerpen uitsluitend beschikbaar is via de Adobe Campaign Web User Interface.

* U kunt nu uw **Adobe Experience Manager Assets-bibliotheek** naast uw Experience Cloud Assets, zelfs als de **Integratie met de Adobe Experience Cloud** is geïnstalleerd op uw Adobe Campaign-exemplaar.

* U kunt geen operatoren meer maken vanaf de clientconsole. U moet nu de Admin Console gebruiken. [Meer informatie](../start/gs-permissions.md).

* Verschillende hulpmiddelen van derden zijn bijgewerkt om de beveiliging te optimaliseren.

### Leverbaarheid-updates {#deliverability-8-6-1}

* Tegen februari 2024 verzendt een bedrijf meer dan 5000 e-mailberichten via Google of Yahoo! zal moeten beginnen gebruikend een authentificatietechnologie die als op domein-gebaseerde Rapportering en Conformiteit van de Authentificatie van het Bericht (DMARC) wordt bekend. Zorg ervoor dat DMARC-record is ingesteld voor alle subdomeinen die u gebruikt met Adobe Campaign. [Meer informatie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=nl){target="_blank"}

* Vanaf 1 juni 2024, Google en Yahoo! voldoen aan uitschrijven met één klik voor lijsten. Adobe Campaign biedt nu ondersteuning voor deze optie. [Meer informatie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Oplossingen {#fixes-8-6-1}

De volgende kwesties zijn in deze release vastgelegd: NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-6387, NEO-632 94, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-6 1199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, O-50488, NEO-47789