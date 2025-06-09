---
product: campaign
title: Technische opmerking - Referentiegids voor rotatie
description: Adobe Campaign Technical Note - Credential Rotation Guide
hide: true
hidefromtoc: true
exl-id: 0848ee2d-3506-4167-9aea-a1589aa82805
source-git-commit: 14e49a0b4de1b82239113bd670213449f464c27f
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Technische opmerking: Referentiegids voor rotatie {#ac-customer-credentials}

Als klant, bent u verantwoordelijk voor het vervangen van uw geloofsbrieven door een nieuwe reeks periodiek om het risico van compromis te verlichten.

## Referenties Adobe Campaign-opties {#ac-options-credentials}

Van de Ontdekkingsreiziger van Adobe Campaign, staat het **Beleid > Platform > de knoop van Opties** u toe om veranderingen in de opties van Adobe Campaign aan te brengen. Als u enkele gegevens hier hebt opgeslagen, moet u deze roteren.

![](assets/technote-2.png)

## Referenties externe account {#ac-accounts-credentials}

Het **Beleid > Platform > de Externe knoop van Rekeningen** staat u toe om wijzigingen in de externe rekeningen van Adobe Campaign aan te brengen.

Roteer al uw referenties die u hebt opgeslagen in de externe accounts.

>[!CAUTION]
>
>**wijzigt niet** de Adobe beheerde geloofsbrieven. Externe accounts met een `adobe` verwante server mogen niet worden gewijzigd.

![](assets/technote-1.png)

Voor de specifieke technische operatoren `mc*` (bv. mc1, mc2, enz.) en `Interaction*` (bv. interactie1, interactie2, enz.) kan een van de volgende twee methoden worden gevolgd:

1. Adobe kan de referenties voor dergelijke operatoren wijzigen en deze met u delen. Houd er rekening mee dat alle integratie met deze operatoren stopt met werken totdat de gegevens voor deze operatoren aan uw zijde worden bijgewerkt.

1. Adobe kan **nieuwe** exploitanten tot stand brengen die aan elke bestaande exploitanten beantwoorden en hen met u delen. Adobe verwijdert alle instanties van oude operatoren nadat u naar deze nieuwe operatoren bent overgeschakeld.


## Persoonlijke sleutel/certificaat voor mobiele services  {#ac-key-credentials}

Raadpleeg de onderstaande koppelingen voor rotatie van de mobiele services met betrekking tot persoonlijke sleutels en certificaten.

* Voor Android, verwijs naar [ deze documentatie ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android){target="_blank"}.
Blader naar **creeer de mobiele toepassing van Android > vorm de API versie** sectie.

* Voor iOS, verwijs naar [ deze documentatie ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application){target="_blank"}.
Blader aan **Create iOS mobiele app->de wijze van de Authentificatie** sectie.

## GPG-toetsen {#ac-gpg-credentials}

Voor het roteren van GPG sleutels, moeten de volgende stappen worden gevolgd:

1. Decoderen van de bestaande gegevens met de bestaande sleutel. [Meer informatie](https://experienceleague.adobe.com/en/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Maak een nieuw GPG-sleutelpaar. Leer meer over GPG zeer belangrijk beheer in [ deze documentatie ](https://experienceleague.adobe.com/en/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Vervang het bestaande gebruik van de GPG-sleutel in alle workflows door de nieuwe sleutel.

1. Verwijder de bestaande GPG-sleutel.
