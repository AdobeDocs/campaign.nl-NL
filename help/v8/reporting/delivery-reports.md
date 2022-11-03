---
title: Geïntegreerde Adobe Campaign-leveringsrapporten
description: Geïntegreerde Adobe Campaign-leveringsrapporten
feature: Reporting
source-git-commit: 60db4c2e8cd280845ddd0176bd10dc1b7edbb767
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 1%

---


# Leveringsrapporten {#delivery-reports}

U kunt de uitvoering van leveringen bijhouden via verschillende rapporten die toegankelijk zijn vanuit het leveringsoverzicht.

Volg onderstaande stappen om rapporten te openen:

1. Bladeren naar de **[!UICONTROL Campaigns]** en klik op de knop **[!UICONTROL Delivery]** koppeling om de lijst met leveringen weer te geven.
1. Klik op de naam van de levering voor de rapporten die u wilt openen.
1. Selecteer **[!UICONTROL Summary]** en klik op de knop **[!UICONTROL Reports]** link naar de specifieke rapporten over de levering.

   ![](assets/detailed-report-2.png)

   Standaard zijn de volgende rapporten beschikbaar:

   * **[!UICONTROL Delivery throughput]**
   * **[!UICONTROL Sharing to social networks]**
   * **[!UICONTROL Statistics on sharing activities]**
   * **[!UICONTROL Hot clicks]**
   * **[!UICONTROL Tracking statistics]**
   * **[!UICONTROL URLs and click streams]**
   * **[!UICONTROL Tracking indicators]**
   * **[!UICONTROL Non-deliverables and bounces]**
   * **[!UICONTROL User activities]**
   * **[!UICONTROL Delivery summary]**
   * **[!UICONTROL Subscription tracking]**
   * **[!UICONTROL Delivery statistics]**
   * **[!UICONTROL Breakdown of opens]**

## Trackingsindicatoren {#tracking-indicators}

Dit rapport combineert de belangrijkste indicatoren voor het volgen van het gedrag van ontvangers bij het ontvangen van de levering. Het geeft toegang tot levering en ontvangststatistieken, open en klikthrough tarieven, geproduceerde klikstromen, Web het volgen en het delen van activiteiten aan sociale netwerken.

>[!NOTE]
>
>Waarden die worden berekend op basis van berichten die worden geopend, zijn altijd schattingen, vanwege de foutmarge die is gekoppeld aan e-mails in tekstindeling. De **[!UICONTROL Distinct opens/Sum of opens for the population reached]** deze foutenmarge wordt in aanmerking genomen. [Meer informatie](metrics-calculation.md#tracking-opens-).

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]** : Totaal aantal berichten dat na leveringsanalyse moet worden bezorgd.
* **[!UICONTROL Success]** : Aantal berichten verwerkt.

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>De bijbehorende percentages worden berekend op basis van het aantal berichten dat met succes is doorgestuurd.

