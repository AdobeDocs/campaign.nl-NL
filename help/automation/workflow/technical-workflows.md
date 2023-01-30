---
product: campaign
title: Technische workflows
description: Meer informatie over de technische workflows die beschikbaar zijn via Campagne
feature: Workflows
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1639'
ht-degree: 2%

---

# Technische workflows{#about-technical-workflows}

Adobe Campaign wordt geleverd met een reeks ingebouwde technische workflows. Ze beheren bewerkingen en taken die zijn gepland voor periodieke uitvoering op de server. Met deze services kunt u onderhoud uitvoeren in de database, gegevens over leveringen doorsturen of voorlopige processen voor leveringen instellen. Technische workflows worden geconfigureerd via de **[!UICONTROL Administration > Production > Technical workflows]** knooppunt.

![](assets/navtree.png)

Native sjablonen zijn beschikbaar voor het maken van technische workflows. Zij kunnen worden gevormd om aan uw behoeften te passen.

De **[!UICONTROL Campaign process]** subfolder centraliseert de werkschema&#39;s die voor het uitvoeren van processen binnen de campagnes worden vereist: taakomschrijving, voorraadbeheer, kostenberekening, enz.

![](assets/campaign-processes-wf.png)


>[!NOTE]
>
>De lijst met technische workflows die bij elke module worden geïnstalleerd, is beschikbaar in een [speciale sectie](technical-workflows.md).

U kunt andere technische workflows maken in het dialoogvenster **[!UICONTROL Administration > Production > Technical workflows]** knooppunt van de boomstructuur. Dit proces is echter voorbehouden aan professionele gebruikers.

De aangeboden activiteiten zijn dezelfde als voor workflows die zich op de werkstroom richten. [Meer informatie](targeting-workflows.md)

De workflows die in deze sectie worden beschreven, worden geïnstalleerd met de verschillende ingebouwde Adobe Campaign-pakketten. Deze pakketten en de bijbehorende technische workflows zijn afhankelijk van uw licentieovereenkomst.

Standaard zijn technische workflows beschikbaar in een submap van het volgende knooppunt: **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**.

Merk op dat de technische werkschema&#39;s slechts door exploitanten met de toestemmingen van het Beleid kunnen worden begonnen en worden gewijzigd.

>[!NOTE]
>
>De technische werkschema&#39;s met betrekking tot de toe:voegen van het Centrum van het Bericht zijn beschikbaar door gebrek in **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Message Center]** > **[!UICONTROL Technical workflows]** knooppunt.

Leer hoe u de technische workflows in deze [speciale sectie](monitor-technical-workflows.md).


## Lijst met technische workflows {#list-technical-workflows}

