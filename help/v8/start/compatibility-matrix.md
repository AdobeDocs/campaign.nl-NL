---
title: Compatibiliteitsmatrix voor campagne v8
description: Systemen en versies detecteren die compatibel zijn met Campagne v8
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 374c0df2cd95e656cfbaa1fb355bf1f48828dfee
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 22%

---

# Compatibiliteitsmatrix voor campagne v8 {#compat-matrix}

In dit document worden alle systemen en componenten weergegeven die worden ondersteund voor de meest recente build van **Adobe Campaign v8** clientconsole. Tenzij anders vermeld, worden alle kleine releases ondersteund. Producten en versies die niet in deze lijst staan, zijn niet compatibel met Adobe Campaign.

Aangezien specifieke versies van deze systemen en hulpmiddelen van derden het einde van de levensduur (EOL) bereiken, is Adobe Campaign niet meer compatibel met die versies en worden ze verwijderd uit deze compatibiliteitsmatrix. Zorg ervoor dat u ondersteunde versies van alle systemen in de compatibiliteitsmatrix gebruikt om problemen te voorkomen.

>[!NOTE]
>
>Adobe Campaign-server en Campagne-clientconsole moeten zich op dezelfde versie bevinden. [Leer hoe u uw versie kunt controleren](upgrades.md#version).

## Clientconsole {#ClientConsoleoperatingsystems}

De volgende besturingssystemen en browsers zijn vereist voor het gebruik van de Campagne-clientconsole. [Meer informatie](connect.md).

### Besturingssystemen{#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11 10

>[!NOTE]
>
>Houd er rekening mee dat de 32-bits versie van de clientconsole sinds de release 8.5 is vervangen. Vanaf 8.6 is de clientconsole alleen beschikbaar in 64 bits. Raadpleeg voor meer informatie over het upgraden van uw systeem de volgende [technote](../../technotes/upgrades/console.md).

### Webbrowser {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, nieuwste versie. Downloaden vanuit [Microsoft Developer-site](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"}.

## CRM-connectoren {#CRMconnectors}

Hieronder vindt u de Customer Relationship Management-systemen (CRM) die compatibel zijn met Adobe Campaign. [Meer informatie](../connect/crm.md).

* **Salesforce** connector API versie 49
* **Microsoft Dynamics** connector, web API: Dynamics 365 on-premise en online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Externe databases die compatibel zijn met de module Adobe Campaign Federated Data Access (FDA) worden hieronder weergegeven. [Meer informatie](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, campagne v8.5 starten
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## Mobiele SDK {#MobileSDK}

Naar [pushmeldingen](../send/push.md) met Campagne, gebruik Adobe Experience Platform Mobile SDK door de uitbreiding van Adobe Campaign Classic in de UI van de Inzameling van Gegevens te vormen.

De compatibele versies voor iOS en Android worden beschreven in het gedeelte [Adobe Developer-documentatie](https://developer.adobe.com/client-sdks/home/)

## Webtoegang {#web-access}

De volgende browsers zijn compatibel met Campaign voor [toegang tot internet](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (meest recente versies)


## Verdere bronnen {#support}

* [Updates van de campagneversie](upgrades.md)
* [De versie van uw campagne controleren](upgrades.md#version)
* [Campagne-clientconsole installeren](connect.md)
* [releases in het regelpaneel](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=nl){target="_blank"}.

Om op de hoogte te worden gebracht van nieuwe versies van de oplossing van het Experience Cloud, onderteken aan [Adobe Prioriteit productupdate](https://www.adobe.com/nl/subscription/priority-product-update.html){target="_blank"}.