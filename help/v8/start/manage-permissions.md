---
title: Rechten verlenen aan Campagne v8
description: Leer hoe u machtigingen verleent aan gebruikers van Campagne v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 90154f84-b6a7-407c-93b7-9731dc94d9de
source-git-commit: 41e39e046ec77de8b5e657ba76645898ff1cd2d7
workflow-type: tm+mt
source-wordcount: '1618'
ht-degree: 0%

---

# Gebruikersmachtigingen beheren{#manage-permissions}

## Gebruikers toevoegen {#add-users}

Als productbeheerder, kunt u gebruikers toevoegen en toegang tot Campagne verlenen.

Volg onderstaande stappen om een gebruiker toe te voegen:

1. In de [ Admin Console ](https://adminconsole.adobe.com/enterprise){target="_blank"} homepage, uitgezochte **voegt Gebruikers** toe.

   ![](assets/add-a-user.png)

1. Voer het e-mailadres van de gebruiker in.
1. Gebruik het plusteken (+) om de productprofielen of gebruikersgroepen te selecteren die aan de gebruiker moeten worden toegewezen.

   ![](assets/add-a-product-profile.png)

   De ingebouwde productprofielen van de campagne zijn vermeld in [ deze sectie ](#ootb-productprofiles).

   Leer hoe te om gebruikersgroepen in [ tot stand te brengen deze sectie ](#user-groups)

1. Klik **sparen**. De gebruiker wordt toegevoegd en wordt weergegeven in de lijst Gebruikers. Als u een beheerdersrol of een productprofiel aan gebruikers toewijst, ontvangen zij een e-mailbericht. Gebruikers moeten de koppeling volgen om hun profiel te voltooien.

Leer meer over gebruikersverwezenlijking in Admin Console in [ deze pagina ](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target="_blank"}.

Wanneer de nieuwe gebruikers [ login aan Campagne ](connect.md) met hun Adobe ID, worden zij toegevoegd aan de lijst van de exploitanten van de Campagne in de Console van de Cliënt. Campagneoperatoren worden opgeslagen in de map **[!UICONTROL Administration > Access management > Operators]** van de Campagneverkenner.

## Werken met productprofielen{#product-profiles}

Gebruik productprofielen om gebruikers de mogelijkheden te bieden die in het product zijn opgenomen.

* Voor elk product op de Admin Console kunt u een of meer productprofielen maken.
* In elk productprofiel wijst u gebruikers en gebruikersgroepen toe (binnen uw organisatie).
* Wanneer een gebruiker zich aanmeldt met de gegevens die zijn opgegeven in het productprofiel, krijgt hij toegang tot de apps en services van het product waarop het productprofiel is gebaseerd.

Deze productprofielen komen overeen met groepen operatoren die zijn opgeslagen in de map **[!UICONTROL Administration > Access management > Operator groups]** van de Campagneverkenner.

In de Admin Console gebruiken productprofielen de volgende syntaxis:

campagne - `<your instance>` - interne naam van de operatorgroep

Bijvoorbeeld, voor de **exploitant van de Levering** groep in de &quot;test&quot;instantie, is het productprofiel in Admin Console:

campagne - test - levering

U kunt standaardproductprofielen gebruiken of nieuwe profielen maken.

### Een productprofiel maken{#create-product-profile}

Als u een nieuw productprofiel aan Adobe wilt toevoegen, moet u het eerst maken in Campagne Client Console en vervolgens toevoegen in de Admin Console.

Volg de onderstaande stappen om bijvoorbeeld een productprofiel voor &#39;revisoren&#39; te maken.

#### De operatorgroep maken in Campagne{#create-op-group}

1. Verbind met Campagne, open de Ontdekkingsreiziger, en doorblader aan **[!UICONTROL Administration > Access management > Operator groups]**.
1. Klik op **[!UICONTROL New]**, definieer de naam van de operatorgroep en stel de interne naam van de groep in (&#39;revisoren&#39;).
   ![](assets/new-op-group.png)
1. Definieer de bijbehorende machtigingen door benoemde rechten te selecteren. De genoemde rechten zijn gedetailleerd in [ deze sectie ](#use-named-rights)
1. Sla de nieuwe operatorgroep op.

#### Het productprofiel maken in de Admin Console{#create-profile-in-admin-console}

1. Verbind met [ Admin Console ](https://adminconsole.adobe.com/enterprise){target="_blank"}.
1. Van het **Product en de diensten** sectie van de homepage, open product van de Campagne.
1. Klik **Nieuw profiel** en ga de naam van het te creëren productprofiel in, met de nauwkeurige correcte syntaxis zoals verklaard [ hier ](#product-profiles). Voor ons voorbeeld voeren we het volgende in: campagne - `<your-instance-name>` - revisoren

   ![](assets/new-product-profile-ui.png)

1. Sla uw wijzigingen op.

U kunt gebruikers aan dit nieuwe productprofiel nu toevoegen, zoals die in [ wordt verklaard deze sectie ](#add-users).

U kunt productprofielen het beste aan gebruikersgroepen toewijzen. Het beheren van machtigingen door gebruikers is geen duurzaam model.


### Standaardproductprofielen en groepen met operatoren {#ootb-productprofiles}

Adobe Campaign komt met ingebouwde **productprofielen** die worden bepaald wanneer Adobe uw milieu toelaat.

![](assets/ootb-product-profiles.png)

Deze productprofielen passen met de exploitantgroepen van de Campagne **** aan. De standaardexploitantgroepen en hun [ genoemde rechten ](#use-named-rights) zijn hieronder vermeld:

1. **[!UICONTROL Administrator]** (admin)

   De operatoren in deze groep hebben volledige toegang tot het exemplaar. Beheerders zijn gebruikers die toegang hebben tot de meest technische onderdelen van de gebruikersinterface.

   Deze groep bevat het volgende benoemde recht:

   * **[!UICONTROL ADMINISTRATION]**: het recht om objecten zoals workflow, levering, scripts, enzovoort uit te voeren, te maken, te bewerken/te verwijderen.

1. **[!UICONTROL Delivery operators]** (levering)

   De operatoren in deze groep zijn verantwoordelijk voor het beheer van de leveringen: zij bieden toegang tot de belangrijkste bronnen die nodig zijn voor het maken en voorbereiden van de leveringen (campagneretypologieën, leveringstoewijzingen, standaardsjablonen, aanpassingsblokken, enz.).

   Deze groep bevat de volgende benoemde rechten:

   * **[!UICONTROL PREPARE DELIVERIES]**: recht om de leveringsanalyse te maken, te bewerken en te starten,
   * **[!UICONTROL START DELIVERIES]** : rechts om eerder geanalyseerde leveringen goed te keuren.

1. **[!UICONTROL Campaign managers]** (bewerking)

   De operatoren in deze groep kunnen marketingcampagnes beheren. U hebt toegang tot de objecten die gekoppeld zijn aan campagnes (plannen, programma&#39;s, workflows, budgetten, enzovoort) in het kader van **[!UICONTROL Campaign]** (optionele Adobe Campaign-module).

   Deze groep bevat de volgende benoemde rechten:

   * **[!UICONTROL INSERT FOLDERS]**: het recht om mappen in te voegen in de Adobe Campaign-structuur (op voorwaarde dat u bewerkrechten hebt voor de betrokken vertakkingen),
   * **[!UICONTROL WORKFLOW]** : recht om workflows te gebruiken.

   >[!NOTE]
   >
   >Met deze groep kunnen operatoren geen leveringen starten.

1. **[!UICONTROL Content contributors]** (inhoud)

   Gebruikers in deze groep hebben toegang tot de inhoudsmappen in de context van de invoegtoepassing **[!UICONTROL Content management]** . Deze groep verleent geen extra toestemmingen.

1. **[!UICONTROL Access to reports]** (rapport)

   Deze groep wordt gereserveerd voor externe exploitanten, om tot de leveringsrapporten via de toegang van het Web van a [ toegang te hebben ](../start/campaign-ui.md#web-browser).

1. **[!UICONTROL Workflow execution]** (workflow)

   Met de **[!UICONTROL Workflow execution]** -groep kunt u de uitvoering en goedkeuring van doelworkflows beheren: de WORKFLOW met de naam right wordt toegewezen aan de operatoren van deze groep. Dit is vereist voor alle handelingen met betrekking tot workflows, naast toegangsrechten tot de gegevensbestanden. Standaard heeft de **[!UICONTROL Workflow execution]** -groep alleen-lezen toegang tot standaarddoelworkbestanden en werkstroomsjablonen. Operatoren in deze groep hebben ook lees- en schrijftoegang tot het goedkeuringsbestand dat in behandeling is.

1. **[!UICONTROL Workflow supervisors]** (workflowSupervisor)

   Gebruikers in deze groep beheren workflowgoedkeuringen en ontvangen een e-mailbericht in geval van waarschuwingen over workflows voor campagnes.

1. **Lokaal/Centraal beheer** (centraal/lokaal)

   Gebruikers in deze groep kunnen **[!UICONTROL Distributed marketing]** add-on gebruiken.

1. **[!UICONTROL Offer managers]** (aanbieding)

   De exploitanten in deze groep kunnen aanbiedingen tot stand brengen en handhaven wanneer het gebruiken van de toe:voegen-op van de Interactie. [Meer informatie](../interaction/interaction-operators.md).

   Deze groep bevat de volgende benoemde rechten:

   * **[!UICONTROL INSERT FOLDERS]**: recht om mappen in te voegen in de Adobe Campaign-structuur (op voorwaarde dat u bewerkrechten hebt voor de betrokken vertakkingen),
   * **[!UICONTROL EDIT FOLDERS]**: rechts om mapeigenschappen zoals interne naam, label, gekoppelde afbeelding, volgorde van submappen, enz. te wijzigen.

   De toestemmingen die aan de managers van de Aanbieding worden toegewezen laten hen toe om de volgende taken uit te voeren:

   * Wijzig **[!UICONTROL Design]** omgevingen.
   * **[!UICONTROL Live]** -omgevingen weergeven.
   * Configureer beheerfuncties (vooraf gedefinieerde spaties en filters).
   * Categorieën maken en bijwerken
   * Maak voorstellen.
   * Geschiktheid van aanbieding configureren.
   * Voorstellen goedkeuren.

   >[!NOTE]
   >
   >**de managers van de Aanbieding** kunnen slechts een aanbieding goedkeuren als geen recensent wordt gespecificeerd, of als zij als recensenten in het aanbiedingsmalplaatje zijn geplaatst.

   De matrijs van de beheertoestemming van het aanbod per milieu is beschikbaar in [ deze pagina ](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## Werken met gebruikersgroepen{#user-groups}

U kunt de Admin Console gebruiken om gebruikersgroepen te maken en er gebruikers aan toe te wijzen.

Een gebruikersgroep is een inzameling van verschillende gebruikers die een gedeelde reeks toestemmingen moeten worden gegeven. Leer hoe te om gebruikersgroepen in [ tot stand te brengen deze sectie ](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target="_blank"}.

U kunt productprofielen toewijzen aan gebruikersgroepen. Alle gebruikers in die groep ontvangen dus dezelfde set productmachtigingen.

## Benoemde rechten{#use-named-rights}

Adobe Campaign wordt geleverd met een reeks benoemde rechten waarmee u de machtigingen kunt definiëren die aan gebruikers en groepen gebruikers zijn toegewezen. Deze rechten kunnen worden bewerkt in de map **[!UICONTROL Administration > Access management > Named rights]** van de Campagneverkenner.

Rechten verlenen machtigingen aan:

* Bewerkingen uitvoeren
Bijvoorbeeld, analyseert **** knoop in de redacteur van de Levering wordt geactiveerd voor leden van de **3} groep van de Exploitant van de Levering die** Gelegde Levering **hebben**

* Toegang tot mappen
Lidmaatschap van groepen met operatoren kan toegangsrechten verlenen of beperken tot mappen door de beveiligingsinstellingen voor mappen te wijzigen. [Meer informatie](folder-permissions.md#restrict-access-to-a-folder).

  Bijvoorbeeld kan het beïnvloeden: **schrijf toegang** om nieuwe entiteiten (zoals leveringen, profielen, enz.) tot stand te brengen, **Gelezen toegang** om entiteiten te gebruiken, **schrapt toegang** om entiteiten te schrappen.

Standaard benoemde rechten in Adobe Campaign zijn:

* **[!UICONTROL ADMINISTRATION]**: operatoren met het **[!UICONTROL ADMINISTRATION]** -recht hebben volledige toegang tot de instantie. Beheerders kunnen elk object, zoals workflow, levering, scripts, enzovoort, uitvoeren, maken, bewerken of verwijderen.

* **[!UICONTROL APPROVAL ADMINISTRATION]**: U kunt meerdere goedkeuringsstappen instellen in workflows en leveringen om ervoor te zorgen dat het huidige frame is goedgekeurd door een toegewezen operator of groep. Gebruikers met de optie **[!UICONTROL APPROVAL ADMINISTRATION]** kunnen goedkeuringsstappen instellen en ook een operator of groep van operatoren toewijzen die deze stappen moeten goedkeuren.

* **[!UICONTROL CENTRAL]**: Recht op centraal beheer (Distributed Marketing).

* **[!UICONTROL DELETE FOLDER]**: rechts om mappen te verwijderen. Met dit recht kunnen gebruikers mappen verwijderen uit de verkennerweergave.

* **[!UICONTROL EDIT FOLDERS]**: rechts om mapeigenschappen zoals interne naam, label, gekoppelde afbeelding, volgorde van submappen, enz. te wijzigen.

* **[!UICONTROL EXPORT]**: gebruikers kunnen gegevens uit hun Adobe Campaign-instanties exporteren naar een bestand op een server of lokale computer met behulp van de **[!UICONTROL EXPORT]** -workflowactiviteit.

* **[!UICONTROL FILES ACCESS]**: Recht op lees- en schrijftoegang voor bestanden via een script dat in de **[!UICONTROL JavaScript]** -workflowactiviteit kan worden geschreven om bestanden op een server te lezen/schrijven.

* **[!UICONTROL IMPORT]**: rechts voor het importeren van generieke gegevens. Met **[!UICONTROL IMPORT]** kunt u gegevens importeren in een andere tabel, terwijl met **[!UICONTROL RECIPIENT IMPORT]** right alleen gegevens kunnen worden geïmporteerd in de ontvangende tabel.

* **[!UICONTROL INSERT FOLDERS]**: rechts om mappen in te voegen. Gebruikers met de rechtermuisknop van **[!UICONTROL INSERT FOLDERS]** kunnen nieuwe mappen in de mappenstructuur in de verkennerweergave maken.

* **[!UICONTROL LOCAL]**: Recht op lokaal beheer (Distributed Marketing).

* **[!UICONTROL MERGE]**: rechts om de geselecteerde records samen te voegen tot één record. Als ontvangers bestaan als duplicaten, staat het recht van **[!UICONTROL MERGE]** gebruiker toe om de duplicaten te selecteren en hen samen te voegen in een primaire ontvanger.

* **[!UICONTROL PREPARE DELIVERIES]**: Recht om een levering te maken, bewerken en opslaan. Gebruikers met de optie **[!UICONTROL PREPARE DELIVERIES]** kunnen ook het analyseproces voor de levering starten.

* **[!UICONTROL PRIVACY DATA RIGHT]**: recht om privacygegevens te verzamelen en te verwijderen. [Meer informatie](privacy.md).

* **[!UICONTROL PROGRAM EXECUTION]**: recht om opdrachten uit te voeren in verschillende programmeertalen.

* **[!UICONTROL RECIPIENT IMPORT]**: Recht om ontvangers te importeren. Gebruikers met de optie **[!UICONTROL RECIPIENT IMPORT]** kunnen een lokaal bestand importeren in de tabel met ontvangers.

* **[!UICONTROL SQL SCRIPT EXECUTION]** Recht om een SQL-opdracht rechtstreeks in de database uit te voeren.

* **[!UICONTROL START DELIVERIES]**: Recht om eerder geanalyseerde leveringen goed te keuren. Na de afleveringsanalyse wordt de levering onderbroken in verschillende goedkeuringsstappen en moet deze worden goedgekeurd om te worden hervat. Gebruikers met de optie **[!UICONTROL START DELIVERIES]** rechts mogen leveringen goedkeuren.

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**: Recht om uw eigen SQL manuscripten te schrijven gebruikend de SQL activiteit van het Beheer van Gegevens, om het werklijsten tot stand te brengen en te bevolken. [Meer informatie](../../automation/workflow/sql-data-management.md).

* **[!UICONTROL WORKFLOW]**: Dit genoemde recht is specifiek voor workflows: het laat u werkschema&#39;s creëren, beginnen en tegenhouden. Het genoemde recht is alleen van toepassing als het workflowbestand leesrechten bevat. Voor doelworkflows is het lezen naar rechts in de map **[!UICONTROL Profiles and Targets]** noodzakelijk.


* **[!UICONTROL WEBAPP]**: recht om webtoepassingen te gebruiken.

>[!NOTE]
>
>Deze lijst kan verschillen, afhankelijk van de invoegtoepassingen die op uw omgeving zijn geïnstalleerd.



## Verdere bronnen{#additional-res}

* [Machtigingen voor workflows beheren](../../automation/workflow/managing-rights.md)
* [Rechten voor gedistribueerde marketing beheren](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [Rechten voor de interactiemodule beheren](../interaction/interaction-operators.md)
* [Toegang tot schema&#39;s filteren](../dev/filter-schema.md)
* [PI-weergave beperken](../dev/restrict-pi-view.md)
