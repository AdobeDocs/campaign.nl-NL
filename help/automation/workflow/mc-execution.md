---
product: campaign
title: Berichtcentrum (uitvoering)
description: Berichtcentrum (uitvoering)
feature: Workflows
role: User
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 2%

---


# Berichtcentrum (uitvoering){#message-center-execution}

De hieronder gedetailleerde werkschema&#39;s worden geïnstalleerd met het **Centrum van het Bericht - de uitvoering** toe:voegen-op door gebrek.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong> Interne naam </strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gebeurtenisstatus bijwerken</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Met deze workflow kunt u een status aan een gebeurtenis toewijzen. De status van de gebeurtenis is als volgt:<br /> 
    <ul> 
     <li> <p><strong> Hangende </strong>: de gebeurtenis is in een rij. Er is nog geen berichtsjabloon aan gekoppeld.</p> </li> 
     <li> <p><strong> Hangende levering </strong>: de gebeurtenis is in een rij, is een berichtmalplaatje verbonden aan het en momenteel verwerkt door de levering.</p> </li> 
     <li> <p><strong> Verzonden </strong>: deze status wordt gekopieerd van de leveringslogboeken. Dit betekent dat de levering is verzonden.</p> </li> 
     <li> <p><strong> genegeerd door de levering </strong>: deze status wordt gekopieerd van de leveringslogboeken. Het betekent dat de levering is genegeerd.</p> </li> 
     <li> <p><strong> fout van de Levering </strong>: deze status wordt gekopieerd van de leveringslogboeken. Het betekent dat de levering is mislukt.</p> </li> 
     <li> <p><strong> Gebeurtenis niet behandeld </strong>: de gebeurtenis is er niet in geslaagd om met een berichtmalplaatje worden geassocieerd. De gebeurtenis wordt niet opnieuw verwerkt.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol"> de partijgebeurtenissen van de Verwerking </span> <br /> </td> 
   <td> <span class="uicontrol"> batchEventsProcessing </span> <br /> </td> 
   <td> Met deze workflow kunt u batchgebeurtenissen in een wachtrij plaatsen voordat u ze aan een berichtsjabloon koppelt. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol"> Verwerking real time gebeurtenissen </span> <br /> </td> 
   <td> <span class="uicontrol"> rtEventsProcessing </span> <br /> </td> 
   <td> Dit werkschema laat u gebeurtenissen in real time in een rij zetten alvorens hen met een berichtmalplaatje te associëren. <br /> </td> 
  </tr> 
 </tbody> 
</table>

