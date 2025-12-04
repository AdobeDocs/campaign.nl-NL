---
title: Bewaking van uw leveringen in de interface van de campagne
description: Leer hoe u de lijst met leveringen kunt openen en het dashboard voor levering kunt gebruiken om uw leveringen te controleren
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 2%

---

# Bewaking van uw leveringen in de interface van de campagne {#delivery-dashboard}

Het is van essentieel belang dat u uw leveringen controleert om ervoor te zorgen dat uw campagnes efficiënt zijn en uw klanten bereiken. Adobe Campaign biedt u hulpprogramma&#39;s om toegang te krijgen tot uw leveringen en de prestaties ervan te controleren via de leveringslijst en het leveringsdashboard.

## Toegang krijgen tot de lijst met leveringen {#list-of-deliveries}

Via het knooppunt **[!UICONTROL Campaign Management > Deliveries]** van de boomstructuur hebt u toegang tot leveringen vanuit de leveringslijst.

![](assets/deliveries-list.png)

Standaard bevat de lijst met leveringen de namen en statussen van de leveringen die in het geselecteerde knooppunt zijn gemaakt. Het toont ook het aantal berichten om te verzenden, te verwerken en met succes te verzenden.

* Het aantal **[!UICONTROL Messages to send]** komt overeen met het aantal ontvangers dat na analyse en vóór levering als doel is geselecteerd.
* Het aantal berichten in de kolom **[!UICONTROL Success]** komt overeen met het aantal berichten dat door de server wordt verzonden en door de ontvangers wordt ontvangen.
* Het aantal **[!UICONTROL Processed]** berichten komt overeen met het aantal ontvangen berichten plus het aantal berichten met fouten.

>[!NOTE]
>
>Voor grote leveringen wilt u deze waarden mogelijk bijwerken. U doet dit door de desbetreffende levering te selecteren en er vervolgens met de rechtermuisknop op te klikken. Selecteer **[!UICONTROL Action > Recompute delivery and tracking indicators...]** en gebruik vervolgens de assistent om deze gegevens bij te werken.

## Overzicht van het leveringsdashboard {#delivery-dashboard-overview}

Het **leveringsdashboard** is zeer belangrijk om uw leveringen en uiteindelijke kwesties te controleren die tijdens het verzenden van berichten worden ontmoet.

Hiermee kunt u informatie over een levering ophalen en deze indien nodig bewerken. De tabinhoud kan niet meer worden gewijzigd nadat de levering is verzonden.

Hier volgt de informatie die u kunt controleren met de verschillende tabbladen die beschikbaar zijn in het dashboard:

