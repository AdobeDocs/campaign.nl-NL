---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4fe8b8eaf88f763e796dbe06ef3c1477de12bad6
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 12%

---

# Laatste versies {#latest-release}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met Campagne v8 (console) **&#x200B;**&#x200B;komen meest recente versies. Leer meer over de versies, versies, en verbeteringen van de Campagne in [&#x200B; deze pagina &#x200B;](upgrades.md). Andere versies worden vermeld in de sectie Vorige releases van deze documentatie.

## Release 8.9.1 {#release-8-9-1}

_jan 27, 2026_

>[!CAUTION]
>
> De upgrade van Client Console is verplicht. Lees op deze [pagina](../start/connect.md#upgrade-ac-console) hoe u uw Client Console kunt upgraden.

### Nieuwe functies {#new-8-9-1}

De **nieuwe SMS verzendende schakelaar** is nu beschikbaar aan alle klanten (GA). Verwijs naar de [&#x200B; gedetailleerde documentatie &#x200B;](../send/sms/sms.md).

Deze versie wordt geleverd met een reeks functies die beschikbaar zijn in de gebruikersinterface van het Web van de Campagne:

* [&#x200B; Meertalige leveringsmogelijkheden (GA) &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=nl-NL){target="_blank"}
* [&#x200B; de Verrijking van het Profiel in Transactionele Berichten (GA) &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=nl-NL){target="_blank"}
* [&#x200B; levende Adobe Experience Manager en taalexemplaren &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=nl-NL){target="_blank"}
* [&#x200B; experimenten van de Inhoud - het testen A/B &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=nl-NL){target="_blank"}
* [&#x200B; Ononderbroken leveringsactiviteit &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=nl-NL){target="_blank"}
* [&#x200B; het goedkeuringsbeheer van de Campagne &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=nl-NL){target="_blank"}

Verwijs naar UI van het Web van de Campagne [&#x200B; versienota&#39;s &#x200B;](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=nl-NL){target="_blank"}

### Beveiligingsverbeteringen {#security-8-9-1}

* De externe rekeningen van Snowflake steunen nu authentificatie OAuth2, die moderne en veilige authentificatiemethodes voor gefedereerde verbindingen van de gegevenstoegang verstrekt. (NEO-87013)
* Vaste kwetsbaarheden voor toegang tot workflowbestand door bewerkingen te beperken tot geautoriseerde mappen, toegang door onbevoegden te voorkomen en externe code mogelijk uit te voeren. (NEO-88460)
* Toegevoegde FTP URL die controles voegt op lijst van gewenste personen aan werkschemaJavaScript codeactiviteiten, die uitgaande verbindingen van FTP tot geoorloofde slechts adressen beperken. (NEO-89083)

### Andere wijzigingen {#changes-8-9-1}

* Verbeterd containergeheugenbeheer door automatische workflowvertraging toe te passen bij hoge geheugencondities, met intelligente mogelijkheden voor opnieuw opstarten van de workflow en geheugeninstructies voor niet-kritieke processen. (NEO-89041)
* Toegevoegde ondersteuning voor asymmetrische versleutelings- en decoderingsfuncties in Campagneworkflows. (NEO-80257)
* Verbeterde prestaties van de replicatieagent en geheugenveerkracht voor grote gegevens uploadt in plaatsingen FFDA. (NEO-88430)


### Oplossingen {#fixes-8-9-1}

* Probleem verholpen waarbij de databasestructuur niet kon worden bijgewerkt nadat sysFilter was gewijzigd. (NEO-93306)
* Oplossing voor een probleem waarbij dynamische rapportgegevens ontbraken na migratie. (NEO-92962)
* Probleem opgelost waarbij de leveringsstatus niet correct werd bijgewerkt. (NEO-92908)
* Er is een oplossing toegevoegd voor de CATALOG-beperking van Databricks FDA USE. (NEO-92900)
* Probleem verholpen waarbij de Visual Editor de HTML-lay-out in Outlook Windows-bureaublad heeft verbroken. (NEO-92611)
* Oplossing voor een probleem met kritieke gegevensintegriteit waarbij primaire leveringssleutels halverwege de upgrade werden gedupliceerd. (NEO-92424)
* Probleem verholpen waarbij koppelingen in een levering niet konden worden uitgeschakeld in het dialoogvenster Bijhouden en afbeeldingen. (NEO-92381)
* Correctie van een probleem waarbij de functie nms.subscribtion.RecipientSubscribe() niet werkte voor bulkabonnementen. (NEO-92308)
* Oplossing voor een probleem waarbij leveringsfouten optraden als gevolg van ontbrekende leveringsonderdelen na de upgrade. (NEO-92278)
* Probleem opgelost in de workflow voor bijhouden. (NEO-92239)
* Oplossing voor een probleem waarbij tijdelijke opsommingsreferenties ontbraken in de lijst-XML na het maken van de lijst met behulp van een workflow. (NEO-91158)
* Correctie van een probleem waarbij het dialoogvenster Publiceren/Publiceren ongedaan maken van de RT niet werd gesloten en bevroren. (NEO-91038)
* Het probleem waarbij ontvangers die vastzaten aan de status &quot;Rekening gehouden met de status van de dienstverlener&quot;, niet op het moment kwamen. (NEO-90927)
* Probleem verholpen waarbij de oorsprong van het abonnement (Un)in v8 ontbreekt voor de optie om te weigeren. (NEO-90714)
* Correctie van een probleem waarbij het toevoegen van coupons niet kon worden voorbereid voor levering. (NEO-90547)
* Probleem verholpen waarbij het aantal geweigerde bestanden invoegen niet correct werd weergegeven op het tabblad Audit. (NEO-90318)
* Oplossing voor een beveiligingsprobleem dat toepassingsontkenning van service zou kunnen veroorzaken. (NEO-89984)
* Probleem verholpen waarbij de gedownloade PDF van het Hotclick-rapport werd verbroken. (NEO-89954)
* Oplossing voor een SSL-fout die optrad na de upgrade, waardoor een onverwachte EOF werd veroorzaakt tijdens het lezen van fouten. (NEO-89108)
* Probleem verholpen waarbij geen gegevens konden worden opgevraagd in gegevensschema na upgrade. (NEO-88663)
* Correctie van een fout die optrad wanneer het aaneenschakelen van een &quot;klusje&quot;gebied in PostgreSQL 15. (NEO-88028)
* Probleem verholpen waarbij de volgorde van de variabelen van de leveringssjabloon veranderde bij het opslaan of dupliceren van de sjabloon. (NEO-87845)
* Oplossing van een kwestie waar het creëren van een nieuw schema van de Bibliotheek van Gegevens de interface van het Web veroorzaakte om te crashen. (NEO-87816)
* Probleem verholpen waarbij de fragmentcode van het complement-set van de deduplicatieactiviteit niet werkte. (NEO-87711)
* Een aanvraag voor een installatiepakket zonder X11-afhankelijkheid is opgelost. (NEO-87471)
* Probleem opgelost waarbij segmentcodes niet konden worden gebruikt in dynamische rapporten. (NEO-87276)
* Oplossing voor een probleem waarbij workflows vastzaten in de activiteit Gegevens bijwerken. (NEO-87252)
* Probleem verholpen waarbij BigQuery een onjuiste tijdzone gebruikte. (NEO-86622)
* Correctie van een JavaScript-fout die optrad tijdens de evaluatie van het script &#39;mcSynch_mcExec1/jsReplicateUrl&#39;. (NEO-86553)
* Oplossing voor een probleem waarbij dubbele gebeurtenissen werden weergegeven in de tabel eventHisto vanwege de berekeningsmethode voor id&#39;s. (NEO-86544)
* Probleem verholpen waarbij het tabblad Geavanceerd niet werd weergegeven voor iOS Push bij kopiëren. (NEO-86231)
* Oplossing van een kwestie waar de Replicate werkschema van de Lijsten van de Verwijzing in het repliceren van het nms :delivery schema ontbrak. (NEO-85884)
* Probleem verholpen waarbij null-domeinfouten die overeenkwamen met MXIP-adressen werden weergegeven in foutlogboeken tijdens het verzenden van leveringen. (NEO-85238)
* Er is een manier toegevoegd om de technische leveringssjablonen te vernieuwen na eventuele wijzigingen die in de opties zijn aangebracht. (NEO-84149)
* Oplossing voor een fout in de factureringsworkflow buiten de doos. (NEO-83624)
* Probleem opgelost met uitsluiting van duplicaten op basis van alleen de primaire sleutel van doelrecords. (NEO-82910)
* Oplossing voor discrepanties in de rapporten van de UI van het Web van de Campagne waar het volgen van statistieken verschillende waarden in vergelijking met de console toonde. De volgende Indicatoren, het Verzenden van Samenvatting, en URL klikken de rapporten van Streams tonen nu verenigbare metriek over beide interfaces. (NEO-82339)
* Correctie van een kwestie waar de laatste gewijzigde datum veranderde zelfs als het verslag niet in de activiteit van de Gegevens van de Update zou moeten worden bijgewerkt. (NEO-82002)
* Probleem verholpen waarbij het toevoegen van nieuwe kenmerken in een lijst ertoe leidde dat werkstromen die de lijst lezen, mislukten. (NEO-80258)
* Een anomalie in het rapport Tracking Indicators is opgelost. (NEO-79466)