| Technische workflow | Pakket | Beschrijving |
|------|--------|-----------|
| **Aliasreiniging** (aliasCleansing) | Standaard geïnstalleerd | Deze werkstroom normaliseert opsommingswaarden. Deze wordt standaard elke dag om 3 uur geactiveerd. |
| **Facturering** (facturering) | Standaard geïnstalleerd | Deze workflow stuurt het systeemactiviteitenrapport per e-mail naar de &#39;factureringsoperator&#39;. Het wordt teweeggebracht 25e van elke maand op de instantie van de Marketing. |
| **Campagnebanen** (operationMgt) | Standaard geïnstalleerd | In deze workflow worden de taken voor marketingcampagnes beheerd (starttaken, bestanden uitpakken, enz.). Het leidt ook tot werkschema&#39;s met betrekking tot terugkomende en periodieke campagnes. |
| **Gegevens verzamelen voor de service HeatMap** (collectDataHeatMapService) | Standaard geïnstalleerd | Deze werkstroom wint gegevens terug die door de dienst HeatMap worden vereist. |
| **Verzoeken om privacy verzamelen** (collectPrivacyRequests) | Verordening inzake bescherming van privacydata | Met deze workflow worden de gegevens van de ontvanger gegenereerd die in Adobe Campaign zijn opgeslagen en kunnen deze worden gedownload op het scherm van de privacyaanvraag. |
| **Kostprijsberekening** (begrotingsbeheer) | Standaard geïnstalleerd | Deze workflow start de berekening van kosten en kostenposten voor de begrotingen, plannen, programma&#39;s, campagnes, leveringen en taken. |
| **Database opschonen** (opruimen) | Standaard geïnstalleerd | Deze workflow is de workflow voor databaseonderhoud: het maakt verschillende berekeningen van de statistieken en de processen, en schrapt verouderde gegevens van het gegevensbestand volgens de bepaalde configuratie in de plaatsingsmedewerker. Het wordt teweeggebracht elke dag om 4am door gebrek. |
| **Geblokkeerde lijngebruikers verwijderen** (deleteBlockedLineUsersV2) | LINE-kanaal | Deze workflow zorgt ervoor dat de gegevens van de gebruikers van de LIJN V2 worden verwijderd nadat ze de officiële account van de LIJN gedurende 180 dagen hebben geblokkeerd. |
| **Gegevens over privacyverzoeken verwijderen** (deletePrivacyRequestsData) | Verordening inzake bescherming van privacydata | Deze workflow verwijdert de gegevens die de ontvanger in Adobe Campaign heeft opgeslagen. |
| **Leveringsindicatoren** (leveringsindicatoren) | Midsourcingplatform | Deze werkstroom werkt leveringsvolgindicatoren voor een levering bij. Deze workflow wordt standaard elke uur geactiveerd. |
| **Verspreide marketingprocessen** (centralLocalMgt) | Centrale/lokale Marketing (Distributed Marketing) | Deze workflow begint met het verwerken van de gedistribueerde marketingmodule. Het lanceert de verwezenlijking van lokale campagnes en beheert berichten met betrekking tot orden en campagnepakketbeschikbaarheid. |
| **Gebeurtenis leegmaken** (webAnalyticsPurgeWebEvents) | Webanalytische connectors | Met deze workflow kunt u elke gebeurtenis uit het databaseveld verwijderen op basis van de periode die is geconfigureerd in het veld Lifespan. |
| **Soorten publiek exporteren naar de Adobe Experience Cloud** (exportSharedAudience) | Integratie met Adobe Experience Cloud | Deze workflow exporteert soorten publiek als gedeeld publiek/segmenten. Deze doelgroepen kunnen worden gebruikt in de verschillende Adobe Experience Cloud-oplossingen die u gebruikt. |
| **Voorspelling** (prognoses) | Levering | Deze workflow analyseert leveringen die zijn opgeslagen in de voorlopige kalender (maakt voorlopige logbestanden). Het wordt teweeggebracht elke dag bij 1am door gebrek. |
| **Volledige geaggregeerde berekening (voorzettingskubus)** (agg_nmsproposition_rcp_full) | Aanbiedingsengine (interactie) | Deze workflow werkt het volledige aggregaat voor de keuzelijst met voorstellen van aanbiedingen bij. Het wordt teweeggebracht elke dag om 6 uur door gebrek. In dit aggregaat worden de volgende afmetingen vastgelegd: Kanaal, levering, marketingaanbieding en datum. De blokje van het voorstel van de Aanbieding wordt dan gebruikt om rapporten te produceren die op voorstellen worden gebaseerd. Meer informatie over kubussen in  [deze sectie](../../v8/reporting/gs-cubes.md). |
| **Identificatie van omgezette contactpersonen** (webAnalyticsFindConverted) | Webanalytische connectors | Deze workflow indexeert bezoekers van de site die hun aankoop hebben voltooid na een campagne voor het opnieuw op de markt brengen van producten. De gegevens die door deze workflow worden hersteld, zijn toegankelijk via het efficiëntierapport voor opnieuw in de handel brengen (zie deze pagina). |
| **Publiek importeren uit de Adobe Experience Cloud** (importSharedAudience) | Integratie met Adobe Experience Cloud | Met deze workflow kunt u soorten publiek/segmenten van verschillende Adobe Experience Cloud-oplossingen importeren in Adobe Campaign. |
| **Banen op leveringen in campagnes** (deliveryMgt) | Standaard geïnstalleerd | Deze workflow activeert de goedgekeurde leveringen en start de naverwerking van de serviceprovider voor een externe levering. Het verzendt ook goedkeuringsberichten en herinneringen. |
| **Banen voor dienstverleners** (providerMgt) | Standaard geïnstalleerd | Dit werkschema begint de leverancier (e-mail aan de router en post-verwerking) te verwerken zodra de leveringen zijn goedgekeurd. |
| **MID naar migratie naar LineUserID** (MIDToUserIDMigration) | LINE-kanaal | Deze workflow genereert de LINE V2-gebruikers-id voor migratie van LIJN V1 naar LIJN V2. |
| **Berichtencentrum &lt;external_account_name>** (mcSynch_&lt;external_account_name>) | Transactionaal berichtenbeheer (Berichtcentrum - Controle) | Deze workflow: <ul><li>Hiermee wordt de lijst met gebeurtenissen hersteld die door de bewerking(en) zijn verwerkt.</li><li>synchroniseert met de tabel NmsBroadLogMsg om de kwalificaties van de leveringsberichten te herstellen.</li><li>Hiermee worden de logbestanden voor gebeurtenislevering hersteld zodra de synchronisatie met de tabel NmsBroadLogMsg is voltooid.</li><li>synchroniseert met de tabel NmsTrackingUrl om de tracking voor bezorgings-URL&#39;s te herstellen.</li><li>Hiermee worden URL&#39;s voor het bijhouden van gebeurtenissen hersteld zodra de synchronisatie met de tabel NmsTrackingUrl is voltooid.</li><li>Hiermee kunt u alle e-mailadressen herstellen die elke drie uur nadat een levering is verzonden, in quarantaine zijn geplaatst.</li></ul> |
| **MessageCenter volledige geaggregeerde berekening** (agg_messageCenter_full) | Transactionaal berichtenbeheer (Berichtcentrum - Controle) | Deze werkstroom werkt het Volledige aggregaat voor de kubus van het Centrum van het Bericht bij. Deze wordt standaard elke dag om 3 uur geactiveerd. In dit aggregaat worden de volgende afmetingen vastgelegd: Het type Kanaal, Datum, Status en Gebeurtenis. De kubus van het centrum van het Bericht wordt dan gebruikt om rapporten te produceren die op gebeurtenissen worden gebaseerd. Meer informatie over kubussen vindt u in  |
| **Midden-sourcing (leveringstellers)** (defaultMidSourcingDlv) | Overdracht naar midsourcing | Deze workflow verzamelt tellingsinformatie voor leveringen op de server voor midsourcing. De telgegevens omvatten algemene leveringsindicatoren zoals het aantal verzonden leveringen, enz. Trackinggegevens zoals die worden geopend, worden niet opgenomen. Deze wordt standaard om de tien minuten geactiveerd. |
| **Midden-sourcing (leveringslogboeken)** (defaultMidSourcingLog) | Overdracht naar midsourcing | Deze workflow verzamelt leveringslogboeken op de server voor midsourcing. Deze wordt standaard elke uur geactiveerd. |
| **NMAC-opt-out-beheer** (mobileAppOptOutMgt) | Mobile App Channel (push) | Met deze workflow worden afmeldingsopties op mobiele apparaten bijgewerkt. Het wordt teweeggebracht om de 6 uur tussen 1am en middernacht. |
| **Melding voorstel** (aanbiedingsbeheer) | Standaard geïnstalleerd | Deze workflow implementeert goedgekeurde aanbiedingen in de onlineomgeving en in elke categorie in de aanbiedingencatalogus. |
| **Opschonen van gepauzeerde workflows** (CleupPausedWorkflows) | Standaard geïnstalleerd | In deze workflow worden gepauzeerde workflows geanalyseerd waarvoor de ernst is ingesteld op Normaal en worden waarschuwingen en meldingen geactiveerd wanneer deze al te lang zijn gepauzeerd. Na een maand worden gepauzeerde technische workflows onvoorwaardelijk gestopt. Standaard wordt de activering elke maandag om 17.00 uur gestart. Raadpleeg voor meer informatie [Afhandeling van gepauzeerde workflows](monitor-workflow-execution.md#handling-of-paused-workflows). |
| **Opmaak van privacyverzoek** (cleanPrivacyRequests) | Verordening inzake bescherming van privacydata | Deze workflow wist de bestanden met toegangsverzoeken die ouder zijn dan 90 dagen. |
| **Batchgebeurtenissen verwerken** (batchEventsProcessing) | Transactiebericht uitvoeren (Berichtcentrum - Uitvoering) | Met deze workflow kunt u batchgebeurtenissen in een wachtrij plaatsen voordat u ze aan een berichtsjabloon koppelt. |
| **Real-time gebeurtenissen verwerken** (rtEventsProcessing) | Transactiebericht uitvoeren (Berichtcentrum - Uitvoering) | Dit werkschema laat u gebeurtenissen in real time in een rij zetten alvorens hen met een berichtmalplaatje te associëren. |
| **Propositiesynchronisatie** (propositionSynch) | Besturing van de aanbiedingsengine met uitvoeringsinstantie | Deze workflow synchroniseert voorstellingen tussen de marketinginstantie en de uitvoeringsinstantie die voor interacties wordt gebruikt. |
| **Herstel van webgebeurtenissen** (webAnalyticsGetWebEvents) | Webanalytische connectors | Elk uur downloadt deze workflow segmenten op het gedrag van internetgebruikers op een bepaalde site, plaatst deze in de Adobe Campaign-database en start de workflow voor het opnieuw in de handel brengen. |
| **Rapportageaggregaten** (reportingAggregates) | Levering | Deze workflow werkt aggregaten bij die worden gebruikt in rapporten. Het wordt teweeggebracht elke dag om 2 uur door gebrek. |
| **Verzending van indicatoren en campagnerekenmerken** (webAnalyticsSendMetrics) | Webanalytische connectors | Met deze workflow kunt u e-mailcampagneindicatoren van Adobe Campaign naar Adobe Experience Cloud Suite verzenden via de Adobe® Analytics-connector. De betrokken indicatoren zijn als volgt: Verzonden (Verzonden), Totaal aantal van opent (iTotalRecipientOpen), Totaal aantal ontvangers die klikte (iTotalRecipientClick), Fouten (iError), Opt-Out (opt-out) (iOptOut). |
| **Voorraad: Orders en waarschuwingen** (stockMgt) | Standaard geïnstalleerd | Deze workflow start voorraadberekening op de orderregels en beheert drempelwaarden voor waarschuwingen. |
| **Tekstspatiëring** (reeksspatiëring | Standaard geïnstalleerd | Deze workflow voert het herstel en de consolidatie van trackinggegevens uit. Het verzekert ook de herberekening van het volgen en leveringsstatistieken, vooral die gebruikt door het archiveren van het Centrum van het Bericht werkschema. Deze wordt standaard één keer per uur geactiveerd. |
| **Status van gebeurtenis bijwerken** (updateEventsStatus) | Transactiebericht uitvoeren (Berichtcentrum - Uitvoering) | Met deze workflow kunt u een status aan een gebeurtenis toewijzen. Gebeurtenisstatussen zijn als volgt:<ul><li>In behandeling: de gebeurtenis bevindt zich in een wachtrij. Er is nog geen berichtsjabloon aan gekoppeld.</li><li>In afwachting van levering: Als de gebeurtenis zich in een wachtrij bevindt, is er een berichtsjabloon aan gekoppeld en wordt deze momenteel verwerkt door de levering.</li><li>Verzonden: deze status wordt gekopieerd uit de leveringslogboeken. Dit betekent dat de levering is verzonden.</li><li>Genegeerd door de levering: deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is genegeerd.</li><li>Afleveringsfout: deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is mislukt.</li><li>Gebeurtenis niet gedekt: de gebeurtenis is niet gekoppeld aan een berichtsjabloon. De gebeurtenis wordt niet opnieuw verwerkt.</li></ul> |
| **Update voor leverbaarheid** (DeliabilityUpdate) | Standaard geïnstalleerd | Zodra het pakket voor de bewaking van de aflevering (e-mail aflevering) is geïnstalleerd, wordt deze workflow elke avond uitgevoerd en worden de kwalificatieregels voor stuiterende e-mailadressen en de lijst met domeinen en MX&#39;s beheerd. Hiervoor moet de HTTPS-poort open zijn op het platform. |
