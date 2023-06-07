---
title: Aan de slag met machtigingen in Campagne v8
description: Meer informatie over het definiëren van machtigingen in Campagne v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 2%

---

# Aan de slag met machtigingen{#gs-permissions}

Met Adobe Campaign kunt u de rechten definiëren en beheren die aan gebruikers zijn toegewezen. Dit zijn een reeks rechten en beperkingen die autoriseren of weigeren:

* Toegang tot bepaalde mogelijkheden
* Toegang tot bepaalde gegevens
* Toegang tot bepaalde handelingen (maken, wijzigen, verwijderen)

Deze toestemmingen worden bepaald door de toestemmingen van de exploitantgroep, genoemde rechten en toestemmingen op omslagen te combineren.

In Adobe Campaign zijn gebruikers **operatoren** en **groepen met operatoren** vertegenwoordigen gebruikersrollen. Een operator is een Adobe Campaign-gebruiker die gemachtigd is om zich aan te melden en handelingen uit te voeren. Gebruikers worden in de Admin Console gemaakt. De machtigingen zijn van toepassing op gebruikersprofielen of groepen gebruikers. Er zijn twee soorten toestemmingen u kunt verlenen:

* U kunt groepen operatoren definiëren waaraan u rechten toewijst en de operatoren vervolgens koppelen aan een of meer groepen. Op deze manier kunt u rechten opnieuw gebruiken en de consistentie van operatorprofielen verhogen. Het vergemakkelijkt ook het beheer en het onderhoud van gebruikersprofielen.
* U kunt benoemde rechten rechtstreeks aan gebruikers toewijzen, in sommige gevallen om de rechten die via groepen zijn toegewezen, te overladen.

## Belangrijke stappen om machtigingen te verlenen{#key-steps-permissions}

Als productbeheerder, kunt u toestemmingen aan de gebruikers van uw organisatie verlenen. Machtigingen worden verleend via Adobe Admin Console en Campagne Client Console. Gebruikers melden zich aan bij Adobe Campaign met hun Adobe ID. Leer hoe u verbinding maakt met Adobe Campaign in [deze pagina](connect.md).

De belangrijkste stappen zijn:

* **Stap 1**: Definieer de groepen met operatoren en wijs deze machtigingen toe in de Campagne Client Console. [Meer informatie](manage-permissions.md#create-product-profile).
U kunt ook ingebouwde groepen operatoren gebruiken om mee te beginnen. Deze standaardgroepen en hun machtigingen worden vermeld in [deze sectie](manage-permissions.md#ootb-productprofiles).
* **Stap 2**: Maak in de Admin Console productprofielen die overeenkomen met deze groepen. [Meer informatie](manage-permissions.md#create-product-profile).
U kunt ingebouwde productprofielen gebruiken om met te beginnen. [Meer informatie](manage-permissions.md#ootb-productprofiles).
* **Stap 3**: Maak gebruikers in de Admin Console en wijs ze toe aan een productprofiel. [Meer informatie](manage-permissions.md#add-users).
* **Stap 4** (optioneel): Machtigingen toewijzen aan mappen. [Meer informatie](manage-permissions.md#ootb-productprofiles).

## Over de Admin Console{#gs-admin-console}

De Adobe Admin Console is een centrale locatie voor het beheer van de rechten van de Adobe in uw organisatie. Dit is alleen toegankelijk voor productbeheerders.

Gebruik de Admin Console om gebruikers toe te voegen, productprofielen te creëren en toe te wijzen (die groepen exploitantrollen zijn).

Leer hoe u gebruikers kunt toevoegen in [deze pagina](manage-permissions.md#add-users).

## Productprofielen{#ootb-product-profiles}

Productprofielen zijn groepen producten en services die u aan gebruikers kunt toewijzen. In Adobe Experience Cloud zijn machtigingen gebaseerd op het profiel van een product, niet op de gebruiker. U kunt beheerrechten echter wel delegeren aan bepaalde gebruikers.

In de Admin Console, elke Adobe Experience Cloud **productprofiel** voor Campagne is gekoppeld aan een **groep met operatoren** in Campaign Client Console.

Leer hoe u productprofielen maakt en toewijst in [deze pagina](manage-permissions.md#create-a-product-profile).

## Campagne met benoemde rechten{#named-rights}

Als lid van een productprofiel (d.w.z. exploitantgroep), heeft een gebruiker rechten om verrichtingen uit te voeren, genoemd &quot;Benoemde Rechten&quot;, en heeft lees en/of schrijf toegang tot gegevens. Een operator kan lid zijn van meerdere groepen operatoren: rechten en toegangsrechten zijn additief .

Meer informatie over benoemde rechten in [deze sectie](manage-permissions.md#use-named-rights).
