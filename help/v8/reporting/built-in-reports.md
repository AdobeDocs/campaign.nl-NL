---
title: Geïntegreerde Adobe Campaign-rapporten
description: Ingebouwde rapporten
feature: Reporting
role: User
level: Beginner
exl-id: b63e6905-3bd4-4de4-9e7e-7638e5fc1192
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 1%

---

# Geïntegreerde Adobe Campaign-rapporten {#ootb-reports}

Deze pagina bevat een lijst met ingebouwde Adobe Campaign-rapporten, hun inhoud en hun context. Adobe Campaign biedt een reeks ingebouwde rapporten die toegankelijk zijn met de clientconsole of een internetbrowser.

De volgende typen rapporten zijn beschikbaar:

* Rapporten over het hele platform. [Meer informatie](global-reports.md).
* Leveringsrapporten. [Meer informatie](delivery-reports.md).

U kunt tot ingebouwde rapporten van de homepage van de Campagne, het specifieke rapportdashboard of de leveringslijst toegang hebben. De manier het rapport in UI toont hangt van zijn context af.

Een lijst van zeer belangrijke rapporten is beschikbaar op de homepage en laat u tot leveringsgegevens snel toegang hebben. U kunt deze lijst naar wens wijzigen. U kunt ook leren hoe u uw eigen rapporten kunt toevoegen aan de **[!UICONTROL Reports]** tab.

Raadpleeg voor meer informatie over deze aangepaste configuraties [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/configuring-access-to-the-report.html?lang=nl-NL){target="_blank"}.


## Ingebouwde rapporten openen {#access-ootb-reports}

Voor toegang tot geïntegreerde campagnerapporten:

1. Selecteer de **[!UICONTROL Reports]** van de Adobe Campaign-interface.

   ![](assets/reporting-access-from-home.png)

1. Gebruik de onderzoeksgebieden om de getoonde rapporten te filtreren.

1. Klik vervolgens op het rapport dat u wilt weergeven.

   ![](assets/edit-a-report.png)

1. Klik op de knop **[!UICONTROL Back]** de verbinding bij de bovenkant van het scherm neemt u terug naar de lijst van rapporten.

   ![](assets/back-button.png)

Rapporten die specifiek zijn voor een campagne of levering zijn toegankelijk via hun respectieve dashboards.

![](assets/reporting-on-delivery.png)

Dit beginsel geldt ook voor lijsten, diensten, aanbiedingen, enz. zoals hieronder weergegeven:

![](assets/reporting-on-offer.png)


## Verslagen over leveringen {#reports-on-deliveries}

De ingebouwde rapporten van Adobe Campaign zijn te vinden in de onderstaande tabel.

