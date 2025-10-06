---
title: Campagne-gebruikersinterface detecteren
description: Leer hoe u door de gebruikersinterface van Campagne kunt bladeren en deze kunt gebruiken
feature: Overview
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: fbde111671fb972f6c96ba45eba4c8a88dbcac64
workflow-type: tm+mt
source-wordcount: '1121'
ht-degree: 1%

---

# De gebruikersinterface detecteren {#ui-client-console}

U kunt tot Adobe Campaign via zijn cliëntconsole of zijn gebruikersinterface van het Web toegang hebben. U kunt ook API&#39;s gebruiken om gegevens te beheren en taken uit te voeren in uw campagneplatform.

* **de console van de Cliënt** - de cliëntconsole van de campagne is een inheemse toepassing die met de de toepassingsserver van Adobe Campaign door standaard Internet protocollen, zoals SOAP en HTTP communiceert. De de cliëntconsole van de campagne centraliseert alle mogelijkheden en montages, en vereist minimale bandbreedte aangezien het op een lokaal geheime voorgeheugen baseert. Campagne-clientconsole is ontworpen voor eenvoudige implementatie en kan worden geïmplementeerd vanuit een internetbrowser, automatisch worden bijgewerkt. Hiervoor is geen specifieke netwerkconfiguratie nodig omdat alleen HTTP(S)-verkeer wordt gegenereerd. [Meer informatie](#ui-access)

  Leer hoe te om de cliëntconsole van de Campagne in [&#x200B; te installeren en te vormen deze sectie &#x200B;](../start/connect.md).

* **toegang van het Web** - de mogelijkheden van de het Webtoegang van Adobe Campaign laten u tot een ondergroep van de eigenschappen van de Campagne met Webbrowser toegang hebben, gebruikend een gebruikersinterface van HTML. Gebruik deze webinterface om rapporten te openen, berichten te besturen en te valideren, toegang te krijgen tot controledashboards en nog veel meer.  Leer meer over de Toegang van het Web van de Campagne [&#x200B; in deze sectie &#x200B;](../start/connect.md#web-access).

* **APIs** - om meer gebruiksgevallen te richten, kan het systeem van externe toepassingen worden geroepen gebruikend de Diensten APIs van het Web die via het protocol van SOAP worden blootgesteld. Leer meer over Campagne APIs [&#x200B; in deze pagina &#x200B;](../dev/api.md).

* **gebruikersinterface van het Web** - als een gebruiker van de Campagne v8, die versie v8.6.1 begint, hebt u nu toegang tot een Webmilieu, beschikbaar door het centrale gebruikersinterface van Adobe Experience Cloud. Vervolgens kunt u vanuit een webbrowser verbinding maken met Adobe Campaign. Met deze nieuwe interface kunt u belangrijke marketingacties maken, beheren en uitvoeren. Alle campagnemogelijkheden zijn echter niet beschikbaar. [Meer informatie](#ac-web-ui).

  >[!AVAILABILITY]
  >
  >De gebruikersinterface van het Web van de campagne is slechts beschikbaar aan gebruikers van de Campagne v8 die met Campagne met hun Adobe ID verbinden. Leer meer over [&#x200B; het Systeem van Adobe Identity Management (IMS) &#x200B;](https://helpx.adobe.com/nl/enterprise/using/identity.html){target="_blank"}.
  >

>[!CAUTION]
>
>Deze documentatie is geconcentreerd op het gebruik van de console van de Cliënt van de Campagne. Als een gebruiker van de Campagne v8, als u het de gebruikersinterface van het Web van de Campagne gebruikt, verwijs naar [&#x200B; deze documentatie &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=nl-NL){target="_blank"}.

## Werken met de clientconsole {#ui-access}

Campagne-clientconsole is een native toepassing die communiceert met de Adobe Campaign-toepassingsserver via standaard internetprotocollen, zoals SOAP en HTTP. De de cliëntconsole van de campagne centraliseert alle mogelijkheden en montages, en vereist minimale bandbreedte aangezien het op een lokaal geheime voorgeheugen baseert. Campagne-clientconsole is ontworpen voor eenvoudige implementatie en kan worden geïmplementeerd vanuit een internetbrowser, automatisch worden bijgewerkt. Hiervoor is geen specifieke netwerkconfiguratie nodig omdat alleen HTTP(S)-verkeer wordt gegenereerd.  [&#x200B; Leer meer over de cliëntconsole van de Campagne &#x200B;](../start/connect.md).



>[!BEGINTABS]

>[!TAB Campaign v8]

Zodra u met Campagne wordt verbonden, hebt u toegang tot de homepage van Adobe Campaign. In Campagne v8, gebruik de centrale kaarten om het nieuwe de gebruikersinterface van het Web van de Campagne, en het Controlebord van de Campagne te doorbladeren.

![&#x200B; het Huis van de Console van de Cliënt van de Campagne v8 &#x200B;](assets/web-ui.png)

>[!NOTE]
>
>Als de kaart van het gebruikersinterface van het Web niet wordt getoond, zorg ervoor dat de volgende gebieden niet leeg binnen uw externe rekening van Experience Cloud van A [&#x200B; worden verlaten &#x200B;](../config/external-accounts.md): **Server**, **Haakzame**, **Callback server**, en **het teken van de Vereniging**.

U kunt tot het [&#x200B; Controlebord van de Campagne &#x200B;](../config/self-service.md) van de homepage ook toegang hebben.

>[!TAB Campaign Classic v7]

Zodra u met Campagne wordt verbonden, hebt u toegang tot de homepage van Adobe Campaign met verbindingen en kortere weg aan toegangsmogelijkheden, documentatie, steunwebsite, en de gemeenschap van de Campagne.

![&#x200B; Campaign Classic v7 het Huis van de Console van de Cliënt 1&rbrace;](assets/v7_user_interface_home.png)


>[!ENDTABS]


U kunt ook een webbrowser gebruiken om toegang te krijgen tot Campagne. In dit verband is slechts een subset van campagnemogelijkheden beschikbaar. [Meer informatie](#web-browser)

### Door de interface bladeren {#ui-browse}

Als u eenmaal verbinding hebt met de Campagne-clientconsole, bladert u door de tabbladen in de bovenste sectie naar de mogelijkheden van de Campagne-sleutel:

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

* De linkersectie toont de boom van de Ontdekkingsreiziger van de Campagne en laat u alle componenten en montages van uw instantie doorbladeren - die op uw toestemmingen wordt gebaseerd. U kunt omslagen toevoegen en aanpassen zoals die in [&#x200B; wordt verklaard deze pagina &#x200B;](../audiences/folders-and-views.md).

* In de bovenste sectie ziet u de lijst met records in de huidige map. Deze lijsten zijn volledig aanpasbaar. [Meer informatie](../config/ui-settings.md)

* In de onderste sectie worden de details van de geselecteerde record weergegeven.


## Gebruikersinterface Campagne Web {#ac-web-ui}

Als gebruiker van Campagne v8, die versie 8.6.1 begint, hebt u toegang tot een Webmilieu, beschikbaar door de centrale gebruikersinterface van Adobe Experience Cloud. Experience Cloud is een geïntegreerde Adobe-reeks met digitale marketingtoepassingen, producten en services. Via de intuïtieve interface hebt u snel toegang tot uw cloudtoepassingen, productfuncties en services.

![&#x200B; Web van Adobe Campaign Web User Interface Homepage &#x200B;](assets/ac-web-home.png)

>[!AVAILABILITY]
>
>De gebruikersinterface van het Web van de campagne is slechts beschikbaar aan gebruikers van de Campagne v8 die met Campagne met hun Adobe ID verbinden. Leer meer over [&#x200B; het Systeem van Adobe Identity Management (IMS) &#x200B;](https://helpx.adobe.com/nl/enterprise/using/identity.html){target="_blank"}.
>

Leer meer over het nieuwe Gebruikersinterface van het Web van de Campagne in [&#x200B; deze documentatie &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=nl-NL){target="_blank"}. U kunt de specifieke [&#x200B; Veelgestelde pagina van Vragen &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-web/v8/start/faq){target="_blank"}, in de documentatie van het Gebruikersinterface van het Web van de Campagne ook bezoeken.

Aanvullende en geavanceerde mogelijkheden, configuratie en instellingen zijn alleen beschikbaar in de clientconsole. Leer meer over mogelijkheden beschikbaar in beide gebruikersinterfaces [&#x200B; in de documentatie van het het gebruikersinterface van het Web van de Campagne &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html?lang=nl-NL){target="_blank"}.


## Ondersteunde talen {#languages}

Welke talen worden ondersteund, is afhankelijk van de gebruikersinterface.

* Voor de interface van de clientconsole van Campagne zijn de ondersteunde talen:

   * Engels (VK)
   * Engels (VS)
   * Frans
   * Duits
   * Japans


  >[!CAUTION]
  >
  >De taal wordt geselecteerd tijdens het installatieproces, en **kan niet** achteraf worden veranderd.

* Voor het gebruikersinterface van het Web van de Campagne gesteunde talen, [&#x200B; verwijzen naar deze pagina &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html?lang=nl-NL#language-pref){target="_blank"}.

## Indelingen

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
   <td> <p>%2M/%2D/%4Y</p><p><strong>ex: 25-09-2025</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>ex: 25-09-2025</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Korte datum met tijd <br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>ex: 09/25/2025 10 :47: 25 PM</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>ex: 25/09/2025 22 :47: 25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>


## Aanvullende bronnen

* **[Werk met Opsommingen](../dev/enumerations.md)** - normaliseer gebiedswaarden met vooraf bepaalde drop-down lijsten voor snellere, consistentere gegevensingang.
* **[Opsommingen in schema&#39;s](../dev/schema-structure.md#enumerations)** - als ontwikkelaar van de Campagne, gebruik vrije, vaste, of op gegevensbestand-gebaseerde opsommingen in uw schema&#39;s om gebiedswaarden te controleren.