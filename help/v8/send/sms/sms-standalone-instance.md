---
title: SMS in een standalone instantie
description: Leer hoe te om een levering van SMS in een standalone instantie te vormen
feature: SMS
role: User
hide: true
hidefromtoc: true
level: Beginner, Intermediate
badge: label="Beperkte beschikbaarheid" type="Informative"
exl-id: 7cebcde0-c5a8-4b9b-baba-27a62bebde91
source-git-commit: 30babc4bec802f61d3bd28a7ebcf0c15e22b2284
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# SMS in een standalone instantie {#sms-standalone}

>[!IMPORTANT]
>
>Deze documentatie is voor Adobe Campaign v8.7.2 en hoger.
>
>Voor oudere versies, gelieve de [ documentatie van Campaign Classic v7 ](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up) te lezen.

In een standalone geval, vereist het verzenden van een levering van SMS:

1. Een **externe rekening** die een schakelaar en het type van bericht specificeren, [ leren meer hier ](#external-account)

1. A **leveringsmalplaatje** waarin deze externe rekening van verwijzingen wordt voorzien, [ meer hier ](#sms-delivery-template) leren

## Een externe account maken {#external-account}

>[!IMPORTANT]
>
>Het gebruik van hetzelfde account en wachtwoord voor meerdere externe SMS-accounts kan leiden tot conflicten en overlapping tussen de accounts. Leer meer op [ het oplossen van problemenpagina van SMS ](smpp-connection.md#sms-troubleshooting).

Hier volgen de stappen voor het maken van uw externe SMPP-account:

1. Klik in **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]** op het pictogram **[!UICONTROL New]**

   ![](assets/sms_extaccount.png){zoomable="yes"}

1. Stel de **[!UICONTROL Label]** en de **[!UICONTROL Internal name]** van uw externe account in. Definieer het accounttype als **[!UICONTROL Routing]** , schakel het selectievakje **[!UICONTROL Enabled]** in, selecteer **[!UICONTROL Mobile (SMS)]** voor het kanaal en **[!UICONTROL Bulk delivery]** voor de leveringsmodus.

   ![](assets/sms_extaccount_new.png){zoomable="yes"}

1. Bewaar **[!UICONTROL Extended generic SMPP]** in de vervolgkeuzelijst **[!UICONTROL Connector]** op het tabblad **[!UICONTROL Mobile]** .
Het vak **[!UICONTROL Send messages through a dedicated process]** is standaard ingeschakeld.

   ![](assets/sms_extaccount_connector.png){zoomable="yes"}

   Als u de verbinding wilt instellen, moet u de tabbladen van dit formulier invullen. Voor details, [ leren meer over externe rekening SMPP ](smpp-external-account.md#smpp-connection-settings).


## De leveringssjabloon configureren {#sms-delivery-template}

Om de verwezenlijking van uw levering van SMS te vergemakkelijken, creeer een leveringsmalplaatje van SMS waar uw externe rekening SMPP van verwijzingen wordt voorzien.

Klik in **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** met de rechtermuisknop op de bestaande mobiele leveringssjabloon en kies **[!UICONTROL Duplicate]** .

![](assets/sms_template_duplicate.png){zoomable="yes"}

Wijzig de tags **[!UICONTROL Label]** en **[!UICONTROL Internal name]** van de sjabloon om deze gemakkelijk te herkennen en klik op de knop **[!UICONTROL Properties]** .

![](assets/sms_template_name.png){zoomable="yes"}

Selecteer op het tabblad **[!UICONTROL General]** in **[!UICONTROL Routing]** de externe SMPP-account.

![](assets/sms_template_routing.png){zoomable="yes"}

Op het tabblad **[!UICONTROL SMS]** kunt u optionele parameters aan de sjabloon toevoegen.

![](assets/sms_template_properties.png){zoomable="yes"}

[ leer meer over deze het lusjeconfiguratie van SMS ](sms-delivery-settings.md).
