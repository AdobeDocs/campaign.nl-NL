---
title: Compatibiliteitsmatrix voor campagne v8
description: Systemen en versies detecteren die compatibel zijn met Campagne v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 90dde8bb3bde4893971a2f364aa636ade6fff10f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11, 10, 8

>[!NOTE]
>
>Microsoft Windows 10 wordt aanbevolen voor Japanse instanties.

### Webbrowser{#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, nieuwste versie. Downloaden vanuit [Microsoft Developer-site](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"}.

## CRM-connectoren{#CRMconnectors}

Hieronder vindt u de Customer Relationship Management-systemen (CRM) die compatibel zijn met Adobe Campaign. [Meer informatie](../connect/crm.md).

* **Salesforce** connector API versie 49
* **Microsoft Dynamics** connector, web-API: Dynamics 365 on-premise en online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Externe databases die compatibel zijn met de module Adobe Campaign Federated Data Access (FDA) worden hieronder weergegeven. [Meer informatie](../connect/fda.md).

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## Mobiele SDK{#MobileSDK}

U kunt Campagne gebruiken om te verzenden [pushmeldingen](../send/push.md) op de hieronder vermelde besturingssystemen, met behulp van de bijbehorende mobiele SDK.

* **Android** 12, 9.0, 8.x, 7.x, met Campagne Android SDK build 1.1.1.
* **Apple iOS** 9 - 16 met Campagne iOS SDK build 1.0.26, compatibel met 32- en 64-bits versies. Apple iOS 16 wordt ondersteund voor startcampagne v8.4.


## Webtoegang{#web-access}

De volgende browsers zijn compatibel met Campaign voor [toegang tot internet](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (nieuwste versies)

## Hoe te om uw versie van de Campagne te controleren en te bouwen{#version}

Toegang krijgen tot **Help > Info...** om uw versie te controleren.

![](assets/ac-version.png)

U hebt toegang tot de volgende informatie:

* De **versie** nummer van uw clientconsole en toepassingsserver. In het bovenstaande voorbeeld is de versie 8.1.5 voor zowel de clientconsole als de toepassingsserver.
* Het SHA-getal tussen haakjes.
* Een koppeling om contact op te nemen met de klantenservice van Adobe.
* Koppelingen naar het privacybeleid van Adobe, de Gebruiksvoorwaarden en het Cookies-beleid.
