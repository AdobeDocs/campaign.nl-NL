---
product: campaign
title: Aan de slag met gedistribueerde marketing
description: Aan de slag met gedistribueerde marketing
feature: Distributed Marketing
role: User
exl-id: c9f5b277-3ad8-4316-94b9-789d37813b8b
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 0%

---

# Aan de slag met gedistribueerde marketing{#about-distributed-marketing}

Adobe Campaign biedt de toepassing van de a **Verdeelde Marketing** voor het uitvoeren van coöperatieve campagnes tussen centrale entiteiten (hoofdkwartier, marketing afdelingen, enz.) en lokale entiteiten (verkooppunten, regionale agentschappen, enz.) aan. Deze samenwerking is gebaseerd op een gedeelde werkruimte, de zogenaamde **[!UICONTROL list of campaign packages]** , waar centraal gemaakte campagnemalplaatjes en -instanties worden aangeboden aan lokale entiteiten.

De centrale entiteit verstrekt campagnes die lokale entiteiten kunnen gebruiken. Campagnes worden geconcretiseerd door pakketten die lokale of samenwerkingscampagnes vertegenwoordigen. Om een campagne te kunnen voeren, moet de lokale entiteit deze opdracht geven en moet de bestelling worden goedgekeurd.

>[!CAUTION]
>
>De verdeelde module van de Marketing is de optie van de a **Campagne**. Controleer hiervoor uw licentieovereenkomst.

## Terminologie {#terminology}

* **Centrale entiteiten**

  De centrale entiteiten bestaan uit marketingexploitanten die verantwoordelijk zijn voor het specificeren van de communicatie en die lokale entiteiten bijstaan bij het uitvoeren van hun marketingcampagne.

  De verdeelde marketing module staat de centrale entiteit toe om:

   * het opzetten van marketingcampagnes voor lokale entiteiten;
   * de mate van autonomie van lokale entiteiten ten aanzien van hun keuze in klant/vooruitzicht communicatie, het richten, inhoud, enz. te vergroten.
   * beheer- en controlekosten;
   * een netwerk van agentschappen te beheren.

* **Lokale entiteiten**

  Lokale entiteiten kunnen agentschappen, winkels of groepen van specifieke lokale exploitanten zijn (landelijke of regionale managers, merkbeheerders, enz.).

  Met Distributed Marketing kunnen lokale entiteiten meer autonomie hebben en tegelijk de uitvoeringskosten optimaliseren.

* **Localization**

  Lokalisatie is de capaciteit van een lokale entiteit om het doel en de inhoud van een campagne te wijzigen. Het mogelijke niveau van localisatie hangt van het type van campagne en zijn implementatie af.

* **Lijst van campagnepakketten**

  De lijst met campagnepakketten bevat de campagnes die beschikbaar zijn voor lokale entiteiten.

* **pakket van de Campagne**

  Sjabloon (of campagneexemplaar) dat door een centrale entiteit is gemaakt en ter beschikking is gesteld van een set lokale entiteiten.

