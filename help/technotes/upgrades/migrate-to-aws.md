---
title: Campagne migreren die infrastructuur naar Amazon Web Services (AWS) verzendt
description: Campagne migreren die infrastructuur naar Amazon Web Services (AWS) verzendt
hide: true
hidefromtoc: true
source-git-commit: 15beb6e4aae7a00b245277bcb4c6c60c13b22884
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 2%

---


# Campagne die de migratie van de infrastructuur naar Amazon Web Services (AWS) verzendt {#migrate-infra-to-aws}

## Wat is er veranderd?{#aws-changes}

Als onderdeel van onze voortdurende inspanningen om de service voor e-maillevering van de hoogste kwaliteit te bieden, wordt de infrastructuur voor het verzenden van e-mailberichten via campagne verplaatst van door de Adobe gehoste datacenters naar Amazon Web Services (AWS).

Deze stap zorgt voor hoge beschikbaarheid, optimale doorvoer en de mogelijkheid om te schalen om aan de behoeften van onze klanten te voldoen.

## Heeft dit gevolgen voor u?{#aws-impact}

Deze wijziging heeft invloed op:

* Campaign Classic v7-gehoste en hybride klanten
* Campagne voor Managed Services-klanten
* Alle v8-klanten voor campagne
* Campaigns Standard

## Wanneer zal deze migratie plaatsvinden?{#aws-timeline}

De migratie naar ontwikkelings- en testomgevingen vindt plaats in **Oktober 2023**.

De migratie naar productieomgevingen wordt gepland om te beginnen in **januari 2024**. Naarmate de datum nadert, zullen meer details worden verstrekt.

Als klant van de Campagne, zult u extra bericht ontvangen aangezien de migratiegolven gepland zijn. Meldingen worden ten minste 7 dagen vóór de migratie voor werkgebiedomgevingen verzonden en ten minste 30 dagen vóór de migratie voor productieomgevingen.

## Wat is de impact?{#impact}

Deze stap is transparant voor klanten:

* De migratie zal naar verwachting 30 tot 60 minuten duren

* Campagneinstanties kunnen geen e-mail verzenden tijdens het migratievenster. Geen enkele andere Campagnefunctie wordt beïnvloed.


## Veelgestelde vragen {#aws-faq}

* **Waarom is dit een verplichte upgrade?**

  Adobe is van plan het oude datacenter uit te schakelen, Adobe Campaign-instanties die daar actief zijn, moeten worden overgebracht naar het nieuwe referentiecentrum in Amazon Web Services (AWS).

  De Adobe Managed Services cloud wordt gehost op Amazon Web Services (AWS), een moderne, veilige en geoptimaliseerde omgeving. [Meer informatie over Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **Welke klanten worden gericht voor deze migratie?**

  Alle klanten van Campaign v8 en Campaign Classic v7 hybride, gehoste en Campaign Managed Services zullen hun omgevingen migreren. Ook de afnemers in de Campaign Standard hebben gevolgen.

* **Wat is de verwachte onderbreking?**

  De verwachte downtime ligt tussen 30 en 60 minuten.

* **Zijn er acties die door de klant voor migratie worden vereist?**

  Er zijn geen handelingen vereist omdat de Adobe de migratie automatisch uitvoert.

* **Welke bevestigingen moeten door de klanten worden in werking gesteld?**

  Voor deze migratie zijn geen specifieke tests nodig. Indien een probleem wordt vastgesteld, kunt u contact opnemen met [Klantenservice Adoben](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **Kan ik om een verandering in Datum/Tijd in de geplande groef van de veiligheidsverbetering verzoeken?**

  Aangezien dit een verplichte migratie is, raden we u ten zeerste aan zich aan te passen aan het bestaande schema.


Voor elke andere vraag kunt u zich tot [Klantenservice Adoben](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
