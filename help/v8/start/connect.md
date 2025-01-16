---
title: Verbinden met Campagne met de cliëntconsole
description: Leer hoe u de Campagne-clientconsole op uw computer installeert en verbinding maakt met Adobe Campaign
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: a9f26a033d63ab1dece9ef9780392823ee130047
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 2%

---

# Verbinden met Campagne met de cliëntconsole{#gs-ac-connect}

Om met Campagne met de cliëntconsole te verbinden, moet u het eerst installeren en vormen.

Voordat u begint, moet u:

* Controleer uw systeem en hulpmiddelverenigbaarheid met Adobe Campaign in de [ matrijs van de Verenigbaarheid ](compatibility-matrix.md)
* URL van campagneserver ophalen
* Maak je Adobe ID of ontvang je gebruikersgegevens van je bedrijf
* Installeer de Microsoft Edge Webview2-runtime op uw systeem. [Meer informatie](#webview)


>[!NOTE]
>
>U kunt ook via een webbrowser verbinding maken met de gebruikersinterface van Campagne Web. Leer meer over het nieuwe Gebruikersinterface van het Web van de Campagne in [ deze documentatie ](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html) {target="_blank"}.


## De clientconsole installeren{#download-ac-console}

### Microsoft Edge Webview2-runtime {#webview}

Vanuit Campaign Classic 8.4 is de installatieversie van Microsoft Edge Webview 2 runtime vereist voor elke installatie van de clientconsole.

De webweergave wordt standaard geïnstalleerd als onderdeel van het besturingssysteem Windows 11. Als het niet reeds op uw systeem aanwezig is, zal het programma van de de cliëntconsole van de Campagne u ertoe aanzetten om het van [ de website van de Ontwikkelaar van Microsoft ](http://www.adobe.com/go/acc-ms-webview2-runtime-download) {target="_blank"} te downloaden. De downloadkoppeling werkt niet in Internet Explorer 11, omdat Microsoft de ondersteuning heeft vervangen. Zorg ervoor dat u een andere browser gebruikt om de koppeling te openen.

### De console downloaden{#install-ac-console}

Wanneer u Campagne voor het eerst gebruikt, moet u de clientconsole downloaden en installeren.

Er zijn twee opties beschikbaar om de clientconsole te downloaden:

1. Als beheerder van de Campagne, verbind met de Distributie van de Software van de Adobe [ ](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) {target="_blank"}.

1. Als eindgebruiker, stelt uw beheerder van de Campagne de cliëntconsole voor u op, en stelt het beschikbaar door een specifieke URL.

Wanneer het installatieprogramma van de clientconsole is gedownload, installeert u dit op uw lokale computer.

U kunt de taal van de clientconsole niet wijzigen nadat u deze hebt geïnstalleerd.

## Uw verbinding maken{#create-your-connection}

Nadat de clientconsole is geïnstalleerd, voert u de onderstaande stappen uit om de verbinding met de toepassingsserver tot stand te brengen:

1. Start de console en blader in de rechterhoek naar de koppeling om het scherm voor de verbindingsconfiguratie te openen.

1. Klik op **[!UICONTROL Add > Connection]** en voer het label en de URL van de Adobe Campaign-toepassingsserver in.

1. Geef een verbinding met uw Adobe Campaign-toepassingsserver op via een URL. Gebruik of DNS of een alias van de machine, of uw IP adres.

   U kunt bijvoorbeeld het type URL `https://<machine>.<domain>.com` gebruiken.

1. Schakel de optie **[!UICONTROL Connect with an Adobe ID]** in.

1. Klik op **[!UICONTROL Ok]** om uw instellingen op te slaan.

U kunt zo veel verbindingen toevoegen als u nodig hebt om bijvoorbeeld verbinding te maken met uw test-, stage- en productieomgeving.

>[!NOTE]
>
>Met de knop **[!UICONTROL Add]** kunt u **[!UICONTROL folders]** maken om al uw verbindingen te organiseren. U hoeft alleen elke verbinding naar een map te slepen.

## Aanmelden bij Adobe Campaign {#logon-to-ac}

Campagnegebruikers maken via hun Adobe ID verbinding met de Adobe Campaign-console, via Adobe Identity Management System (IMS). Zij kunnen zelfde identiteitskaart alle oplossingen van de Adobe gebruiken. De verbinding wordt bewaard wanneer het gebruiken van Adobe Campaign met andere oplossingen. Leer meer over Adobe IMS in [ deze pagina ](https://helpx.adobe.com/enterprise/using/identity.html) {target="_blank"}.

Volg onderstaande stappen om u aan te melden bij een instantie:

1. Start de console en blader in de rechterhoek naar de koppeling om het scherm voor de verbindingsconfiguratie te openen.

   ![](assets/connectToCampaign.png)

1. Selecteer de instantie Campagne waaraan u zich moet aanmelden.

1. Klik op **[!UICONTROL Ok]**.

U kunt zich vervolgens aanmelden bij Campagne met uw Adobe ID.

![](assets/adobeID.png)

>[!NOTE]
>
>Aangezien Microsoft Edge Webview2 geen volmachtsgeloofsbrieven opslaat, kan de Console u vragen om tweemaal bij uw eerste verbinding voor authentiek te verklaren.

## Upgrade uw clientconsole uitvoeren{#upgrade-ac-console}

Wanneer uw systeem naar een nieuwere versie wordt geüpgraded, moet u uw cliëntconsole aan die zelfde versie bijwerken. Dit is een beste praktijk, en voor sommige versies is deze verbetering verplicht. In dat geval, wordt het vermeld in de [ Nota&#39;s van de Versie ](release-notes.md).

Als Beheerde gebruiker van Cloud Servicen, stelt de Adobe de cliëntconsole voor u op. Wanneer u verbinding maakt met uw geüpgrade omgeving, wordt u gevraagd om de meest recente versie van de clientconsole te downloaden in een pop-upvenster. U moet deze upgrade accepteren en de clientconsole naar wens bijwerken.

>[!CAUTION]
>
>Adobe raadt u aan de optie **[!UICONTROL No longer ask this question]** niet in te schakelen om ervoor te zorgen dat u een melding ontvangt wanneer er een nieuwe versie van de Console beschikbaar is. Als deze optie is geselecteerd, wordt de gebruiker niet geïnformeerd dat een consoleverbetering is vereist.
>



## Toegang verlenen aan gebruikers{#grant-access}

Met Adobe Campaign kunt u de rechten definiëren en beheren die aan de verschillende operatoren zijn toegewezen.

Als campagnebeheerder bent u verantwoordelijk voor het maken van de operatoren en het delen van hun referenties met de gebruikers.

Leer meer over gebruikers en hoe te om hun toestemmingen in [ te bepalen deze sectie ](gs-permissions.md).


## Campagne openen met een webbrowser {#connect-web-ac}

### Webgebruikersinterface {#connect-web-ui}

De aanvang van de Versie van Campagne v8.6, hebt u toegang tot het nieuwe **de gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud. Experience Cloud is de geïntegreerde familie van digitale marketingtoepassingen, producten en diensten van de Adobe. Via de intuïtieve interface hebt u snel toegang tot uw cloudtoepassingen, productfuncties en services.

>[!AVAILABILITY]
>
>De gebruikersinterface van het Web van de campagne is slechts beschikbaar aan gebruikers die met Adobe Campaign met hun Adobe ID verbinden. Leer meer over [ het Systeem van Identity Management van de Adobe (IMS) ](https://helpx.adobe.com/enterprise/using/identity.html) {target="_blank"}.
>

Leer hoe te met Adobe Experience Cloud te verbinden, en tot de interface van het Web van Adobe Campaign [ in deze pagina ](campaign-ui.md#ac-web-ui) toegang te hebben.

Leer meer in de [ gebruikersinterfacedocumentatie van het Web van Adobe Campaign ](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home) {target="_blank"}.

### Webtoegang {#web-access}

Bepaalde delen van de toepassing zijn toegankelijk via een webbrowser met behulp van een HTML-gebruikersinterface: rapportage, goedkeuring van levering, controle van instanties en meer.

De toegang van het Web verstrekt een interface die aan de console maar met een verminderde reeks functionaliteiten gelijkaardig is.

Bijvoorbeeld, voor een bepaalde exploitant, zal een campagne met de volgende opties in de console verschijnen:

![](assets/campaign-from-console.png)

Terwijl met de toegang van het Web, de opties hoofdzakelijk het bekijken zullen toelaten:

![](assets/campaign-from-web.png)

De toegang van het Web wordt ook gebruikt aan in het bevestigingsproces: de exploitanten kunnen op het goedkeuringsverzoek e-mail klikken en met Campagne verbinden door hun Webbrowser om een leveringsinhoud of een budget te bevestigen of te verwerpen.

De URL is: `https://<your adobe campaign server>:<port number>/view/home` om vanaf het web toegang te krijgen tot uw instantie Campagne.
