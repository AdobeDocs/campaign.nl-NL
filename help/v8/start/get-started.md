---
product: Adobe Campaign
title: Aan de slag met campagne v8
description: Leer meer over belangrijke functies, de gebruikersinterface en algemene richtlijnen
feature: Overzicht
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: bf2c44adc560d2be700a27b02ab35f6630192d00
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 42%

---

# Aan de slag met Adobe Campaign{#gs-ac-v8}

Adobe Campaign biedt een platform voor het ontwerpen van de ervaringen van klanten over verschillende kanalen en een omgeving voor visuele campagneorchestratie, interactiebeheer in real time en uitvoering via meerdere kanalen.

Campagne gebruiken om:

* **** Drivepersonalisatie en betrokkenheid via één toegankelijke weergave van de klant
* **E-mail, mobiele, online en offline kanalen** integreren in de reis van de klant
* **De levering van betekenisvolle en actuele berichten en aanbiedingen** automatiseren

![](assets/ac-capabilities.png)

## Integrated Customer Profile {#integrated-customer-profile}

Profielen worden gecentraliseerd in een krachtige cloud-database. Er zijn vele mogelijke mechanismen om profielen te verwerven en deze database op te bouwen: online verzameling via webformulieren, handmatig of automatisch importeren van tekstbestanden, replicatie met bedrijfsdatabases of andere informatiesystemen. Met Adobe Campaign kunt u de marketinggeschiedenis, aankoopdata, voorkeuren, CRM-data en alle relevante PII-data in een geconsolideerde weergave opnemen om te analyseren en actie te ondernemen.

In Adobe Campaign zijn ontvangers de standaardprofielen voor het verzenden van leveringen (e-mails, sms’en, enzovoort). Dankzij de ontvangerdata die in de database worden opgeslagen, kunt u het doel filteren dat een bepaalde levering zal ontvangen en personalisatiedata in uw leveringscontent toevoegen. De database bevat andere typen profielen. Ze zijn ontworpen voor verschillende applicaties. Seed-profielen worden bijvoorbeeld gemaakt om de leveringen te testen voordat ze naar het uiteindelijke doel worden verzonden.

[!DNL :bulb:] De grondbeginselen van profielbeheer worden uitgelegd in  [deze sectie](audiences.md).

[!DNL :bulb:] Leer hoe u profielen aan campagne kunt toevoegen in  [deze sectie](import.md).

## Doelgerichte segmentatie {#targeted-segmentation}

Adobe Campaign beschikt over krachtige, gebruiksvriendelijke segmentatie- en targetingfuncties waarmee u heel doelgerichte, gedifferentieerde aanbiedingen kunt maken. Met de functionaliteit voor beschrijvende analyse kunt u informatie upstream en downstream van uw marketingcampagnes analyseren, en met de functionaliteit voor filterbeheer en de grafische query-editor kunt u uw ledenpopulatie filteren en doelgroepen testen en maken op basis van een onbeperkt aantal criteria.

De geavanceerde functionaliteit voor data management breidt de mogelijkheden voor dataverwerking uit. Het vereenvoudigt en optimaliseert het targetingproces door data op te nemen die niet in de datamart worden gemodelleerd.

[!DNL :bulb:] Meer informatie over segmentatie, publiekscreatie en personalisatie vindt u in  [deze sectie](audiences.md).

## Kanaaloverschrijdende orkestrering van campagnes {#cross-channel-campaign-orchestration}

Met Adobe Campaign kunt u doelgerichte en gepersonaliseerde campagnes ontwerpen en organiseren op meerdere kanalen: e-mail, direct mail, sms, pushmelding. Eén enkele interface voorziet u van alle functies die vereist zijn om al uw campagnes en communicatie te plannen, te organiseren, te configureren, te personaliseren, te automatiseren, uit te voeren en te meten.

[!DNL :bulb:] Leer hoe u een campagne ontwerpt, plant en uitvoert in  [deze sectie](campaigns.md).

## Workflows

