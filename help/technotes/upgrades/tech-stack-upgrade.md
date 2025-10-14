---
product: campaign
title: Technote - Adobe Campaign-systeemupgrades
description: Adobe Campaign-systeemupgrade
hide: true
hidefromtoc: true
exl-id: cc64cce1-2473-4136-aadc-8b13e89ef7f9
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Adobe Campaign 2023-upgrades voor de omgeving {#ac-system-upgrade}

De campagneinfrastructuur is afhankelijk van systemen van derden die regelmatig met de meest recente versies en correcties moeten worden bijgewerkt. Deze updates zijn verplicht om de continuïteit van de service en veilige Campagneomgevingen tegen beveiligingsrisico&#39;s te garanderen. Daarnaast is een Campagne-upgrade vereist om te zorgen voor compatibiliteit met systeemwijzigingen van derden.

Als a **Beheerde klant van de Diensten van de Wolk**, informeert Adobe u over deze verbeteringen wanneer zij nodig zijn. Uw omgevingen moeten overeenkomstig de aanbevelingen worden geüpgraded om naleving te garanderen.

Voor veiligheidsredenen, moet Adobe [&#x200B; de recentste Bouwstijl van de Campagne &#x200B;](#ac-upgrade) installeren, en dan uw [&#x200B; werkend systeem &#x200B;](#os-upgrade) en/of uw [&#x200B; Systeem van het Beheer van het Gegevensbestand van de Verhouding (RDBMS) &#x200B;](#pg-upgrade) bevorderen.

>[!NOTE]
>
>Voor vragen over deze wijzigingen neemt u contact op met de [Adobe-klantenservice](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>

## Verbetering van campagne-build {#ac-upgrade}

**Heeft dit gevolgen voor u?**

Als u door de [&#x200B; werkend systeemverbetering &#x200B;](#os-upgrade) en/of de [&#x200B; hieronder gedetailleerde verbetering van het gegevensbestandsysteem &#x200B;](#pg-upgrade) wordt beïnvloed, moet Adobe uw milieu&#39;s van de Campagne aan [&#x200B; recentste versie 8.4.3 &#x200B;](../../v8/start/release-notes.md) bevorderen, die met deze systemen compatibel is.

**Hoe kan ik bijwerken?**

Als klant van de Managed Cloud Services zal Adobe contact met u opnemen en uw versie van de Campagne upgraden.

## Upgrade van besturingssysteem {#os-upgrade}

**Heeft dit gevolgen voor u?**

Als u Campagne op een Debian werkend systeem in werking stelt, om van recentste Debian veiligheidsupdates te profiteren, moet Adobe uw infrastructuur van de Campagne aan **Debian 11** bewegen. De beveiligingsondersteuning voor Debian 9 is beschikbaar tot 30 juni 2023.

**Hoe kan ik bijwerken?**

Als klant van Managed Cloud Services zal Adobe contact met u opnemen en uw omgeving upgraden.

## Upgrade van databasesysteem {#pg-upgrade}

**Heeft dit gevolgen voor u?**

Als uw gegevensbestandsysteem voor Campagne PostSQL is, om van recentste innovaties en veiligheidsupdates te profiteren PostgreSQL, moet Adobe aan **PostgreSQL 14** bevorderen. Merk op dat PostgreSQL 11 eind van het Leven op 9 November 2023 zal bereiken.

**Hoe kan ik bijwerken?**

Als klant van de Managed Cloud Services zal Adobe contact met u opnemen en uw databasesysteem upgraden van PostgreSQL 11 naar PostgreSQL 14.