* [Leveringsoverzicht](#delivery-summary)
* [Leveringsrapporten](#delivery-reports)
* [Afleveringslogs, spiegelpagina&#39;s, uitsluitingen](#delivery-logs-and-history)
* [Logbestanden en geschiedenis voor het bijhouden van leveringen](#tracking-logs)
* [Rendering van levering](#delivery-rendering)
* [Afleveringscontrole](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**Verwante onderwerpen:**

* [Leveringsfouten begrijpen](delivery-failures.md)
* [Quarantainebeheer](quarantines.md)
* [Best practices voor leveringen](../start/delivery-best-practices.md)
* [Te leveren items beheren](about-deliverability.md)

## Leveringsoverzicht {#delivery-summary}

Het tabblad **[!UICONTROL Summary]** bevat de kenmerken van de levering: de leveringsstatus, het gebruikte kanaal, informatie over de afzender, het onderwerp en informatie over de uitvoering.

## Leveringsrapporten {#delivery-reports}

Met de koppeling **[!UICONTROL Reports]** , die toegankelijk is vanaf het tabblad **[!UICONTROL Summary]** , kunt u een set rapporten bekijken die betrekking hebben op de leveringsactie: algemeen leveringsrapport, gedetailleerd rapport, leverrapport, distributie van mislukte berichten, openingsfrequentie, klikken en transacties, enz.

De inhoud van dit lusje kan volgens uw vereisten worden gevormd. Voor meer op leveringsrapporten, verwijs naar [&#x200B; deze sectie &#x200B;](../reporting/delivery-reports.md).

![](assets/delivery-report.png)

## Leveringslogboeken, geschiedenis en uitsluitingen {#delivery-logs-and-history}

Het tabblad **[!UICONTROL Delivery]** geeft een geschiedenis van de gebeurtenissen in deze levering. Het bevat de leveringslogboeken, d.w.z. de lijst van verzonden berichten en hun status en de bijbehorende berichten.

Voor een levering kunt u (bijvoorbeeld) alleen ontvangers met een mislukte levering of een adres in quarantaine weergeven. Klik hiertoe op de knop **[!UICONTROL Filters]** en selecteer **[!UICONTROL By state]** . Selecteer vervolgens het frame in de vervolgkeuzelijst. Diverse statussen worden vermeld in de [&#x200B; leveringsstatuspagina &#x200B;](delivery-statuses.md).

>[!NOTE]
>
>De lijst met de leveringslogboeken kan worden aangepast, net als elke andere lijst in Campagne. U kunt bijvoorbeeld een kolom toevoegen om te weten welk IP-adres elke e-mail in een bezorging heeft verzonden. Voor meer bij het vormen lijstvertoning, verwijs naar [&#x200B; deze sectie &#x200B;](../config/ui-settings.md#customize-lists).

![](assets/s_ncs_user_delivery_delivery_tab.png)

Met de koppeling **[!UICONTROL Display the mirror page for this message...]** kunt u de spiegelpagina weergeven voor de inhoud van de levering die in de lijst is geselecteerd in een nieuw venster.

De spiegelpagina is alleen beschikbaar voor leveringen waarvoor HTML-inhoud is gedefinieerd. Voor meer op dit, verwijs naar [&#x200B; Verbinding aan de spiegelpagina &#x200B;](mirror-page.md).

![](assets/s_ncs_user_wizard_miror_page_link.png)

## Logbestanden en geschiedenis voor het bijhouden van leveringen {#tracking-logs}

Op het tabblad **[!UICONTROL Tracking]** wordt de geschiedenis van het bijhouden van gegevens voor deze levering weergegeven. Op dit tabblad worden trackinggegevens weergegeven voor de verzonden berichten, d.w.z. alle URL&#39;s die door Adobe Campaign moeten worden gevolgd. De volgende gegevens worden per uur bijgewerkt.

>[!NOTE]
>
>Als &#39;tracking&#39; niet is ingeschakeld voor levering, wordt dit tabblad niet weergegeven.

De het volgen configuratie wordt uitgevoerd in het aangewezen stadium in de leveringsmedewerker. Zie [&#x200B; hoe te om gevolgde verbindingen &#x200B;](tracking.md) te vormen.

**[!UICONTROL Tracking]** -gegevens worden geïnterpreteerd in de leveringsrapporten. Zie [deze sectie](../reporting/delivery-reports.md).

![](assets/s_ncs_user_delivery_tracking_tab.png)

## Inboxrendering {#delivery-rendering}

Op het tabblad **[!UICONTROL Inbox rendering]** kunt u een voorvertoning van het bericht weergeven in de verschillende contexten waarin het kan worden ontvangen en kunt u de compatibiliteit van belangrijke desktops en toepassingen controleren.

Op deze manier kunt u ervoor zorgen dat uw bericht optimaal aan de ontvangers wordt weergegeven op verschillende webclients, webmails en apparaten.

Voor meer op inbox teruggevend, verwijs naar [&#x200B; deze pagina &#x200B;](inbox-rendering.md)


## Afleveringscontrole {#delivery-audit-}

Het tabblad **[!UICONTROL Audit]** bevat het leveringslogboek en alle berichten met betrekking tot de proefdrukken.

Met de knop **[!UICONTROL Refresh]** kunt u de gegevens bijwerken. Gebruik de knop **[!UICONTROL Filters]** om een filter voor de gegevens te definiëren.

Met speciale pictogrammen kunt u fouten of waarschuwingen herkennen. Zie [&#x200B; de analyse van de Levering &#x200B;](delivery-analysis.md).

Met het subtabblad **[!UICONTROL Proofs]** kunt u de lijst met proefdrukken weergeven die zijn verzonden.

![](assets/s_ncs_user_delivery_log_tab.png)

U kunt de informatie wijzigen die wordt weergegeven in dit venster (en die van de tabbladen **[!UICONTROL Delivery]** en **[!UICONTROL Tracking]** ) door de kolommen te selecteren die moeten worden weergegeven. Klik hiertoe op het pictogram **[!UICONTROL Configure list]** in de rechterbenedenhoek. Voor meer bij het vormen lijstvertoning, verwijs naar [&#x200B; deze sectie &#x200B;](../config/ui-settings.md#customize-lists).

## Synchronisatie van het dashboard voor levering {#delivery-dashboard-synchronization}

Van uw leveringsdashboard, wilt u de verwerkte berichten en leveringslogboeken controleren om ervoor te zorgen dat uw levering met succes werd verzonden.

Sommige indicatoren of status kunnen onjuist of niet bijgewerkt zijn, dit kan met de volgende oplossingen worden opgelost:

* Als uw leveringsstatus onjuist is, controleert u of alle vereiste goedkeuringen zijn uitgevoerd voor deze levering of of de **[!UICONTROL operationMgt]** - en **[!UICONTROL deliveryMgt]** -technische workflows zonder fouten worden uitgevoerd.

* Als uw leveringsteller niet overeenkomt met uw levering, probeert u de indicatoren opnieuw te berekenen door met de rechtermuisknop op de desbetreffende levering in de Adobe Campaign-verkenner te klikken en **[!UICONTROL Actions]** > **[!UICONTROL Recompute delivery and tracking indicators]** te selecteren om opnieuw te synchroniseren. Voor meer informatie bij het volgen van indicatoren, verwijs naar deze [&#x200B; sectie &#x200B;](../reporting/delivery-reports.md#tracking-indicators).

U kunt uw leveringen ook bijhouden met verschillende rapporten via het leveringsdashboard. Raadpleeg deze [sectie](../reporting/delivery-reports.md) voor meer informatie.

>[!NOTE]
>
>Als gebruiker van Campagne v8 Managed Cloud Services wordt de infrastructuur gecontroleerd en beheerd door Adobe. Neem contact op met de klantenservice van Adobe als u voortdurend problemen ondervindt met leveringsindicatoren of dashboardsynchronisatie.

## Problemen met trage leveringen oplossen {#troubleshooting-slow-deliveries}

Als de levering langer dan normaal lijkt te duren nadat u op de knop **[!UICONTROL Send]** hebt geklikt, controleert u de volgende mogelijke oorzaken:

### IP de kwesties van de adresreputatie

Sommige e-mailproviders hebben mogelijk uw IP-adressen aan een lijst van gewezen personen toegevoegd. Controleer uw leveringslogboeken (uitzendingen) in het **[!UICONTROL Delivery]** lusje voor bounce berichten die op reputatie wijzen. Raadpleeg de [&#x200B; sectie van de 0&rbrace; leveringscontrole &lbrace;voor begeleiding op reputatie beheer.](monitoring-deliverability.md)

### Grootte en complexiteit van de levering

Je levering is mogelijk te groot om snel te worden verwerkt. Dit kan voorkomen bij:

Zware JavaScript-personalisatie die aanzienlijke gegevensverwerking vereist voor elke ontvanger.

De levering weegt meer dan 60 kilobytes door grote HTML-inhoud, ingesloten afbeeldingen of uitgebreide personalisatie.

Verwijs naar [&#x200B; beste praktijken van de Levering &#x200B;](../start/delivery-best-practices.md) om over inhoudsrichtlijnen en verpersoonlijkingsbeste praktijken te leren. De aanbevolen maximale grootte is ongeveer 35 kB voor optimale prestaties.

### Systeemprestaties

Systeemproblemen kunnen ervoor zorgen dat servers hun producten niet efficiënt verwerken. Als u prestatieskwesties vermoedt, controleer de leveringslogboeken voor onderbrekingsfouten of communicatie kwesties.

>[!NOTE]
>
>Als Campagne versie 8 Managed Cloud Services-gebruiker wordt de controle van de serverinfrastructuur beheerd door Adobe. Als u blijvende prestatieproblemen ondervindt bij het verzenden van de levering, neemt u contact op met de klantenservice van Adobe met uw leveringslogboeken.