Adobe Campaign biedt een uitgebreide grafische omgeving waarmee u complexe processen kunt ontwerpen, zoals segmentatie, uitvoering van campagnes, bestandsverwerking, enzovoort. U kunt bijvoorbeeld een workflow gebruiken om een bestand van een server te downloaden, het te decomprimeren en vervolgens de records in de Adobe Campaign-database te importeren.

Een werkstroom kan gebruikers ook betrekken door hen taken toe te wijzen of hen te laten uitgevoerde taken goedkeuren. Dit betekent u een taak aan één of verscheidene gebruikers kunt toewijzen om aan inhoud te werken of doelstellingen te specificeren, en proefdrukken goed te keuren alvorens het bericht te verzenden.

Workflows kunnen in verschillende contexten worden gebruikt, zoals:

* Het richten om publiek te beheren of berichten te verzenden.
* Gegevensbeheer (ETL) voor het manipuleren van gegevens.
* Gegevens importeren in de Campagne-database.
* Technische processen zoals het opschonen van databases, het herstellen van trackinggegevens, enz.

[!DNL :bulb:] Leer hoe u workflows ontwerpt en uitvoert in  [deze sectie](../config/workflows.md).

## Rapportage en analyse {#analysis-and-reporting}

Met Adobe Campaign kunt u het gedrag van uw klanten volgen en interpreteren door hun data en profielen geleidelijk te verrijken. Met de rapportage- en analysetools kunt u profiteren van elke nieuwe campagne, uw marketinginitiatieven beter richten en hun impact en rendement op investeringen optimaliseren.

[!DNL :bulb:] Meer informatie over rapporten en het volgen mogelijkheden in  [deze sectie](reporting.md).

## Adobe Experience Cloud-integraties {#adobe-experience-cloud-integrations}

U kunt de leveringsfuncties en functies voor geavanceerd campagnebeheer van Adobe Campaign combineren met een reeks oplossingen die u helpen uw gebruikerservaring te personaliseren: bijvoorbeeld Adobe Experience Manager-, Adobe Analytics-, Adobe Target- of Adobe Experience Cloud-triggers.

[!DNL :bulb:] Leer hoe u in  [deze sectie](../connect/integration.md) kunt integreren met Adobe-services en -oplossingen.

## Meer informatie over de mogelijkheden van campagnes {#core-capabilities-and-add-ons}

Adobe Campaign biedt een aantal mogelijkheden om u te helpen de functionaliteit voor marketing van gesprekken te implementeren en te optimaliseren, afhankelijk van uw behoeften en architectuur. Sommige zijn kernmogelijkheden en sommige hangen van de installatie van een pakket op uw configuratie af. Hier vindt u een gedetailleerde productbeschrijving: [Adobe Campaign v8 Productbeschrijving](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html).

[!DNL :bulb:] Ben je al bekend met Campaign Classic? Leer belangrijke verschillen tussen Campaign Classic en Campagne v8 in [deze pagina](capability-matrix.md).

## Werkruimte en aanpassing

De werkruimte van de campagne is beschikbaar door [Clientconsole](../dev/general-architecture.md).

![](assets/home-page.png)

[!DNL :bulb:] [Meer informatie over de Campagne-clientconsole](../start/connect.md).

De campagnewerkruimte kan afhankelijk van uw behoeften worden aangepast.

[!DNL :arrow_upper_right:]  Leer hoe u de Campagne-werkruimte kunt gebruiken in de documentatie van  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)

[!DNL :arrow_upper_right:]  Leer hoe u lijsten kunt aanpassen in  [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)

U hebt ook toegang tot bepaalde functies via het web.

[!DNL :bulb:] [Meer weten over Campagne Web Access](../start/connect.md#web-access)?


## Talen

De gebruikersinterface van Campagne v8 is beschikbaar in de volgende talen:

* Engels (VK)
* Engels (VS)
* Frans
* Duits
* Japans

De taal wordt geselecteerd tijdens het installatieproces.

>[!CAUTION]
>
>De taal kan na het maken van de instantie niet meer worden gewijzigd.

Datums en tijdnotaties worden beïnvloed door de taal. Raadpleeg [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time) voor meer informatie.

