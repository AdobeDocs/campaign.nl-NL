---
title: Globale Adobe Campaign-rapporten
description: Leer hoe u algemene rapporten kunt openen en gebruiken
feature: Reporting, Monitoring
role: User, Data Engineer
exl-id: 6e3409d8-86bd-44ba-a40d-10287f53a960
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '1750'
ht-degree: 2%

---

# Algemene rapporten {#global-reports}

Deze rapporten hebben betrekking op de activiteit van de gegevens in de gehele database. Ga naar het tabblad **[!UICONTROL Reports]** als u het dashboard met rapporten wilt weergeven.

![](assets/reports-tab.png)

Klik op de naam van de rapporten om deze weer te geven. De volgende rapporten zijn standaard beschikbaar:

![](assets/report-global-list.png)

>[!NOTE]
>
>In deze sectie worden alleen de rapporten weergegeven die betrekking hebben op leveringen.

* **[!UICONTROL Delivery throughput]**: verwijs naar [ productie van de Levering ](#delivery-throughput).
* **[!UICONTROL Browsers]**: verwijs naar [ Browsers ](#browsers).
* **[!UICONTROL Sharing to social networks]**: verwijs naar [ het Delen aan sociale netwerken ](#sharing-to-social-networks).
* **[!UICONTROL Statistics on sharing activities]**: verwijs naar [ Statistieken over het delen van activiteiten ](#statistics-on-sharing-activities).
* **[!UICONTROL Operating systems]**: verwijs naar [ Werkende systemen ](#operating-systems).
* **[!UICONTROL URLs and click streams]**: verwijs naar [ URLs en klik stromen ](delivery-reports.md#urls-and-click-streams).
* **[!UICONTROL Tracking indicators]**: verwijs naar [ het Volgen indicatoren ](delivery-reports.md#tracking-indicators).
* **[!UICONTROL Non-deliverables and bounces]**: verwijs naar [ Niet-te leveren punten en stuitingen ](#non-deliverables-and-bounces).
* **[!UICONTROL User activities]**: verwijs naar [ activiteiten van de Gebruiker ](#user-activities).
* **[!UICONTROL Subscription tracking]**: verwijs naar [ het volgen van het Abonnement ](#subscription-tracking).
* **[!UICONTROL Delivery summary]**: verwijs naar [ Overzicht van de Levering ](delivery-reports.md#delivery-summary).
* **[!UICONTROL Delivery statistics]**: verwijs naar [ statistieken van de Levering ](#delivery-statistics).
* **[!UICONTROL Breakdown of opens]**: verwijs naar [ Uitsplitsing van opent ](#breakdown-of-opens).

## Leveringsdoorvoer {#delivery-throughput}

Dit verslag bevat informatie over de leveringsproductie van het gehele platform voor een bepaalde periode. Om de snelheid te meten waarbij de berichten worden geleverd, zijn de criteria het aantal berichten die per uur worden verzonden en de grootte van de berichten (in beetjes per seconde). In het onderstaande voorbeeld ziet u in de eerste grafiek de geslaagde leveringen in blauw en het aantal onjuiste leveringen in oranje.

![](assets/report-toolbar.png)

U kunt de weergegeven waarden configureren door de tijdschaal te wijzigen: een weergave van 1 uur, een weergave van 3 uur, een weergave van 24 uur, enzovoort. Klik op **[!UICONTROL Refresh]** om uw selectie te bevestigen.

>[!NOTE]
>
>U kunt het aantal leveringen ook controleren die per uur gebruikend het [ Controlebord ](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/sftp-storage-management.html){target="_blank"} worden verzonden.
>
>Het configuratiescherm is toegankelijk voor alle gebruikers met beheerdersrechten. De stappen om toegang met beheerdersrechten aan een gebruiker te verlenen worden gedetailleerd beschreven op [deze pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=nl#discover-control-panel){target="_blank"}.
>

## Gebruikersactiviteiten {#user-activities}

Dit rapport toont de uitsplitsing van opent, klikt en transacties per half uur, uur of dag, in de vorm van een grafiek.

De volgende opties zijn beschikbaar:

* **[!UICONTROL Opens]**: Het totale aantal geopende berichten. E-mails in tekstindeling worden niet in aanmerking genomen. [Meer informatie](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]**: Het totale aantal klikken op koppelingen in leveringen. Er wordt geen rekening gehouden met klikken op abonnementkoppelingen en spiegelpagina&#39;s.
<!--
* **[!UICONTROL Transactions]**: Total number of transactions after a message is received. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->

## Niet-leverbare items en niet-bezorgingen {#non-deliverables-and-bounces}

Dit verslag geeft een overzicht van de niet-te leveren posten en een uitsplitsing van de bedragen per internetdomein.

**[!UICONTROL Number of messages processed]** vertegenwoordigt het totale aantal berichten die door de leveringsserver worden verwerkt. Deze waarde is lager dan het aantal berichten dat moet worden afgeleverd wanneer bepaalde leveringen zijn gestopt of gepauzeerd (voordat deze door de server worden verwerkt).

**[!UICONTROL Breakdown of errors by type]**

>[!NOTE]
>
>De fouten die in dit rapport worden weergegeven, activeren het quarantaineproces. Voor meer op quarantainebeheer, verwijs naar [ het beheer van de quarantaine ](../send/quarantines.md).

In het eerste deel van dit verslag wordt de uitsplitsing van niet-te leveren producten in de vorm van een tabel van waarden en een grafiek weergegeven.

Voor elk fouttype hebben we:

* het aantal foutberichten van dit type;
* het percentage berichten met dergelijke fouten in vergelijking met het totale aantal berichten met fouten;
* het percentage van foutenmeldingen van dit type vergeleken met het totale aantal verwerkte berichten.

De volgende indicatoren worden gebruikt:

* **[!UICONTROL User unknown]**: Fouttype dat tijdens de levering wordt gegenereerd om aan te geven dat het e-mailadres ongeldig is.
* **[!UICONTROL Invalid domain]**: Fouttype dat wordt gegenereerd bij het verzenden van een levering om aan te geven dat het domein van het e-mailadres onjuist is of niet bestaat.
* **[!UICONTROL Inbox full]**: Fouttype dat wordt gegenereerd na vijf leveringspogingen om aan te geven dat het Postvak IN van de ontvangers te veel berichten bevat.
* **[!UICONTROL Account disabled]**: Fouttype dat wordt gegenereerd bij het verzenden van een levering om aan te geven dat het adres niet langer bestaat.
* **[!UICONTROL Rejected]**: Het type van fout produceerde wanneer een adres door IAP (Internet Access Provider) wordt verworpen, bijvoorbeeld na de toepassing van een veiligheidsregel (anti-spamsoftware).
* **[!UICONTROL Unreachable]**: Het type van fout dat in het koord van de berichtdistributie voorkomt: incident op het relais SMTP, domein tijdelijk onbereikbaar, etc.
* **[!UICONTROL Not connected]**: Fouttype om aan te geven dat de mobiele telefoon van de ontvanger op het moment van verzending wordt uitgeschakeld of losgekoppeld van het netwerk.

  >[!NOTE]
  >
  >Deze indicator heeft op leveringen op [ mobiele kanalen ](../send/send.md) slechts betrekking.

  U kunt elke regel van de waardetabel openen door op het symbool `[+]` te klikken. Voor elk fouttype kunt u de indeling van foutberichten per domein weergeven.

**[!UICONTROL Breakdown of errors per domain]**

In het tweede gedeelte van dit rapport wordt de uitsplitsing van fouten per internetdomein getoond in de vorm van een tabel met waarden en een grafiek.

Voor elke domeinnaam hebben we:

* het aantal berichten met fouten voor dit domein,
* het percentage berichten met fouten voor dit domein in vergelijking met het totale aantal berichten dat voor dit domein wordt verwerkt;
* het percentage foutberichten voor dit domein in vergelijking met het totale aantal foutberichten.

U kunt elke lijn van de waardetabel openen door [ + ] te klikken symbool. Voor elk domeintype kunt u de indeling van foutberichten per fouttype weergeven.

![](assets/errors-report-details.png)

>[!NOTE]
>
>De domeinnamen die in dit rapport worden weergegeven, worden op kubusniveau gedefinieerd. Als u deze waarden wilt wijzigen, bewerkt u de kubus **[!UICONTROL Delivery logs (broadlogrcp)]** . Voor meer op dit, verwijs naar [ deze sectie ](gs-cubes.md). De categorie **[!UICONTROL Others]** bevat domeinnamen die niet tot een specifieke klasse behoren.

## Browsers {#browsers}

Dit verslag geeft een overzicht van de internetbrowsers die door de ontvangers van de levering voor de betrokken periode zijn gebruikt.

>[!NOTE]
>
>De waarden in dit rapport zijn schattingen: alleen ontvangers die op een levering hebben geklikt, worden in aanmerking genomen.

**Globale statistieken**

De algemene statistieken over browsergebruik worden gepresenteerd in de vorm van een tabel met waarden en een grafiek.

![](assets/browser-report.png)

De volgende indicatoren worden gebruikt:

* **[!UICONTROL Visitors]**: Het totale aantal beoogde ontvangers (per internetbrowser) nadat u minstens één keer op een levering hebt geklikt.
* **[!UICONTROL Pages viewed]**: Het totale aantal klikken op koppelingen in een levering (per internetbrowser) voor alle leveringen.
* **[!UICONTROL Usage rate]**: Deze frequentie geeft de uitsplitsing weer van bezoekers (per internetbrowser) in verhouding tot het totale aantal bezoekers.

**Statistieken per browser**

In de lijst van globale statistische waarden, kunt u elke browser naam klikken om hun gebruiksstatistieken te bekijken.

![](assets/browser-report-info.png)

Statistieken worden gepresenteerd in de vorm van een curve, een grafiek en een tabel met waarden.

De **[!UICONTROL History]** -curve geeft de aanwezigheidsgraad van deze browser per dag aan. De frequentie is de verhouding tussen het aantal bezoekers per dag (in deze browser) en het aantal bezoekers dat wordt gemeten op de dag met de hoogste aanwezigheidsgraad.

Het **[!UICONTROL Breakdown per version]** -diagram geeft de uitsplitsing weer van bezoekers per versie in vergelijking met het totale aantal bezoekers (in deze browser).

In de waardetabel worden de volgende indicatoren gebruikt:

* **[!UICONTROL Global rate]**: Deze frequentie geeft de uitsplitsing weer van bezoekers per versie in vergelijking met het totale aantal bezoekers (in alle browsers).
* **[!UICONTROL Relative rate]**: Deze frequentie geeft de uitsplitsing weer van bezoekers per versie in vergelijking met het totale aantal bezoekers (in deze browser).


<!--
### Sharing to social networks {#sharing-to-social-networks}

Viral marketing lets delivery recipients share information with their contact network: they can add a link to their profile (Facebook, Twitter, etc.) or send a message to a friend. Each share and each access to shared information is tracked within the delivery. For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

This report shows the breakdown of shared and opened messages per social network (Facebook, Twitter, etc.) and/or per email.

![](assets/s_ncs_user_social_report.png)

**[!UICONTROL Email delivery statistics]**

In the email delivery statistics, two values are displayed:

* **[!UICONTROL Number of messages to be delivered]**: Total number of messages processed during delivery analysis.
* **[!UICONTROL Number of successful deliveries]**: Number of messages processed successfully.

**[!UICONTROL Sharing activities and mail open statistics]**

The central table shows the statistics on email shares and opens.

In the **[!UICONTROL Shares]** column, we have the following indicators:

* **[!UICONTROL No. of sharing activities]**: Total number of messages shared on each social network. This value equals the total number of clicks on the icon of the matching **[!UICONTROL Links for sharing to social networks]** personalization block.
* **[!UICONTROL Breakdown]**: This rate represents the breakdown of shares per social network, in relation to the total number of shares.
* **[!UICONTROL Sharing rate]**: This rate represents the breakdown of shares per social network, in relation to the number of messages to be delivered.

In the **[!UICONTROL Opens]** column, we have the following indicators:

* **[!UICONTROL No. of opens]**: Total number of messages opened by people whom the message was forwarded to (via the **[!UICONTROL Links for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Breakdown]**: This rate represents the breakdown of opens per social network, in relation to the total number of opens.
* **[!UICONTROL Rate of opens]**: This rate represents the breakdown of opens per social network, in relation to the total number of shares.

**[!UICONTROL Breakdown of sharing activities and opens]**

This section includes two charts which represent the breakdown of sharing activities and opens per social network.


## Statistics on sharing activities {#statistics-on-sharing-activities}

This report shows the evolution of shares to social media in time.

For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

Statistics are presented in the form of a table of values and a chart.

The following indicators are used:

* **[!UICONTROL New contacts]**: Number of new subscriptions following the reception of a message shared via email. This value matches the number of people who received a message shared via email, clicked the **[!UICONTROL Subscription link]** and filled in the subscription form. 
* **[!UICONTROL Opens]**: Total number of messages opened by people whom the message was transferred to (via the **[!UICONTROL Link for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Sharing activities]**: Total number of messages shared via social networks. This value matches the total number of clicks on the icon of the **[!UICONTROL Links for sharing to social networks]** personalization block.
-->

## Besturingssystemen {#operating-systems}

Dit verslag geeft een overzicht van de exploitatiesystemen die door de ontvangers van de levering voor de betrokken periode worden gebruikt.

>[!NOTE]
>
>De waarden in dit rapport zijn schattingen: alleen ontvangers die op een levering hebben geklikt, worden in aanmerking genomen.

**Globale statistieken**

De algemene gebruiksstatistieken van besturingssystemen worden gepresenteerd in de vorm van een tabel met waarden en een grafiek.

![](assets/os-report.png)

De volgende indicatoren worden gebruikt:

* **[!UICONTROL Visitors]**: dagelijks gemiddelde van het totale aantal beoogde ontvangers (per besturingssysteem) die ten minste één keer op een levering hebben geklikt.
* **[!UICONTROL Pages viewed]**: dagelijkse gemiddelde van het totale aantal klikken op leveringskoppelingen (per besturingssysteem) voor alle leveringen.
* **[!UICONTROL Rate of use]**: Deze frequentie geeft de uitsplitsing weer van bezoekers (per besturingssysteem) in verhouding tot het totale aantal bezoekers.

**Statistieken per werkend systeem**

In de lijst van globale statistiekwaarden, klik de naam van elk werkend systeem om de statistieken per werkend systeem te bekijken.

![](assets/os-report-details.png)

Statistieken worden gepresenteerd in de vorm van een curve, een grafiek en een tabel met waarden.

De **[!UICONTROL History]** -curve geeft de gebruiksfrequentie van dit besturingssysteem per dag aan. Dit percentage is de verhouding tussen het aantal bezoekers per dag (op dit besturingssysteem) en het aantal bezoekers dat wordt gemeten op de dag met de hoogste aanwezigheid.

Het **[!UICONTROL Breakdown by version]** -diagram geeft de uitsplitsing van bezoekers per versie weer in verhouding tot het totale aantal bezoekers op dit besturingssysteem.

In de waardetabel worden de volgende indicatoren gebruikt:

* **[!UICONTROL Global rate]**: Deze frequentie geeft de uitsplitsing weer van bezoekers (per versie) in verhouding tot het totale aantal bezoekers in het besturingssysteem.
* **[!UICONTROL Relative rate]**: Deze frequentie geeft de uitsplitsing weer van bezoekers (per versie) in verhouding tot het totale aantal bezoekers voor dit besturingssysteem.

## Abonnement bijhouden {#subscription-tracking}

Met dit rapport kunt u abonnementen op informatieservices controleren. Er worden abonnementen en afkortingen weergegeven.

![](assets/service-report.png)

Deze kan voor een abonnement worden weergegeven door op het knooppunt **[!UICONTROL Profiles and targets > Services and subscriptions]** van de startpagina of de verkenner te klikken. Selecteer het gewenste abonnement en klik op de tab **[!UICONTROL Reports]** . Het rapport **[!UICONTROL Subscriptions tracking]** is standaard beschikbaar. Het laat u de abonnement en unsubscription tendensen en het loyaliteitstarief over een periode zien. U kunt de representatie van deze gegevens configureren via de vervolgkeuzelijst. Klik **[!UICONTROL Refresh]** om de geselecteerde configuratie te bevestigen.

Voor verdere informatie, verwijs naar [ deze pagina ](../start/subscriptions.md).

**[!UICONTROL Number subscribed to date]** vertegenwoordigt het totale aantal mensen momenteel geabonneerd.

**[!UICONTROL Overall evolution of subscriptions]**

In de waardetabel worden de volgende indicatoren gebruikt:

* **[!UICONTROL Subscribers]**: het totale aantal abonnees voor de betrokken periode.
* **[!UICONTROL Subscriptions]**: aantal abonnementen voor de betrokken periode.
* **[!UICONTROL Unsubscriptions]**: aantal aflossingen voor de betrokken periode.
* **[!UICONTROL Evolution]**: aantal afmeldingsopties min het aantal abonnementen. Het tarief wordt berekend op basis van het totale aantal abonnees.
* **[!UICONTROL Loyalty]**: Loyalty van abonnees voor de betrokken periode.

**[!UICONTROL Subscription evolution curves]**

Deze grafiek toont de ontwikkeling van de abonnementen en afboekingen voor de betrokken periode.

## Leveringsstatistieken {#delivery-statistics}

Dit rapport toont de uitsplitsing naar internetdomein van alle verwerkte en verzonden berichten, van harde en zachte geluiden, opent, klikt en afmeldt.

![](assets/broadcast-report.png)

De volgende indicatoren worden gebruikt:

* **[!UICONTROL Emails processed]**: Het totale aantal berichten dat door de leveringsserver wordt verwerkt.
* **[!UICONTROL Delivered]**: percentage van het aantal berichten dat is verwerkt in verhouding tot het totale aantal verwerkte berichten.
* **[!UICONTROL Hard bounces]**: percentage van het aantal &#39;harde&#39; grenzen in vergelijking met het totale aantal verwerkte berichten.
* **[!UICONTROL Soft bounces]**: percentage van het aantal &#39;zachte&#39; grenzen in vergelijking met het totale aantal verwerkte berichten.

  >[!NOTE]
  >
  >Voor meer op harde en zachte grenzen, verwijs naar [ deze pagina ](../send/quarantines.md).

* **[!UICONTROL Opens]**: percentage van het aantal beoogde ontvangers dat een bericht ten minste één keer heeft geopend in vergelijking met het aantal berichten dat met succes is verwerkt.
* **[!UICONTROL Clicks]**: percentage van het aantal personen dat ten minste één keer in een levering heeft geklikt in vergelijking met het aantal berichten dat met succes is verwerkt.
* **[!UICONTROL Unsubscription]**: percentage van het aantal klikken op een koppeling zonder abonnement in verhouding tot het aantal berichten dat met succes is verwerkt.

## Indeling van openen {#breakdown-of-opens}

In dit rapport wordt de uitsplitsing van de openingen per besturingssysteem, apparaat en browser voor de betrokken periode weergegeven. Voor elke categorie worden twee grafieken gebruikt. De eerste toont statistieken betreffende opent op een computer en mobiele apparaten. In het tweede voorbeeld worden alleen statistieken weergegeven over het openen op mobiele apparaten.

Het aantal openingen komt overeen met het totale aantal geopende berichten. E-mails met tekstopmaak worden niet geteld. Voor meer informatie bij het Volgen opent, verwijs naar [ deze sectie ](metrics-calculation.md#tracking-opens-).

![](assets/user-agent-report.png)

>[!NOTE]
>
>De namen van de browser en het besturingssysteem maken deel uit van de informatie die door de gebruikersagent van de browser is verzonden en waarnaar het bericht is geopend. Adobe Campaign brengt het type apparaat af op basis van de apparaatgegevens.
