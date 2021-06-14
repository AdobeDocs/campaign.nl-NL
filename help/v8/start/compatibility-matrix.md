---
product: Adobe Campaign
title: Compatibiliteitsmatrix voor campagne v8
description: Meer informatie over systemen en versies die compatibel zijn met Campagne v8
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 29d6a1545722afa3a07c98de1ab453cdb0a618d2
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 30%

---

# Compatibiliteitsmatrix voor campagne v8

Dit document bevat een lijst met alle systemen en onderdelen die worden ondersteund voor de nieuwste build van **Adobe Campaign v8**. Producten en versies die geen deel uitmaken van deze lijst, zijn niet compatibel met Adobe Campaign.

>[!CAUTION]
>
>* Tenzij anders vermeld worden alle kleine releases ondersteund.
>* Aangezien specifieke versies van deze systemen en hulpmiddelen van derden het einde van de levensduur (EOL) bereiken, is Adobe Campaign niet meer compatibel met die versies en worden ze verwijderd uit deze compatibiliteitsmatrix. Zorg ervoor dat u ondersteunde versies van alle systemen in de compatibiliteitsmatrix gebruikt om problemen te voorkomen.


## Compatibele systemen

### Clientconsole{#ClientConsoleoperatingsystems}

:waarschuwing: de volgende besturingssystemen en browsers zijn vereist om de Campaign-clientconsole te gebruiken.

**Besturingssystemen**

* **Microsoft Windows Server**  2016, 2012
* **Microsoft Windows** 8, 10 (aanbevolen voor Japanse instanties)

**Browser**

**Microsoft Internet Explorer** 11

### CRM-connectoren{#CRMconnectors}

* **** Salesforceconnector API versie 49
* **Microsoft** DynamicConnector, Web API: Dynamics 365 On-premise en Online

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

### Mobiele SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 met mobiele SDK build 1.1.1.
* **Apple iOS** 9 - 14 met mobiele SDK build 1.0.26, compatibel met 32- en 64-bits versies.

### Ondersteunde browsers {#Browsers}

De volgende browsers zijn compatibel met Campaign voor toegang tot internet.

* **Microsoft Edge**,  **Mozilla Firefox**,  **Google Chrome**,  **Safari**  (nieuwste versies)

* **Internet Explorer** 11

## Hoe te om uw versie van de Campagne te controleren en te bouwen

Gebruik het menu **Help > Info..** om uw versie te controleren.

![](assets/ac-version.png)

U hebt toegang tot de volgende informatie:

* Het **versienummer** van uw clientconsole en toepassingsserver. In het bovenstaande voorbeeld is de versie 8.1.5 voor zowel de clientconsole als de toepassingsserver.
* Het SHA-getal tussen haakjes.
* Een koppeling om contact op te nemen met de klantenservice van Adobe.
* Koppelingen naar het privacybeleid van Adobe, de Gebruiksvoorwaarden en het Cookies-beleid.
