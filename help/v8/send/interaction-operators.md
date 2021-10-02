---
title: Operatoren voor Campagne-interactie
description: Beheerders van aanbiedingen maken
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: bda1fc37181396d295ee23a7161053d839d9cfc7
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Operatorprofielen {#operator-profiles}

Twee typen operatoren kunnen Campagne-interactie gebruiken: **Bied managers** en **Leveringsmanagers** aan. Elk van hen heeft specifieke toestemmingen en beperkingen. Meer informatie over campagneoperatoren en -machtigingen vindt u op [deze pagina](../start/permissions.md).

* Met **[!UICONTROL Offer manager]** worden aanbiedingen gemaakt en onderhouden.
* De **[!UICONTROL Delivery manager]** keurt en gebruikt aanbiedingen goed

## Een beheerder van een voorstel maken{#offer-manager}

1. Maak een nieuwe operator.

   ↗️ stappen om een exploitant in Campagne tot stand te brengen zijn gedetailleerd in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Ga naar het **[!UICONTROL Groups and named rights]** venster, klik **[!UICONTROL Add]** en selecteer **[!UICONTROL Offer manager]** groep.

De aan de Offertenbeheerder toegekende rechten stellen hen in staat de volgende taken uit te voeren:

* Wijzig **[!UICONTROL Design]** milieu&#39;s.
* **[!UICONTROL Live]**-omgevingen weergeven.
* Vorm beleidsfuncties (vooraf bepaalde ruimten en filters).
* Categorieën maken en wijzigen.
* Maak voorstellen.
* Geschiktheid van aanbieding configureren.
* Voorstel goedkeuren.

Als aanbiedingen worden gebruikt in een workflow, moet de operator worden toegevoegd aan de operatorgroep **[!UICONTROL Administrator]** of **[!UICONTROL Offer managers]** om de workflow uit te voeren.

>[!NOTE]
>
>**Aanbiedingsmanagers** kunnen een aanbieding alleen goedkeuren als er geen controleur is opgegeven of als deze in de aanbiedingstemplate als controleurs is gedeclareerd.

## Een leveringsmanager-operator maken {#delivery-manager}

1. Maak een nieuwe operator.

   ↗️ stappen om een exploitant in Campagne tot stand te brengen zijn gedetailleerd in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Ga naar het **[!UICONTROL Groups and named rights]** venster, klik **[!UICONTROL Add]** en selecteer **[!UICONTROL Delivery manager]** groep.

Met de aan leveringsmanagers toegekende rechten kunnen zij de volgende taken uitvoeren:

* Geef **[!UICONTROL Live]** omgevingen weer.
* Categorieën voorstellen weergeven en wijzigen.
* Aanbiedingen goedkeuren als ze revisoren zijn.

   >[!NOTE]
   >
   >**De** manager van de levering kan slechts een aanbieding goedkeuren als zij als recensent in de aanbiedingsconfiguratie zijn verklaard.

## Machtigingsmatrix per interactie-operator {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Aanbiedingsbeheer (ontwerpversie)</strong><br /> </td> 
   <td> <strong>Aanbiedingsbeheer (Live env)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Boomstructuurniveau</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Voorstellen die worden bewerkt/Live voorstellen<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontvanger - Omgeving<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Beheer<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Spaties<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Vooraf gedefinieerde aanbiedingsfilters<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologie<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologische regels<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Catalogus aanbod<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Aanbiedingscategorie<br /> </td> 
   <td> Lezen/Schrijven<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Leveringsmanager (Design Env.)</strong><br /> </td> 
   <td> <strong>Leveringsmanager (Live Env.)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Boomstructuurniveau</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Voorstellen die worden bewerkt/Live voorstellen<br /> </td> 
   <td> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontvanger - Omgeving<br /> </td> 
   <td> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Beheer<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Spaties<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Vooraf gedefinieerde aanbiedingsfilters<br /> </td> 
   <td> Lezen<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologie<br /> </td> 
   <td> Lezen<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologische regels<br /> </td> 
   <td> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Catalogus aanbod<br /> </td> 
   <td> Lezen<br /> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
  <tr> 
   <td> Aanbiedingscategorie<br /> </td> 
   <td> </td> 
   <td> Lezen<br /> </td> 
  </tr> 
 </tbody> 
</table>