* **Lokale campagne**

  Een lokale campagne is een geval dat van een malplaatje wordt gecreeerd dat in de lijst van **[!UICONTROL campaign packages]** met a **wordt van verwijzingen wordt voorzien specifiek uitvoeringsprogramma**. Zijn doel is om aan een lokale communicatie behoefte te voldoen gebruikend een campagnemalplaatje dat opstelling en gevormd door de centrale entiteit was.

  De mate van autonomie van de lokale entiteit hangt af van de gebruikte implementatie.

  Verwijs naar [&#x200B; Creërend een lokale campagne &#x200B;](creating-a-local-campaign.md).

* **Samenwerkende campagne**

  Een samenwerkingscampagne is een campagne de waarvan **uitvoeringsprogramma** door de centrale entiteit wordt bepaald, die de lokale entiteit kan gebruiken. De inhoud blijft voor elke lokale entiteit hetzelfde, maar de kosten worden gedeeld. Om deel te nemen, onderschrijven lokale entiteiten de samenwerkingscampagne.

   * **[!UICONTROL Collaborative campaign (by form)]**: aanbevolen voor campagnes waarbij maximaal 300 lokale entiteiten zijn betrokken. De lokale entiteit kan vooraf gedefinieerde parameters invoeren voor het toewijzen van doelen en inhoud aan de persoonlijke voorkeur in een webformulier. Het formulier kan een Adobe Campaign-formulier of een extern formulier (extranetclient) zijn. Een functionele beheerder kan het formulier definiëren en configureren op basis van een formuliersjabloon dat door de integrator is gedefinieerd. Om de campagne te bestellen, heeft de lokale entiteit enkel Webtoegang nodig.
   * **[!UICONTROL Collaborative campaign (by campaign)]** : aanbevolen voor campagnes die zijn gericht op tientallen lokale entiteiten. Dit type campagne leidt tot kindcampagnes voor elke lokale entiteit. Nadat **[!UICONTROL collaborative campaign (by campaign)]** door de centrale entiteit is goedgekeurd, wordt de campagne beschikbaar gesteld aan de lokale entiteit, die deze kan wijzigen. Uitvoering wordt automatisch gesynchroniseerd tussen bovenliggende en onderliggende campagnes. De lokale entiteit moet toegang hebben tot een instantie om een campagne te bestellen en er deel van te nemen.
   * **[!UICONTROL Collaborative campaign (by target approval)]** : aanbevolen voor campagnes gericht op duizenden lokale entiteiten. De lokale entiteit ontvangt een lijst van contacten die door de centrale entiteit vooraf is bepaald. De lokale entiteit beslist of bepaalde contacten op basis van de inhoud van de campagne al dan niet via een webformulier worden onderhouden. Lokale entiteiten worden afgeleid van de lijst met geselecteerde contactpersonen. Om aan de campagne deel te nemen, heeft de lokale entiteit enkel Webtoegang nodig.
   * **[!UICONTROL Collaborative campaign (simple)]** : deze modus zorgt voor compatibiliteit met de specifieke uitvoeringsprocessen van eerdere versies.

  Verwijs naar [&#x200B; Creërend een samenwerkingscampagne &#x200B;](creating-a-collaborative-campaign.md).

**die tot campagnepakketten opdracht geven**

Als een lokale entiteit zich voor een campagne registreert, wordt dit in een orde gemaakt die alle informatie met betrekking tot de campagnemelocalisatie groepeert.

## Workspace {#workspace}

De lijst van campagnepakketten kan van de **Campagnes** tabel worden betreden: klik de **[!UICONTROL Campaign packages]** verbinding.

![](assets/mkg_dist_home_local_op.png)

Met dit venster kunnen alle lokale operatoren de campagnes bekijken die beschikbaar zijn voor hun lokale agentschap.

In het geval van centrale agentschappen, toont dit venster alle pakketten beschikbaar in de lijst van campagnepakketten en biedt extra verbindingen voor het uitgeven van de lijst.

## Exploitanten en entiteiten {#operators-and-entities}

Begin door de centrale en lokale entiteitexploitanten via de **[!UICONTROL Access management]** omslag te specificeren.

![](assets/s_advuser_mkg_dist_tree.png)

### Operatoren {#operators}

U moet centrale en lokale operatoren maken.

Centrale operatoren moeten behoren tot de operatorgroep **[!UICONTROL Central management]** of de operator **[!UICONTROL CENTRAL]** een naam geven.

Lokale operatoren moeten tot de **[!UICONTROL Local management]** -operatorgroep behoren of de **[!UICONTROL LOCAL]** -operator een naam geven. Zij moeten ook gekoppeld zijn aan hun lokale entiteit.

![](assets/s_advuser_mkg_dist_local_create.png)

### Organisatorische entiteiten {#organizational-entities}

Als u een organisatie-entiteit wilt maken, klikt u op de map **[!UICONTROL Administration > Access management > Organizational entities]** en klikt u op het pictogram **[!UICONTROL New]** boven de lijst met entiteiten.

![](assets/s_advuser_mkg_dist_local_list.png)

Elke organisatorische entiteit bevat identificatiegegevens (label, interne naam, contactgegevens, enz.) en groepen die betrokken zijn bij het goedkeuringsproces van orders. Deze worden gedefinieerd in de sectie **[!UICONTROL Notifications and approvals]** op het tabblad **[!UICONTROL General]** .

* Definieer een groep met pakketmeldingen: operatoren in deze groep ontvangen elke keer dat een nieuw pakket aan de lijst met campagnepakketten wordt toegevoegd en elke keer dat een campagne beschikbaar wordt.
* Selecteer de groep van controleurs die belast is met de goedkeuring van orders, d.w.z. de controleurs die verantwoordelijk zijn voor de goedkeuring van door de lokale entiteit bestelde campagnes.
* Tot slot selecteert u de groep van controleurs die verantwoordelijk is voor de goedkeuring van de lokale campagne (doel, inhoud, budget, enz.). Afhankelijk van de sjabloon kan deze groep worden toegevoegd aan het bestellen van een campagne.

>[!NOTE]
>
>Het goedkeuringsproces wordt voorgesteld in de [&#x200B; sectie van het proces van de Goedkeuring &#x200B;](creating-a-local-campaign.md#approval-process).

## Implementatie {#implementation}

De verdeelde campagnes van de Marketing worden gecreeerd en door de centrale entiteit gepubliceerd. Zij kunnen door zowel lokale als centrale entiteiten worden gebruikt wanneer dat nodig is.

De procedure voor de tenuitvoerlegging hangt af van het type campagnemakket dat wordt gebruikt en het niveau van de delegaties van de lokale entiteit.

### Integratietaken {#integrator-side}

1. Lokale entiteiten maken.
1. Verbind ontvangers met de exploitanten die lokale entiteiten beheren.

   ![](assets/mkg_dist_local_entity_association.png)

1. Rechten en bladerregels voor lokale entiteiten opgeven
1. Geef de set velden op die nodig zijn voor de lokalisatie van de campagne:

   * definitie van het doel en maximumgrootte;
   * inhoudsdefinitie,
   * uitvoeringsprogramma (contactdatum en extractiedatum), **slechts voor lokale exploitanten**,
   * uitbreiding van het bestelschema met alle noodzakelijke extra gebieden.

1. Maak een webformulier (Adobe of extranet) waarmee u lokalisatieparameters kunt weergeven, het doel en het budget kunt evalueren en een voorvertoning van de inhoud kunt weergeven en de volgorde kunt goedkeuren.

   Voor **samenwerkingscampagnes (door doelgoedkeuring)**, creeer de lijst waar de goedkeuringen voor elke lokale entiteit zullen worden bewaard.

### Functionele beheerderstaken {#functional-administrator-side}

Deze stappen moeten worden uitgevoerd bij het opzetten van elke campagne.

1. Werk het formulier bij met de velden die worden gebruikt voor de lokalisatie van de campagne.
1. Maak een instantie van een geschikt campagnemalplaatje (samenwerkingscampagne) of dupliceer de campagnemalplaatje (lokale campagne).
1. Configureer de campagne met de lokalisatievelden en de formulierverwijzing.
1. Publiceer de campagne.

### Lokale operatortaken {#local-operator-side}

Deze stappen moeten voor elke campagne worden uitgevoerd.

1. Nadat u een melding hebt ontvangen over de beschikbaarheid van het campagnepakket, geeft u de locatie van de campagne op (optioneel).
1. Evalueer het doel, de begroting, enz.
1. Voorbeeld van inhoud campagne.
1. De campagne bestellen.