* **[!UICONTROL Distinct opens for the population reached]** : Schatting van het aantal ontvangers voor wie het bericht bestemd is dat een bericht ten minste eenmaal heeft geopend. Er wordt rekening gehouden met klikken op bijgehouden URL&#39;s omdat e-mails moeten worden geopend om op een koppeling te klikken.
* **[!UICONTROL Sum of opens for the population reached]** : Schatting van het totale aantal openingen door de beoogde ontvangers.
* **[!UICONTROL Clicks on opt-out link]** : Aantal klikken op de verbinding van het unsubscription.
* **[!UICONTROL Clicks on the mirror page link]** : Aantal klikken op de verbinding aan de spiegelpagina. Om in aanmerking te worden genomen, moet de verbinding als dusdanig in de leveringstovenaar (bijgehouden URLs) worden bepaald. <!--Refer to this [page](../../delivery/using/about-delivery-monitoring.md).-->
* **[!UICONTROL Estimation of forwards]** : Schatting van het aantal e-mails dat door de beoogde ontvangers is doorgestuurd. Deze waarde wordt berekend door het aantal verschillende personen en het aantal verschillende ontvangers af te trekken die in de e-mail hebben geklikt.

   >[!NOTE]
   >
   >Voor meer informatie over het verschil tussen verschillende personen en beoogde ontvangers raadpleegt u [Gerichte personen/ontvangers](metrics-calculation.md#targeted-persons---recipients).

**[!UICONTROL 3. Open and click-through rate]**

Deze waardetabel toont de uitsplitsing van leveringen, opent, klikt en ruwe reactiviteit per domein van Internet. De volgende indicatoren worden gebruikt:

* **[!UICONTROL Sent]** : Het totale aantal berichten dat op dit domein wordt verzonden.
* **[!UICONTROL Complaints]** : Aantal berichten voor dit domein die als ongewenst door de ontvanger zijn gemeld. Het tarief wordt berekend gebaseerd op het totale aantal berichten die op dit domein worden verzonden.
* **[!UICONTROL Opens]** : Aantal verschillende beoogde ontvangers voor dit domein die een bericht minstens eenmaal hebben geopend. Het tarief wordt berekend gebaseerd op het totale aantal berichten die op dit domein worden verzonden.
* **[!UICONTROL Clicks]** : Aantal afzonderlijke beoogde ontvangers die minstens één keer op dezelfde levering hebben geklikt. Het tarief wordt berekend gebaseerd op het totale aantal berichten die op dit domein worden verzonden
* **[!UICONTROL Raw reactivity]** : Percentage van het aantal ontvangers dat ten minste één keer op een levering heeft geklikt in vergelijking met het aantal ontvangers dat een levering ten minste één keer heeft geopend.

>[!NOTE]
>
>De domeinnamen die in dit rapport worden weergegeven, worden gedefinieerd in de gespecificeerde lijst die op kubusniveau wordt gebruikt. Als u standaarddomeinen wilt wijzigen, toevoegen of verwijderen, bewerkt u de **[!UICONTROL Domains]** gespecificeerde lijst en wijzigt waarden en aliassen. De **[!UICONTROL Others]** de categorie omvat domeinnamen die niet tot om het even welke waarde van de gespecificeerde lijst behoren.
>
>Leer hoe te om tot uw opsommingen toegang te hebben en te vormen in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/managing-enumerations.html){target=&quot;_blank&quot;}.


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>De bijbehorende percentages worden berekend op basis van het aantal berichten dat met succes is doorgestuurd.

* **[!UICONTROL Distinct clicks for the population reached]** : Aantal verschillende personen dat ten minste één keer in een levering heeft geklikt.
* **[!UICONTROL Cumulated clicks]** : Het totale aantal klikken door beoogde ontvangers, exclusief koppelingen zonder abonnement en spiegel.
* **[!UICONTROL Recipient clicks]** : Aantal afzonderlijke beoogde ontvangers die minstens één keer op dezelfde levering hebben geklikt.
* **[!UICONTROL Estimated recipient reactivity]** : Verhouding van het aantal ontvangers dat ten minste eenmaal in een levering heeft geklikt ten opzichte van het geschatte aantal ontvangers dat een levering ten minste eenmaal heeft geopend. Er wordt geen rekening gehouden met de klikken op de pagina-link Weigeren en de koppeling spiegelen.
<!--
**[!UICONTROL 5. Web tracking]**

* **[!UICONTROL Visited pages]** : Number of web pages visited following message reception.
* **[!UICONTROL Transactions]** : Number of purchases following message reception.
* **[!UICONTROL Total amount]** : Total amount of purchases following message reception. 
* **[!UICONTROL Average transaction amount]** : Average purchase made by distinct delivery recipients. 
* **[!UICONTROL Articles]** : Number of articles purchased by the delivery recipients. 
* **[!UICONTROL Average count of articles per transaction]** : Average number of items per purchase made by distinct recipients.
* **[!UICONTROL Average amount per message]** : Average amount of purchases generated per message.

  >[!NOTE]
  >
  >In order for a visited page, transaction, amount or article to be taken into account, a webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).

**[!UICONTROL 6. Sharing activities to email and social networks]**

