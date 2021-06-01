---
product: Adobe Campaign
title: Uitvoeringsrichtsnoeren
description: Leer hoe u campagne v8 kunt implementeren
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 2%

---

# Richtlijnen voor de uitvoering van campagnes

In deze sectie leert u hoe u Adobe Campaign kunt aanpassen aan de vereisten van uw bedrijf. Gebruik de volgende richtlijnen om uw implementatie te structureren en te organiseren.

1. **Instellingen** definiëren: verlenen toegang, delen de Console van de Cliënt, vormen kanalen (e-mail, duw, sms)
1. **Uw omgeving** voorbereiden: profielen importeren, publiek maken, werkstroom ontwerpen en campagnesjablonen maken, typologische regels maken
1. **Uw exemplaar** aanpassen: nieuwe gegevensvelden maken, tabellen/schema&#39;s toevoegen
1. **Breid uw plaatsing** uit: verbinding maken met Adobe-oplossingen, andere producten en systemen - connectors, instellingen voor meerdere oplossingen

>[!CAUTION]
>
>Met **Beheerde Cloud Services van de Campagne**, zijn uw milieu en aanvankelijke configuratie geplaatst door Adobe, volgens de termijnen van uw vergunningsovereenkomst. U mag geïnstalleerde ingebouwde pakketten, ingebouwde schema&#39;s of rapporten niet wijzigen.
>
>Als u een toe:voegen-op van de Campagne of een specifiek vermogen moet gebruiken dat niet voor u is provisioned, moet u **Adobe de Zorg van de Klant** contacteren.

## Voordat u begint

Deze sectie bevat kritieke informatie over privacy en veiligheid die moet worden herzien en in overweging genomen alvorens zelfs met de daadwerkelijke implementatie te beginnen.

### Privacy

Adobe Campaign wordt geleverd met processen en instellingen waarmee u Campagne kunt gebruiken in overeenstemming met de toepasselijke wetgeving inzake privacy van gegevens en de voorkeuren van uw ontvanger. U kunt het volgende beheren:

