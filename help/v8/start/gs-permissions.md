---
title: Aan de slag met machtigingen in Campagne v8
description: Meer informatie over het definiëren van machtigingen in Campagne v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 1%

---

# Aan de slag met machtigingen{#gs-permissions}

Met Adobe Campaign kunt u de rechten definiëren en beheren die aan gebruikers zijn toegewezen. Dit zijn een reeks rechten en beperkingen die autoriseren of weigeren:

* Toegang tot bepaalde mogelijkheden
* Toegang tot bepaalde gegevens
* Toegang tot bepaalde handelingen (maken, wijzigen, verwijderen)

Deze machtigingen worden gedefinieerd door machtigingen voor groepen van operatoren, benoemde rechten en machtigingen voor mappen te combineren.

In Adobe Campaign, zijn de gebruikers **exploitanten** en **exploitantgroepen** vertegenwoordigen gebruikersrollen. Een operator is een Adobe Campaign-gebruiker die gemachtigd is om zich aan te melden en handelingen uit te voeren. Gebruikers worden gemaakt in de Admin Console. De machtigingen zijn van toepassing op gebruikersprofielen of groepen gebruikers. Er zijn twee soorten toestemmingen u kunt verlenen:

* U kunt groepen operatoren definiëren waaraan u rechten toewijst en de operatoren vervolgens koppelen aan een of meer groepen. Op deze manier kunt u rechten opnieuw gebruiken en de consistentie van operatorprofielen verhogen. Het vergemakkelijkt ook het beheer en het onderhoud van gebruikersprofielen.
* U kunt benoemde rechten rechtstreeks aan gebruikers toewijzen, in sommige gevallen om de rechten die via groepen zijn toegewezen, te overladen.

## Belangrijke stappen om machtigingen te verlenen{#key-steps-permissions}

Als productbeheerder, kunt u toestemmingen aan de gebruikers van uw organisatie verlenen. Machtigingen worden verleend via Adobe Admin Console en Campagne Client Console. Gebruikers melden zich aan bij Adobe Campaign met hun Adobe ID. Leer hoe te met Adobe Campaign in [&#x200B; te verbinden deze pagina &#x200B;](connect.md).

De belangrijkste stappen zijn:

* **Stap 1**: Bepaal uw exploitantgroepen en wijs hen toestemmingen in de Console van de Cliënt van de Campagne toe. [&#x200B; leer meer &#x200B;](manage-permissions.md#create-product-profile).
U kunt ook ingebouwde groepen operatoren gebruiken om mee te beginnen. Deze standaardgroepen, en hun toestemmingen, zijn vermeld in [&#x200B; deze sectie &#x200B;](manage-permissions.md#ootb-productprofiles).
* **Stap 2**: Creeer productprofielen in Adobe Admin Console die met die groepen aanpassen. [&#x200B; leer meer &#x200B;](manage-permissions.md#create-product-profile).
U kunt ingebouwde productprofielen gebruiken om met te beginnen. [Meer informatie](manage-permissions.md#ootb-productprofiles).
* **Stap 3**: Creeer gebruikers in Adobe Admin Console, en wijs hen aan een productprofiel toe. [Meer informatie](manage-permissions.md#add-users).
* **Stap 4** (facultatief): Wijs toestemmingen op omslagen toe. [Meer informatie](manage-permissions.md#ootb-productprofiles).

## Over de Admin Console{#gs-admin-console}

De Adobe Admin Console is een centrale locatie voor het beheer van Adobe-rechten in uw hele organisatie. Dit is alleen toegankelijk voor productbeheerders.

Gebruik de Admin Console om gebruikers toe te voegen, productprofielen te maken en toe te wijzen (dit zijn groepen operatorrollen).

Leer hoe te om gebruikers in [&#x200B; toe te voegen deze pagina &#x200B;](manage-permissions.md#add-users).

## Productprofielen{#ootb-product-profiles}

Productprofielen zijn groepen producten en services die u aan gebruikers kunt toewijzen. In Adobe Experience Cloud zijn machtigingen gebaseerd op het profiel van een product, niet op de gebruiker. U kunt beheerrechten echter wel delegeren aan bepaalde gebruikers.

In Admin Console, wordt elk Adobe Experience Cloud **productprofiel** voor Campagne geassocieerd aan een **exploitantgroep** in de Console van de Cliënt van de Campagne.

Leer om productprofielen in [&#x200B; tot stand te brengen en toe te wijzen deze pagina &#x200B;](manage-permissions.md#create-a-product-profile).

## Campagne met benoemde rechten{#named-rights}

Als lid van een productprofiel (d.w.z. exploitantgroep), heeft een gebruiker rechten om verrichtingen uit te voeren, genoemd &quot;Benoemde Rechten&quot;, en heeft lees en/of schrijf toegang tot gegevens. Een operator kan lid zijn van meerdere groepen operatoren: rechten en toegangsmachtigingen zijn additief.

Leer meer over genoemde rechten in [&#x200B; deze sectie &#x200B;](manage-permissions.md#use-named-rights).
