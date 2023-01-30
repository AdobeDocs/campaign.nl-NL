---
product: campaign
title: Campaign
description: Campaign
feature: Workflows
topic-tags: technical-workflows
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 3%

---


# Campaign{#campaign}

De hieronder beschreven workflows worden geïnstalleerd met de **Campagne** module standaard.

>[!CAUTION]
>
>Deze workflows MOETEN worden gestart om de campagneprocessen op campagnereniveau te kunnen uitvoeren.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Interne naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Kostprijsberekening</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span> <br /> </td> 
   <td> Deze workflow start de berekening van kosten en kostenposten voor de begrotingen, plannen, programma's, campagnes, leveringen en taken.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Voorraad: Orders en waarschuwingen</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> Deze workflow start voorraadberekening op de orderregels en beheert drempelwaarden voor waarschuwingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Banen op leveringen in campagnes</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> Deze workflow activeert de goedgekeurde leveringen en start de naverwerking van de serviceprovider voor een externe levering. Het verzendt ook goedkeuringsberichten en herinneringen.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Campagnebanen</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> In deze workflow worden de taken voor marketingcampagnes beheerd (starttaken, bestanden uitpakken, enz.). Het leidt ook tot werkschema's met betrekking tot terugkomende en periodieke campagnes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Banen voor dienstverleners</span> <br /> </td> 
   <td> <span class="uicontrol">providerbeheer</span> <br /> </td> 
   <td> Dit werkschema begint de leverancier (e-mail aan de router en post-verwerking) te verwerken zodra de leveringen zijn goedgekeurd. <br /> </td> 
  </tr> 
 </tbody> 
</table>

