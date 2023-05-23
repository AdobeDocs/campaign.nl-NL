---
title: Globale Adobe Campaign-rapporten
description: Leer hoe u algemene rapporten kunt openen en gebruiken
feature: Reporting, Monitoring
exl-id: 6e3409d8-86bd-44ba-a40d-10287f53a960
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '1763'
ht-degree: 3%

---

# Algemene rapporten {#global-reports}

Deze rapporten hebben betrekking op de activiteit van de gegevens in de gehele database. Ga naar het **[!UICONTROL Reports]** tab.

![](assets/reports-tab.png)

Klik op de naam van de rapporten om deze weer te geven. De volgende rapporten zijn standaard beschikbaar:

![](assets/report-global-list.png)

>[!NOTE]
>
>In deze sectie worden alleen de rapporten weergegeven die betrekking hebben op leveringen.

* **[!UICONTROL Delivery throughput]** : verwijzen naar [Leveringsdoorvoer](#delivery-throughput).
* **[!UICONTROL Browsers]** : verwijzen naar [Browsers](#browsers).
* **[!UICONTROL Sharing to social networks]** : verwijzen naar [Delen naar sociale netwerken](#sharing-to-social-networks).
* **[!UICONTROL Statistics on sharing activities]** : verwijzen naar [Statistieken over de activiteiten voor het delen van diensten](#statistics-on-sharing-activities).
* **[!UICONTROL Operating systems]** : verwijzen naar [Besturingssystemen](#operating-systems).
* **[!UICONTROL URLs and click streams]** : verwijzen naar [URL&#39;s en klik op streams](delivery-reports.md#urls-and-click-streams).
* **[!UICONTROL Tracking indicators]** : verwijzen naar [Traceringsindicatoren](delivery-reports.md#tracking-indicators).
* **[!UICONTROL Non-deliverables and bounces]** : verwijzen naar [Niet-te leveren producten en bedragen](#non-deliverables-and-bounces).
* **[!UICONTROL User activities]** : verwijzen naar [Gebruikersactiviteiten](#user-activities).
* **[!UICONTROL Subscription tracking]** : verwijzen naar [Abonnement bijhouden](#subscription-tracking).
* **[!UICONTROL Delivery summary]** : verwijzen naar [Overzicht van levering](delivery-reports.md#delivery-summary).
* **[!UICONTROL Delivery statistics]** : verwijzen naar [Leveringsstatistieken](#delivery-statistics).
* **[!UICONTROL Breakdown of opens]** : verwijzen naar [Indeling van openen](#breakdown-of-opens).

## Leveringsdoorvoer {#delivery-throughput}

Dit verslag bevat informatie over de leveringsproductie van het gehele platform voor een bepaalde periode. Om de snelheid te meten waarbij de berichten worden geleverd, zijn de criteria het aantal berichten die per uur worden verzonden en de grootte van de berichten (in beetjes per seconde). In het onderstaande voorbeeld ziet u in de eerste grafiek de geslaagde leveringen in blauw en het aantal onjuiste leveringen in oranje.

![](assets/report-toolbar.png)

U kunt de weergegeven waarden configureren door de tijdschaal te wijzigen: Weergave van 1 uur, weergave van 3 uur, weergave van 24 uur, enz. Klik op **[!UICONTROL Refresh]** om uw selectie te bevestigen.

>[!NOTE]
>
>U kunt ook het aantal verzonden leveringen per uur controleren met de opdracht [Deelvenster Beheer](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/sftp-storage-management.html).
>
>Het configuratiescherm is toegankelijk voor alle gebruikers met beheerdersrechten. De stappen om toegang met beheerdersrechten aan een gebruiker te verlenen worden gedetailleerd beschreven op [deze pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=nl#discover-control-panel).

## Gebruikersactiviteiten {#user-activities}

Dit rapport toont de uitsplitsing van opent, klikt en transacties per half uur, uur of dag, in de vorm van een grafiek.

De volgende opties zijn beschikbaar:

* **[!UICONTROL Opens]** : Het totale aantal geopende berichten. E-mails in tekstindeling worden niet in aanmerking genomen. [Meer informatie](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]** : Het totale aantal klikken op koppelingen in leveringen. Er wordt geen rekening gehouden met klikken op abonnementkoppelingen en spiegelpagina&#39;s.
<!--
* **[!UICONTROL Transactions]** : Total number of transactions after a message is received. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->

## Niet-leverbare items en niet-bezorgingen {#non-deliverables-and-bounces}

Dit verslag geeft een overzicht van de niet-te leveren posten en een uitsplitsing van de bedragen per internetdomein.

De **[!UICONTROL Number of messages processed]** vertegenwoordigt het totale aantal berichten die door de leveringsserver worden verwerkt. Deze waarde is lager dan het aantal berichten dat moet worden afgeleverd wanneer bepaalde leveringen zijn gestopt of gepauzeerd (voordat deze door de server worden verwerkt).

**[!UICONTROL Breakdown of errors by type]**

>[!NOTE]
>
>De fouten die in dit rapport worden weergegeven, activeren het quarantaineproces. Voor meer informatie over quarantainebeheer raadpleegt u [Quarantainebeheer](../send/quarantines.md).

In het eerste deel van dit verslag wordt de uitsplitsing van niet-te leveren producten in de vorm van een tabel van waarden en een grafiek weergegeven.

Voor elk fouttype hebben we:

* het aantal foutberichten van dit type;
* het percentage berichten met dergelijke fouten in vergelijking met het totale aantal berichten met fouten;
* het percentage van foutenmeldingen van dit type vergeleken met het totale aantal verwerkte berichten.

De volgende indicatoren worden gebruikt:

* **[!UICONTROL User unknown]** : Fouttype dat tijdens de levering wordt gegenereerd om aan te geven dat het e-mailadres ongeldig is.
* **[!UICONTROL Invalid domain]** : Fouttype dat wordt gegenereerd bij het verzenden van een levering om aan te geven dat het domein van het e-mailadres onjuist is of niet bestaat.
* **[!UICONTROL Inbox full]** : Het type van fout na vijf leveringspogingen wordt geproduceerd om erop te wijzen dat de ontvangers inbox teveel berichten bevat.
* **[!UICONTROL Account disabled]** : Fouttype dat wordt gegenereerd bij het verzenden van een levering om aan te geven dat het adres niet langer bestaat.
* **[!UICONTROL Rejected]** : Het type van fout produceerde wanneer een adres door IAP (Internet Access Provider) wordt verworpen, bijvoorbeeld na de toepassing van een veiligheidsregel (anti-spamsoftware).
* **[!UICONTROL Unreachable]** : Fouttype dat optreedt in de tekenreeks voor berichtdistributie: incident op het SMTP relais, tijdelijk onbereikbaar domein, enz.
* **[!UICONTROL Not connected]** : Fouttype om aan te geven dat de mobiele telefoon van de ontvanger op het moment van verzending wordt uitgeschakeld of losgekoppeld van het netwerk.

   >[!NOTE]
   >
   >Deze indicator heeft betrekking op leveringen op [mobiele kanalen](../send/send.md) alleen.

   U kunt elke regel van de waardetabel openen door op de knop `[+]` symbool. Voor elk fouttype kunt u de indeling van foutberichten per domein weergeven.

**[!UICONTROL Breakdown of errors per domain]**

In het tweede gedeelte van dit rapport wordt de uitsplitsing van fouten per internetdomein getoond in de vorm van een tabel met waarden en een grafiek.

Voor elke domeinnaam hebben we:

* het aantal berichten met fouten voor dit domein,
* het percentage berichten met fouten voor dit domein in vergelijking met het totale aantal berichten dat voor dit domein wordt verwerkt;
* het percentage foutberichten voor dit domein in vergelijking met het totale aantal foutberichten.

U kunt elke regel van de waardetabel openen door op de knop [+] symbool. Voor elk domeintype kunt u de indeling van foutberichten per fouttype weergeven.

![](assets/errors-report-details.png)

>[!NOTE]
>
>De domeinnamen die in dit rapport worden weergegeven, worden op kubusniveau gedefinieerd. Als u deze waarden wilt wijzigen, bewerkt u de **[!UICONTROL Delivery logs (broadlogrcp)]** kubus. Raadpleeg [deze sectie](gs-cubes.md) voor meer informatie. De **[!UICONTROL Others]** de categorie omvat domeinnamen die niet tot een specifieke klasse behoren.

## Browsers {#browsers}

Dit verslag geeft een overzicht van de internetbrowsers die door de ontvangers van de levering voor de betrokken periode zijn gebruikt.

>[!NOTE]
>
>De waarden in dit rapport zijn schattingen: alleen ontvangers die op een levering hebben geklikt , worden in aanmerking genomen .

**Algemene statistieken**

De algemene statistieken over browsergebruik worden gepresenteerd in de vorm van een tabel met waarden en een grafiek.

![](assets/browser-report.png)

De volgende indicatoren worden gebruikt:

* **[!UICONTROL Visitors]** : Het totale aantal beoogde ontvangers (per internetbrowser) dat minstens één keer op een levering heeft geklikt.
* **[!UICONTROL Pages viewed]** : Het totale aantal klikken op koppelingen in een levering (per internetbrowser) voor alle leveringen.
* **[!UICONTROL Usage rate]** : Dit percentage is de uitsplitsing van bezoekers (per internetbrowser) in verhouding tot het totale aantal bezoekers.

**Statistieken per browser**

In de lijst van globale statistische waarden, kunt u elke browser naam klikken om hun gebruiksstatistieken te bekijken.

![](assets/browser-report-info.png)

Statistieken worden gepresenteerd in de vorm van een curve, een grafiek en een tabel met waarden.

De **[!UICONTROL History]** De curve geeft de aanwezigheidsgraad van deze browser per dag aan. De frequentie is de verhouding tussen het aantal bezoekers per dag (in deze browser) en het aantal bezoekers dat wordt gemeten op de dag met de hoogste aanwezigheidsgraad.

De **[!UICONTROL Breakdown per version]** De grafiek geeft de uitsplitsing van bezoekers per versie weer ten opzichte van het totale aantal bezoekers (in deze browser).

In de waardetabel worden de volgende indicatoren gebruikt:

* **[!UICONTROL Global rate]** : Dit percentage geeft de uitsplitsing van bezoekers per versie weer ten opzichte van het totale aantal bezoekers (in alle browsers).
* **[!UICONTROL Relative rate]** : Dit percentage geeft de uitsplitsing van bezoekers per versie weer in vergelijking met het totale aantal bezoekers (in deze browser).


<!--
### Sharing to social networks {#sharing-to-social-networks}

Viral marketing lets delivery recipients share information with their contact network: they can add a link to their profile (Facebook, Twitter, etc.) or send a message to a friend. Each share and each access to shared information is tracked within the delivery. For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

This report shows the breakdown of shared and opened messages per social network (Facebook, Twitter, etc.) and/or per email.

![](assets/s_ncs_user_social_report.png)

**[!UICONTROL Email delivery statistics]**

In the email delivery statistics, two values are displayed:

* **[!UICONTROL Number of messages to be delivered]** : Total number of messages processed during delivery analysis.
* **[!UICONTROL Number of successful deliveries]** : Number of messages processed successfully.

**[!UICONTROL Sharing activities and mail open statistics]**

The central table shows the statistics on email shares and opens.

In the **[!UICONTROL Shares]** column, we have the following indicators:

* **[!UICONTROL No. of sharing activities]** : Total number of messages shared on each social network. This value equals the total number of clicks on the icon of the matching **[!UICONTROL Links for sharing to social networks]** personalization block.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of shares per social network, in relation to the total number of shares.
* **[!UICONTROL Sharing rate]** : This rate represents the breakdown of shares per social network, in relation to the number of messages to be delivered.

In the **[!UICONTROL Opens]** column, we have the following indicators:

* **[!UICONTROL No. of opens]** : Total number of messages opened by people whom the message was forwarded to (via the **[!UICONTROL Links for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of opens per social network, in relation to the total number of opens.
* **[!UICONTROL Rate of opens]** : This rate represents the breakdown of opens per social network, in relation to the total number of shares.

**[!UICONTROL Breakdown of sharing activities and opens]**

This section includes two charts which represent the breakdown of sharing activities and opens per social network.


## Statistics on sharing activities {#statistics-on-sharing-activities}

This report shows the evolution of shares to social media in time.

For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

Statistics are presented in the form of a table of values and a chart.

The following indicators are used:

* **[!UICONTROL New contacts]** : Number of new subscriptions following the reception of a message shared via email. This value matches the number of people who received a message shared via email, clicked the **[!UICONTROL Subscription link]** and filled in the subscription form. 
* **[!UICONTROL Opens]** : Total number of messages opened by people whom the message was transferred to (via the **[!UICONTROL Link for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Sharing activities]** : Total number of messages shared via social networks. This value matches the total number of clicks on the icon of the **[!UICONTROL Links for sharing to social networks]** personalization block.
-->

## Besturingssystemen {#operating-systems}

Dit verslag geeft een overzicht van de exploitatiesystemen die door de ontvangers van de levering voor de betrokken periode worden gebruikt.

>[!NOTE]
>
>De waarden in dit rapport zijn schattingen: alleen ontvangers die op een levering hebben geklikt , worden in aanmerking genomen .

**Algemene statistieken**

De algemene gebruiksstatistieken van besturingssystemen worden gepresenteerd in de vorm van een tabel met waarden en een grafiek.

![](assets/os-report.png)

De volgende indicatoren worden gebruikt:

* **[!UICONTROL Visitors]** : Daggemiddelde van het totale aantal beoogde ontvangers (per besturingssysteem) die ten minste één keer op een levering hebben geklikt.
* **[!UICONTROL Pages viewed]** : Het dagelijkse gemiddelde van het totale aantal klikken op leveringsverbindingen (per werkend systeem) voor alle leveringen.
* **[!UICONTROL Rate of use]** : Dit percentage is de uitsplitsing van bezoekers (per besturingssysteem) in verhouding tot het totale aantal bezoekers.

**Statistieken per besturingssysteem**

In de lijst van globale statistiekwaarden, klik de naam van elk werkend systeem om de statistieken per werkend systeem te bekijken.

![](assets/os-report-details.png)

Statistieken worden gepresenteerd in de vorm van een curve, een grafiek en een tabel met waarden.

De **[!UICONTROL History]** De curve geeft de gebruiksfrequentie van dit besturingssysteem per dag aan. Dit percentage is de verhouding tussen het aantal bezoekers per dag (op dit besturingssysteem) en het aantal bezoekers dat wordt gemeten op de dag met de hoogste aanwezigheid.

De **[!UICONTROL Breakdown by version]** De grafiek geeft de uitsplitsing van bezoekers per versie weer in verhouding tot het totale aantal bezoekers op dit besturingssysteem.

In de waardetabel worden de volgende indicatoren gebruikt:

* **[!UICONTROL Global rate]** : Dit percentage geeft de uitsplitsing van bezoekers (per versie) weer in verhouding tot het totale aantal bezoekers in de besturingssystemen.
* **[!UICONTROL Relative rate]** : Dit percentage geeft de uitsplitsing van bezoekers (per versie) weer in verhouding tot het totale aantal bezoekers voor dit besturingssysteem.

## Abonnement bijhouden {#subscription-tracking}

Met dit rapport kunt u abonnementen op informatieservices controleren. Er worden abonnementen en afkortingen weergegeven.

![](assets/service-report.png)

Het kan voor een abonnement worden getoond door te klikken **[!UICONTROL Profiles and targets > Services and subscriptions]** knooppunt van de startpagina of de verkenner. Selecteer het gewenste abonnement en klik op de knop **[!UICONTROL Reports]** tab. De **[!UICONTROL Subscriptions tracking]** rapport is standaard beschikbaar. Het laat u de abonnement en unsubscription tendensen en het loyaliteitstarief over een periode zien. U kunt de representatie van deze gegevens configureren via de vervolgkeuzelijst. Klikken **[!UICONTROL Refresh]** om de geselecteerde configuratie te bevestigen.

Zie voor meer informatie [deze pagina](../start/subscriptions.md).

De **[!UICONTROL Number subscribed to date]** geeft het totale aantal personen aan waarop momenteel is geabonneerd.

**[!UICONTROL Overall evolution of subscriptions]**

In de waardetabel worden de volgende indicatoren gebruikt:

* **[!UICONTROL Subscribers]** : Totaal aantal abonnees voor de betrokken periode.
* **[!UICONTROL Subscriptions]** : Aantal abonnementen voor de betrokken periode.
* **[!UICONTROL Unsubscriptions]** : Aantal aflossingen voor de betrokken periode.
* **[!UICONTROL Evolution]** : Aantal aflossingen min het aantal abonnementen. Het tarief wordt berekend op basis van het totale aantal abonnees.
* **[!UICONTROL Loyalty]** : Loyalty van abonnees voor de betrokken periode.

**[!UICONTROL Subscription evolution curves]**

In deze grafiek wordt de ontwikkeling van de abonnementen en afboekingen voor de betrokken periode weergegeven.

## Leveringsstatistieken {#delivery-statistics}

Dit rapport toont de uitsplitsing naar internetdomein van alle verwerkte en verzonden berichten, van harde en zachte geluiden, opent, klikt en afmeldt.

![](assets/broadcast-report.png)

De volgende indicatoren worden gebruikt:

* **[!UICONTROL Emails processed]** : Het totale aantal berichten dat door de leveringsserver wordt verwerkt.
* **[!UICONTROL Delivered]** : percentage van het aantal met succes verwerkte berichten in verhouding tot het totale aantal verwerkte berichten.
* **[!UICONTROL Hard bounces]** : percentage van het aantal &quot;harde&quot; grenzen in vergelijking met het totale aantal verwerkte berichten.
* **[!UICONTROL Soft bounces]** : percentage van het aantal &quot;zachte&quot; grenzen in vergelijking met het totale aantal verwerkte berichten.

   >[!NOTE]
   >
   >Raadpleeg voor meer informatie over harde en zachte golven [deze pagina](../send/quarantines.md).

* **[!UICONTROL Opens]** : percentage van het aantal beoogde ontvangers die een bericht ten minste eenmaal hebben geopend in vergelijking met het aantal berichten dat met succes is verwerkt.
* **[!UICONTROL Clicks]** : percentage van het aantal mensen die in een levering ten minste eenmaal klikte in vergelijking met het aantal berichten dat met succes is verwerkt.
* **[!UICONTROL Unsubscription]** : percentage van het aantal klikken op een koppeling voor het opzeggen van een abonnement in verhouding tot het aantal berichten dat met succes is verwerkt.

## Indeling van openen {#breakdown-of-opens}

In dit rapport wordt de uitsplitsing van de openingen per besturingssysteem, apparaat en browser voor de betrokken periode weergegeven. Voor elke categorie worden twee grafieken gebruikt. De eerste toont statistieken betreffende opent op een computer en mobiele apparaten. In het tweede voorbeeld worden alleen statistieken weergegeven over het openen op mobiele apparaten.

Het aantal openingen komt overeen met het totale aantal geopende berichten. E-mails met tekstopmaak worden niet geteld. Voor meer informatie over het Volgen opent, verwijs naar [deze sectie](metrics-calculation.md#tracking-opens-).

![](assets/user-agent-report.png)

>[!NOTE]
>
>De namen van de browser en het besturingssysteem maken deel uit van de informatie die door de gebruikersagent van de browser is verzonden en waarnaar het bericht is geopend. Adobe Campaign brengt het type apparaat af op basis van de apparaatgegevens.
