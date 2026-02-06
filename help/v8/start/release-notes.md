---
title: Opmerkingen bij de release Campagne v8
description: Nieuwste versie van Campagne v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 981fa2029528cac5806da7c39aec3a2e6de0bf56
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 13%

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
* Vaste kwetsbaarheden voor toegang tot workflowbestand door bewerkingen te beperken tot geautoriseerde mappen, toegang door onbevoegden te voorkomen en externe code mogelijk uit te voeren. (NEO-88460)
* Toegevoegde FTP URL die controles voegt op lijst van gewenste personen aan werkschemaJavaScript codeactiviteiten, die uitgaande verbindingen van FTP tot geoorloofde slechts adressen beperken. (NEO-89083)

### Andere wijzigingen {#changes-8-9-1}

* Verbeterd containergeheugenbeheer door automatische workflowvertraging toe te passen bij hoge geheugencondities, met intelligente mogelijkheden voor opnieuw opstarten van de workflow en geheugeninstructies voor niet-kritieke processen. (NEO-89041)
* Toegevoegde ondersteuning voor asymmetrische versleutelings- en decoderingsfuncties in Campagneworkflows. (NEO-80257)
* Verbeterde prestaties van de replicatieagent en geheugenveerkracht voor grote gegevens uploadt in plaatsingen FFDA. (NEO-88430)


### Oplossingen {#fixes-8-9-1}

* Probleem verholpen waarbij in dynamische rapporten onjuiste tellingen werden weergegeven bij groeperen op bepaalde kolommen. (NEO-86898)
* Oplossing voor verschillen in gegevens tussen dynamische rapporten en werkelijke campagnegegevens. (NEO-88068)
* Correctie van aaneenschakelingsproblemen met &quot;char&quot;gebiedstypes PostgreSQL die onverwachte resultaten in vragen veroorzaakten. (NEO-87769)
* Correctie van een probleem waarbij bepaalde parameters niet correct werden afgehandeld met de opdracht JavaScript logInfo. (NEO-88263)
* Opgeloste synchronisatie hanteert problemen in real-time gebeurtenisverwerking in Message Center. (NEO-88330)
* Probleem verholpen waarbij de Visual Editor HTML-inhoud automatisch opnieuw opmaakte, waardoor de layout veranderde. (NEO-88409)
* Correctie van een probleem waarbij de deduplicatieactiviteit niet goed werkte met tijdelijke schema&#39;s. (NEO-88577)
* Probleem verholpen waarbij zaadadressen niet konden worden gegenereerd wanneer proefdrukken werden verzonden. (NEO-88720)
* Verbeterde PostSQL vraagprestaties door verdelingskolom behandeling te optimaliseren. (NEO-88771)
* Probleem opgelost waarbij bestandsoverdrachtactiviteiten regelvervolgtekens niet correct afhandelden. (NEO-88812)
* Verbeterde PostSQL vraagoptimalisering voor betere prestaties in grote datasets. (NEO-88885)
* Probleem verholpen waarbij de fout &quot;Toestemming geweigerd&quot; werd verholpen waardoor hybride campagnes niet konden worden geopend. (NEO-88955)
* Uitgebreide ondersteuning voor streepjescodefuncties voor het verwerken van langere tekstreeksen. (NEO-88958)
* Correctie van een fout in campagnelogboeken die voorkwam wanneer het gebruiken van proeven met terugkomende leveringen. (NEO-88976)
* Probleem verholpen waarbij het verzenden van e-mail in bepaalde scenario&#39;s werd beïnvloed. (NEO-89019)
* Oplossing voor een probleem waarbij de modus voor het starten van de workflow onverwachts werd gewijzigd van Direct in Normaal. (NEO-89025)
* Correctie van fouten die optraden bij het uitvoeren van de activiteit Gegevens bijwerken onder bepaalde omstandigheden. (NEO-89031)
* Correctie van een kwestie waar de activiteit van Gegevens van de Update de meta-gegevens van het douaneschema verloor. (NEO-89056)
* Oplossing voor een validatiefout die optrad tijdens de voorbereiding van de levering. (NEO-89063)
* Oplossing voor ongeldige SQL-generatie wanneer query&#39;s filters bevatten op 1-1 koppelingsrelaties. (NEO-89065)
* Probleem verholpen waarbij de incrementele query-activiteit de geconfigureerde groottelimiet niet respecteerde. (NEO-89066)
* Verbeterde workflowprestaties in FFDA-implementaties voor grootschalige bewerkingen. (NEO-89098)
* Verbeterd geheugenbeheer en stabiliteit voor workflowprocessen. (NEO-89105)
* Strikte kolomvalidatie voor webformulieren is ingeschakeld om inconsistenties in gegevens te voorkomen. (NEO-89111)
* Oplossing voor de synchronisatieproblemen van het Centrum van het Bericht die verwerkingsvertragingen veroorzaakten. (NEO-89138)
* Correctie van fouten in de workflow &quot;Vernieuwen voor levering&quot; die een correcte uitvoering verhinderden. (NEO-89160)
* Correctie van fouten die optraden bij het uitvoeren van JavaScript-codeactiviteiten in workflows. (NEO-89169)
* Opgeslagen Snowflake-opslagconfiguraties zijn verwijderd om de juiste instellingen voor externe accounts mogelijk te maken. (NEO-89201)
* Correctie 403 Verboden fouten die optraden tijdens workflowbestandsoverdracht. (NEO-89226)
* Geoptimaliseerde langzame vragen over de ontvankelijke lijst in plaatsingen FFDA. (NEO-89268)
* Probleem verholpen waarbij incrementele query-activiteiten geconfigureerde planningen negeerden. (NEO-89317)
* Toegangsfouten zijn opgelost bij het openen van campagnes in hybride omgevingen. (NEO-89320)
* Oplossing voor discrepanties in de rapporten van de UI van het Web van de Campagne waar het volgen van statistieken verschillende waarden in vergelijking met de console toonde. De volgende Indicatoren, het Verzenden van Samenvatting, en URL klikken de rapporten van Streams tonen nu verenigbare metriek over beide interfaces. (NEO-82339)