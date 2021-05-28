---
solution: Campaign v8
product: Adobe Campaign
title: Operatoren voor Campagne-interactie
description: Beheerders van aanbiedingen maken
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: 167730cc3e81ee47f02bcdbc2c39fe793a99c534
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# Operatorprofielen {#operator-profiles}

Twee typen operatoren kunnen Campagne-interactie gebruiken: **Bied managers** en **Leveringsmanagers** aan. Elk van hen heeft specifieke toestemmingen en beperkingen. Meer informatie over campagneoperatoren en -machtigingen vindt u op [deze pagina](../start/permissions.md).

* Met **[!UICONTROL Offer manager]** worden aanbiedingen gemaakt en onderhouden.
* De **[!UICONTROL Delivery manager]** keurt en gebruikt aanbiedingen goed

## Creeer een manager van de Aanbieding exploitant{#offer-manager}

1. Maak een nieuwe operator.

   [!DNL :arrow_upper_right:] De stappen om een exploitant in Campagne tot stand te brengen zijn gedetailleerd in  [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

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
>Een **Aanbiedingsmanager** kan alleen een aanbieding goedkeuren als er geen controleur is opgegeven of als hij/zij is gedeclareerd als controleur in de aanbiedingstemplate waarop de aanbieding was gebaseerd.

## Een leveringsbeheeroperator {#delivery-manager} maken

1. Maak een nieuwe operator.

   [!DNL :arrow_upper_right:] De stappen om een exploitant in Campagne tot stand te brengen zijn gedetailleerd in  [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Ga naar het **[!UICONTROL Groups and named rights]** venster, klik **[!UICONTROL Add]** en selecteer **[!UICONTROL Delivery manager]** groep.

De aan de leveringsmanager toegewezen rechten zijn/laten hen toe om de volgende taken uit te voeren:

* Geef **[!UICONTROL Live]** omgevingen weer.
* Categorieën voorstellen weergeven en wijzigen.
* Aanbiedingen goedkeuren als s/he is opgegeven als een van de controleurs.

   >[!NOTE]
   >
   >Een **Leveringsmanager** kan een aanbieding slechts goedkeuren als hij/zij als recensent tijdens de aanbiedingsconfiguratie is verklaard.

## Machtigingsmatrix per interactieoperator {#recap-of-rights-according-to-operator}

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
   <td> Typologieregels<br /> </td> 
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
   <td> Typologieregels<br /> </td> 
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
