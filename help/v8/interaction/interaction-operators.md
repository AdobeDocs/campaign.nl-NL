---
title: Operatorprofielen
description: Beheerders van aanbiedingen maken
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 8a43f0fad9f84849745f3a0d426329efbf228105
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# Operatorprofielen {#operator-profiles}

Twee typen operatoren kunnen Campagne-interactie gebruiken: **Aanbiedingsmanagers** en **Leveringsmanagers**. Elk van hen heeft specifieke toestemmingen en beperkingen. Meer informatie over campagneoperatoren en -machtigingen in [deze pagina](../start/permissions.md).

* De **[!UICONTROL Offer manager]** aanbiedingen maken en onderhouden.
* De **[!UICONTROL Delivery manager]** goedkeurt en gebruikt voorstellen

## Een beheerder van een voorstel maken{#offer-manager}

1. Maak een operator.

   ![](../assets/do-not-localize/book.png) De stappen om een exploitant in Campagne tot stand te brengen zijn gedetailleerd in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Ga naar de **[!UICONTROL Groups and named rights]** venster, klikt u op **[!UICONTROL Add]** en selecteert u de **[!UICONTROL Offer manager]** groep.

De aan de Offertenbeheerder toegekende rechten stellen hen in staat de volgende taken uit te voeren:

* Wijzigen **[!UICONTROL Design]** omgevingen.
* Weergave **[!UICONTROL Live]** omgevingen.
* Configureer beheerfuncties (vooraf gedefinieerde spaties en filters).
* Categorieën maken en wijzigen.
* Maak voorstellen.
* Geschiktheid van aanbieding configureren.
* Voorstel goedkeuren.

Als aanbiedingen in een workflow worden gebruikt, moet de operator aan de **[!UICONTROL Administrator]** of **[!UICONTROL Offer managers]** groep met operatoren om de workflow uit te voeren.

>[!NOTE]
>
>**Aanbiedingsmanagers** kan een aanbieding alleen goedkeuren als er geen controleur is opgegeven of als deze in de aanbiedingstemplate als controleurs is gedeclareerd.

## Een leveringsmanager-operator maken {#delivery-manager}

1. Maak een operator.

   ![](../assets/do-not-localize/book.png) De stappen om een exploitant in Campagne tot stand te brengen zijn gedetailleerd in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Ga naar de **[!UICONTROL Groups and named rights]** venster, klikt u op **[!UICONTROL Add]** en selecteert u de **[!UICONTROL Delivery manager]** groep.

Met de aan leveringsmanagers toegekende rechten kunnen zij de volgende taken uitvoeren:

* Weergave **[!UICONTROL Live]** omgevingen.
* Categorieën voorstellen weergeven en wijzigen.
* Aanbiedingen goedkeuren als ze revisoren zijn.

   >[!NOTE]
   >
   >**Leveringsmanagers** kan een aanbieding alleen goedkeuren als deze in de aanbiedingsconfiguratie als controleur is gedeclareerd.

## Machtigingsmatrix per interactie-operator {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Aanbiedingsbeheer (ontwerpomgeving)</strong><br /> </td> 
   <td> <strong>Aanbiedingsbeheer (Live-omgeving)</strong><br /> </td> 
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
   <td> Ontvanger - Milieu<br /> </td> 
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
   <td> vooraf gedefinieerde aanbiedingsfilters<br /> </td> 
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
   <td> Aanbiedingscatalogus<br /> </td> 
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
   <td> Ontvanger - Milieu<br /> </td> 
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
   <td> vooraf gedefinieerde aanbiedingsfilters<br /> </td> 
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
   <td> Aanbiedingscatalogus<br /> </td> 
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