Raadpleeg voor meer informatie over de inhoud van deze rapporten [deze sectie](delivery-reports.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label en interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Gebruikersactiviteiten (receivingActivity)<br /> </td> 
   <td> Uitsplitsing van open transacties, klikken en transacties naar tijdsperiode.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Leveringsdoorvoer (doorvoer)<br /> </td> 
   <td> Levering de grafieken van de productie, in berichten/uur en Mbits/s.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Fouten en stuitingen (fouten)<br /> </td> 
   <td> Bounces en niet-te leveren items per oorzaak en domein.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Trackingindicatoren (feedback voor levering)<br /> </td> 
   <td> Overzicht van belangrijke indicatoren voor het volgen van ontvankelijk gedrag.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Trackingindicatoren (mobileAppDeliveryFeedback)<br /> </td> 
   <td> Indicatoren voor het bijhouden van een levering aan een mobiele toepassing.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Browsers (browserStatistics)<br /> </td> 
   <td> Statistieken over browsers die door ontvangers worden gebruikt die in berichten klikten.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> Delen naar sociale netwerken (deliveryForward)<br /> </td> 
   <td> Het delen van activiteit en post open statistieken.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Hete kliks (hotels)<br /> </td> 
   <td> Toont het bericht en de kliktarieven bovenop.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Hypotheseverslag (deliveryHypothesis)<br /> </td> 
   <td> Toont de samenvatting van maatregelen op leveringshypothesen.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Leveringsstatistieken (statisticsPerDelivery)<br /> </td> 
   <td> Statistieken (verwerkte berichten, geleverde berichten, harde stuitingen, zachte stuitingen, kliks, unsubscriptions) per e-maildomein.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Statistieken betreffende de deelactiviteiten (forwardActivity)<br /> </td> 
   <td> Analyse van het delen van activiteiten, het openen en de abonnementen per tijdsperiode.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking statistics (trackingStatistics)<br /> </td> 
   <td> Open, klik en het rapport van de transactietarieven.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Afleveringsoverzicht (leveringVerzenden)<br /> </td> 
   <td> Samenvatting van leveringsindicatoren: doel, uitsluiting en verzonden berichten.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Overzicht van levering (deliveryStatistics)<br /> </td> 
   <td> Overzichtstabel voor geselecteerde leveringen: doelen, uitsluitingen en berichten verzonden.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> Besturingssystemen (osStatistics)<br /> </td> 
   <td> Statistieken over de werkende systemen die door ontvangers worden gebruikt die in een bericht klikte.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> Reactiviteitspercentage (deliveryFeedbackSocial)<br /> </td> 
   <td> Uitsplitsing naar leverreactiviteit en reactie.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
  <tr> 
   <td> URL's en klik op doorvoer (topUrlDelivery)<br /> </td> 
   <td> De meeste reactieve URLs en bijbehorende klikstromen.<br /> </td> 
   <td> nms:levering<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Verslagen over campagnes {#reports-on-campaigns}

De verslagen over campagnes hebben betrekking op de gegevens in het **nms:bewerking** tabel.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label en interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Gebruikersactiviteiten (operationRecipientActivity)<br /> </td> 
   <td> De uitsplitsing van opent, klikt en transacties naar tijdsperiode, hangt van Campagne af.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leveringsdoorvoer (operationThroughput)<br /> </td> 
   <td> De grafieken van de leveringproductie, in post/uur en Mbits/s, hangt van Campagne af.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campagnekosten (budgetOperationExpenses)<br /> </td> 
   <td> Hiermee geeft u de items van de campagneregel in detail weer, afhankelijk van Campagne.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fouten en fouten (operationErrors)<br /> </td> 
   <td> Bounces en niet-te leveren items per oorzaak en domein, zijn afhankelijk van campagne.<br /> </td> 
  </tr> 
  <tr> 
   <td> Kosten verkennen (budgetExplorerOperation)<br /> </td> 
   <td> Een beschrijvende analyse van de kostenposten is afhankelijk van MRM.<br /> </td> 
  </tr> 
  <tr> 
   <td> Trackingindicatoren (operationFeedback)<br /> </td> 
   <td> Overzicht van belangrijke volgindicatoren: Opens, Kliks en Transacties, hangt van Campagne af.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delen naar sociale netwerken (operationForward)<br /> </td> 
   <td> Het delen van activiteit en post open statistieken, hangt van Campagne af.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hypotheseverslag (operationHypothesis)<br /> </td> 
   <td> De samenvatting van hypothesemetingen voor de campagneleveringen wordt weergegeven, afhankelijk van Campagne.<br /> </td> 
  </tr> 
  <tr> 
   <td> Statistieken over de deelactiviteit (forwardActivityOpt)<br /> </td> 
   <td> De analyse van het delen van activiteiten, opent en abonnementen per tijdspanne, hangt van Campagne af.<br /> </td> 
  </tr> 
  <tr> 
   <td> Overzicht van levering (operationStatistics)<br /> </td> 
   <td> Samenvattend overzicht van de campagneleveringen: doelstellingen, uitsluitingen en verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL's en klik op doorvoer (operationTopUrlDelivery)<br /> </td> 
   <td> De meeste reactieve URL's en de bijbehorende klikstreams zijn afhankelijk van Campagne.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rapporten over diensten {#reports-on-services}

De verslagen over diensten hebben betrekking op de gegevens in de **nms:service** tabel.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label en interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Verwervingen van ventilatoren (socialAcquisitionsByWebapp)<br /> </td> 
   <td> Welke Webtoepassingen lieten de perspectiefverwervingen toe? Afhankelijk van de add-on voor sociale marketing.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uitsplitsing van abonnementen (mobileAppDistribution)<br /> </td> 
   <td> De onderverdeling van actieve abonnementen per mobiele toepassing is afhankelijk van de add-on voor mobiele toepassingskanalen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abonnementen bijhouden (subscriptionsProgress)<br /> </td> 
   <td> Ontwikkeling van de abonnementen op informatiediensten<br /> </td> 
  </tr> 
  <tr> 
   <td> Reactiviteitspercentage (socialReactionRate)<br /> </td> 
   <td> Wat zijn de reactiviteitspercentages voor de meest recente leveringen? Afhankelijk van de add-on voor sociale marketing.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reactiviteitssnelheid (mobileAppReactivityRate)<br /> </td> 
   <td> De mate van reactiviteit voor de meest recente leveringen is afhankelijk van de add-on voor het mobiele toepassingskanaal.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Begrotingsverslagen {#budget-reports}

De ingebouwde rapporten van Adobe Campaign zijn te vinden in de onderstaande tabel.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label en interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Kosten in verband met het programma (de programma's) (budgetProgramCost)<br /> </td> 
   <td> Uitsplitsing van de programmakosten.<br /> </td> 
   <td> nms:programma<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontwikkeling van de begroting (begrotingsontwikkeling)<br /> </td> 
   <td> Ontwikkeling van de begrotingskosten per vastleggingsniveau.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Cumulatieve ontwikkeling van de begroting (begrotingCumulatieve ontwikkeling)<br /> </td> 
   <td> Ontwikkeling van de gecumuleerde begrotingskosten, uitgesplitst naar komma<br /> tentniveau. </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Het onderzoeken van kostenlijnen (budgetExplorerBudget)<br /> </td> 
   <td> Beschrijvende analyse van kostenlijnen.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Het onderzoeken van kostenlijnen (budgetExplorer)<br /> </td> 
   <td> Beschrijvende analyse van kostenlijnen.<br /> </td> 
   <td> nms:costLine<br /> </td> 
  </tr> 
  <tr> 
   <td> Het onderzoeken van kostenlijnen (budgetExplorerPlan)<br /> </td> 
   <td> Beschrijvende analyse van kostenlijnen.<br /> </td> 
   <td> nms:plan<br /> </td> 
  </tr> 
  <tr> 
   <td> Het onderzoeken van kostenlijnen (budgetExplorerProgram)<br /> </td> 
   <td> Beschrijvende analyse van kostenlijnen.<br /> </td> 
   <td> nms:programma<br /> </td> 
  </tr> 
  <tr> 
   <td> Samenvatting van de begroting(en) (begroting)<br /> </td> 
   <td> Opname van de belangrijkste kosten, uitgavencategorieën en begrotingen.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rapporten over simulaties {#reports-on-simulations}

De simulatieverslagen hebben betrekking op de gegevens in het **nms:simulatie** tabel.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label en interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Detail van simulatieuitsluitingen (dlvSimuLossesDetail)<br /> </td> 
   <td> Gedetailleerde tabel van alle oorzaken van uitsluiting.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uitsplitsing van aanbiedingen naar rang (offerSimulationRanking)<br /> </td> 
   <td> Uitsplitsing van aanbiedingen in de simulatie, naar rang.<br /> </td> 
  </tr> 
  <tr> 
   <td> Samenvatting simulatie (dlvSimuLossesSummary)<br /> </td> 
   <td> Overzicht van simulatievolumes en -uitsluitingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Overlap statistische gegevens (dlvSimuOverlapping)<br /> </td> 
   <td> Leveringsdoel overlappende volumes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Overzicht van uitsluitingen als gevolg van de simulatie (dlvSimuLossesSimu)<br /> </td> 
   <td> Uitsluitingstabel als gevolg van de simulatie.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rapporten over webtoepassingen {#reports-on-web-applications}

Rapporten over de toepassingen van het Web betreffen de gegevens in **nms:WebApp** tabel.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label en interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Documentatie (surveyDictionary)<br /> </td> 
   <td> Een beschrijving van de structuur van de enquêtes is afhankelijk van de invoegtoepassing Beoordelingsmanager.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hoofd (surveyProperties)<br /> </td> 
   <td> Eigenschappen van enquêtes<br /> </td> 
  </tr> 
  <tr> 
   <td> Uitsplitsing van de antwoorden (surveyDistribution)<br /> </td> 
   <td> Uitsplitsing van antwoorden op vragen.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Overige taakrapporten {#other-ootb-reports}

De volgende rapporten worden ook ingebouwd verstrekt. Raadpleeg voor meer informatie het desbetreffende document over de functionaliteit.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label en interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Analyse van aanbieding (offerteanalyse)<br /> </td> 
   <td> De analyse van de aanbieding per datum en kanaal, hangt van de toe:voegen-op van de Interactie af.<br /> </td> 
   <td> nms:aanbieding<br /> </td> 
  </tr> 
  <tr> 
   <td> Efficiëntie van hermarketing (remarketingEffect)<br /> </td> 
   <td> Meting van de efficiëntie van het opnieuw in de handel brengen<br /> </td> 
   <td> nms:webEvent<br /> </td> 
  </tr> 
  <tr> 
   <td> Geschiedenis van sociale vooruitzichten (socialVisitorStatistics)<br /> </td> 
   <td> De geschiedenis van X (vroeger genoemd geworden Twitter) en de perspectiefverwervingen van Facebook, hangt van de sociale marketing toe:voegen-op af.<br /> </td> 
   <td> nms:bezoeker<br /> </td> 
  </tr> 
  <tr> 
   <td> Recente propositie-tracking (recentProposities)<br /> </td> 
   <td> Real-time proposition tracking<br /> </td> 
   <td> nms:propositionRcp<br /> </td> 
  </tr> 
 </tbody> 
</table>
