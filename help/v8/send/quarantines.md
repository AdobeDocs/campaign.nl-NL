---
title: Quarantainebeheer in Campagne
description: Werken met quarantainebeheer in Adobe Campaign
feature: Profiles, Monitoring
role: User, Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 4%

---

# Quarantine {#quarantine-management}

Adobe Campaign beheert een lijst met in quarantaine geplaatste adressen voor onlinekanalen (e-mail, SMS, pushmelding). Sommige providers van internettoegang beschouwen e-mails automatisch als spam als de snelheid van ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat deze providers aan de lijst van gewezen personen worden toegevoegd. Bovendien zijn de verzendkosten voor sms-berichten lager doordat onjuiste telefoonnummers van de levering worden uitgesloten.

Wanneer hun adres of telefoonaantal quarantined is, worden de ontvangers uitgesloten van het doel tijdens leveringsanalyse: u zult geen marketingberichten, met inbegrip van geautomatiseerde werkschemae-mails, naar die contacten kunnen verzenden. Als die quarantined adressen ook in lijsten aanwezig zijn, zullen zij wanneer het verzenden naar die lijsten worden uitgesloten. Een e-mailadres kan in quarantaine worden geplaatst, bijvoorbeeld wanneer de brievenbus volledig is, als het adres niet bestaat, of als de e-mailserver niet beschikbaar is.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

## Quarantaine versus lijst van gewezen personen

