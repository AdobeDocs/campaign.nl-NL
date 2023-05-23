---
title: Tips en trucs voor beveiliging
description: Ga aan de slag met best practices voor Campagne-beveiliging
feature: Privacy, PI
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---

# Tips en trucs voor beveiliging {#ac-security}

Bij Adobe nemen we de beveiliging van je digitale ervaring zeer serieus. Beveiligingspraktijken zijn diep verankerd in onze interne processen en tools voor softwareontwikkeling en -bewerkingen en worden rigoureus gevolgd door onze interfunctionele teams om incidenten op een snelle manier te voorkomen, op te sporen en erop te reageren.

Bovendien helpen onze samenwerking met partners, toonaangevende onderzoekers, instellingen voor veiligheidsonderzoek en andere brancheorganisaties ons bij het up-to-date houden met de nieuwste dreigingen en kwetsbaarheden en wij nemen regelmatig geavanceerde veiligheidstechnieken op in de producten en diensten die wij aanbieden.

## Privacy

De configuratie van de privacy en het verharden is een zeer belangrijk element van veiligheidsoptimalisering. Hier volgen enkele aanbevolen procedures voor privacy:

* Protect uw klant Personal Information (PI) via HTTPS in plaats van HTTP
* Gebruiken [Beperking van PI-weergave](../dev/restrict-pi-view.md) om de privacy te beschermen en te voorkomen dat gegevens worden misbruikt
* Controleer of gecodeerde wachtwoorden beperkt zijn
* Protect de pagina&#39;s die persoonlijke gegevens kunnen bevatten, zoals spiegelpagina&#39;s, webtoepassingen, enz.

![](../assets/do-not-localize/speech.png)  Als Beheerde gebruiker van Cloud Services, zal Adobe met u werken om deze configuraties op uw milieu uit te voeren.


## Toegangsbeheer

Toegangsbeheer is een belangrijk onderdeel van de beveiliging. Hier volgen enkele van de belangrijkste aanbevolen procedures:

* Maak genoeg beveiligingsgroepen
* Controleren of elke operator de juiste toegangsrechten heeft

Meer informatie over machtigingen in [deze sectie](../start/gs-permissions.md)

## Codeerrichtlijnen

Volg bij het ontwikkelen in Adobe Campaign (workflows, Javascript, JSSP, enz.) altijd de volgende richtlijnen:

* **Scripts**: Probeer SQL-instructies te vermijden, gebruik parameterized functies in plaats van tekenreekssamenvoeging en vermijd SQL-injectie door de SQL-functies toe te voegen die u aan de lijst van gewenste personen wilt gebruiken.

* **Het gegevensmodel beveiligen**: gebruik genoemde rechten om exploitatoracties te beperken, systeemfilters toe te voegen (sysFilter)

* **Hoofdletters toevoegen aan webtoepassingen**: Voeg hoofdletters toe aan uw openbare bestemmingspagina&#39;s en abonnementspagina&#39;s.

![](../assets/do-not-localize/book.png) Meer informatie in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}


## Personalisatie

Wanneer u persoonlijke koppelingen toevoegt aan uw inhoud, moet u altijd geen persoonlijke instellingen opgeven in het gedeelte hostnaam van de URL om mogelijke hiaten in de beveiliging te voorkomen. De volgende voorbeelden mogen nooit in alle URL-kenmerken worden gebruikt &lt;`a href="">` of `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Gegevensbeperking

U moet ervoor zorgen dat de gecodeerde wachtwoorden niet toegankelijk zijn voor gebruikers met lage bevoegdheden. Daarvoor zijn er twee manieren: de toegang tot wachtwoordvelden of tot de gehele entiteit beperken.

Met deze beperking kunt u wachtwoordvelden verwijderen, maar de externe account blijft toegankelijk vanuit de interface voor alle gebruikers. Meer informatie in [deze pagina](../dev/restrict-pi-view.md).

1. Ingaan **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Een nieuwe **[!UICONTROL Extension of a schema]**.

1. Kies **[!UICONTROL External Account]** (extAccount).

1. In het laatste scherm, kunt u uw nieuw srcSchema uitgeven om toegang tot alle wachtwoordgebieden te beperken:

   U kunt het hoofdelement (`<element name="extAccount" ... >`) door:

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   Zo kan uw uitgebreide srcSchema als kijken:

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >U kunt `$(loginId) = 0 or $(login) = 'admin'` door `hasNamedRight('admin')` om alle gebruikers met het juiste admin te laten deze wachtwoorden zien.


## Toegangsbeheer

Toegangsbeheer is een belangrijk onderdeel van de beveiliging. Hier volgen enkele van de belangrijkste aanbevolen procedures:

* Maak genoeg beveiligingsgroepen
* Controleren of elke operator de juiste toegangsrechten heeft

Meer informatie over machtigingen in [in deze sectie](../start/gs-permissions.md).

## Codeerrichtlijnen

Volg bij het ontwikkelen in Adobe Campaign (workflows, Javascript, JSSP, enz.) altijd de volgende richtlijnen:

* **Scripts**: Probeer SQL-instructies te vermijden, gebruik parameterized functies in plaats van tekenreekssamenvoeging en vermijd SQL-injectie door de SQL-functies toe te voegen die u aan de lijst van gewenste personen wilt gebruiken.

* **Het gegevensmodel beveiligen**: gebruik genoemde rechten om exploitatoracties te beperken, systeemfilters toe te voegen (sysFilter)

* **Hoofdletters toevoegen aan webtoepassingen**: Voeg hoofdletters toe aan uw openbare bestemmingspagina&#39;s en abonnementspagina&#39;s.

![](../assets/do-not-localize/book.png) Meer informatie in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}
