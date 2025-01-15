---
title: Campagne-gebruikersinterface detecteren
description: Leer hoe u door de gebruikersinterface van Campagne kunt bladeren en deze kunt gebruiken
feature: Overview
role: User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 87426a5924e1044faf212631ba868753ae43fad6
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 1%

---

# De gebruikersinterface detecteren {#ui-client-console}

U kunt tot Adobe Campaign via zijn cliëntconsole of zijn gebruikersinterface van het Web toegang hebben. U kunt ook API&#39;s gebruiken om gegevens te beheren en taken uit te voeren in uw campagneplatform.

>[!CAUTION]
>
>Deze documentatie is geconcentreerd op het gebruik van de console van de Cliënt van de Campagne. Als u het de gebruikersinterface van het Web van de Campagne gebruikt, verwijs naar [ deze documentatie ](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html) {target="_blank"}.

* **de console van de Cliënt** - de cliëntconsole van de campagne is een inheemse toepassing die met de de toepassingsserver van Adobe Campaign door standaard Internet protocollen, zoals SOAP en HTTP communiceert. De de cliëntconsole van de campagne centraliseert alle mogelijkheden en montages, en vereist minimale bandbreedte aangezien het op een lokaal geheime voorgeheugen baseert. Campagne-clientconsole is ontworpen voor eenvoudige implementatie en kan worden geïmplementeerd vanuit een internetbrowser, automatisch worden bijgewerkt. Hiervoor is geen specifieke netwerkconfiguratie nodig omdat alleen HTTP(S)-verkeer wordt gegenereerd. [Meer informatie](#ui-access)

  Leer hoe te om de cliëntconsole van de Campagne in [ te installeren en te vormen deze sectie ](../start/connect.md).

* **gebruikersinterface van het Web** - als een gebruiker van de Campagne v8, die versie v8.6.1 begint, hebt u nu toegang tot een Webmilieu, beschikbaar door het centrale gebruikersinterface van Adobe Experience Cloud. Vervolgens kunt u vanuit een webbrowser verbinding maken met Adobe Campaign. Met deze nieuwe interface kunt u belangrijke marketingacties maken, beheren en uitvoeren. Alle campagnemogelijkheden zijn echter niet beschikbaar. [Meer informatie](#ac-web-ui).

* **toegang van het Web** - de mogelijkheden van de het Webtoegang van Adobe Campaign laten u tot een ondergroep van de eigenschappen van de Campagne met Webbrowser toegang hebben, gebruikend een gebruikersinterface van HTML. Gebruik deze webinterface om rapporten te openen, berichten te besturen en te valideren, toegang te krijgen tot controledashboards en nog veel meer.  Leer meer over de Toegang van het Web van de Campagne [ in deze sectie ](../start/connect.md#web-access).

* **APIs** - om meer gebruiksgevallen te richten, kan het systeem van externe toepassingen worden geroepen gebruikend de Diensten APIs van het Web die via het SOAP protocol worden blootgesteld. Leer meer over Campagne APIs [ in deze pagina ](../dev/api.md).


## Werken met de clientconsole {#ui-access}

Campagne-clientconsole is een native toepassing die communiceert met de Adobe Campaign-toepassingsserver via standaard internetprotocollen, zoals SOAP en HTTP. De de cliëntconsole van de campagne centraliseert alle mogelijkheden en montages, en vereist minimale bandbreedte aangezien het op een lokaal geheime voorgeheugen baseert. Campagne-clientconsole is ontworpen voor eenvoudige implementatie en kan worden geïmplementeerd vanuit een internetbrowser, automatisch worden bijgewerkt. Hiervoor is geen specifieke netwerkconfiguratie nodig omdat alleen HTTP(S)-verkeer wordt gegenereerd.  [ Leer meer over de cliëntconsole van de Campagne ](../start/connect.md). U kunt op het gebruikersinterface van het Web van de Campagne van de specifieke kaart in de homepage van de cliëntconsole schakelen.

![](assets/web-ui.png)


>[!NOTE]
>
>Als de nieuwe toegangskaart niet wordt getoond, gelieve ervoor te zorgen dat de volgende gebieden niet leeg binnen uw externe rekening van Adobe Experience Cloud worden verlaten: **Server**, **Aannemer**, **Callback server**, en **het teken van de Vereniging**.


U kunt ook een webbrowser gebruiken om toegang te krijgen tot Campagne. In dit verband is slechts een subset van campagnemogelijkheden beschikbaar. [Meer informatie](#web-browser)

### Door de interface bladeren {#ui-browse}

Zodra u met de cliëntconsole van de Campagne wordt verbonden, hebt u toegang tot de homepage. Blader door de koppelingen naar toegangsmogelijkheden. Welke mogelijkheden beschikbaar zijn in de interface, is afhankelijk van uw opties en machtigingen.

Vanuit het centrale gedeelte van de startpagina gebruikt u koppelingen voor toegang tot het Help-materiaal voor campagnes, de community en de ondersteuningswebsite. Gebruik de centrale kaarten om het nieuwe de gebruikersinterface van het Web van de Campagne, en het Controlebord van de Campagne te doorbladeren.

Blader door de tabbladen in de bovenste sectie naar de mogelijkheden van de Campagne-sleutel:

![](assets/overview-home.png)

>[!NOTE]
>
>De lijst met kernmogelijkheden waartoe u toegang hebt, is afhankelijk van uw machtigingen en uw implementatie.

Voor elke mogelijkheid hebt u toegang tot de set met sleutelfuncties in de sectie **[!UICONTROL Browsing]** . Met de koppeling **[!UICONTROL More]** hebt u toegang tot alle andere componenten.

Wanneer u bijvoorbeeld naar het tabblad **[!UICONTROL Profiles and targets]** bladert, hebt u toegang tot de lijsten met ontvangers, abonnementsservices, bestaande workflows voor activering en de sneltoetsen voor het maken van al deze componenten.

![](assets/overview-list.png)

Wanneer u een element op het scherm selecteert, wordt het in een nieuw lusje geladen zodat u gemakkelijk inhoud kunt doorbladeren.

![](assets/new-tab.png)

### Een element maken {#create-an-element}

Gebruik sneltoetsen in de sectie **[!UICONTROL Create]** links van het scherm om nieuwe elementen toe te voegen. U kunt ook de knop **[!UICONTROL Create]** boven de lijst gebruiken om nieuwe elementen toe te voegen aan de huidige lijst.

Gebruik bijvoorbeeld op de leveringspagina de knop **[!UICONTROL Create]** om een nieuwe levering te maken.

![](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

[Learn more about Campaign web access](../start/connect.md#web-access).-->

### Campagneverkenner openen {#ac-explorer-ui}

Blader in Campagneverkenner om alle Adobe Campaign-mogelijkheden en -instellingen te openen.

![](assets/explorer.png)

In deze werkruimte hebt u toegang tot de Explorer-structuur om door alle functies en opties te bladeren.

* De linkersectie toont de boom van de Ontdekkingsreiziger van de Campagne en laat u alle componenten en montages van uw instantie doorbladeren - die op uw toestemmingen wordt gebaseerd. U kunt omslagen toevoegen en aanpassen zoals die in [ wordt verklaard deze pagina ](../audiences/folders-and-views.md).

* In de bovenste sectie ziet u de lijst met records in de huidige map. Deze lijsten zijn volledig aanpasbaar. [Meer informatie](../config/ui-settings.md)

* In de onderste sectie worden de details van de geselecteerde record weergegeven.


## Gebruikersinterface Campagne Web {#ac-web-ui}

Als gebruiker van de Campagne v8 clientconsole, die versie v8.6.1 begint, hebt u nu toegang tot een webomgeving die beschikbaar is via de centrale Adobe Experience Cloud-gebruikersinterface. Experience Cloud is de geïntegreerde familie van digitale marketingtoepassingen, producten en diensten van de Adobe. Via de intuïtieve interface hebt u snel toegang tot uw cloudtoepassingen, productfuncties en services.

![ Web van Adobe Campaign Web User Interface Homepage ](assets/ac-web-home.png)

>[!AVAILABILITY]
>De gebruikersinterface van het Web van de campagne is slechts beschikbaar aan gebruikers die met Adobe Campaign met hun Adobe ID verbinden. Leer meer over [ het Systeem van Identity Management van de Adobe (IMS) ](https://helpx.adobe.com/enterprise/using/identity.html) {target="_blank"}.
>

Leer meer over het nieuwe Gebruikersinterface van het Web van de Campagne in [ deze documentatie ](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html) {target="_blank"}.

Aanvullende en geavanceerde mogelijkheden, configuratie en instellingen zijn alleen beschikbaar in de clientconsole. Leer meer over mogelijkheden beschikbaar in beide gebruikersinterfaces [ in de documentatie van het gebruikersinterface van het Web van de Campagne ](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html) {target="_blank"}.


## Ondersteunde talen {#languages}

Welke talen worden ondersteund, is afhankelijk van de gebruikersinterface.

* Voor de Campagne v8 client console-interface worden de volgende talen ondersteund:

   * Engels (VK)
   * Engels (VS)
   * Frans
   * Duits
   * Japans


  >[!CAUTION]
  >
  >De taal wordt tijdens het installatieproces geselecteerd en kan daarna niet worden gewijzigd.

* Voor het gebruikersinterface van het Web van de Campagne gesteunde talen, [ verwijzen naar deze pagina ](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html#language-pref) {target="_blank"}.


Taal is van invloed op datums en tijdnotaties.

De belangrijkste verschillen tussen het Engels van de VS en het Engels van het Verenigd Koninkrijk zijn:

<table> 
 <thead> 
  <tr> 
   <th> Formaten <br /> </th> 
   <th> Engels (VS) <br /> </th> 
   <th> Engels (EN) <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Datum <br /> </td> 
   <td> Week begint op zondag <br /> </td> 
   <td> Week begint op maandag <br /> </td> 
  </tr> 
  <tr> 
   <td> Korte datum <br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>ex: 25-09-2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>ex: 25-09-2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Korte datum met tijd <br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>ex: 09/25/2018 10 :47: 25 PM</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>ex: 25/09/2018 22 :47: 25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
