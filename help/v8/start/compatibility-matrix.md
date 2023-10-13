---
title: Compatibiliteitsmatrix voor campagne v8
description: Systemen en versies detecteren die compatibel zijn met Campagne v8
feature: Release Notes
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 32%

---

# Compatibiliteitsmatrix voor campagne v8

Dit document bevat een lijst met alle systemen en onderdelen die worden ondersteund voor de nieuwste versie van **Adobe Campaign v8**. Tenzij anders vermeld worden alle kleine releases ondersteund. Producten en versies die niet in deze lijst staan, zijn niet compatibel met Adobe Campaign.

Aangezien specifieke versies van deze systemen en hulpmiddelen van derden het einde van de levensduur (EOL) bereiken, is Adobe Campaign niet meer compatibel met die versies en worden ze verwijderd uit deze compatibiliteitsmatrix. Zorg ervoor dat u ondersteunde versies van alle systemen in de compatibiliteitsmatrix gebruikt om problemen te voorkomen.

>[!NOTE]
>
>Adobe Campaign Server en Client Console moeten dezelfde versie hebben. [Leer hoe u uw versie kunt controleren](#version).

## Clientconsole{#ClientConsoleoperatingsystems}

De volgende besturingssystemen en browsers zijn vereist om de Campaign-clientconsole te gebruiken. [Meer informatie](connect.md).

### Besturingssystemen{#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11 10

>[!NOTE]
>
>De 32-bits versie van de clientconsole is vanaf versie 8.5 vervangen. Vanaf 8.6 is de Client Console alleen beschikbaar in 64 bits. Raadpleeg voor meer informatie over het upgraden van uw besturingssysteem [technote](../../technotes/upgrades/console.md).

### Webbrowser{#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, nieuwste versie. Downloaden vanuit [Microsoft Developer-site](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"}.

## CRM-connectoren{#CRMconnectors}

Hieronder vindt u de Customer Relationship Management-systemen (CRM) die compatibel zijn met Adobe Campaign. [Meer informatie](../connect/crm.md).

* **Salesforce** connector API versie 49
* **Microsoft Dynamics** connector, web API: Dynamics 365 on-premise en online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Externe databases die compatibel zijn met de module Adobe Campaign Federated Data Access (FDA) worden hieronder weergegeven. [Meer informatie](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, vanaf Campaign v8.5
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## Mobiele SDK{#MobileSDK}

Naar [pushmeldingen](../send/push.md) met Campagne, gebruik Adobe Experience Platform Mobile SDK door de uitbreiding van Adobe Campaign Classic in de UI van de Inzameling van Gegevens te vormen.


## Webtoegang{#web-access}

De volgende browsers zijn compatibel met Campaign voor [toegang tot internet](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (meest recente versies)

## Hoe te om uw versie van de Campagne te controleren en te bouwen{#version}

Toegang krijgen tot de **Help > Info...** om uw versie te controleren.

![](assets/ac-version.png)

U hebt toegang tot de volgende informatie:

* De **versie** nummer van uw clientconsole- en toepassingsserver. In het bovenstaande voorbeeld is de versie 8.1.5 voor zowel de clientconsole als de toepassingsserver.
* Het SHA-getal tussen haakjes.
* Een koppeling voor contact met de klantenservice van de Adobe.
* Koppelingen naar het privacybeleid, de Gebruiksvoorwaarden en het Cookies-beleid van de Adobe.
