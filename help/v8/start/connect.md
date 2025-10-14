---
title: Verbinding maken met Campagne v8
description: Leer hoe u verbinding maakt met Adobe Campaign v8 en de console op uw computer installeert voor eenvoudige toegang.
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 2%

---

# Verbinding maken met Adobe Campaign v8{#gs-ac-connect}

Als u wilt gaan werken met Campagne, moet u de Client Console installeren en configureren.

De clientconsole is een native toepassing die communiceert met de Adobe Campaign-toepassingsserver via standaard internetprotocollen, zoals SOAP en HTTP. De Console van de Cliënt van de campagne centraliseert alle mogelijkheden en montages, en vereist minimale bandbreedte aangezien het op een lokaal geheime voorgeheugen baseert. Campagne Client Console is ontworpen voor eenvoudige implementatie en kan worden geïmplementeerd vanuit een internetbrowser, automatisch worden bijgewerkt. Hiervoor is geen specifieke netwerkconfiguratie nodig omdat alleen HTTP(S)-verkeer wordt gegenereerd.

Voordat u begint, moet u:

* Controleer uw systeem en hulpmiddelverenigbaarheid met Adobe Campaign in de [&#x200B; matrijs van de Verenigbaarheid &#x200B;](compatibility-matrix.md)
* URL van campagneserver ophalen
* Maak je Adobe ID of ontvang je gebruikersgegevens van je bedrijf
* Installeer de Microsoft Edge Webview2-runtime op uw systeem. [Meer informatie](#webview)

## De clientconsole installeren{#download-ac-console}

### Microsoft Edge Webview2-runtime {#webview}

Vanuit Campaign Classic 8.4-versie is de installatie van Microsoft Edge Webview 2-runtime vereist voor elke installatie van de clientconsole.

De webweergave wordt standaard geïnstalleerd als onderdeel van het besturingssysteem Windows 11. Als het niet reeds op uw systeem aanwezig is, zal het de installatieprogramma van de Console van de Campagne u ertoe aanzetten om het van [&#x200B; Microsoft Developer website &#x200B;](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"} te downloaden. De downloadkoppeling werkt niet in Internet Explorer 11, omdat Microsoft de ondersteuning heeft vervangen. Zorg ervoor dat u een andere browser gebruikt om de koppeling te openen.

### De console downloaden{#install-ac-console}

Wanneer u Campagne voor de eerste keer gebruikt, moet u de Client Console downloaden en installeren.

Er zijn twee opties beschikbaar om de clientconsole te downloaden:

1. Als beheerder van de Campagne, verbind met de Distributie van de Software van Adobe [&#128279;](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"}.

1. Als eindgebruiker, stelt uw beheerder van de Campagne de Console van de Cliënt voor u op, en stelt het beschikbaar door een specifieke URL.

Nadat het installatieprogramma van de clientconsole is gedownload, installeert u dit op uw lokale computer.

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

Campagnegebruikers maken via hun Adobe ID verbinding met de Adobe Campaign-console via Adobe Identity Management System (IMS). Ze kunnen dezelfde id gebruiken voor alle Adobe-oplossingen. De verbinding wordt bewaard wanneer het gebruiken van Adobe Campaign met andere oplossingen. Leer meer over Adobe IMS in [&#x200B; deze pagina &#x200B;](https://helpx.adobe.com/nl/enterprise/using/identity.html){target="_blank"}.

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

## Uw clientconsole upgraden{#upgrade-ac-console}

Wanneer uw systeem is bijgewerkt naar een nieuwere versie, moet u de clientconsole bijwerken naar dezelfde versie. Dit is een beste praktijk, en voor sommige versies is deze verbetering verplicht. In dat geval, wordt het vermeld in de [&#x200B; Nota&#39;s van de Versie &#x200B;](release-notes.md).

Als gebruiker van Managed Cloud Services implementeert Adobe de Client Console voor u. Wanneer u verbinding maakt met uw geüpgrade omgeving, wordt u gevraagd om de nieuwste versie van de clientconsole te downloaden in een pop-upvenster. U moet deze upgrade accepteren en de clientconsole naar wens bijwerken.

>[!CAUTION]
>
>Adobe raadt u aan de optie **[!UICONTROL No longer ask this question]** niet in te schakelen om ervoor te zorgen dat u een melding ontvangt wanneer er een nieuwe versie van de Console beschikbaar is. Als deze optie is geselecteerd, wordt de gebruiker niet geïnformeerd dat een consoleverbetering is vereist.
>



## Toegang verlenen aan gebruikers{#grant-access}

Met Adobe Campaign kunt u de rechten definiëren en beheren die aan de verschillende operatoren zijn toegewezen.

Als campagnebeheerder bent u verantwoordelijk voor het maken van de operatoren en het delen van hun referenties met de gebruikers.

Leer meer over gebruikers en hoe te om hun toestemmingen in [&#x200B; te bepalen deze sectie &#x200B;](gs-permissions.md).


## Campagne openen met een webbrowser {#connect-web-ac}

### Webgebruikersinterface {#connect-web-ui}

De aanvang van de Versie van Campagne v8.6, hebt u toegang tot het nieuwe **de gebruikersinterface van het Web van de Campagne**, beschikbaar door het centrale milieu van Adobe Experience Cloud. Experience Cloud is een geïntegreerde Adobe-reeks met digitale marketingtoepassingen, producten en services. Via de intuïtieve interface hebt u snel toegang tot uw cloudtoepassingen, productfuncties en services.

>[!AVAILABILITY]
>
>De gebruikersinterface van het Web van de campagne is slechts beschikbaar aan gebruikers die met Adobe Campaign met hun Adobe ID verbinden. Leer meer over [&#x200B; het Systeem van Adobe Identity Management (IMS) &#x200B;](https://helpx.adobe.com/nl/enterprise/using/identity.html){target="_blank"}.
>

Leer hoe te met Adobe Experience Cloud te verbinden, en tot de interface van het Web van Adobe Campaign [&#x200B; in deze pagina &#x200B;](campaign-ui.md#ac-web-ui) toegang te hebben.

Leer meer in de [&#x200B; gebruikersinterfacedocumentatie van het Web van Adobe Campaign &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

### Webtoegang {#web-access}

Bepaalde delen van de toepassing zijn toegankelijk via een webbrowser via een HTML-gebruikersinterface: rapportage, goedkeuring van levering, controle van instanties en meer.

De toegang van het Web verstrekt een interface die aan de console maar met een verminderde reeks functionaliteiten gelijkaardig is.

Bijvoorbeeld, voor een bepaalde exploitant, zal een campagne met de volgende opties in de console verschijnen:

![](assets/campaign-from-console.png)

Terwijl met de toegang van het Web, de opties hoofdzakelijk het bekijken zullen toelaten:

![](assets/campaign-from-web.png)

De toegang van het Web wordt ook gebruikt aan in het bevestigingsproces: de exploitanten kunnen op het goedkeuringsverzoek e-mail klikken en met Campagne verbinden door hun Webbrowser om een leveringsinhoud of een budget te bevestigen of te verwerpen.

De URL is: `https://<your adobe campaign server>:<port number>/view/home` om vanaf het web toegang te krijgen tot uw instantie Campagne.
