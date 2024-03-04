---
product: campaign
title: Technote - Adobe Campaign-systeemupgrades
description: Adobe Campaign-systeemupgrade
hide: true
hidefromtoc: true
source-git-commit: c362e6ff932f5017530434c4b458070ec1a97abc
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Adobe Campaign 2023-upgrades voor de omgeving {#ac-system-upgrade}

De campagneinfrastructuur is afhankelijk van systemen van derden die regelmatig met de meest recente versies en correcties moeten worden bijgewerkt. Deze updates zijn verplicht om de continuïteit van de service en veilige Campagneomgevingen tegen beveiligingsrisico&#39;s te garanderen. Daarnaast is een Campagne-upgrade vereist om te zorgen voor compatibiliteit met systeemwijzigingen van derden.

Als **Klant voor beheerde Cloud Servicen**, informeert de Adobe u over deze upgrades wanneer deze nodig zijn. Uw omgevingen moeten overeenkomstig de aanbevelingen worden geüpgraded om naleving te garanderen.

Om veiligheidsredenen moet de Adobe [De nieuwste build voor campagne installeren](#ac-upgrade)en upgrade vervolgens uw [besturingssysteem](#os-upgrade) en/of uw [Relation Database Management System (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>Voor vragen over deze wijzigingen neemt u contact op met de [Adobe-klantenservice](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>

## Verbetering van campagne-build {#ac-upgrade}

**Heeft dit gevolgen voor u?**

Als de [besturingssysteemupgrade](#os-upgrade) en/of de [upgrade van databasesysteem](#pg-upgrade) hieronder gedetailleerd, moet de Adobe uw Campagneomgevingen upgraden naar [de nieuwste versie 8.4.3](../../v8/start/release-notes.md), die compatibel is met deze systemen.

**Hoe kan ik bijwerken?**

Als klant van Beheerde Cloud Servicen, zal de Adobe u contacteren en uw versie van de Campagne bevorderen.

## Upgrade van besturingssysteem {#os-upgrade}

**Heeft dit gevolgen voor u?**

Als u Campagne op een Debian werkend systeem in werking stelt, om van de recentste beveiligingsupdates van Debian te profiteren, moet de Adobe uw infrastructuur van de Campagne verplaatsen naar **Debian 11**. De beveiligingsondersteuning voor Debian 9 is beschikbaar tot 30 juni 2023.

**Hoe kan ik bijwerken?**

Als Beheerde klant van Cloud Servicen, zal de Adobe u contacteren en uw milieu bevorderen.

## Upgrade van databasesysteem {#pg-upgrade}

**Heeft dit gevolgen voor u?**

Als uw databasesysteem voor Campagne PostSQL is om te kunnen profiteren van de nieuwste innovaties en beveiligingsupdates van PostSQL, moet de Adobe een upgrade uitvoeren om **PostgreSQL 14**. Merk op dat PostgreSQL 11 eind van het Leven op 9 November 2023 zal bereiken.

**Hoe kan ik bijwerken?**

Als Beheerde klant van Cloud Servicen, zal de Adobe u contacteren en uw gegevensbestandsysteem van PostgreSQL 11 aan PostgreSQL 14 bevorderen.
