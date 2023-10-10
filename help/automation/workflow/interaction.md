---
product: campaign
title: Interaction
description: Interaction
feature: Workflows, Interaction
role: User, Admin
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 3%

---


# Interaction{#interaction}

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
   <td> Deze workflow werkt de <strong>Volledig</strong> aggregaat voor de <strong>Voorstel</strong> kubus. Het wordt teweeggebracht elke dag om 6.00 uur door gebrek. In dit aggregaat worden de volgende afmetingen vastgelegd: Kanaal, Levering, Aanbieding en Datum van marketing.<br /> De <strong>Voorstel</strong> kube wordt dan gebruikt om rapporten te produceren die op aanbiedingen worden gebaseerd.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter volledige geaggregeerde berekening</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Deze workflow werkt de <strong>Volledig</strong> aggregaat voor de <strong>Berichtencentrum</strong> kubus. Deze wordt standaard elke dag om 3 uur geactiveerd. In dit aggregaat worden de volgende afmetingen vastgelegd: Kanaal, Datum, Status en gebeurtenistype.<br /> De <strong>Berichtencentrum</strong> kubus wordt dan gebruikt om rapporten te produceren die op gebeurtenissen worden gebaseerd. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Meer informatie over kubussen en aggregaten in [deze sectie](../../v8/reporting/gs-cubes.md).

