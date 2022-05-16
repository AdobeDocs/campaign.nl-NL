---
title: Aan de slag met de campagnearchitectuur
description: Omgevingen en de basis van implementatie ontdekken
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Aan de slag met de campagnearchitectuur{#gs-ac-archi}

## Omgevingen

Campagne wordt beschikbaar gesteld als individuele instanties waarbij elke instantie een volledige omgeving van de Campagne vertegenwoordigt.

Drie soorten omgevingen beschikbaar met Campagne Cloud Service:

* **Productieomgeving**: gastheren de toepassingen voor de bedrijfsartsen.

* **Stage-omgeving**: worden gebruikt voor verschillende prestatie- en kwaliteitstests voordat wijzigingen in de toepassing worden doorgevoerd in de productieomgeving.

* **Ontwikkelingsomgeving**: Hiermee kunnen ontwikkelaars campagne implementeren onder dezelfde runtimevoorwaarden als de stadium- en productieomgeving.

U kunt pakketten van de ene omgeving naar de andere exporteren en importeren.

![](../assets/do-not-localize/book.png) Meer informatie over pakketten in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Midsourcingimplementatie{#mid-sourcing-deployment}

De algemene communicatie tussen servers en processen wordt uitgevoerd volgens het volgende schema:

![](assets/architecture.png)

* De uitvoerings en stuitbeheersmodules zijn onbruikbaar gemaakt op de instantie.

* De toepassing wordt gevormd om berichtuitvoering op een verre &quot;midsourced&quot;server uit te voeren die gebruikend de vraag van de ZEEP (over HTTP of HTTPS) wordt gedreven.

>[!NOTE]
>
> Campagne v8 is gebaseerd op een hybride architectuur. Als u van Campaign Classic v7 overgaat, merk op dat alle leveringen door de midsourcingserver gaan.
> Als gevolg hiervan is interne routering **niet mogelijk** in Campagne v8 en de externe account is dienovereenkomstig uitgeschakeld.

## Berichtencentrum{#transac-msg-archi}

Transactioneel overseinen (het Centrum van het Bericht) is de module van de Campagne die voor het beheren van trekkerberichten wordt ontworpen.

![](../assets/do-not-localize/glass.png) Meer informatie over het verzenden van transactieberichten in [deze sectie](../send/transactional.md).

Als reactie op een actie van een klant op een website, wordt een gebeurtenis verzonden Campagne door REST API, en het berichtmalplaatje wordt bevolkt met de informatie of de gegevens die door de API vraag worden verstrekt, en een transactiebericht wordt verzonden in real time naar de klant. Deze berichten kunnen individueel of in partijen via e-mail, SMS of push-berichten worden verzonden.

In deze specifieke architectuur, wordt de uitvoeringscel gescheiden van de controleinstantie om hoge beschikbaarheid en ladingsbeheer te verzekeren.

* De **Control-instantie** (of marketinginstantie) wordt door marketers en IT-teams gebruikt om berichtsjablonen te maken, te configureren en te publiceren. Deze instantie centraliseert ook gebeurteniscontrole en geschiedenis.

   ![](../assets/do-not-localize/glass.png) Meer informatie over het maken en publiceren van berichtsjablonen in [deze sectie](../send/transactional.md).

* De **Uitvoeringsinstantie** treitert binnenkomende gebeurtenissen (bijvoorbeeld opnieuw instellen van wachtwoord of bestellingen van een website) op en stuurt gepersonaliseerde berichten. Er kunnen meer dan één uitvoeringsinstantie zijn om berichten te verwerken via het taakverdelingsmechanisme en het aantal gebeurtenissen te schalen dat moet worden uitgevoerd voor maximale beschikbaarheid.

>[!CAUTION]
>
>De bedieningsinstantie en de uitvoeringsinstantie(s) moeten op verschillende computers zijn geïnstalleerd. Ze kunnen niet dezelfde Campagne-instantie delen.

![](assets/messagecenter_diagram.png)

### Verificatie

Om deze mogelijkheden te gebruiken, de gebruikers van Adobe Campaign login aan de controleinstantie om transactionele berichtmalplaatjes tot stand te brengen, de berichtvoorproef te produceren gebruikend een zaadlijst, vertoningsrapporten en controle uitvoeringsinstantie(s).

* Één enkele uitvoeringsinstantie wanneer het in wisselwerking staan met een Adobe ontvangen de uitvoeringsinstantie van het Centrum van het Bericht, kan een extern systeem een zittingsteken eerst terugwinnen (dat door gebrek in 24 uren) verloopt, door een api vraag aan de methode van de zittingsopening van een sessie te maken, gebruikend een verstrekt rekeningslogin en wachtwoord.
Dan, met sessionToken die door de uitvoeringsinstantie in antwoord op de bovengenoemde vraag wordt verstrekt, kan de externe toepassing BEEP api aanroepen (rtEvents of batchEvents) maken om mededelingen te verzenden, zonder de behoefte om in elke vraag van de ZEEP de rekeningslogin en het wachtwoord te omvatten.

* Meerdere uitvoeringsinstanties In een architectuur met meerdere cellen voor uitvoering met meerdere uitvoeringsinstanties achter een taakverdelingsmechanisme, gaat de openings van een sessiemethode die door de externe toepassing wordt aangeroepen door het taakverdelingsmechanisme: daarom kan een tokengebaseerde verificatie niet worden gebruikt. Een op gebruiker/wachtwoord-gebaseerde authentificatie wordt vereist.

![](../assets/do-not-localize/book.png) Meer informatie over Transactionele berichtengebeurtenissen in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)