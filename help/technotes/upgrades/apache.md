---
product: campaign
title: Technote - Adobe Campaign - Beveiligingsupdate Apache-versie
description: Adobe Campaign - Beveiligingsupdate Apache-versie
hide: true
hidefromtoc: true
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 50dcdf1f6bcc8c8a195a0bf0a37af254f33b80d5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Adobe Campaign - Beveiligingsupdate Apache-versie {#apache-update}

>[!CAUTION]
>Dit artikel is van toepassing op: klanten van Campaign Classic v7 Managed Cloud Services, klanten van Campaign v8 en klanten van Campaign Standard.

Adobe Campaign werkt met hulpprogramma&#39;s van derden en de compatibiliteit wordt regelmatig bijgewerkt, zodat alleen ondersteunde versies kunnen worden geïmplementeerd en de nieuwste correcties en verbeteringen kunnen worden toegepast.

Adobe Campaign bevat Apache Tomcat, die via HTTP als ingangspunt fungeert in de toepassingsserver, en die is geïntegreerd met Apache Web-server. De Apache Software Foundation heeft Apache HTTP Server 2.4.53 uitgebracht. Deze versie verhelpt kwetsbaarheden die een externe aanvaller in staat kunnen stellen de controle over een beïnvloed systeem te verkrijgen. Leer meer in [ Apache 2.4.53 aankondiging ](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

Het team van Adobe Campaign zal de Apache activiteit van de de verbeteringsverbetering van de versieveiligheid tegen **15 Juni, 2022** leiden om deze kwetsbaarheid van Apache te verlichten en uw instantiemilieu veiliger te maken. Deze upgrade is van toepassing op alle klanten van Campaign Classic v7 Managed Cloud Services, Campaign v8 en Campaign Standard die op een kwetsbare versie van Apache HTTP Server werken. Adobe heeft al contact met u opgenomen om u op de hoogte te stellen van deze upgrade.

Van deze upgrade wordt verwacht dat deze automatisch buiten de normale kantooruren wordt uitgevoerd, zodat u de Campagneservice zonder onderbreking kunt blijven gebruiken.

Uw niet-productie-instantie(s) worden eerst door onze teams geüpgraded voordat we uw productie-instantie(s) upgraden. Aangezien dit een automatisch upgradeproces is dat eigendom is van Adobe, hoeft u niets te doen. Nochtans, als u om het even welke kwesties ervaart, gelieve [ de Zorg van de Klant van Adobe ](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"} te contacteren.


>[!NOTE]
>Deze upgrade vereist om de Apache-webserver opnieuw te starten. De downtime zal niet langer zijn dan 10 minuten binnen de hieronder vermelde periode.
> 

## Veelgestelde vragen {#apache-faq}

* **waarom is dit een verplichte verbetering?**

  De huidige Apache-versie is kwetsbaar en heeft een potentieel veiligheidsrisico. Het is belangrijk dat uw instantie(s) van de Campagne wordt (worden) geüpgraded naar de meest recente toepasselijke Apache-versie om het beveiligingsrisico te verhelpen.


* **welke klanten voor veiligheidsverbeteringen worden gericht?**

  Alle klanten die gebruikmaken van Campagne-omgevingen die zijn geïmplementeerd in oudere Apache-versies, worden geüpgraded naar de nieuwste Apache-versie die van toepassing is.

* **wat is de verwachte onderbreking?**

  De verwachte downtime is minder dan 10 minuten.

* **zijn er om het even welke acties die door de klant voor deze veiligheidsverbetering worden vereist?**

  Er zijn geen handelingen vereist omdat de beveiligingsupgrade automatisch wordt uitgevoerd.

* **Welke bevestigingen door de klanten moeten worden in werking gesteld?**

  Er is geen specifieke test nodig voor deze beveiligingsupgrade. Voor het geval om het even welke kwestie wordt waargenomen, te bereiken gelieve uit [ de Zorg van de Klant van Adobe ](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **kan ik om een verandering in Datum/Tijd aan de geplande groef van de veiligheidsverbetering verzoeken?**

  Aangezien dit een veiligheidsmoeilijke situatie is, adviseren wij u sterk aan het bestaande programma aan te passen.


Voor een andere vraag, kunt u uit aan [ de Zorg van de Klant van Adobe ](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"} bereiken.
