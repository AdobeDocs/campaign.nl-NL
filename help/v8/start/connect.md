---
title: Verbinden met Campagne met de cliëntconsole
description: Leer hoe u de Campagne-clientconsole op uw computer installeert en verbinding maakt met Adobe Campaign
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 9df599ec0a898a1af16cb92d334d50375fde86ba
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 1%

---

# Verbinden met Campagne met de cliëntconsole{#gs-ac-connect}

Om met Campagne met de cliëntconsole te verbinden, moet u het eerst installeren en vormen.

Voordat u begint, moet u:

* Controleer de compatibiliteit van uw systeem en gereedschappen met Adobe Campaign in de [Compatibiliteitsmatrix](compatibility-matrix.md)
* URL van campagneserver ophalen
* Maak je Adobe ID of ontvang je gebruikersgegevens van je bedrijf
* Installeer de Microsoft Edge Webview2-runtime op uw systeem. [Meer informatie](#webview)


>[!NOTE]
>
>U kunt ook via een webbrowser verbinding maken met de gebruikersinterface van Campagne Web. Meer informatie over de nieuwe gebruikersinterface van het Web voor campagne in [deze documentatie](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.


## De clientconsole installeren{#download-ac-console}

### Microsoft Edge Webview2-runtime {#webview}

Vanuit Campaign Classic 8.4 is de installatie van Microsoft Edge Webview 2 runtime vereist voor elke installatie van de clientconsole.

De webweergave wordt standaard geïnstalleerd als onderdeel van het besturingssysteem Windows 11. Als dit nog niet het geval is op uw systeem, wordt u via het installatieprogramma van de Campagne-clientconsole gevraagd het programma te downloaden van [Microsoft Developer-website](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"}. De downloadkoppeling werkt niet in Internet Explorer 11, omdat Microsoft de ondersteuning heeft vervangen. Zorg ervoor dat u een andere browser gebruikt om de koppeling te openen.

### De console downloaden{#install-ac-console}

Wanneer u Campagne voor het eerst gebruikt, moet u de clientconsole downloaden en installeren.

Er zijn twee opties beschikbaar om de clientconsole te downloaden:

1. Als beheerder van de Campagne, verbind met Adobe [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"}.

1. Als eindgebruiker, stelt uw beheerder van de Campagne de cliëntconsole voor u op, en stelt het beschikbaar door een specifieke URL.

Wanneer het installatieprogramma van de clientconsole is gedownload, installeert u dit op uw lokale computer.

U kunt de taal van de clientconsole niet wijzigen nadat u deze hebt geïnstalleerd.

## Uw verbinding maken{#create-your-connection}

Nadat de clientconsole is geïnstalleerd, voert u de onderstaande stappen uit om de verbinding met de toepassingsserver tot stand te brengen:

1. Start de console en blader in de rechterhoek naar de koppeling om het scherm voor de verbindingsconfiguratie te openen.

1. Klikken **[!UICONTROL Add > Connection]** en voert u het label en de URL van de Adobe Campaign-toepassingsserver in.

1. Geef een verbinding met uw Adobe Campaign-toepassingsserver op via een URL. Gebruik of DNS of een alias van de machine, of uw IP adres.

   U kunt bijvoorbeeld de opdracht [`https://<machine>.<domain>.com`](https://myserver.adobe.com) type URL.

1. Schakel de optie in **[!UICONTROL Connect with an Adobe ID]**.

1. Klikken **[!UICONTROL Ok]** om uw instellingen op te slaan.

U kunt zo veel verbindingen toevoegen als u nodig hebt om bijvoorbeeld verbinding te maken met uw test-, stage- en productieomgeving.

>[!NOTE]
>
>De **[!UICONTROL Add]** knop laat u maken **[!UICONTROL folders]** om al uw verbindingen te organiseren. U hoeft alleen elke verbinding naar een map te slepen.

## Aanmelden bij Adobe Campaign {#logon-to-ac}

Campagnegebruikers maken via hun Adobe ID verbinding met de Adobe Campaign-console, via Adobe Identity Management System (IMS). Zij kunnen zelfde identiteitskaart alle oplossingen van de Adobe gebruiken. De verbinding wordt bewaard wanneer het gebruiken van Adobe Campaign met andere oplossingen. Meer informatie over Adobe IMS in [deze pagina](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.

Volg onderstaande stappen om u aan te melden bij een instantie:

1. Start de console en blader in de rechterhoek naar de koppeling om het scherm voor de verbindingsconfiguratie te openen.

   ![](assets/connectToCampaign.png)

1. Selecteer de instantie Campagne waaraan u zich moet aanmelden.

1. Klik op **[!UICONTROL Ok]**.

U kunt zich vervolgens aanmelden bij Campagne met uw Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Aangezien Microsoft Edge Webview2 geen proxyreferenties opslaat, wordt u mogelijk door de Console gevraagd om tweemaal te verifiëren bij de eerste verbinding.

## Upgrade uw clientconsole uitvoeren{#upgrade-ac-console}

Wanneer uw systeem naar een nieuwere versie wordt geüpgraded, moet u uw cliëntconsole aan die zelfde versie bijwerken. Dit is een beste praktijk, en voor sommige versies is deze verbetering verplicht. In dat geval wordt dit vermeld in het [Opmerkingen bij de release](release-notes.md).

Als Beheerde gebruiker van Cloud Servicen, stelt de Adobe de cliëntconsole voor u op. Wanneer u verbinding maakt met uw geüpgrade omgeving, wordt u gevraagd om de meest recente versie van de clientconsole te downloaden in een pop-upvenster. U moet deze upgrade accepteren en de clientconsole naar wens bijwerken.

>[!CAUTION]
>
>Adobe beveelt aan deze optie te laten **[!UICONTROL No longer ask this question]** niet geselecteerd om ervoor te zorgen dat u gewaarschuwd wordt wanneer een nieuwe versie van de Console beschikbaar is. Als deze optie is geselecteerd, wordt de gebruiker niet geïnformeerd dat een consoleverbetering is vereist.
>



## Toegang verlenen aan gebruikers{#grant-access}

Met Adobe Campaign kunt u de rechten definiëren en beheren die aan de verschillende operatoren zijn toegewezen.

Als campagnebeheerder bent u verantwoordelijk voor het maken van de operatoren en het delen van hun referenties met de gebruikers.

Meer informatie over gebruikers en het definiëren van hun machtigingen vindt u in [deze sectie](gs-permissions.md).


## Webtoegang{#web-access}

Bepaalde delen van de toepassing zijn toegankelijk via een webbrowser met behulp van een HTML-gebruikersinterface: rapportage, goedkeuring van levering, controle van instanties en meer.

De toegang van het Web verstrekt een interface die aan de console maar met een verminderde reeks functionaliteiten gelijkaardig is.

Bijvoorbeeld, voor een bepaalde exploitant, zal een campagne met de volgende opties in de console verschijnen:

![](assets/campaign-from-console.png)

Terwijl met de toegang van het Web, de opties hoofdzakelijk het bekijken zullen toelaten:

![](assets/campaign-from-web.png)

De toegang van het Web wordt ook gebruikt aan in het bevestigingsproces: de exploitanten kunnen op het goedkeuringsverzoek e-mail klikken en met Campagne verbinden door hun Webbrowser om een leveringsinhoud of een budget te bevestigen of te verwerpen.

De URL is:  `https://<your adobe campaign server>:<port number>/view/home`.
