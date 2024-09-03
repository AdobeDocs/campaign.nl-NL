---
title: SMS verzenden met Adobe Campaign
description: Aan de slag met SMS in de campagne
feature: SMS
role: User, Data Engineer
level: Beginner
badge: label="Beperkte beschikbaarheid" type="Informative"
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 4%

---

# Aan de slag met sms {#gs-sms-channel}

Gebruik Adobe Campaign om persoonlijke SMS-berichten te verzenden.

>[!IMPORTANT]
>
>Deze documentatie is voor Adobe Campaign v8.7.2 en hoger.
>
>Voor oudere versies, gelieve de [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up) te lezen.

>[!NOTE]
>
>Adobe Campaign laat u ook dupberichten op mobiles, via zijn **Adobe Campaign Mobiele App Kanaal (NMAC)** optie voorleggen. Lees meer in [deze sectie](../push.md).

De eenvoud en het gemak van het gebruik van SMS maken het een zeer waardevol communicatiekanaal naast zijn robuustheid en ongeëvenaarde verenigbaarheid over miljarden terminals.

Er zijn twee manieren om een SMS-bericht te verzenden:

* Verzend het manueel van een telefoon. Dat is de gebruikelijke manier om rechtstreeks tussen mensen te communiceren.
* Verzend het van Internet. Dat is de manier waarop Adobe Campaign berichten verzendt. Hiervoor hebt u een SMS-serviceprovider nodig die een brug maakt van internet naar het mobiele netwerk.

U kunt in deze documentatie de stappen zien om een levering van SMS te vormen, te verzenden en te controleren:

* **Sms-kanaal configureren**

Eerst, moet u het kanaal van SMS op uw [ midsourcing infrastructuur ](sms-mid-sourcing.md) vormen.

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

Voor deze configuratie, moet u de [ SMPP externe accountparameters ](smpp-external-account.md) en de [ het kanaalkenmerken van SMS ](sms-channel.md) begrijpen.

Na deze opstelling, controleer uw [ verbinding SMPP en weet hoe te om het problemen op te lossen indien nodig ](smpp-connection.md).

* **creeer uw eerste levering van SMS**

Om met de configuratie van uw levering van SMS te beginnen:

1. Creeer uw levering, en vul de [ leveringsmontages van SMS ](sms-delivery-settings.md) in,

1. [ bepaal de inhoud ](sms-content.md) van uw levering,

1. [ selecteer het publiek ](sms-audience.md).

De stappen om een publiek te bepalen zijn gedetailleerd op [ deze pagina ](../../audiences/create-audiences.md).

* **bevestigt en verzendt SMS**

Na het aanmaken van de levering:

1. [ verzendt proef ](sms-proofs.md) om het teruggeven en de inhoud te bevestigen,

1. Dan, [ verzend naar het definitieve publiek ](sms-send.md).

* **Monitor en spoor SMS**

Na verzenden, [ leren hoe te om uw SMS ](sms-monitor.md) te controleren en te volgen.
