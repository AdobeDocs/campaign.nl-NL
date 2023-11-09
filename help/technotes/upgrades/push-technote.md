---
product: campaign
title: Wijzigingen in pushmeldingskanaal
description: Wijzigingen in pushmeldingskanaal
hide: true
hidefromtoc: true
source-git-commit: 70d1e7336cce7660890b13def5efcb614c0dc12e
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# Wijzigingen in pushmeldingskanaal {#push-upgrade}

Er zijn belangrijke wijzigingen in de FCM-service (Firebase Cloud Messaging) die van invloed kunnen zijn op uw Adobe Campaign Classic-implementatie.

Als onderdeel van de voortdurende inspanningen van Google om haar diensten te verbeteren, zullen de bestaande FCM API&#39;s in juni 2024 worden stopgezet ([HTTP-protocol voor Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/http-server-ref))

Deze API&#39;s zijn momenteel geïntegreerd met Adobe Campaign Classic voor het verzenden van pushberichten. Wij begrijpen dat veel van onze klanten, zoals u, voor uw marketingcampagnes en communicatiebehoeften en vooral voor Android-apparaten op deze services vertrouwen.

## Heeft dit gevolgen voor u?

* **HTTP (Verouderd) API-gebruikers**: Als een van uw actieve pushmeldingscampagnes de HTTP (verouderde) API gebruikt, wordt deze wijziging rechtstreeks van invloed op uw installatie. We raden u ten zeerste aan uw huidige configuraties te bekijken en de migratie naar de nieuwere API&#39;s voor te bereiden.

* **Goed nieuws voor HTTP v1 API-gebruikers**: Als uw installatie uitsluitend de HTTP v1-API voor Android Push-berichten gebruikt, voldoet u al aan de vereisten en hoeft u verder niets te doen.

## Wat doen we?

* **Overgangsplan**: Ons team werkt actief aan de ontwikkeling van een alomvattend overgangsplan. Zo kunt u, indien nodig, uw implementatie bijwerken naar de nieuwere FCM API&#39;s die al beschikbaar zijn in de recente versies van Adobe Campaign en met minimale onderbreking van uw campagnes.

* **Gedetailleerde instructies**: Wij zullen een stapsgewijze gids en andere middelen ter beschikking stellen om een soepel overgangsproces te vergemakkelijken.

* **Ondersteuning**: Ons klantenondersteuningsteam is beschikbaar om u tijdens deze overgang te helpen. We kunnen ook webinars en machtigingssessies organiseren om de technische aspecten en beste praktijken voor de overgang te behandelen.

## Wat verwachten we van u?

* **Op de hoogte blijven**: Houd uw postvak in de gaten voor verdere communicatie van ons, inclusief het gedetailleerde overgangsplan.

* **Huidige instelling controleren**: Neem deze tijd om uw huidige configuratie en aanpassing in Adobe Campaign Classic te bekijken zodat u bereid bent om indien nodig noodzakelijke wijzigingen aan te brengen.

* **Contact opnemen**: Als u directe zorgen hebt of vragen hebt, kunt u contact opnemen met ons ondersteuningsteam.

## Implementatiestappen

In de komende weken zullen we meer details delen over het overgangsplan voor oudere FCM API&#39;s, waaronder tijdlijnen en actiepunten. U kunt ervan op aan dat ons primaire doel is om deze overgang zo naadloos mogelijk te maken voor u en uw team.

Wij waarderen uw zaken en danken u voor uw begrip aangezien wij aan deze veranderingen aanpassen. Uw succes is onze hoogste prioriteit, en wij zijn geëngageerd om u elke stap van de weg te steunen.

U kunt dus vooruitlopen op de wijziging. Hier volgen de algemene stappen die nodig zijn om uw pushconfiguratie te migreren van HTTP (Verouderd) naar de FCM HTTPv1-API.

### Buildupgrade

* Campaign Classic: de ondersteuning van HTTPv1 is toegevoegd in versie 20.3.1. Als u een vorige versie gebruikt, moet u eerst aan de recentste bouwstijl van het Campaign Classic bevorderen.

* Campagne v8: HTTPv1 wordt ondersteund door alle Campagne v8-releases. Geen upgrade nodig.

### Marketingsserver

De veranderingen van de configuratie kunnen door de klant/de partner worden uitgevoerd.

1. Eerst moet u het JSON-bestand uitpakken. Het JSON-bestand van de Firebase Admin SDK-service is nodig om de mobiele toepassing naar HTTPv1 te verplaatsen. Zie dit [page](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. Ga naar uw lijst met **Services en abonnementen**.

1. Zoek alle mobiele toepassingen met behulp van de HTTP (verouderde) API-versie.

1. Stel voor elk van deze mobiele toepassingen de optie **API-versie** naar HTTPv1 en volg de configuratie-instructies die in het dialoogvenster [documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

>[!NOTE]
>
>Bij nieuwe leveringen wordt rekening gehouden met de overgang naar de HTTPv1-API. Leveringen in retry, in uitvoering en in gebruik zullen nog steeds de HTTP (legacy) API gebruiken.

### Midden-bronserver

Er zijn geen wijzigingen vereist.

### Uitvoeringsserver in realtime

Hiervoor moet u contact opnemen met Adobe Campaign-ondersteuning. De migratieprocedure is het zelfde als voor de marketing server.

### Android-besturingssysteem en Android Mobile-toepassing

Er zijn geen specifieke wijzigingen vereist in de code van de Android Mobile-toepassingen en het meldingsgedrag moet niet worden gewijzigd.

Toch introduceert HTTPv1 drie nieuwe payload-elementen:

| Naam | Standaardwaarde |
|---|---|
| kleverig | Onwaar |
| prioriteit | Standaard |
| zichtbaarheid | Onwaar |
| kleverig | Persoonlijk |
