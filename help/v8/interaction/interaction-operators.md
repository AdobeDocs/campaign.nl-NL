---
title: Operatorprofielen
description: Beheerders van aanbiedingen maken
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: eed3396584940f99a865eef2358887b6bf5c4936
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 4%

---

# Operatorprofielen {#operator-profiles}

Twee typen operatoren kunnen Campagne-interactie gebruiken: **Aanbiedingsmanagers** en **Leveringsmanagers**. Elk van hen heeft specifieke toestemmingen en beperkingen. Meer informatie over campagneoperatoren en -machtigingen in [deze pagina](../start/gs-permissions.md).

* De **[!UICONTROL Offer manager]** aanbiedingen maken en onderhouden.
* De **[!UICONTROL Delivery manager]** goedkeurt en gebruikt voorstellen

## Een beheerder van een voorstel maken{#offer-manager}

1. Maak een operator. [Meer informatie](../start/manage-permissions.md#add-users)
1. Bladeren naar de **[!UICONTROL Groups and named rights]** venster, klikt u op **[!UICONTROL Add]** en selecteert u de **[!UICONTROL Offer manager]** groep.

Machtigingen die zijn gekoppeld aan Offertenmanagers worden beschreven [hier](../start/manage-permissions.md#ootb-productprofiles)

## Een leveringsmanager-operator maken {#delivery-manager}

1. Maak een operator. [Meer informatie](../start/manage-permissions.md#add-users)
1. Bladeren naar de **[!UICONTROL Groups and named rights]** tabblad, klikt u op **[!UICONTROL Add]** en selecteert u de **[!UICONTROL Delivery manager]** groep.

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