**quarantaine** is slechts op een **adres**, a **telefoonaantal**, of a **apparatenteken** van toepassing, maar niet op het profiel zelf. Een profiel waarvan het e-mailadres in quarantaine is geplaatst, kan bijvoorbeeld zijn profiel bijwerken en een nieuw adres invoeren. Dit profiel kan dan opnieuw worden geactiveerd door leveringsacties. Eveneens, als twee profielen gebeuren om het zelfde telefoonaantal te hebben, zullen zij allebei worden beïnvloed als het aantal quarantined is. De quarantined adressen of telefoonaantallen worden getoond in [&#x200B; uitsluitingslogboeken &#x200B;](#delivery-quarantines) (voor een levering) of in de [&#x200B; quarantainelijst &#x200B;](#non-deliverable-bounces) (voor het volledige platform).

>[!NOTE]
>
>Wanneer de ontvangers uw bericht als spam melden of op een bericht van SMS met een sleutelwoord zoals &quot;STOP&quot;antwoorden, wordt hun adres of telefoonaantal quarantined als **[!UICONTROL Denylisted]**. Hun profiel wordt dienovereenkomstig bijgewerkt.

Anderzijds, **de profielen** kunnen op de **lijst van gewezen personen** zijn zoals na een unsubscription (opt-out), voor een bepaald kanaal: dit impliceert dat zij niet meer door om het even welke levering worden gericht. Als een profiel op de lijst van gewezen personen voor het e-mailkanaal twee e-mailadressen heeft, worden beide adressen daarom uitgesloten van levering. In de sectie **[!UICONTROL No longer contact]** van het tabblad **[!UICONTROL General]** van het profiel kunt u controleren of er zich op de lijst van gewezen personen een of meer kanalen bevinden in de sectie  van het profiel. [Meer informatie](../audiences/view-profiles.md)

>[!NOTE]
>
>Ontvangen ontvangers die zich niet hebben geabonneerd via de methode [&#x200B; &quot;mailto&quot; List-Unsubscribe &#x200B;](https://experienceleague.adobe.com/nl/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations#mailto-list-unsubscribe){target="_blank"} , worden niet verzonden naar quarantaine. Zij of worden unsubscribed van de [&#x200B; dienst &#x200B;](../start/subscriptions.md) verbonden aan de levering, of verzonden naar de lijst van gewezen personen (zichtbaar in de 2&rbrace; sectie van het profiel &lbrace;) als geen dienst voor de levering werd bepaald.**[!UICONTROL No longer contact]**

<!--For the mobile app channel, device tokens are quarantined.-->

## Waarom wordt een e-mail, telefoon of apparaat verzonden naar quarantaine {#quarantine-reason}

Adobe Campaign beheert quarantaine op basis van het type leveringsfout en de oorzaak ervan. Deze worden toegewezen tijdens de kwalificatie van foutberichten. Leer meer over het beheer van de leveringsmislukking [&#x200B; op deze pagina &#x200B;](delivery-failures.md).

Er kunnen twee typen of fouten worden vastgelegd:

* **Harde fout**: het e-mailadres, het telefoonaantal of het apparaat wordt onmiddellijk verzonden naar quarantaine.
* **Zachte fout**: de zachte fouten verhogen een foutenteller, en zouden een e-mail, telefoonaantal of apparatenteken in quarantaine kunnen plaatsen. De campagne voert [&#x200B; opnieuw probeert &#x200B;](delivery-failures.md#retries) uit: wanneer de foutenteller de grensdrempel bereikt, wordt het adres, het telefoonaantal of het apparatenteken quarantined. [Meer informatie](delivery-failures.md#retries).

In de lijst van quarantined adressen, wijst het **[!UICONTROL Error reason]** gebied erop waarom het geselecteerde adres in quarantaine werd geplaatst. [Meer informatie](#non-deliverable-bounces).


Als een gebruiker een e-mail als spam kwalificeert, wordt het bericht automatisch opnieuw gericht naar een technische brievenbus die door Adobe wordt geleid. Het e-mailadres van de gebruiker wordt vervolgens automatisch in quarantaine geplaatst met de status **[!UICONTROL Denylisted]**. Deze status verwijst alleen naar het adres, het profiel staat niet op de lijst van gewezen personen, zodat de gebruiker SMS-berichten en pushberichten blijft ontvangen. Leer meer over de lijnen van de Terugkoppeling in de [&#x200B; Gids van Beste praktijken van de Levering &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=nl-NL#feedback-loops){target="_blank"}.

>[!NOTE]
>
>Quarantaine in Adobe Campaign is hoofdlettergevoelig. Zorg dat u de e-mailadressen in kleine letters importeert, zodat ze later niet opnieuw worden getarget.

## Beheer van zachte fouten {#soft-error-management}

In tegenstelling tot harde fouten, verzenden de zachte fouten niet onmiddellijk een adres naar quarantaine, maar zij verhogen in plaats daarvan een foutenteller. Wanneer de foutenteller de grensdrempel bereikt, is het adres quarantined. Leer meer over pogingen en foutentypes in [&#x200B; Begrijpend leveringsmislukkingen &#x200B;](delivery-failures.md).

De foutenteller wordt opnieuw geïnitialiseerd als de laatste significante fout meer dan 10 dagen geleden voorkwam. De adresstatus verandert vervolgens in **[!UICONTROL Valid]** en wordt door de **[!UICONTROL Database cleanup]** -workflow verwijderd uit de lijst met quarantines. [&#x200B; leer meer over technische werkschema&#39;s &#x200B;](../config/workflows.md#technical-workflows).

## Toegang tot quarantineadressen {#access-quarantined-addresses}

De gekwalificeerde adressen kunnen voor een specifieke levering of voor het volledige platform worden getoond.

### Quarantines voor levering{#delivery-quarantines}

Quarantaineadressen worden vermeld tijdens de voorbereidingsfase van de levering, in de leveringslogboeken van het leveringsdashboard.

Voor elke levering, kunt u het **[!UICONTROL Delivery summary]** rapport ook controleren: het toont het aantal adressen in quarantaine in het leveringsdoel, en toont:

* het aantal adressen dat tijdens de afleveringsanalyse in quarantaine wordt geplaatst;
* Het aantal adressen die in quarantaine na de leveringsactie worden geplaatst.

Leer meer over leveringsrapporten in [&#x200B; deze sectie &#x200B;](../reporting/gs-reporting.md).

### Niet-leverbare en stuitbare adressen{#non-deliverable-bounces}

Om de lijst van quarantined adressen **voor het volledige platform** te bekijken, kunnen de Beheerders van de Campagne aan **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** doorbladeren. Deze sectie maakt een lijst van quarantined elementen voor **e-mail**, **SMS** en **Push bericht** kanalen.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Het aantal quarantaine neemt met de tijd toe. Als de levensduur van een e-mailadres bijvoorbeeld wordt beschouwd als drie jaar en de tabel met ontvangers elk jaar met 50% toeneemt, kan de toename van quarantaine als volgt worden berekend:
>
>Eind van Jaar 1: (1 &#42; 0.33)/(1+0.5)=22%.
>
>Eind van Jaar 2: (1.22 &#42; 0.33) + 0.33)/(1.5+0.75)=32.5%.

Bovendien **[!UICONTROL Non-deliverables and bounces]** ingebouwd rapport, beschikbaar bij de **2&rbrace; sectie van Rapporten &lbrace;van deze homepage, toont informatie over de adressen in quarantaine, de types van aangetroffen fout, en een mislukkingsonderbreking door domein.** U kunt gegevens filteren voor een specifieke levering, of dit rapport aanpassen zoals nodig.

Leer meer over stuiterende adressen in de [&#x200B; Gids van de Beste praktijken van de Levering &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=nl-NL){target="_blank"}.

### Gegarandeerd e-mailadres {#quarantined-recipient}

U kunt de status van het e-mailadres van elke ontvanger opzoeken.

Selecteer hiertoe het ontvangende profiel en klik op de tab **[!UICONTROL Deliveries]** . Voor alle leveringen aan die ontvanger, kunt u te weten komen of het ontbroken adres, tijdens analyse in quarantined, enz. was.

Voor elke map kunt u alleen de ontvangers weergeven van wie het e-mailadres in quarantaine staat, met het ingebouwde filter **[!UICONTROL Quarantined email address]** , zoals hieronder:

![](assets/quarantine-filter.png)


## Een in quarantaine geplaatst adres verwijderen {#remove-a-quarantined-address}

### Automatische updates {#unquarantine-auto}

Adressen die aan specifieke voorwaarden voldoen, worden automatisch uit de quarantainelijst verwijderd door de ingebouwde workflow van **[!UICONTROL Database cleanup]** .

De adressen worden automatisch verwijderd uit de quarantainelijst in de volgende gevallen:

* Adressen in de status **[!UICONTROL With errors]** worden na een geslaagde levering uit de quarantainelijst verwijderd.
* Adressen in een status **[!UICONTROL With errors]** worden uit de quarantainelijst verwijderd als de laatste zachte stuit meer dan 10 dagen geleden plaatsvond. Voor meer op softfoutenbeheer, zie [&#x200B; deze sectie &#x200B;](#soft-error-management).
* Adressen in een **[!UICONTROL With errors]** -status die met de **[!UICONTROL Mailbox full]** -fout zijn gemarkeerd, worden na 30 dagen uit de quarantainelijst verwijderd.

De status verandert vervolgens in **[!UICONTROL Valid]** .

>[!CAUTION]
>
>Ontvangers met een adres in de status **[!UICONTROL Quarantine]** of **[!UICONTROL Denylisted]** worden nooit verwijderd, zelfs niet als ze een e-mail ontvangen.

### Handmatige updates {#unquarantine-manual}

U kunt ook handmatig een adres uit de quarantainelijst verwijderen. Als u een adres handmatig uit quarantaine wilt verwijderen, kunt u de status wijzigen in **[!UICONTROL Valid]** van het knooppunt **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** .

![](assets/tech-quarantine-status.png)

### Bulkupdates {#unquarantine-bulk}

U zou bulkupdates op de quarantainelijst in specifieke situaties kunnen moeten uitvoeren, zoals een ISP stroomonderbreking waarin de e-mails verkeerd als grenzen worden gemerkt omdat zij niet met succes aan hun ontvanger kunnen worden geleverd.

Een bulkupdate uitvoeren:

1. Creeer een werkschema en voeg een vraag op de quarantainelijst (**[!UICONTROL nms:address]**) toe om beïnvloede ontvangers te filtreren
2. De vraagvoorwaarden van het gebruik om adressen te identificeren die zouden moeten zijn unquarantined, zoals:
   * **E-maildomein (@domein)** evenaart het beïnvloede ISP domein(s)
   * **status van de Update (@lastModified)** binnen timeframe van de stroomonderbreking
   * **Status (@status)** evenaart quarantainestatus
3. Voeg een **[!UICONTROL Update data]** activiteit toe om de adresstatus aan **[!UICONTROL Valid]** te plaatsen

De adressen worden dan automatisch uit de quarantainelijst verwijderd door de **[!UICONTROL Database cleanup]** -workflow en kunnen in toekomstige leveringen worden opgenomen.

## Verwante onderwerpen

* [&#x200B; Begrijpend leveringsmislukkingen &#x200B;](delivery-failures.md) - Leer over de verschillende soorten leveringsmislukkingen en hoe de Behandelt van de Campagne stuitert
* [&#x200B; leveringen van de Monitor &#x200B;](delivery-dashboard.md) - de leveringslogboeken van de Toegang en de prestaties van de monitorlevering
* [&#x200B; beste praktijken van de Levering &#x200B;](../start/delivery-best-practices.md) - Beste praktijken voor het handhaven van goede leverbaarheid en het vermijden van quarantines

