---
product: campaign
title: Leveringen
description: Meer informatie over standaardleveringsworkflows
feature: Workflows
role: User, Admin
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 6%

---


# Leveringen{#deliveries}



De hieronder beschreven workflows worden geïnstalleerd met de **Leveringen** module standaard.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Rapportageaggregaten</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Deze workflow werkt aggregaten bij die worden gebruikt in rapporten. Deze wordt standaard elke dag om 2 uur geactiveerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturering</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> Deze workflow stuurt het systeemactiviteitenrapport per e-mail naar de 'factureringsoperator'. Deze wordt standaard geactiveerd op de 25e van elke maand.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aliasreiniging</span> <br /> </td> 
   <td> <span class="uicontrol">aliasCleansing</span> <br /> </td> 
   <td> Deze werkstroom normaliseert opsommingswaarden. Deze wordt standaard elke dag om 3 uur geactiveerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update for deliverability</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Met deze workflow kunt u een lijst maken met regels voor stuiterende mailkwalificatie en een lijst met domeinen en MX's in het platform. Deze workflow werkt alleen als de HTTPS-poort geopend is. Deze lijsten worden alleen bijgewerkt als de module Leverbaarheid is geïnstalleerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database opschonen</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> <p>Dit werkschema is het werkschema van het gegevensbestandonderhoud: het maakt verschillende berekeningen van de statistieken en de processen, en schrapt verouderde gegevens uit het gegevensbestand volgens de bepaalde configuratie in de plaatsingsmedewerker. Het wordt teweeggebracht elke dag om 4.00 uur door gebrek.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Opschonen van gepauzeerde workflows</span> <br /> </td> 
   <td> <span class="uicontrol">cleanPausedWorkflows</span> <br /> </td> 
   <td> <p>In deze workflow worden gepauzeerde workflows geanalyseerd waarvoor de ernst is ingesteld op Normaal en worden waarschuwingen en meldingen geactiveerd wanneer deze al te lang zijn gepauzeerd. Na een maand worden gepauzeerde technische workflows onvoorwaardelijk gestopt. Standaard wordt de activering elke maandag om 17.00 uur gestart.</p> <p>Raadpleeg De afhandeling van gepauzeerde workflows voor meer informatie</a>.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Melding voorstel</span> <br /> </td> 
   <td> <span class="uicontrol">aanbiedingsbeheer</span> <br /> </td> 
   <td> Deze workflow implementeert goedgekeurde aanbiedingen in de onlineomgeving en in elke categorie in de aanbiedingencatalogus.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Prognose</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> Deze workflow analyseert leveringen die zijn opgeslagen in de voorlopige kalender (maakt voorlopige logbestanden). Het wordt teweeggebracht elke dag bij 1am door gebrek.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Tracking</span> <br /> </td> 
   <td> <span class="uicontrol">bijhouden</span> <br /> </td> 
   <td> Deze workflow voert het herstel en de consolidatie van trackinggegevens uit. Het verzekert ook de herberekening van het volgen en leveringsstatistieken, vooral die gebruikt door het archiveren van het Centrum van het Bericht werkschema. Deze wordt standaard één keer per uur geactiveerd. <br /> </td> 
  </tr> 
 </tbody> 
</table>

