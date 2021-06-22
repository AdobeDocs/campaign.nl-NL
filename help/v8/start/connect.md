---
product: Adobe Campaign
title: Verbinding maken met Campagne v8
description: Leer hoe u verbinding maakt met Campagne v8
feature: Doelgroepen
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 3%

---

# Verbinding maken met Adobe Campaign v8{#gs-ac-connect}

De Console van de Cliënt van de campagne is een rijke cliënt die u toelaat om met uw de toepassingsserver(s) van de Campagne te verbinden.

Voordat u begint, moet u:

* Controleer de compatibiliteit van uw systeem en gereedschappen met Adobe Campaign in de [Compatibiliteitsmatrix](compatibility-matrix.md)
* URL van campagneserver ophalen
* Je gebruikersgegevens ophalen

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

1. Als Adobe Identity Management System (IMS) is geconfigureerd voor uw organisatie, controleert u de optie **[!UICONTROL Connect with an Adobe ID]**.

1. Klik **[!UICONTROL Ok]** om uw montages te bewaren.

U kunt zo veel verbindingen toevoegen als u nodig hebt om bijvoorbeeld verbinding te maken met uw test-, stage- en productieomgeving.

>[!NOTE]
>
>Met de knop **[!UICONTROL Add]** kunt u **[!UICONTROL folders]** maken om al uw verbindingen te organiseren. U hoeft alleen elke verbinding naar een map te slepen.

## Aanmelden bij Adobe Campaign

Volg onderstaande stappen om u aan te melden bij een bestaande instantie:

1. Start de console vanuit het menu Windows **[!UICONTROL Start]** in de programmagroep **Adobe Campaign**.

1. Klik op de koppeling in de rechterbovenhoek van de aanmeldingsvelden om het venster voor de verbindingsconfiguratie te openen.

1. Selecteer de instantie Campagne waaraan u zich moet aanmelden.

1. Klik op **[!UICONTROL Ok]**.

1. Voer uw aanmeldingsgegevens voor de gebruiker in en klik op **[!UICONTROL LOG IN]**.

   ![](assets/sign-in-v8.png)

Afhankelijk van uw configuratie, kunnen uw geloofsbrieven zijn:

* verstrekt door uw beheerder van de Campagne die u toegang verleende
* Adobe ID

## Toegang verlenen aan gebruikers

Met Adobe Campaign kunt u de rechten definiëren en beheren die aan de verschillende operatoren zijn toegewezen. Dit zijn een reeks rechten en beperkingen die autoriseren of weigeren:

* Toegang tot bepaalde functies (via genoemde rechten);
* Toegang tot bepaalde elementen
* Elementen maken, wijzigen en/of verwijderen (levering, contactpersonen, campagnes, groepen, enz.).

Leer meer over gebruikers en hoe te om hun toestemmingen in [dit sectie](permissions.md) te bepalen.

Als campagnebeheerder bent u verantwoordelijk voor het maken van de operatoren en het delen van hun referenties met de gebruikers.

## Verbinden met Campagne met uw Adobe ID{#connect-ims}

Campagnegebruikers kunnen verbinding maken met de Adobe Campaign-console via hun Adobe ID, via Adobe Identity Management System (IMS). Deze implementatie biedt de volgende voordelen:

* Dezelfde id kan voor alle Experience Cloud-oplossingen worden gebruikt.
* De verbinding wordt onthouden bij het gebruik van Adobe Campaign met verschillende integraties.
* Meer beleid voor wachtwoordbeheer.
* Gebruik van Federated ID-accounts (externe id-provider).

[!DNL :speech_balloon:] Als Beheerde gebruiker van Cloud Services,  [contacteer ](campaign-faq.md#support) Adobe om Adobe IMS met Campagne uit te voeren.

## Verbinden met Campagne met uw login LDAP

Adobe Campaign kan zo worden geconfigureerd dat de gebruiker toegang krijgt tot het platform via de LDAP-verificatie.

[!DNL :speech_balloon:] Als gebruiker van Beheerde Cloud Services,  [contacteer ](campaign-faq.md#support) Adobe om LDAP integratie met Campagne te vormen.


## Webtoegang{#web-access}

Bepaalde delen van de toepassing zijn via een eenvoudige webbrowser toegankelijk via een HTML-gebruikersinterface: Campagne-dashboard, kubusrapportage, Instance Monitoring en meer.

[!DNL :arrow_upper_right:] Meer informatie over webtoegang in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#console-and-web-access){target=&quot;_blank&quot;}

De toegang van het Web verstrekt een interface die aan de console, maar met een gereduceerde reeks functionaliteiten gelijkaardig is.

Bijvoorbeeld, voor een bepaalde exploitant, zal een campagne met de volgende opties in de console verschijnen:

![](assets/campaign-from-console.png)

Terwijl met de toegang van het Web, de opties hoofdzakelijk het bekijken zullen toelaten:

![](assets/campaign-from-web.png)

De toegang van het Web wordt ook gebruikt aan in het bevestigingsproces: operators kunnen klikken op de goedkeuringsaanvraag per e-mail en via hun webbrowser verbinding maken met Campagne om een leveringsinhoud of -budget te valideren of af te wijzen.

[!DNL :arrow_upper_right:] Leer hoe u goedkeuringen instelt en beheert in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns){target=&quot;_blank&quot;}
