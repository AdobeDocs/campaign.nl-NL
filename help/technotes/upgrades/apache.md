---
product: campaign
title: Technote - Adobe Campaign - Beveiligingsupdate Apache-versie
description: Adobe Campaign - Beveiligingsupdate Apache-versie
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Adobe Campaign - Beveiligingsupdate Apache-versie {#apache-update}

>[!CAUTION]
>Dit artikel is van toepassing op: Campaign Classic v7 Beheerde klanten van Cloud Servicen, klanten van de Campagne v8 en klanten van de Campaign Standard.

Adobe Campaign werkt met hulpprogramma&#39;s van derden en de compatibiliteit wordt regelmatig bijgewerkt, zodat alleen ondersteunde versies kunnen worden geïmplementeerd en de nieuwste correcties en verbeteringen kunnen worden toegepast.

Adobe Campaign bevat Apache Tomcat, die via HTTP als ingangspunt fungeert in de toepassingsserver, en die is geïntegreerd met Apache Web-server. De Apache Software Foundation heeft Apache HTTP Server 2.4.53 uitgebracht. Deze versie verhelpt kwetsbaarheden die een externe aanvaller in staat kunnen stellen de controle over een beïnvloed systeem te verkrijgen. Meer informatie in [Apache 2.4.53](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

Het Adobe Campaign-team voert de upgradeactiviteiten voor de Apache-versie uit door **15 juni 2022** om deze Apache-kwetsbaarheid te beperken en uw instantieomgeving veiliger te maken. Deze upgrade is van toepassing op alle klanten van Campaign Classic v7 Managed Cloud Servicen, Campaign v8 en Campaigns Standard die op een kwetsbare versie van Apache HTTP Server werken. Als dit gevolgen heeft, heeft de Adobe al contact met u opgenomen om u op de hoogte te stellen van deze upgrade.

Van deze upgrade wordt verwacht dat deze automatisch buiten de normale kantooruren wordt uitgevoerd, zodat u de Campagneservice zonder onderbreking kunt blijven gebruiken.

Uw niet-productie-instantie(s) worden eerst door onze teams geüpgraded voordat we uw productie-instantie(s) upgraden. Aangezien dit een automatisch upgradeproces is dat eigendom is van de Adobe, is er geen actie van uw kant vereist. Als u echter problemen ondervindt, kunt u contact opnemen met [Klantenservice Adoben](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


>[!NOTE]
>Deze upgrade vereist om de Apache-webserver opnieuw te starten. De downtime zal niet langer zijn dan 10 minuten binnen de hieronder vermelde periode.
> 

## Veelgestelde vragen {#apache-faq}

* **Waarom is dit een verplichte upgrade?**

  De huidige Apache-versie is kwetsbaar en heeft een potentieel veiligheidsrisico. Het is belangrijk dat uw instantie(s) van de Campagne wordt (worden) geüpgraded naar de meest recente toepasselijke Apache-versie om het beveiligingsrisico te verhelpen.


* **Welke klanten worden gericht voor veiligheidsupgrades?**

  Alle klanten die gebruikmaken van Campagne-omgevingen die zijn geïmplementeerd in oudere Apache-versies, worden geüpgraded naar de nieuwste Apache-versie die van toepassing is.

* **Wat is de verwachte onderbreking?**

  De verwachte downtime is minder dan 10 minuten.

* **Zijn er om het even welke acties die door de klant voor deze veiligheidsverbetering worden vereist?**

  Er zijn geen handelingen vereist omdat de beveiligingsupgrade automatisch wordt uitgevoerd.

* **Welke bevestigingen moeten door de klanten worden in werking gesteld?**

  Er is geen specifieke test nodig voor deze beveiligingsupgrade. Indien een probleem wordt vastgesteld, kunt u contact opnemen met [Klantenservice Adoben](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **Kan ik om een verandering in Datum/Tijd in de geplande groef van de veiligheidsverbetering verzoeken?**

  Aangezien dit een veiligheidsmoeilijke situatie is, adviseren wij u sterk aan het bestaande programma aan te passen.


Voor elke andere vraag kunt u zich tot [Klantenservice Adoben](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
