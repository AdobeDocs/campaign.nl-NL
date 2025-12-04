---
title: Leveringsstatussen
description: Meer informatie over de statussen op het dashboard voor levering
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 3%

---

# Leveringsstatussen {#delivery-statuses}

Zodra een levering is verzonden, toont het leveringsdashboard een status die u toestaat om te controleren als het verzenden succesvol was. Mogelijke statussen worden beschreven in de onderstaande sectie.

![](assets/delivery-status.png)

Voor meer details op de verschillende leveringsmislukkingen kunt u ontmoeten, en hoe te om hen op te lossen, verwijs naar [&#x200B; Begrijpend leveringsmislukkingen &#x200B;](delivery-failures.md).

**Verwante onderwerpen:**

* [Uw e-mails verzenden en controleren](send.md)
* [Leveringsfouten begrijpen](delivery-failures.md)
* [Aan de slag met de prestaties](about-deliverability.md)

## Lijst van leveringsstatussen {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> Status <br /> </th> 
   <th> Definities en oplossingen <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Verzonden<br /> </td> 
   <td> De levering werd correct verzonden naar de berichtleverancier (maar de ontvanger niet noodzakelijk het ontving).<br /> </td> 
  </tr> 
  <tr> 
   <td> Genegeerd <br /> </td> 
   <td> De levering is niet naar de ontvanger verzonden vanwege een fout met hun adres. Het was of op lijst van gewezen personen, quarantined, niet verstrekt of een duplicaat. <br /> </td> 
  </tr> 
  <tr> 
   <td> Mislukt <br /> </td> 
   <td> De levering kan de ontvanger bijvoorbeeld niet bereiken vanwege een ongeldig adres of een volledig postvak. Het kan ook met een kwestie met verpersoonlijkingsblokken worden verbonden aangezien zij fouten kunnen produceren wanneer de schema's niet de leveringsafbeelding aanpassen. Zie <a href="delivery-failures.md" target="_blank"> Begrip leveringsmislukkingen </a><br /> </td> 
  </tr>
  <tr> 
   <td> In behandeling <br /> </td> 
   <td> De levering is klaar om te worden verzonden en zal door de leveringsserver (MTA) worden verwerkt. Zie <a href="#pending-status" target="_blank"> Hangende status </a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Niet van toepassing <br /> </td> 
   <td> De levering werd in aanmerking genomen door de server (MTA) maar niet verwerkt.<br /> </td> 
  </tr>  
  <tr> 
   <td> Aflevering geannuleerd <br /> </td> 
   <td> De levering werd geannuleerd door een exploitant.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rekening gehouden met door de dienstverlener <br /> </td> 
   <td> Voor SMS-leveringen heeft de SMS-serviceprovider de levering ontvangen.<br /> Voor e-mailleveringen is het bericht via Campagne doorgestuurd naar de MTA (Mail Transfer Agent).</td> 
  </tr> 
  <tr> 
   <td> Ontvangen op mobiel <br /> </td> 
   <td> De ontvanger ontving SMS op hun mobiele apparaat.<br /> </td> 
  </tr>
  <tr> 
   <td> Verzonden aan de dienstverlener <br /> </td> 
   <td> De levering werd verzonden naar de dienstverlener van SMS maar nog niet ontvangen.<br />
   </td> 
  </tr> 
  <tr> 
   <td> Voorbereid <br /> </td> 
   <td> De intermediaire status die slechts voor externe schakelaars zoals het mobiele kanaal wordt gebruikt. Het volgt de "Hangende"status en is de externe schakelaar die de volgende status zal bepalen.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Leren hoe te om de leverbaarheid van uw e-mails van Adobe Campaign te optimaliseren, verwijs naar [&#x200B; deze sectie &#x200B;](about-deliverability.md). Voor een diepere duik op leverability, verwijs naar de [&#x200B; Gids van de Beste praktijken van de Levering van Adobe &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl).

## Status in behandeling {#pending-status}

Nadat u de levering hebt bevestigd, ziet u dat de status van de levering **[!UICONTROL Pending]** is. Deze status houdt in dat het uitvoeringsproces wacht op de beschikbaarheid van bepaalde bronnen.

De status **[!UICONTROL Pending]** kan eerst betekenen dat de levering gepland is en in behandeling is tot de opgegeven datum. Voor meer op dit, verwijs naar de [&#x200B; levering die van het Programma &#x200B;](configure-and-send.md#schedule-delivery-sending) sectie verzendt.

Als uw levering niet wordt verzonden en de status ervan **[!UICONTROL Pending]** blijft, kan dit het gevolg zijn van:

* **Te veel campagnes die gelijktijdig lopen**

  De limiet van gelijktijdige campagnes wordt gedefinieerd in de optie **[!UICONTROL NmsOperation_LimitConcurrency]** . De standaardwaarde is 10.

  Als gebruiker van Managed Cloud Services kunt u indien nodig met Adobe samenwerken om deze limiet aan te passen. Leer meer over opties in [&#x200B; Campaign Classic v7 documentatie &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html?lang=nl-NL){target="_blank"}.

* **de beschikbaarheidskwesties van het Middel**

  MTA (de Agent van de Overdracht van het Bericht) kan op middelen wachten om beschikbaar te worden alvorens uw levering te verwerken.

>[!NOTE]
>
>Als Campagne v8 Managed Cloud Services-gebruiker wordt de MTA-infrastructuur gecontroleerd en beheerd door Adobe. Neem contact op met de klantenservice van Adobe als er zich blijvende problemen voordoen met in behandeling zijnde leveringen.

**Verwante onderwerpen:**

* [Uw e-mails verzenden en controleren](send.md#email-monitoring)
* [Leveringsfouten begrijpen](delivery-failures.md)
* [De Campagneomgeving bewaken](../start/monitor.md#monitor-deliveries)

