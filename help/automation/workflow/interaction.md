---
product: campaign
title: Interaction
description: Interactie
feature: Workflows, Interaction
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 3%

---


# Interactie{#interaction}

De hieronder beschreven workflows worden geïnstalleerd met de **Aanbiedingsengine (interactie)** standaard invoegtoepassing.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Volledige geaggregeerde berekening (voorzettingskubus)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> Deze workflow werkt de <strong>Volledig</strong> aggregaat voor de <strong>Voorstel</strong> kubus. Het wordt teweeggebracht elke dag om 6 uur door gebrek. In dit aggregaat worden de volgende afmetingen vastgelegd: Kanaal, levering, marketingaanbieding en datum.<br /> De <strong>Voorstel</strong> kube wordt dan gebruikt om rapporten te produceren die op aanbiedingen worden gebaseerd.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter volledige geaggregeerde berekening</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Deze workflow werkt de <strong>Volledig</strong> aggregaat voor de <strong>Berichtencentrum</strong> kubus. Deze wordt standaard elke dag om 3 uur geactiveerd. In dit aggregaat worden de volgende afmetingen vastgelegd: Het type Kanaal, Datum, Status en Gebeurtenis.<br /> De <strong>Berichtencentrum</strong> kubus wordt dan gebruikt om rapporten te produceren die op gebeurtenissen worden gebaseerd. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Meer informatie over kubussen en aggregaten in [deze sectie](../../v8/reporting/gs-cubes.md).

