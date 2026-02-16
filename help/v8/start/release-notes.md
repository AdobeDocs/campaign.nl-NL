---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 91796cd0d107b65377e8d724a81d1de4f907f7e5
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 12%

---

# Laatste versies {#latest-release}

Deze pagina maakt een lijst van nieuwe mogelijkheden, verbeteringen en moeilijke situaties die met Campagne v8 (console) **** komen meest recente versies. Leer meer over de versies, versies, en verbeteringen van de Campagne in [ deze pagina ](upgrades.md). Andere versies worden vermeld in de sectie Vorige releases van deze documentatie.

## Release 8.9.1 {#release-8-9-1}

_jan 27, 2026_

>[!CAUTION]
>
> De upgrade van Client Console is verplicht. Lees op deze [pagina](../start/connect.md#upgrade-ac-console) hoe u uw Client Console kunt upgraden.

### Nieuwe functies {#new-8-9-1}

De **nieuwe SMS verzendende schakelaar** is nu beschikbaar aan alle klanten (GA). Verwijs naar de [ gedetailleerde documentatie ](../send/sms/sms.md).

Deze versie wordt geleverd met een reeks functies die beschikbaar zijn in de gebruikersinterface van het Web van de Campagne:

* [ Meertalige leveringsmogelijkheden (GA) ](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [ de Verrijking van het Profiel in Transactionele Berichten (GA) ](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [ levende Adobe Experience Manager en taalexemplaren ](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [ experimenten van de Inhoud - het testen A/B ](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [ Ononderbroken leveringsactiviteit ](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [ het goedkeuringsbeheer van de Campagne ](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

Verwijs naar UI van het Web van de Campagne [ versienota&#39;s ](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html){target="_blank"}

### Beveiligingsverbeteringen {#security-8-9-1}

* De externe rekeningen van Snowflake steunen nu authentificatie OAuth2, die moderne en veilige authentificatiemethodes voor gefedereerde verbindingen van de gegevenstoegang verstrekt. (NEO-87013)
* De externe rekeningen van gegevensbestanden steunen nu authentificatie OAuth2 via dienst principal (niet-interactieve stroom van cliëntgeloofsbrieven), die veilige authentificatiemethodes voor de verbindingen van de gefedereerde gegevenstoegang verstrekt. Interactieve OAuth2-verificatie zal in een toekomstige release beschikbaar zijn. (NEO-87422) [Meer informatie](../config/external-accounts.md#databricks-external-accounts)
* Vaste kwetsbaarheden voor toegang tot workflowbestand door bewerkingen te beperken tot geautoriseerde mappen, toegang door onbevoegden te voorkomen en externe code mogelijk uit te voeren. (NEO-88460)
* Toegevoegde FTP URL die controles voegt op lijst van gewenste personen aan werkschemaJavaScript codeactiviteiten, die uitgaande verbindingen van FTP tot geoorloofde slechts adressen beperken. (NEO-89083)

### Andere wijzigingen {#changes-8-9-1}

* Verbeterd containergeheugenbeheer door automatische workflowvertraging toe te passen bij hoge geheugencondities, met intelligente mogelijkheden voor opnieuw opstarten van de workflow en geheugeninstructies voor niet-kritieke processen. (NEO-89041)
* Toegevoegde ondersteuning voor asymmetrische versleutelings- en decoderingsfuncties in Campagneworkflows. (NEO-80257)
* Verbeterde prestaties van de replicatieagent en geheugenveerkracht voor grote gegevens uploadt in plaatsingen FFDA. (NEO-88430)


### Oplossingen {#fixes-8-9-1}

* Probleem verholpen waarbij de databasestructuur niet kon worden bijgewerkt nadat sysFilter was gewijzigd. (NEO-93306)
* Probleem verholpen waarbij dynamische rapportgegevens ontbraken na migratie. (NEO-92962)
* Probleem opgelost waarbij de leveringsstatus niet correct werd bijgewerkt. (NEO-92908)
* Oplossing voor een probleem met betrekking tot de beperking van de FDA-catalogus voor databases. (NEO-92900)
* Probleem verholpen waarbij lay-outfouten in HTML konden optreden op het bureaublad van Outlook Windows. (NEO-92611)
* Probleem met gegevensintegriteit verholpen waarbij primaire leveringssleutels halverwege na een upgrade werden gedupliceerd. (NEO-92424)
* Probleem verholpen waarbij koppelingen niet konden worden uitgeschakeld in het dialoogvenster Bijhouden en afbeeldingen in een levering. (NEO-92381)
* Probleem verholpen waarbij de functie nms.subscribtion.RecipientSubscribe() niet werkte voor bulkabonnementen. (NEO-92308)
* Probleem verholpen waarbij leveringsfouten optraden als gevolg van ontbrekende leveringsonderdelen na een upgrade. (NEO-92278)
* Probleem verholpen in de traceringsworkflow waarbij dubbele statusfouten en SQL-syntaxisfouten ervoor zorgden dat trackingindicatoren niet konden worden bijgewerkt. (NEO-92239)
* Probleem verholpen waarbij labels voor opsommingsvelden ontbreken of onjuist werden weergegeven in lijsten die via workflow zijn gemaakt bij het gebruik van dbEnum-velden. (NEO-91158)
* Probleem verholpen waarbij het dialoogvenster Publiceren/publiceren van RT niet werd gesloten en bevroren. (NEO-91038)
* Oplossing voor een probleem dat optrad voor ontvangers met de status &quot;waarmee rekening is gehouden door de dienstverlener&quot;. (NEO-90927)
* Probleem verholpen waarbij de oorsprong van het (un)abonnement ontbrak voor uitschakelkoppelingen. (NEO-90714)
* Probleem verholpen waarbij het toevoegen van coupons niet kon worden voorbereid voor levering. (NEO-90547)
* Probleem verholpen waarbij het aantal geweigerde bestanden invoegen niet correct werd weergegeven op het tabblad Audit. (NEO-90318)
* Probleem met beveiliging verholpen waarbij de toepassing de service kon weigeren. (NEO-89984)
* Probleem opgelost waarbij de gedownloade PDF van het Hotclick-rapport werd verbroken. (NEO-89954)
* Oplossing voor een SSL-fout die optrad na een upgrade, waardoor een onverwachte EOF werd veroorzaakt tijdens het lezen van fouten. (NEO-89108)
* Probleem verholpen waarbij geen gegevens konden worden opgevraagd in een gegevensschema na een upgrade. (NEO-88663)
* Oplossing voor een fout die optrad bij het samenvoegen van een &quot;char&quot;-veld in PostgreSQL 15. (NEO-88028)
* Probleem verholpen waarbij de volgorde van de variabelen van de leveringssjabloon veranderde bij het opslaan of dupliceren van de sjabloon. (NEO-87845)
* Probleem verholpen waarbij het maken van een nieuw schema in de gegevensbibliotheek ertoe leidde dat de webinterface vastliep. (NEO-87816)
* Probleem opgelost waarbij de deduplicatieactiviteit werd ingesteld met complementsets. (NEO-87711)
* Oplossing voor een aanvraag voor een installatiepakket zonder X11-afhankelijkheid. (NEO-87471)
* Probleem opgelost waarbij segmentcodes niet konden worden gebruikt in dynamische rapporten. (NEO-87276)
* Probleem verholpen waarbij workflows vastzaten in de activiteit Gegevens bijwerken. (NEO-87252)
* Probleem verholpen waarbij BigQuery een onjuiste tijdzone gebruikte. (NEO-86622)
* Probleem verholpen met een JavaScript-fout die optrad tijdens de evaluatie van het script &#39;mcSynch_mcExec1/jsReplicateUrl&#39;. (NEO-86553)
* Probleem verholpen waarbij dubbele gebeurtenissen werden weergegeven in de tabel eventHisto als gevolg van een onjuiste methode voor het berekenen van id&#39;s. (NEO-86544)
* Probleem verholpen waarbij het tabblad Geavanceerd niet werd weergegeven voor iOS Push bij kopiëren. (NEO-86231)
* Probleem verholpen waarbij het replicate werkschema van verwijzingstabellen in het repliceren van het nms :delivery schema ontbrak. (NEO-85884)
* Probleem verholpen waarbij null-domeinfouten die overeenkwamen met MXIP-adressen werden weergegeven in foutlogboeken tijdens het verzenden van leveringen. (NEO-85238)
* Probleem verholpen waarbij de technische leveringssjablonen niet werden vernieuwd nadat de opties waren gewijzigd. (NEO-84149)
* Oplossing voor een fout in de factureringsworkflow buiten de doos. (NEO-83624)
* Probleem verholpen waarbij duplicaten alleen op basis van de primaire sleutel van doelrecords werden uitgesloten. (NEO-82910)
* Oplossing voor discrepanties in de rapporten van de UI van het Web van de Campagne waar het volgen van statistieken verschillende waarden in vergelijking met de console toonde. (NEO-82339)
* Probleem verholpen waarbij de laatste gewijzigde datum werd gewijzigd, zelfs als de record niet mocht worden bijgewerkt in de activiteit Gegevens bijwerken. (NEO-82002)
* Probleem verholpen waarbij het toevoegen van nieuwe kenmerken in een lijst ertoe leidde dat werkstromen die de lijst lezen, mislukten. (NEO-80258)
* Probleem verholpen waarbij in het rapport Tracking Indicators onjuiste waarden werden weergegeven voor verschillende openingen. (NEO-79466)