* **Gegevensverwerving**: Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en vertrouwelijke informatie. Het is daarom van essentieel belang dat u toestemming krijgt en beheert van uw ontvangers. Meer informatie in de [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Gebruikerstoestemming en gegevensbewaring**: Leer hoe u toestemming van de gebruiker krijgt, dubbele opt-in-abonnementsmechanismen instelt, de opt-out faciliteert en gegevensbewaring configureert in de privacydocumentatie van  [Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **Privacy- en gegevensbeschermingsvoorschriften**: Raadpleeg de  [Campaign Classic privacy-](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) documentatie voor informatie over de algemene gegevensbeschermingsverordening van de Europese Unie (GDPR), de California Consumer Privacy Act (CCPA) en andere internationale privacyvereisten, en hoe deze regels van invloed zijn op uw organisatie en Adobe Campaign.

### Beveiliging

Leer beveiligingsrichtlijnen en -beginselen met Adobe Campaign in [Controlelijst Campagnebeveiliging](../config/security.md).

## Campagne-instellingen definiëren

### Gebruikers toevoegen en machtigingen verlenen

U kunt gebruikers handmatig toevoegen aan Campagne en deze koppelen aan groepen, uitgelijnd op uw rolhiërarchie. De gebruikers zullen dan login en tot de gegevens en de toestemmingen kunnen toegang hebben die voor hen aangewezen zijn.

[!DNL :arrow_upper_right:] Leer hoe u in  [deze sectie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started) gebruikers aan Adobe Campaign kunt toevoegen.

### Campagne-clientconsole installeren

De hoofdgebruikersinterface van de toepassing is een rijke client, met andere woorden een native toepassing (Windows) die alleen communiceert met de Adobe Campaign-toepassingsserver met standaard internetprotocollen (SOAP, HTTP, enzovoort). Adobe Campaign Client Console biedt geweldige gebruiksvriendelijkheid voor productiviteit, gebruikt zeer weinig bandbreedte (door het gebruik van een lokale cache) en is ontworpen voor eenvoudige implementatie. Deze console kan vanuit een internetbrowser worden geïmplementeerd, kan automatisch worden bijgewerkt en vereist geen specifieke netwerkconfiguratie omdat alleen HTTP(S)-verkeer wordt gegenereerd.

[!DNL :bulb:] [Meer informatie over de Campagne-clientconsole](connect.md).

## Uw omgeving voorbereiden

Voordat u begint met het verzenden van berichten en het maken van marketingcampagnes, moet u:

1. Profielen importeren en publiek maken

   Met de campagne kunt u contactpersonen toevoegen aan de Cloud-database. U kunt een dossier laden, veelvoudige contactupdates plannen en automatiseren, gegevens op het Web verzamelen, of profielinformatie direct in de ontvankelijke lijst ingaan.

   [!DNL :bulb:] [Leer hoe u profielen](import.md) importeert.

   Soorten publiek worden gegroepeerd in lijsten en kunnen worden gemaakt via werkstromen. Deze kunnen vervolgens worden gebruikt voor leveringen tussen kanalen.

   [!DNL :bulb:] [Leer hoe u het publiek](audiences.md) definieert.

1. Sjablonen maken

   Campagnes, leveringen, taken of workflows zijn allemaal gebaseerd op een sjabloon waarin de belangrijkste instellingen en mogelijkheden zijn opgeslagen. Een ingebouwde sjabloon wordt geleverd voor elke component, waarvoor geen specifieke configuratie is gedefinieerd. U moet malplaatjes vormen en aanpassen aan uw behoeften en hen ter beschikking stellen aan eindgebruikers.

   [!DNL :arrow_upper_right:] [Meer informatie over e-mailsjablonen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   [!DNL :arrow_upper_right:] Meer informatie over het werken met campagnesjablonen op  [deze pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] Leer hoe u een werkstroomsjabloon op  [deze pagina configureert](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)

1. Typologische regels configureren

   De typologieregels van de Campagne van de hefboomwerking aan filter, controle en monitorlevering die verzenden. Zo regelt u met vermoeidheidsregels de regelfrequentie en de hoeveelheid berichten om overmatige aansporing van ontvangers te voorkomen. Na implementatie worden de typologische regels vermeld in leveringen.

   [!DNL :arrow_upper_right:] [Meer informatie over typologieën en vermoeidheidsbeheer](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. Krijg vertrouwd met het ingebouwde gegevensmodel van de Campagne

   Adobe Campaign bevat een vooraf gedefinieerd datamodel. Als u uw omgeving wilt implementeren en aanpassen, moet u vertrouwd zijn met de ingebouwde tabellen van het Adobe Campaign-gegevensmodel en hoe deze op elkaar betrekking hebben.

   [!DNL :bulb:] [Meer weten over het datamodel](../dev/datamodel.md) Campaign?

## Instantie aanpassen

U kunt vele verschillende campagnegebieden en mogelijkheden aanpassen. De meeste van onze klanten passen drie dingen aan:

1. **Tabellen en schema&#39;s**

   Adobe Campaign wordt geleverd met gemeenschappelijke schema&#39;s voor het identificeren van gegevens zoals: ontvangers, leveringslogboeken, abonnementen, en meer.

   [!DNL :bulb:] Raadpleeg deze sectie voor meer informatie over het ingebouwde datamodel van de  [Campagne](../dev/datamodel.md).

   [!DNL :bulb:] U kunt bestaande schema&#39;s uitbreiden of nieuwe schema&#39;s van kras tot stand brengen. Meer informatie vindt u op [deze pagina](../dev/customize.md).

1. **Dashboards en lijsten**

   U kunt lijsten eenvoudig configureren, velden toevoegen en verwijderen en kolommen aanpassen.

   [!DNL :bulb:] Leer hoe u filters en lijsten in Campagne op  [deze pagina](../dev/customize.md#gs-lists-and-filters) beheert.

   Afhankelijk van uw behoeften kunt u ook nieuwe dashboards maken om Campagnegegevens weer te geven.

   [!DNL :bulb:] Meer weten op  [deze pagina](../dev/customize.md#gs-custom-dashboards)?

1. **Rapporten**

   De campagne verstrekt een reeks ingebouwde rapporten over levering controle, URLs en klik stromen, het volgen, leverbaarheidsindicatoren, en meer.

   Naast ingebouwde rapporten kunt u in Adobe Campaign rapporten in verschillende contexten genereren om aan verschillende behoeften te voldoen. In dit document worden beginselen van gebruik en uitvoeringsmodi uiteengezet.

   [!DNL :bulb:] Meer informatie over rapportagemogelijkheden in Campagne vindt u op  [deze pagina](reporting.md).


## Campagne automatiseren instellen

Als u complexe marketingcampagnes op verschillende kanalen wilt ordenen, kunt u de automatiseringsmogelijkheden van de campagne benutten.

* Workflows: processen en gegevens beheren

* Abonnementen en bestemmingspagina&#39;s

* Typologische regels: vermoeidheid en controlebeheer

## Uw implementatie uitbreiden

### Implementatie van meerdere oplossingen

Als u andere Adobe-oplossingen gebruikt, kunt u deze aansluiten op uw Campagneomgeving en mogelijkheden combineren.

* Campagne - Journey Orchestration
* Campagne - Real-time CDP
* Campagne - Experience Cloud Triggers
* Campagne - Experience Manager
* Campagne - Doel
* Campagne - Audience Manager/People core-service
* Campagne - Middelen
* Campagne - Analytics Data connectors


U kunt ook Single Sign-On (SSO) gebruiken om verbinding te maken met Campaign. Meer informatie vindt u op [deze pagina](connect.md).

[!DNL :bulb:] Ontdek de volledige lijst met Adobe-oplossingen die  [op deze pagina](../connect/integration.md) met Adobe Campaign kunnen worden geïntegreerd.

### Connectoren

Verbind Campagne met derdesystemen om een grote waaier van mogelijkheden te combineren en processen te automatiseren.

[!DNL :bulb:] Meer informatie over beschikbare connectors in  [deze sectie](../connect/integration.md).

**Sluit uw CRM aan Campagne aan**

U kunt uw Adobe Campaign-platform verbinden met uw CRM-systemen van derden en gegevens synchroniseren: contacten, rekeningen, aankopen enz.

[!DNL :bulb:] Leer hoe te om uw systeem van CRM aan Campagne in  [deze sectie aan te sluiten](../connect/integration.md#gs-crm-connectors)

**Verbinding maken met een externe database**

U kunt de Campagne Cloud-database verbinden met externe systemen via de FDA-module (Federated Data Access).

[!DNL :bulb:] Leer hoe te om de module van FDA van de Campagne te vormen om toegangsparameters in  [deze sectie te bepalen](../connect/integration.md#gs-fda)
