---
product: campaign
title: Webanalyse
description: Meer informatie over het pakket Webanalyse
feature: Workflows, Analytics Integration
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 1%

---


# Webanalyse{#web-analytics}



De hieronder gedetailleerde werkschema&#39;s worden geïnstalleerd met de **schakelaars van de Analyse van het Web** module door gebrek.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong> Interne naam </strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol"> verzendt van indicatoren en campagnerekenmerken </span> <br /> </td> 
   <td> <span class="uicontrol"> webAnalyticsSendMetrics </span> <br /> </td> 
   <td> Met deze workflow kunt u e-mailcampagneindicatoren van Adobe Campaign naar Adobe Experience Cloud Suite verzenden via de Adobe® Analytics-connector. De betrokken indicatoren zijn als volgt: <strong> Verzonden </strong> (Verzonden), <strong> Totale telling van opent </strong> (iTotalRecipientOpen), <strong> Totaal aantal ontvangers die </strong> (iTotalRecipientClick) klikte, <strong> Fouten </strong> (iError), <strong> Opt-Out </strong> (opt-out) (iOptOut).<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol"> Identificatie van omgezette contacten </span> <br /> </td> 
   <td> <span class="uicontrol"> webAnalyticsFindConverted </span> <br /> </td> 
   <td> Deze workflow indexeert bezoekers van de site die hun aankoop hebben voltooid na een campagne voor het opnieuw op de markt brengen van producten. De gegevens die door dit werkschema worden teruggekregen kunnen in het <span class="uicontrol"> re-marketing efficiëntierapport </span> worden betreden (verwijs naar dit). <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol"> De purge van de Gebeurtenis </span> <br /> </td> 
   <td> <span class="uicontrol"> webAnalyticsPurgeWebEvents </span> <br /> </td> 
   <td> Dit werkschema laat u elke gebeurtenis van het gegevensbestandgebied volgens de periode schrappen die op het <span class="uicontrol"> wordt gevormd Levensduur </span> gebied. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol"> Terugwinning van Webgebeurtenissen </span> <br /> </td> 
   <td> <span class="uicontrol"> webAnalyticsGetWebEvents </span> <br /> </td> 
   <td> Elk uur downloadt deze workflow segmenten op het gedrag van internetgebruikers op een bepaalde site, plaatst deze in de Adobe Campaign-database en start de workflow voor het opnieuw in de handel brengen. <br /> </td> 
  </tr> 
 </tbody> 
</table>

