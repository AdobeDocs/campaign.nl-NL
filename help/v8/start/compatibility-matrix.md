---
title: Compatibiliteitsmatrix voor campagne v8
description: Meer informatie over systemen en versies die compatibel zijn met Campagne v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 50b6c9c8f55bb870e95c91bd1de22e3392e732dd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 25%

---

# Compatibiliteitsmatrix voor campagne v8

In dit document worden alle systemen en componenten weergegeven die worden ondersteund voor de **nieuwste build van Adobe Campaign v8**. Tenzij anders vermeld worden alle kleine releases ondersteund. Producten en versies die niet in deze lijst staan, zijn niet compatibel met Adobe Campaign.

Aangezien specifieke versies van deze systemen en hulpmiddelen van derden het einde van de levensduur (EOL) bereiken, is Adobe Campaign niet meer compatibel met die versies en worden ze verwijderd uit deze compatibiliteitsmatrix. Zorg ervoor dat u ondersteunde versies van alle systemen in de compatibiliteitsmatrix gebruikt om problemen te voorkomen.

>[!NOTE]
>
>Adobe Campaign Server en Client Console moeten dezelfde versie hebben. [Leer hoe u uw versie kunt controleren](#version).

## Clientconsole{#ClientConsoleoperatingsystems}

Als u de Campagne Client Console wilt gebruiken, is een van de volgende besturingssystemen vereist. [Meer informatie](connect.md).

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11 (startcampagne v8.3), 10, 8

>[!NOTE]
>
>Microsoft Windows 10 wordt aanbevolen voor Japanse instanties.

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

* **Android** 12 (startcampagne v8.3), 9.0, 8.x, 7.x, met Campagne Android SDK build 1.1.1.
* **Apple iOS** 9 - 15 met Campagne iOS SDK build 1.0.26, compatibel met 32- en 64-bits versies. iOS 15 wordt ondersteund vanaf Campaign v8.3.

## Webtoegang

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
