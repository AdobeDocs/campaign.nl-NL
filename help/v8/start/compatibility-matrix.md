---
title: Compatibiliteitsmatrix voor campagne v8
description: Systemen en versies detecteren die compatibel zijn met Campagne v8
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: ba27d1e56f7354e500e747f01a27412f8d553e2b
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 15%

---

# Compatibiliteitsmatrix voor campagne v8 {#compat-matrix}

Dit document maakt een lijst van alle systemen en componenten die voor de recentste bouwstijl van **Adobe Campaign v8** cliëntconsole worden gesteund. Tenzij anders vermeld, worden alle kleine releases ondersteund. Producten en versies die niet in deze lijst staan, zijn niet compatibel met Adobe Campaign.

Aangezien specifieke versies van deze systemen en hulpmiddelen van derden het einde van de levensduur (EOL) bereiken, is Adobe Campaign niet meer compatibel met die versies en worden ze verwijderd uit deze compatibiliteitsmatrix. Zorg ervoor dat u ondersteunde versies van alle systemen in de compatibiliteitsmatrix gebruikt om problemen te voorkomen.

>[!NOTE]
>
>Adobe Campaign-server en Campagne-clientconsole moeten zich op dezelfde versie bevinden. [ Leer hoe te om uw versie ](upgrades.md#version) te controleren.

## Clientconsole {#ClientConsoleoperatingsystems}

De volgende besturingssystemen en browsers zijn vereist voor het gebruik van de Campagne-clientconsole. [Meer informatie](connect.md).

### Besturingssystemen {#op-systems}

* **2019, 2016 van de Server van Microsoft Windows**
* **11, 10 van de Vensters van 0} Microsoft**

>[!NOTE]
>De 32-bits versie van de clientconsole is afgekeurd sinds versie 8.5. Vanaf 8.6 is de clientconsole alleen beschikbaar in 64 bits. Voor meer informatie over hoe te om uw systeem te bevorderen, verwijs naar dit [ technote ](../../technotes/upgrades/console.md).

### Webbrowser {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, recentste versie. Download het van [ de plaats van de Ontwikkelaar van Microsoft ](http://www.adobe.com/go/acc-ms-webview2-runtime-download) {target="_blank"}.

## CRM-connectoren {#CRMconnectors}

Hieronder vindt u de Customer Relationship Management-systemen (CRM) die compatibel zijn met Adobe Campaign. Leer meer over de schakelaars van CRM [ in deze pagina ](../connect/crm.md).

* **Salesforce** schakelaarAPI versie 49
* **Microsoft Dynamics** schakelaar, Web API: Dynamiek 365 op-gebouw en online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Externe databases die compatibel zijn met de module Adobe Campaign Federated Data Access (FDA) worden hieronder weergegeven. Leer meer over FDA [ in deze pagina ](../connect/fda.md).

* **[!DNL Amazon Redshift]** ODBC-connector, campagne v8.6.4 starten
* **[!DNL Amazon Redshift]** verouderde connector
* **[!DNL Azure Synapse]** , campagne v8.5 starten
* **[!DNL Databricks]** , campagne v8.6.4 / v8.7 starten
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**


>[!AVAILABILITY]
>Bovendien met [ Uitgebreide Veiligheid toe:voegen-op ](../config/enhanced-security.md#secure-vpn-tunneling), kunt u tot uw gegevensbestanden op-gebouw, door het veilige stempelen van VPN toegang hebben. [Meer informatie](../config/enhanced-security.md#vpn-callouts)

## Mobiele SDK {#MobileSDK}

Om [ dupberichten ](../send/push.md) met Campagne te verzenden, gebruik Adobe Experience Platform Mobile SDK door de uitbreiding van Adobe Campaign Classic in de Inzameling UI van Gegevens te vormen.

De compatibele versies voor iOS en Android zijn gedetailleerd in de [ documentatie van Adobe Developer ](https://developer.adobe.com/client-sdks/home/) {target="_blank"}.

## Webgebruikersinterface {#web-ui}

De volgende browsers zijn compatibel met de Gebruikersinterface van het Web van de Campagne. Leer meer over het Web UI van de Campagne [ in deze pagina ](campaign-ui.md#ac-web-ui).

* **Microsoft Edge**, **Google Chrome**, **Safari** (recentste versies)

## Webtoegang {#web-access}

De volgende browsers zijn compatibel met Campagne voor de Toegang van het Web. Leer meer over de toegang van het Web van de Campagne [ in deze pagina ](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (recentste versies)

## Verdere bronnen {#support}

* [Updates van de campagneversie](upgrades.md)
* [De versie van uw campagne controleren](upgrades.md#version)
* [Campagne-clientconsole installeren](connect.md)
* [ de versies van het Controlebord ](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=nl) {target="_blank"}

Om van nieuwe de oplossingsversies van Experience Cloud op de hoogte te worden gebracht, onderteken aan de [ Update van het Product van de Prioriteit van Adobe ](https://www.adobe.com/nl/subscription/priority-product-update.html) {target="_blank"}.