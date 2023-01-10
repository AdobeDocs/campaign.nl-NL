---
product: campaign
title: TechNote - Adobe Campaign-systeemupgrades
description: Adobe Campaign-systeemupgrade
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: f1e963a880e8499dbbb16c44831a4ce1b537601f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---

# Adobe Campaign 2023-omgevingsupgrades {#ac-system-upgrade}

De campagneinfrastructuur is afhankelijk van systemen van derden die regelmatig met de meest recente versies en correcties moeten worden bijgewerkt. Deze updates zijn verplicht om de continuïteit van de service en veilige Campagneomgevingen tegen beveiligingsrisico&#39;s te garanderen. Daarnaast is een Campagne-upgrade vereist om compatibiliteit met systeemwijzigingen van derden te garanderen.

Als **Klant voor beheerde Cloud Services** Adobe informeert u over deze upgrades wanneer deze nodig zijn. Uw omgevingen moeten overeenkomstig de aanbevelingen worden geüpgraded om naleving te garanderen.

Om veiligheidsredenen moet Adobe [De nieuwste build voor campagne installeren](#ac-upgrade)en upgrade vervolgens uw [besturingssysteem](#os-upgrade) en/of uw [Relation Database Management System (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>Voor vragen over deze wijzigingen neemt u contact op met de [Adobe-klantenservice](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

## Verbetering van campagne-build {#ac-upgrade}

**Heeft dit gevolgen voor u?**

Als de [besturingssysteemupgrade](#os-upgrade) en/of de [upgrade van databasesysteem](#pg-upgrade) hieronder gedetailleerd: Adobe moet uw Campagne-omgevingen upgraden naar [de nieuwste versie 8.4.3](../../v8/start/release-notes.md), die compatibel is met deze systemen.

**Hoe kan ik bijwerken?**

Als klant van Beheerde Cloud Services, zal Adobe u contacteren en uw versie van de Campagne bevorderen.

## Upgrade van besturingssysteem {#os-upgrade}

**Heeft dit gevolgen voor u?**

Als u Campagne op een Debian werkend systeem in werking stelt, om van de recentste beveiligingsupdates van Debian te profiteren, moet Adobe uw infrastructuur van de Campagne verplaatsen naar **Debian 11**. De beveiligingsondersteuning voor Debian 9 is beschikbaar tot 30 juni 2023.

**Hoe kan ik bijwerken?**

Als Beheerde klant van Cloud Services, zal Adobe u contacteren en uw milieu bevorderen.

## Upgrade van databasesysteem {#pg-upgrade}

**Heeft dit gevolgen voor u?**

Als uw databasesysteem voor Campagne PostSQL is om te kunnen profiteren van de nieuwste innovaties en beveiligingsupdates van PostSQL, moet Adobe een upgrade uitvoeren naar **PostgreSQL 14**. Merk op dat PostgreSQL 11 eind van het Leven op 9 November 2023 zal bereiken.

**Hoe kan ik bijwerken?**

Als Beheerde klant van Cloud Services, zal Adobe u contacteren en uw gegevensbestandsysteem van PostgreSQL 11 aan PostgreSQL 14 bevorderen.