This section shows the number of messages shared on each social network. For more on this, refer to [Sharing to social networks](../../reporting/using/global-reports.md#sharing-to-social-networks).

## URLs and click streams {#urls-and-click-streams}

This report shows the list of pages visited following a delivery. 

![](assets/s_ncs_user_url_report.png)

You can configure the contents of this report by selecting: the score chart to be displayed, the time filter (since the action launch, over the first 6 hours following launch, etc.) and the data display mode (by label, by URL, by category. Click **[!UICONTROL Refresh]** to confirm your selection.

The following rates are displayed in the upper section of the report:

* **[!UICONTROL Reactivity]** : Ratio of the number of targeted recipients having clicked in a delivery, in relation to the estimated number of targeted recipients having opened a delivery. Clicks on the opt-out link and on the mirror page are not taken into account.

  >[!NOTE]
  >
  >For more information on tracking opens, refer to [this section](metrics-calculation.md#tracking-opens-).

* **[!UICONTROL Distinct clicks]** : Number of distinct people having clicked at least once (excluding unsubscription link and mirror page) in a delivery. The rate displayed is calculated based on the number of messages delivered successfully. 
* **[!UICONTROL Cumulated clicks]** : Total number of clicks by targeted recipients (excluding unsubscription link and mirror page). The rate displayed is calculated based on the number of messages forwarded successfully.

**[!UICONTROL Platform average]** : This average rate, displayed under each rate (reactivity, distinct clicks, and cumulated clicks), is calculated for deliveries sent over the previous six months. Only deliveries with the same typology and on the same channel are taken into account. Proofs are excluded.

The central table provides the following information:

* **[!UICONTROL Clicks]** : Number of cumulated clicks, per link. 
* **[!UICONTROL Clicks (in %)]** : Breakdown of the number of clicks per link, in relation to the total number of cumulated clicks.

**[!UICONTROL Breakdown of clicks in time]**

This chart shows the breakdown of cumulated clicks per day.
-->

## Leveringsoverzicht {#delivery-summary}

Dit rapport bevat alle belangrijke informatie over de levering.

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

Deze sectie heeft twee indicatoren:

* **[!UICONTROL Initial population]** : Het totale aantal ontvangers waarop de levering betrekking heeft.
* **[!UICONTROL Messages rejected by the rule]** : Aantal adressen genegeerd tijdens de analyse wanneer het toepassen van typologieregels: het adres ontbreekt, quarantined, op lijst van gewezen personen, enz. <!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

Het middelste diagram toont de uitsplitsing per regel van berichten die tijdens de analyse worden verworpen.

**[!UICONTROL Delivery statistics]**

Dit deel omvat de volgende indicatoren:

* **[!UICONTROL Messages to be delivered]** : Totaal aantal berichten dat na leveringsanalyse moet worden bezorgd.
* **[!UICONTROL Success]** : Aantal berichten dat is verwerkt. Het bijbehorende tarief is de verhouding met het aantal te leveren berichten.
* **[!UICONTROL Errors]** : Totaal aantal fouten gecumuleerd tijdens leveringen en automatische terugkerende verwerking. Het bijbehorende tarief is de verhouding met het aantal te leveren berichten.
* **[!UICONTROL New quarantines]** : Aantal adressen in quarantaine na een mislukte levering (onbekende gebruiker, ongeldig domein). Het bijbehorende tarief is de verhouding met het aantal te leveren berichten.

## Hot clicks {#hot-clicks}

Dit rapport toont de berichtinhoud (HTML en/of tekst) met, op elke verbinding, het percentage klikt op verbindingen. De belemmeringen van de verpersoonlijking unsubscription verbindingen, spiegelpaginakoppelingen en aanbiedingsverbindingen worden in de totale gecumuleerde kliks in aanmerking genomen maar niet getoond in het rapport.

>[!NOTE]
>
>Als uw levering voorstellen (Interactie) bevat, verschijnt een doos in het deel boven het rapport tonend het percentage van kliks op de aanbiedingen.


## Trackingstatistieken {#tracking-statistics}

Dit rapport bevat statistieken over openen, klikken en transacties.

Hiermee kunt u de marketingeffecten van de levering volgen. U kunt configureren hoe waarden worden weergegeven door de tijdschaal te wijzigen (1 uur, 3 uur of 24 uur, enz.). Klik op **[!UICONTROL Refresh]** om uw selectie te bevestigen.

Dit rapport bevat een tabel met waarden en een Pareto-grafiek met de tijd die nodig is voor de levering om de maximale efficiëntie te bereiken. De volgende indicatoren worden gebruikt:

* **[!UICONTROL Opens]** : Schatting van de tijd die nodig is om een percentage van het totale aantal geopende berichten te bereiken. E-mails in tekstindeling worden niet in aanmerking genomen. [Meer informatie](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]** : Schatting van de tijd die nodig is om een percentage van het totale aantal geregistreerde klikken te bereiken. Klikken op de opt-out-koppeling en de spiegelpagina worden niet in aanmerking genomen.
<!--
* **[!UICONTROL Transactions]** : Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->


## Cumulatieve rapporten {#cumulated-reports}

U kunt gecumuleerde rapporten weergeven bij leveringen. Selecteer hiertoe de te vergelijken leveringen om de lijst met rapporten voor deze leveringen te verkrijgen.

Als u niet-aangrenzende leveringen in de lijst wilt selecteren, houdt u de CTRL-toets ingedrukt terwijl u een selectie maakt.

Als u leveringen wilt selecteren die in een andere map zijn opgeslagen, klikt u op de knop **[!UICONTROL Display sub-levels]** toegankelijk in de werkbalk. Deze worden vervolgens in dezelfde lijst weergegeven.


