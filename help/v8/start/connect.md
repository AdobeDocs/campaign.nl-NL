---
product: Adobe Campaign
title: Verbinding maken met Campagne v8
description: Leer hoe u verbinding maakt met Campagne v8
feature: Doelgroepen
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: a468597714e3974c85e4ada3b6c2ee405717106a
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# Verbinding maken met Adobe Campaign v8{#gs-ac-connect}

De Console van de Cliënt van de campagne is een rijke cliënt die u toelaat om met uw de toepassingsserver(s) van de Campagne te verbinden.

Voordat u begint, moet u:

* Controleer de compatibiliteit van uw systeem en gereedschappen met Adobe Campaign in de [Compatibiliteitsmatrix](compatibility-matrix.md)
* URL van campagneserver ophalen
* Adobe ID maken of je gebruikersnaam van je bedrijf ophalen

## De clientconsole downloaden en installeren

Wanneer u voor het eerst campagne gebruikt of wanneer u een upgrade naar een nieuwere versie moet uitvoeren, moet u de clientconsole downloaden en installeren.

Er zijn twee opties beschikbaar:

1. Als beheerder van de Campagne, verbind met Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html) en download het de installatieprogramma van de Console van de Cliënt. U kunt de toepassing vervolgens op uw lokale computer installeren.

1. Als eindgebruiker, kan Adobe de Console voor u opstellen: zodra de Console is bijgewerkt, wordt u gevraagd om de nieuwste versie van de Client Console te downloaden in een pop-upvenster.

>[!CAUTION]
>
>Adobe raadt u aan de optie **[!UICONTROL No longer ask this question]** uit te schakelen om ervoor te zorgen dat alle gebruikers worden gewaarschuwd wanneer een nieuwe versie van de console beschikbaar is.  Als deze optie is geselecteerd, wordt de gebruiker niet op de hoogte gesteld van nieuwe beschikbare versies.

## Verbinding maken

Nadat de clientconsole is geïnstalleerd, voert u de onderstaande stappen uit om de verbinding met de toepassingsserver tot stand te brengen:

1. Start de console vanuit het menu Windows **[!UICONTROL Start]** in de programmagroep **Adobe Campaign**.

1. Klik op de koppeling in de rechterbovenhoek van de aanmeldingsvelden om het venster voor de verbindingsconfiguratie te openen.

1. Klik op **[!UICONTROL Add > Connection]** en voer het label en de URL van de Adobe Campaign-toepassingsserver in.

1. Geef een verbinding met uw Adobe Campaign-toepassingsserver op via een URL. Gebruik of DNS of een alias van de machine, of uw IP adres.

   U kunt bijvoorbeeld de URL van het type [`https://<machine>.<domain>.com`](https://myserver.adobe.com) gebruiken.

1. Schakel de optie  in **[!UICONTROL Connect with an Adobe ID]**.

1. Klik **[!UICONTROL Ok]** om uw montages te bewaren.

U kunt zo veel verbindingen toevoegen als u nodig hebt om bijvoorbeeld verbinding te maken met uw test-, stage- en productieomgeving.

>[!NOTE]
>
>Met de knop **[!UICONTROL Add]** kunt u **[!UICONTROL folders]** maken om al uw verbindingen te organiseren. U hoeft alleen elke verbinding naar een map te slepen.

## Aanmelden bij Adobe Campaign

Volg onderstaande stappen om u aan te melden bij een bestaande instantie:

1. Start de console vanuit het menu Windows **[!UICONTROL Start]** in de programmagroep **Adobe Campaign**.

1. Klik op de koppeling in de rechterbovenhoek van de aanmeldingsvelden om het venster voor de verbindingsconfiguratie te openen.

   ![](assets/connectToCampaign.png)

1. Selecteer de instantie Campagne waaraan u zich moet aanmelden.

1. Klik op **[!UICONTROL Ok]**.

1. U kunt zich dan aanmelden bij Campagne met [uw Adobe ID](#connect-ims).

   ![](assets/adobeID.png)

## Toegang verlenen aan gebruikers

Met Adobe Campaign kunt u de rechten definiëren en beheren die aan de verschillende operatoren zijn toegewezen. Dit zijn een reeks rechten en beperkingen die autoriseren of weigeren:

* Toegang tot bepaalde functies (via genoemde rechten);
* Toegang tot bepaalde elementen
* Elementen maken, wijzigen en/of verwijderen (levering, contactpersonen, campagnes, groepen, enz.).

Leer meer over gebruikers en hoe te om hun toestemmingen in [dit sectie](permissions.md) te bepalen.

Als campagnebeheerder bent u verantwoordelijk voor het maken van de operatoren en het delen van hun referenties met de gebruikers.

## Verbinden met Campagne met uw Adobe ID{#connect-ims}

Campagnegebruikers maken via hun Adobe ID verbinding met de Adobe Campaign-console via het Adobe Identity Management System (IMS). Ze kunnen dezelfde id gebruiken voor alle Adobe-oplossingen. De verbinding wordt bewaard wanneer het gebruiken van Adobe Campaign met andere oplossingen.

Meer informatie over Adobe IMS in [deze pagina](https://helpx.adobe.com/enterprise/using/identity.html).

## Webtoegang{#web-access}

Bepaalde delen van de toepassing zijn toegankelijk via een webbrowser via een HTML-gebruikersinterface: rapportage, goedkeuring van levering, controle van instanties, en meer.

De toegang van het Web verstrekt een interface die aan de console maar met een verminderde reeks functionaliteiten gelijkaardig is.

Bijvoorbeeld, voor een bepaalde exploitant, zal een campagne met de volgende opties in de console verschijnen:

![](assets/campaign-from-console.png)

Terwijl met de toegang van het Web, de opties hoofdzakelijk het bekijken zullen toelaten:

![](assets/campaign-from-web.png)

De toegang van het Web wordt ook gebruikt aan in het bevestigingsproces: operators kunnen klikken op de goedkeuringsaanvraag per e-mail en via hun webbrowser verbinding maken met Campagne om een leveringsinhoud of -budget te valideren of af te wijzen.

De URL is:  `https://<your adobe campaign server>:<port number>/view/home`.
