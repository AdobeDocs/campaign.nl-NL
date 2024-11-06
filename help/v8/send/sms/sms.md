---
title: SMS verzenden met Adobe Campaign
description: Aan de slag met SMS in de campagne
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 5b2638927e39b6f839fb3a8639fe106d2c519fbf
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 2%

---

# Aan de slag met sms {#gs-sms-channel}

Adobe Campaign staat u toe om gepersonaliseerde [ SMS ](../send/sms/sms.md) op mobiele apparaten te leveren.

Voor SMS-berichten kunt u alleen in tekstindeling berichten maken, wijzigen en personaliseren. Je kunt ook een voorbeeld van je SMS-berichten bekijken voordat ze worden verzonden.

>[!NOTE]
>
>U kunt Adobe Campaign ook gebruiken om [ LIJN ](../send/line.md) berichten, met tekst en/of beelden en verbindingen te verzenden.

Als u SMS wilt leveren aan een mobiele telefoon met Adobe Campaign, hebt u het volgende nodig:

* Een externe account die is geconfigureerd op het **[!UICONTROL Mobile (SMS)]** -kanaal of op het **[!UICONTROL LINE]** -kanaal.
* Een SMS-leveringssjabloon die correct is gekoppeld aan deze externe account.

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
