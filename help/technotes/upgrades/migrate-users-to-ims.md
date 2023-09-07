---
title: Campagnebeheerders migreren naar Adobe Identity Management System (IMS)
description: Leer hoe u campagneoperatoren kunt migreren naar Adobe Identity Management System (IMS)
hide: true
hidefromtoc: true
source-git-commit: 11128dcb26119383b86aa62561ec0ce1a3c138ad
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 1%

---

# Campagnebeheerders migreren naar Adobe Identity Management System (IMS) {#migrate-users-to-ims}

Vanaf Campagne v8.6 wordt het verificatieproces naar Campagne v8 verbeterd. Alle operatoren gebruiken [Adobe Identity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} alleen om verbinding te maken met Campagne. Verbinding maken met gebruiker/wachtwoord wordt niet langer toegestaan. Adobe raadt aan deze migratie uit te voeren in Campagne v8.5.2 om probleemloos te kunnen migreren naar Campagne v8.6.

In dit artikel worden de stappen beschreven die nodig zijn om een technische operator naar een technische account op de Adobe Developer-console te migreren.

## Wat is er veranderd?{#move-to-ims-changes}

Alle regelmatige gebruikers van de Campagne zouden reeds met de Adobe Campaign cliëntconsole moeten verbinden gebruikend hun Adobe ID, door het Systeem van de Adobe van Identity Management (IMS). Bij sommige oudere configuraties waren de gebruikers-/wachtwoordverbindingen echter nog steeds beschikbaar. Dit is niet langer toegestaan voor het starten van campagne v8.6.

Daarnaast roept de Adobe Campaign Client-toepassing als onderdeel van de inspanningen om het beveiligings- en verificatieproces te versterken nu de campagne-API&#39;s rechtstreeks aan met behulp van het technische IMS-accounttoken. De migratie van technische operatoren vindt plaats in een speciaal artikel dat beschikbaar is in [deze pagina](ims-migration.md).

Deze wijziging is van toepassing vanaf Campagne 8.5.2 en wordt **verplicht** startcampagne v8.6.


## Heeft dit gevolgen voor u?{#migrate-ims-impacts}

Als de exploitanten in uw organisatie met de cliëntconsole van de Campagne gebruikend hun login/wachtwoord verbinden (alias. (native verificatie), heeft dit invloed op u en moet u deze operator(s) migreren naar Adobe IMS, zoals hieronder beschreven.

IMS-migratie is een beveiligingsvereiste om uw omgevingen veilig en gestandaardiseerd te maken, aangezien de meeste andere Adobe DX-apps al op IMS staan.

## Hoe migreren?{#ims-migration-procedure}

### Vereisten{#ims-migration-prerequisites}

Voordat u met het migratieproces begint, moet u contact opnemen met uw Adobe-medewerker (Transition Manager), zodat technische teams van Adoben uw bestaande groepen met operatoren en benoemde rechten kunnen migreren naar het Adobe Identity Management System (IMS).

### Belangrijkste stappen {#ims-migration-steps}

De belangrijkste stappen voor deze migratie worden hieronder weergegeven:

1. Adobe verbetert uw omgevingen naar Campagne v8.5.2.
1. Na de upgrade kunt u nog steeds nieuwe gebruikers maken met beide methoden, als native gebruiker of met IMS.
1. Uw interne beheerder van de Campagne moet unieke e-mails aan alle inheemse gebruikers op de de cliëntconsole van de Campagne toevoegen, en aan uw Manager van de Overgang van de Adobe bevestigen zodra dit wordt gedaan. Deze stap wordt beschreven in [deze sectie](#ims-migration-id).
1. Werk met Adobe om een datum te beveiligen waarop Adobe automatisch kan worden uitgevoerd voor niet-technische gebruikers (operators) en productprofielen. Deze stap vereist een uurvenster zonder onderbreking aan om het even welk van uw instanties.
1. Uw interne beheerder van de Campagne bevestigt deze verandering en verstrekt aftekening. Na deze migratie moet u geen andere operator meer maken die wordt geverifieerd met zijn aanmeldingsnaam en wachtwoord.

U kunt nu de migratie van technische gebruikers naar IMS plannen volgens [dit technote](ims-migration.md)en bevestig dat de Adobe Transition Manager klaar is.
De Adobe markeert de migratie vervolgens als voltooid en schakelt de vlaggen in om het maken van nieuwe native gebruikers en het aanmelden van native gebruikers te blokkeren.

## Veelgestelde vragen? {#ims-migration-faq}

### Wanneer kunt u de migratie starten? {#ims-migration-start}

Een eerste vereiste voor de migratie naar Adobe Identity Management System (IMS) is het upgraden van uw omgeving naar Campaign v8.5.2.

U kunt de migratie van IMS op uw werkgebiedomgeving starten zodra deze is bijgewerkt naar Campagne v8.5.2 en dienovereenkomstig plannen voor de productieomgeving.

### Wat gebeurt na 8.5.2 bouwstijlverbetering? {#ims-migration-after-upgrade}

Nadat uw omgevingen zijn bijgewerkt naar Campagne versie 8.5.2, kunt u Adobe Identity Management System (IMS)-migratie uitvoeren.

Het maken van nieuwe native gebruikers is nog steeds toegestaan totdat de IMS-migratie is voltooid.

### Wanneer is de migratie voltooid? {#ims-migration-end}

Zodra de migratie van de eindgebruiker en de technische gebruikersmigratie aan het Systeem van AdobeIdentity Management (IMS) wordt gedaan, moet u uw Manager van de Overgang van de Adobe contacteren zodat de Adobe uw migratie kan merken volledig, en gebruikersverwezenlijking van de cliëntconsole, en inheemse gebruikerslogin blokkeren.


### Hoe kunt u na de migratie gebruikers maken? {#ims-migration-native}

Zodra de volledige IMS-migratie is voltooid, past de Adobe de beperkingen toe die het maken van nieuwe native gebruikers blokkeren. Deze beperkingen worden niet toegepast totdat de IMS-migratie is voltooid.

Voor nieuwe klanten - het maken van nieuwe native gebruikers is niet vanaf het begin toegestaan.

Als beheerder van de Campagne, kunt u toestemmingen aan de gebruikers van uw organisatie via Adobe Admin Console en de Console van de Cliënt van de Campagne verlenen. Gebruikers melden zich aan bij Adobe Campaign met hun Adobe ID. Meer informatie in [deze documentatie](../../v8/start/gs-permissions.md).

### E-mails toevoegen voor huidige native gebruikers? {#ims-migration-id}

Als Campagnebeheerder moet u e-mailadressen toevoegen aan alle native gebruikers vanaf de clientconsole. Volg onderstaande stappen om dit te doen:

1. Verbinding maken met de clientconsole en bladeren naar **Beheer > Toegangsbeheer > Operatoren**
1. Selecteer de operator die u wilt bijwerken in de lijst met operatoren.
1. Voer de e-mail van de operator in het dialoogvenster **Contactpunten** van het formulier met operatoren.
1. Sla uw wijzigingen op.


### Hoe u zich via IMS aanmeldt bij Campaign? {#ims-migration-log}

Leer hoe u verbinding kunt maken met uw Adobe ID in [deze sectie](../../v8/start/connect.md).