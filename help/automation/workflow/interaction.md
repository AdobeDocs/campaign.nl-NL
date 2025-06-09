---
product: campaign
title: Interactie
description: Interactie
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 1%

---


# Interactie{#interaction}

De hieronder gedetailleerde werkschema&#39;s worden geïnstalleerd met de **motor van de Aanbieding (Interactie)** toe:voegen-op door gebrek.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong> Interne naam </strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol"> Volledige geaggregeerde berekening (de kubus van het voorstel) </span> <br /> </td> 
   <td> <span class="uicontrol"> agg_nmsproposition_rcp_full </span> <br /> </td> 
   <td> Dit werkschema werkt het <strong> Volledige </strong> aggregaat voor de <strong> 3} kubus van het voorstel van de Aanbieding bij. </strong> Het wordt teweeggebracht elke dag om 6.00 uur door gebrek. In dit aggregaat worden de volgende afmetingen vastgelegd: Kanaal, Levering, Aanbieding en Datum van marketing.<br /> De <strong> 2} kubus van het Voorstel van de Aanbieding wordt dan gebruikt om rapporten te produceren die op aanbiedingen worden gebaseerd.<br /></strong> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol"> MessageCenter volledige geaggregeerde berekening </span> <br /> </td> 
   <td> <span class="uicontrol"> agg_messageCenter_full </span> <br /> </td> 
   <td> Dit werkschema werkt het <strong> Volledige </strong> aggregaat voor het <strong> centrum van het Bericht </strong> kubus bij. Deze wordt standaard elke dag om 3 uur geactiveerd. In dit aggregaat worden de volgende afmetingen vastgelegd: Kanaal, Datum, Status en gebeurtenistype.<br /> De <strong> centrum van het Bericht </strong> kubus wordt dan gebruikt om rapporten te produceren die op gebeurtenissen worden gebaseerd. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Leer meer over kubussen en aggregaten in [ deze sectie ](../../v8/reporting/gs-cubes.md).

