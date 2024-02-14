---
title: Implementatierichtlijnen
description: Campaign v8 leren implementeren
feature: Overview
role: User
level: Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 2%

---

# Richtlijnen voor de uitvoering van campagnes{#gs-implementation}

In deze sectie leert u hoe u Adobe Campaign kunt aanpassen aan de vereisten van uw bedrijf. Gebruik de volgende richtlijnen om uw implementatie te structureren en te organiseren.

1. **Instellingen definiëren**: bied toegang aan, deel de clientconsole, configureer kanalen (e-mail, push, sms). [Meer informatie](#implementation-ac-settings)
1. **Uw omgeving voorbereiden**: importeer profielen, maak een publiek, ontwerpworkflow en campagnesjablonen, maak typologische regels. [Meer informatie](#implementation-prepare-your-env)
1. **Instantie aanpassen**: maak nieuwe gegevensvelden, voeg tabellen/schema&#39;s toe. [Meer informatie](#implementation-custom-your-instance)
1. **Automatiseer uw processen**: Adobe Campaign-automatiseringsmogelijkheden configureren. [Meer informatie](#implementation-automation)
1. **Uw implementatie uitbreiden**: maak verbinding met Adobe oplossingen, andere producten en systemen - connectors, instellingen voor meerdere oplossingen. [Meer informatie](#implementation-extend)

>[!CAUTION]
>
>Met **Door campagne beheerde Cloud Servicen**, wordt uw omgeving en initiële configuratie ingesteld door Adobe, volgens de bepalingen van uw licentieovereenkomst. U mag geïnstalleerde ingebouwde pakketten, ingebouwde schema&#39;s of rapporten niet wijzigen.
>
>Als u een toe:voegen-op van de Campagne of een specifieke capaciteit moet gebruiken die niet voor u is provisioned, moet u uw **Adobe-overgangsbeheer**.

## Voordat u begint{#before-starting}

Deze sectie bevat kritieke informatie over privacy en veiligheid die moet worden herzien en in overweging genomen alvorens zelfs met de daadwerkelijke implementatie te beginnen.

### Privacy{#implementation-privacy}

Adobe Campaign wordt geleverd met processen en instellingen waarmee u Campagne kunt gebruiken in overeenstemming met de toepasselijke wetgeving inzake privacy van gegevens en de voorkeuren van uw ontvanger. U kunt het volgende beheren:

* **Gegevensverwerving**: Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en gevoelige gegevens. Het is daarom van essentieel belang dat u toestemming krijgt en beheert van uw ontvangers.

  Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#data-acquisition){target="_blank"}

* **Goedkeuring door de gebruiker en bewaring van gegevens**: u moet toestemming van de gebruiker krijgen, dubbele opt-in-abonnementsmechanismen instellen, de opt-out vergemakkelijken en gegevensbewaring configureren.

  Meer informatie in [Campaign Classic v7 privacydocumentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#consent){target="_blank"}

* **Regels inzake privacy en gegevensbescherming**: verwijs naar [deze sectie](privacy.md) voor meer informatie over de privacyvereisten en hoe deze regels van invloed zijn op uw organisatie en Adobe Campaign.

### Beveiliging

Meer informatie over beveiligingsrichtlijnen en -beginselen met Adobe Campaign in [Controlelijst Campagnebeveiliging](../config/security.md).

## Campagne-instellingen definiëren{#implementation-ac-settings}

### Gebruikers toevoegen en machtigingen verlenen{#implementation-add-users}

U kunt gebruikers handmatig toevoegen aan Campagne en deze koppelen aan groepen, uitgelijnd op uw rolhiërarchie. De gebruikers zullen dan login en tot de gegevens en de toestemmingen kunnen toegang hebben die voor hen aangewezen zijn.

![](../assets/do-not-localize/glass.png) Leer hoe u gebruikers aan Adobe Campaign kunt toevoegen in [deze sectie](../start/gs-permissions.md).

### Campagne-clientconsole installeren{#implementation-install-console}

De hoofdgebruikersinterface van de toepassing is een rijke client, met andere woorden een native toepassing (Windows) die alleen communiceert met de Adobe Campaign-toepassingsserver met standaard internetprotocollen (SOAP, HTTP, enzovoort). Adobe Campaign Client Console biedt geweldige gebruiksvriendelijkheid voor productiviteit, gebruikt zeer weinig bandbreedte (door het gebruik van een lokale cache) en is ontworpen voor eenvoudige implementatie. Deze console kan vanuit een internetbrowser worden geïmplementeerd, kan automatisch worden bijgewerkt en vereist geen specifieke netwerkconfiguratie omdat alleen HTTP(S)-verkeer wordt gegenereerd.

![](../assets/do-not-localize/glass.png) [Meer informatie over Campagne-clientconsole](connect.md).

## Uw omgeving voorbereiden{#implementation-prepare-your-env}

Voordat u begint met het verzenden van berichten en het maken van marketingcampagnes, moet u:

1. **Profielen importeren en publiek maken**

   Met de campagne kunt u contactpersonen toevoegen aan de Cloud-database. U kunt een dossier laden, veelvoudige contactupdates plannen en automatiseren, gegevens op het Web verzamelen, of profielinformatie direct in de ontvankelijke lijst ingaan.

   ![](../assets/do-not-localize/glass.png) [Leer hoe u profielen importeert](import.md).

   De soorten publiek worden gegroepeerd in lijsten en kunnen door werkschema&#39;s worden tot stand gebracht. Deze kunnen vervolgens worden gebruikt voor leveringen tussen kanalen.

   ![](../assets/do-not-localize/glass.png) [Leer hoe u het publiek definieert](audiences.md).

1. **Sjablonen gebruiken**

   Campagnes, leveringen, taken of workflows zijn allemaal gebaseerd op een sjabloon waarin de belangrijkste instellingen en mogelijkheden zijn opgeslagen. Een ingebouwde sjabloon wordt geleverd voor elke component, waarvoor geen specifieke configuratie is gedefinieerd. U moet malplaatjes vormen en aanpassen aan uw behoeften en hen ter beschikking stellen aan eindgebruikers.


   ![](../assets/do-not-localize/glass.png) Meer informatie over het werken met campagnemasjablonen vindt u in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html)

   ![](../assets/do-not-localize/glass.png) Leer hoe u een workflowsjabloon kunt configureren in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html)

   ![](../assets/do-not-localize/book.png) Meer informatie over e-mailsjablonen in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target="_blank"}


1. **Typologieregels configureren**

   De typologieregels van de Campagne van de hefboomwerking aan filter, controle en monitorlevering die verzenden. Zo regelt u met vermoeidheidsregels de regelfrequentie en de hoeveelheid berichten om overmatige aansporing van ontvangers te voorkomen. Na implementatie worden er in leveringen naar typologische regels verwezen.

   Meer informatie over typologieën en vermoeidheidsbeheer in [deze sectie](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html).

1. **Krijg vertrouwd met het ingebouwde gegevensmodel van de Campagne**

   Adobe Campaign bevat een vooraf gedefinieerd datamodel. Als u uw omgeving wilt implementeren en aanpassen, moet u vertrouwd zijn met de ingebouwde tabellen van het Adobe Campaign-gegevensmodel en hoe deze op elkaar betrekking hebben.

   ![](../assets/do-not-localize/glass.png) [Meer informatie over datamodel campagne](../dev/datamodel.md).

## Instantie aanpassen{#implementation-custom-your-instance}

U kunt vele verschillende campagnegebieden en mogelijkheden aanpassen. De meeste van onze klanten passen drie dingen aan:

1. **Tabellen en schema&#39;s**

   Adobe Campaign wordt geleverd met algemene schema&#39;s voor het identificeren van gegevens, zoals ontvangers, leveringslogboeken, abonnementen en meer.

   ![](../assets/do-not-localize/glass.png) Zie deze sectie voor meer informatie over [Ingebouwd datamodel voor campagne](../dev/datamodel.md).

   ![](../assets/do-not-localize/glass.png) U kunt bestaande schema&#39;s uitbreiden of nieuwe schema&#39;s van kras tot stand brengen. Meer informatie in [deze pagina](../dev/customize.md).

1. **Dashboards en lijsten**

   U kunt lijsten eenvoudig configureren, velden toevoegen en verwijderen en kolommen aanpassen.

   ![](../assets/do-not-localize/glass.png) Leer hoe u filters en lijsten beheert in Campagne in [deze pagina](../dev/customize.md#gs-lists-and-filters).

   Afhankelijk van uw behoeften kunt u ook nieuwe dashboards maken om Campagnegegevens weer te geven.

   ![](../assets/do-not-localize/glass.png) Meer informatie in [deze pagina](../dev/customize.md#gs-custom-dashboards).

1. **Rapporten**

   De campagne verstrekt een reeks ingebouwde rapporten over levering controle, URLs en klik stromen, het volgen, leverbaarheidsindicatoren, en meer.

   Naast ingebouwde rapporten kunt u in Adobe Campaign rapporten in verschillende contexten genereren en aan verschillende behoeften voldoen. In dit document worden beginselen van gebruik en uitvoeringsmodi uiteengezet.

   ![](../assets/do-not-localize/glass.png) Meer informatie over rapportagemogelijkheden in Campagne in [deze pagina](../reporting/gs-reporting.md).


## Campagne automatiseren instellen{#implementation-automation}

Als u complexe marketingcampagnes op verschillende kanalen wilt ordenen, kunt u de automatiseringsmogelijkheden van de campagne benutten.

* Gebruiken **workflows** processen en gegevens te beheren. Meer informatie in [deze documentatie](../../automation/workflow/about-workflows.md)

* Instellen **abonnement** processen en **landingspagina&#39;s**.  Meer informatie in [deze pagina](../start/subscriptions.md)

* Configureren **typologieregels** het definiëren van vermoeidheid- en controlebeheer.  Meer informatie in [deze documentatie](../../automation/campaign-opt/campaign-typologies.md)


## Uw implementatie uitbreiden{#implementation-extend}

### Implementatie van meerdere oplossingen{#implementation-multi-solutions}

Als u andere Adobe oplossingen gebruikt, kunt u hen met uw milieu van de Campagne verbinden en mogelijkheden combineren.

* Campagne - Journey Orchestration
* Campagne - Real-time CDP
* Campagne - Experiencen Cloud Triggers
* Campagne - Experience Manager
* Campagne - Doel
* Campagne - Audience Manager/de kerndienst van de Mensen
* Campagne - Middelen
* Campagne - Analytics Data connectors


U kunt Single Sign-On (SSO) alleen gebruiken om verbinding te maken met Campaign. Meer informatie in [deze pagina](connect.md).

![](../assets/do-not-localize/glass.png) Ontdek de volledige lijst met Adobe oplossingen die kunnen worden geïntegreerd met Adobe Campaign [op deze pagina](../connect/integration.md).

### Aansluitingen{#implementation-connectors}

Verbind Campagne met derdesystemen om een grote waaier van mogelijkheden te combineren en processen te automatiseren.

![](../assets/do-not-localize/glass.png) Meer informatie over beschikbare connectors in [deze sectie](../connect/integration.md).

**Sluit uw CRM aan Campagne aan**

U kunt uw Adobe Campaign-platform aansluiten op uw CRM-systemen van derden en gegevens synchroniseren: contactpersonen, accounts, aankopen, enzovoort.

![](../assets/do-not-localize/glass.png) Leer hoe u uw CRM-systeem kunt aansluiten op Campagne in [deze sectie](../connect/integration.md#gs-crm-connectors)

**Verbinding maken met een externe database**

U kunt de Campagne Cloud-database verbinden met externe systemen via de FDA-module (Federated Data Access).

![](../assets/do-not-localize/glass.png) Leer hoe te om de module van FDA van de Campagne te vormen om toegangsparameters te bepalen in [deze sectie](../connect/integration.md#gs-fda)
