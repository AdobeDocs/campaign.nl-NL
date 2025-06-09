---
title: Implementatierichtlijnen
description: Campaign v8 leren implementeren
feature: Overview
role: User
level: Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 3%

---

# Richtlijnen voor de uitvoering van campagnes{#gs-implementation}

In deze sectie leert u hoe u Adobe Campaign kunt aanpassen aan de vereisten van uw bedrijf. Gebruik de volgende richtlijnen om uw implementatie te structureren en te organiseren.

1. **bepaalt montages**: de toegangs van de subsidie, deelt de cliëntconsole, vormt kanalen (e-mail, duw, sms). [Meer informatie](#implementation-ac-settings)
1. **bereidt uw milieu** voor: de invoerprofielen, creëren publiek, ontwerpwerkschema en campagnemalplaatjes, creëren typologische regels. [Meer informatie](#implementation-prepare-your-env)
1. **pas uw instantie** aan: creeer nieuwe gegevensgebieden, voeg lijsten/schema&#39;s toe. [Meer informatie](#implementation-custom-your-instance)
1. **automatiseer uw processen**: vorm de automatiseringsmogelijkheden van Adobe Campaign. [Meer informatie](#implementation-automation)
1. **breid uw plaatsing** uit: verbind met de oplossingen van Adobe, andere producten en systemen - schakelaars, multi-oplossingsmontages. [Meer informatie](#implementation-extend)

>[!CAUTION]
>
>Met **Beheerde de Diensten van de Wolk van de Campagne**, wordt uw milieu en aanvankelijke configuratie geplaatst door Adobe, volgens de termijnen van uw vergunningsovereenkomst. U mag geïnstalleerde ingebouwde pakketten, ingebouwde schema&#39;s of rapporten niet wijzigen.
>
>Als u toe:voegen-op van de Campagne of een specifiek vermogen moet gebruiken dat niet voor u is provisioned, moet u uw **Manager van de Overgang van Adobe** contacteren.

## Voordat u begint{#before-starting}

Deze sectie bevat kritieke informatie over privacy en veiligheid die moet worden herzien en in overweging genomen alvorens zelfs met de daadwerkelijke implementatie te beginnen.

### Privacy{#implementation-privacy}

Adobe Campaign wordt geleverd met processen en instellingen waarmee u Campagne kunt gebruiken in overeenstemming met de toepasselijke wetgeving inzake privacy van gegevens en de voorkeuren van uw ontvanger. U kunt het volgende beheren:

* **de aanwinst van Gegevens**: Adobe Campaign laat u toe om gegevens, met inbegrip van persoonlijke en gevoelige informatie te verzamelen. Het is daarom van essentieel belang dat u toestemming krijgt en beheert van uw ontvangers.

  Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#data-acquisition){target="_blank"}

* **de toestemming van de Gebruiker en gegevensbehoud**: u moet gebruikerstoestemming krijgen, opstelling dubbele opt-in abonnementsmechanismen, vergemakkelijken opt-out en vormen gegevensbehoud.

  Leer meer in [ Campaign Classic v7 privacydocumentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#consent){target="_blank"}

* **Privacy en gegevensbeschermingsverordeningen**: verwijs naar [ deze sectie ](privacy.md) voor informatie over privacyvereisten, en hoe deze verordeningen uw organisatie en Adobe Campaign beïnvloeden.

### Beveiliging

Leer veiligheidsrichtlijnen en principes met Adobe Campaign in [ checklist van de Veiligheid van de Campagne ](../config/security.md).

## Campagne-instellingen definiëren{#implementation-ac-settings}

### Gebruikers toevoegen en machtigingen verlenen{#implementation-add-users}

U kunt gebruikers handmatig toevoegen aan Campagne en deze koppelen aan groepen, uitgelijnd op uw rolhiërarchie. De gebruikers zullen dan login en tot de gegevens en de toestemmingen kunnen toegang hebben die voor hen aangewezen zijn.

Leer hoe te om gebruikers aan Adobe Campaign in [ toe te voegen deze sectie ](../start/gs-permissions.md).

### Campagne-clientconsole installeren{#implementation-install-console}

De hoofdgebruikersinterface van de toepassing is een rijke client, met andere woorden een native toepassing (Windows) die alleen communiceert met de Adobe Campaign-toepassingsserver met standaard internetprotocollen (SOAP, HTTP, enzovoort). Adobe Campaign Client Console biedt geweldige gebruiksvriendelijkheid voor productiviteit, gebruikt zeer weinig bandbreedte (door het gebruik van een lokale cache) en is ontworpen voor eenvoudige implementatie. Deze console kan vanuit een internetbrowser worden geïmplementeerd, kan automatisch worden bijgewerkt en vereist geen specifieke netwerkconfiguratie omdat alleen HTTP(S)-verkeer wordt gegenereerd.

[ Leer meer over de cliëntconsole van de Campagne ](connect.md).

## Uw omgeving voorbereiden{#implementation-prepare-your-env}

Voordat u begint met het verzenden van berichten en het maken van marketingcampagnes, moet u:

1. **de profielen van de Invoer en creeer publiek**

   Met de campagne kunt u contactpersonen toevoegen aan de Cloud-database. U kunt een dossier laden, veelvoudige contactupdates plannen en automatiseren, gegevens op het Web verzamelen, of profielinformatie direct in de ontvankelijke lijst ingaan.

   [ leer hoe te om profielen ](import.md) in te voeren.

   De soorten publiek worden gegroepeerd in lijsten en kunnen door werkschema&#39;s worden tot stand gebracht. Deze kunnen vervolgens worden gebruikt voor leveringen tussen kanalen.

   [ leer hoe te om publiek ](audiences.md) te bepalen.

1. **Sjablonen gebruiken**

   Campagnes, leveringen, taken of workflows zijn allemaal gebaseerd op een sjabloon waarin de belangrijkste instellingen en mogelijkheden zijn opgeslagen. Een ingebouwde sjabloon wordt geleverd voor elke component, waarvoor geen specifieke configuratie is gedefinieerd. U moet malplaatjes vormen en aanpassen aan uw behoeften en hen ter beschikking stellen aan eindgebruikers.


   Leer hoe te met campagnemalplaatjes in [ te werken deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html){target="_blank"}.

   Leer hoe te om een werkschemamalplaatje in [ te vormen deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"}.

   Leer meer over e-mailmalplaatjes in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target="_blank"}.


1. **vorm typologieregels**

   De typologieregels van de Campagne van de hefboomwerking aan filter, controle en monitorlevering die verzenden. Zo regelt u met vermoeidheidsregels de regelfrequentie en de hoeveelheid berichten om overmatige aansporing van ontvangers te voorkomen. Na implementatie worden er in leveringen naar typologische regels verwezen.

   Leer meer over typologieën en vermoeidheidsbeheer in [ deze sectie ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html){target="_blank"}.

1. **krijgt vertrouwd met de ingebouwde campagne gegevensmodel**

   Adobe Campaign bevat een vooraf gedefinieerd datamodel. Als u uw omgeving wilt implementeren en aanpassen, moet u vertrouwd zijn met de ingebouwde tabellen van het Adobe Campaign-gegevensmodel en hoe deze op elkaar betrekking hebben.

   [ leer meer over het gegevensmodel van de Campagne ](../dev/datamodel.md).

## Instantie aanpassen{#implementation-custom-your-instance}

U kunt vele verschillende campagnegebieden en mogelijkheden aanpassen. De meeste van onze klanten passen drie dingen aan:

1. **Lijsten en schema&#39;s**

   Adobe Campaign wordt geleverd met algemene schema&#39;s voor het identificeren van gegevens, zoals ontvangers, leveringslogboeken, abonnementen en meer.

   Verwijs naar deze sectie om meer over [ te leren ingebouwde de gegevensmodel van de Campagne ](../dev/datamodel.md).

   U kunt bestaande schema&#39;s uitbreiden of nieuwe schema&#39;s van kras tot stand brengen. Meer informatie vindt u [op deze pagina](../dev/customize.md).

1. **Dashboards en lijsten**

   U kunt lijsten eenvoudig configureren, velden toevoegen en verwijderen en kolommen aanpassen.

   Leer hoe te om filters en lijsten in Campagne in [ te beheren deze pagina ](../dev/customize.md#gs-lists-and-filters).

   Afhankelijk van uw behoeften kunt u ook nieuwe dashboards maken om Campagnegegevens weer te geven.

   Meer informatie vindt u [op deze pagina](../dev/customize.md#gs-custom-dashboards).

1. **Rapporten**

   De campagne verstrekt een reeks ingebouwde rapporten over levering controle, URLs en klik stromen, het volgen, leverbaarheidsindicatoren, en meer.

   Naast ingebouwde rapporten kunt u in Adobe Campaign rapporten in verschillende contexten genereren en aan verschillende behoeften voldoen. In dit document worden beginselen van gebruik en uitvoeringsmodi uiteengezet.

   Leer meer over het melden van mogelijkheden in Campagne in [ deze pagina ](../reporting/gs-reporting.md).


## Campagne automatiseren instellen{#implementation-automation}

Als u complexe marketingcampagnes op verschillende kanalen wilt ordenen, kunt u de automatiseringsmogelijkheden van de campagne benutten.

* Gebruik **werkschema&#39;s** om processen en gegevens te beheren. Leer meer in [ deze documentatie ](../../automation/workflow/about-workflows.md)

* De opstelling **processen van het abonnement** en **landende pagina&#39;s**.  Leer meer in [ deze pagina ](../start/subscriptions.md)

* Vorm **typologieregels** om vermoeidheid en controlebeheer te bepalen.  Leer meer in [ deze documentatie ](../../automation/campaign-opt/campaign-typologies.md)


## Uw implementatie uitbreiden{#implementation-extend}

### Implementatie van meerdere oplossingen{#implementation-multi-solutions}

Als u andere Adobe-oplossingen gebruikt, kunt u deze aansluiten op uw Campagneomgeving en mogelijkheden combineren.

* Campagne - Journey Orchestration
* Campagne - Real-time CDP
* Campagne - Experience Cloud Triggers
* Campagne - Experience Manager
* Campagne - Doel
* Campagne - Audience Manager/People core-service
* Campagne - Middelen
* Campagne - Analytics Data connectors


U kunt Single Sign-On (SSO) alleen gebruiken om verbinding te maken met Campaign. Meer informatie vindt u [op deze pagina](connect.md).

Ontdek de volledige lijst van de oplossing van Adobe die met Adobe Campaign [ in deze pagina ](../connect/integration.md) kan worden geïntegreerd.

### Aansluitingen{#implementation-connectors}

Verbind Campagne met derdesystemen om een grote waaier van mogelijkheden te combineren en processen te automatiseren.

Leer meer over beschikbare schakelaars in [ deze sectie ](../connect/integration.md).

**verbind uw CRM met Campagne**

U kunt uw Adobe Campaign-platform aansluiten op uw CRM-systemen van derden en gegevens synchroniseren: contactpersonen, accounts, aankopen, enzovoort.

Leer hoe te om uw systeem van CRM aan Campagne in [ te verbinden deze sectie ](../connect/integration.md#gs-crm-connectors)

**verbind met een extern gegevensbestand**

U kunt de Campagne Cloud-database verbinden met externe systemen via de FDA-module (Federated Data Access).

Leer hoe te om de module van FDA van de Campagne te vormen om toegangsparameters in [ te bepalen deze sectie ](../connect/integration.md#gs-fda)
