---
title: Quarantainebeheer in Campagne
description: Werken met quarantainebeheer in Adobe Campaign
feature: Profiles, Monitoring
role: User, Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: cb4cbc9ba14e953d2b3109e87eece4f310bfe838
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 4%

---

# Quarantine {#quarantine-management}

Adobe Campaign beheert een lijst met in quarantaine geplaatste adressen voor onlinekanalen (e-mail, SMS, pushmelding). Sommige providers van internettoegang beschouwen e-mails automatisch als spam als de snelheid van ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat deze providers aan de lijst van gewezen personen worden toegevoegd. Bovendien zijn de verzendkosten voor sms-berichten lager doordat onjuiste telefoonnummers van de levering worden uitgesloten.

Wanneer hun adres of telefoonaantal quarantined is, worden de ontvangers uitgesloten van het doel tijdens leveringsanalyse: u zult geen marketingberichten, met inbegrip van geautomatiseerde werkschemae-mails, naar die contacten kunnen verzenden. Als die quarantined adressen ook in lijsten aanwezig zijn, zullen zij wanneer het verzenden naar die lijsten worden uitgesloten. Een e-mailadres kan in quarantaine worden geplaatst, bijvoorbeeld wanneer de brievenbus volledig is, als het adres niet bestaat, of als de e-mailserver niet beschikbaar is.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

## Quarantaine versus lijst van gewezen personen

**quarantaine** is slechts op een **adres**, a **telefoonaantal**, of a **apparatenteken** van toepassing, maar niet op het profiel zelf. Een profiel waarvan het e-mailadres in quarantaine is geplaatst, kan bijvoorbeeld zijn profiel bijwerken en een nieuw adres invoeren. Dit profiel kan dan opnieuw worden geactiveerd door leveringsacties. Eveneens, als twee profielen gebeuren om het zelfde telefoonaantal te hebben, zullen zij allebei worden beïnvloed als het aantal quarantined is. De quarantined adressen of telefoonaantallen worden getoond in [ uitsluitingslogboeken ](#delivery-quarantines) (voor een levering) of in de [ quarantainelijst ](#non-deliverable-bounces) (voor het volledige platform).

>[!NOTE]
>
>Wanneer de ontvangers uw bericht als spam melden of op een bericht van SMS met een sleutelwoord zoals &quot;STOP&quot;antwoorden, wordt hun adres of telefoonaantal quarantined als **[!UICONTROL Denylisted]**. Hun profiel wordt dienovereenkomstig bijgewerkt.

Anderzijds, **de profielen** kunnen op de **lijst van gewezen personen** zijn zoals na een unsubscription (opt-out), voor een bepaald kanaal: dit impliceert dat zij niet meer door om het even welke levering worden gericht. Als een profiel op de lijst van gewezen personen voor het e-mailkanaal twee e-mailadressen heeft, worden beide adressen daarom uitgesloten van levering. In de sectie **[!UICONTROL No longer contact]** van het tabblad **[!UICONTROL General]** van het profiel kunt u controleren of er zich op de lijst van gewezen personen een of meer kanalen bevinden in de sectie  van het profiel. [Meer informatie](../audiences/view-profiles.md)

>[!NOTE]
>
>Ontvangen ontvangers die zich niet hebben geabonneerd via de methode [ &quot;mailto&quot; List-Unsubscribe ](https://experienceleague.adobe.com/nl/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations#mailto-list-unsubscribe){target="_blank"} , worden niet verzonden naar quarantaine. Zij of worden unsubscribed van de [ dienst ](../start/subscriptions.md) verbonden aan de levering, of verzonden naar de lijst van gewezen personen (zichtbaar in de 2&rbrace; sectie van het profiel &lbrace;) als geen dienst voor de levering werd bepaald.**[!UICONTROL No longer contact]**

<!--For the mobile app channel, device tokens are quarantined.-->

## Waarom wordt een e-mail, telefoon of apparaat verzonden naar quarantaine {#quarantine-reason}

Adobe Campaign beheert quarantaine op basis van het type leveringsfout en de oorzaak ervan. Deze worden toegewezen tijdens de kwalificatie van foutberichten. Leer meer over het beheer van de leveringsmislukking [ op deze pagina ](delivery-failures.md).

Er kunnen twee typen of fouten worden vastgelegd:

* **Harde fout**: het e-mailadres, het telefoonaantal of het apparaat wordt onmiddellijk verzonden naar quarantaine.
* **Zachte fout**: de zachte fouten verhogen een foutenteller, en zouden een e-mail, telefoonaantal of apparatenteken in quarantaine kunnen plaatsen. De campagne voert [ opnieuw probeert ](delivery-failures.md#retries) uit: wanneer de foutenteller de grensdrempel bereikt, wordt het adres, het telefoonaantal of het apparatenteken quarantined. [Meer informatie](delivery-failures.md#retries).

In de lijst van quarantined adressen, wijst het **[!UICONTROL Error reason]** gebied erop waarom het geselecteerde adres in quarantaine werd geplaatst. [Meer informatie](#identifying-quarantined-addresses-for-the-entire-platform).


Als een gebruiker een e-mail als spam kwalificeert, wordt het bericht automatisch opnieuw gericht naar een technische brievenbus die door Adobe wordt geleid. Het e-mailadres van de gebruiker wordt vervolgens automatisch in quarantaine geplaatst met de status **[!UICONTROL Denylisted]**. Deze status verwijst alleen naar het adres, het profiel staat niet op de lijst van gewezen personen, zodat de gebruiker SMS-berichten en pushberichten blijft ontvangen. Leer meer over de lijnen van de Terugkoppeling in de [ Gids van Beste praktijken van de Levering ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=nl-NL#feedback-loops){target="_blank"}.

>[!NOTE]
>
>Quarantaine in Adobe Campaign is hoofdlettergevoelig. Zorg dat u de e-mailadressen in kleine letters importeert, zodat ze later niet opnieuw worden getarget.

## Toegang tot quarantineadressen {#access-quarantined-addresses}

De gekwalificeerde adressen kunnen voor een specifieke levering of voor het volledige platform worden getoond.

### Quarantines voor levering{#delivery-quarantines}

Quarantaineadressen worden vermeld tijdens de voorbereidingsfase van de levering, in de leveringslogboeken van het leveringsdashboard.

Voor elke levering, kunt u het **[!UICONTROL Delivery summary]** rapport ook controleren: het toont het aantal adressen in quarantaine in het leveringsdoel, en toont:

* het aantal adressen dat tijdens de afleveringsanalyse in quarantaine wordt geplaatst;
* Het aantal adressen die in quarantaine na de leveringsactie worden geplaatst.

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

Leer meer over stuiterende adressen in de [ Gids van de Beste praktijken van de Levering ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=nl-NL){target="_blank"}.

### Gegarandeerd e-mailadres {#quarantined-recipient}

U kunt de status van het e-mailadres van elke ontvanger opzoeken.

Selecteer hiertoe het ontvangende profiel en klik op de tab **[!UICONTROL Deliveries]** . Voor alle leveringen aan die ontvanger, kunt u te weten komen of het ontbroken adres, tijdens analyse in quarantined, enz. was.

Voor elke map kunt u alleen de ontvangers weergeven van wie het e-mailadres in quarantaine staat, met het ingebouwde filter **[!UICONTROL Quarantined email address]** , zoals hieronder:

![](assets/quarantine-filter.png)


## Een in quarantaine geplaatst adres verwijderen {#remove-a-quarantined-address}

Adressen die specifieke voorwaarden aanpassen worden automatisch geschrapt van de quarantainelijst door het **ingebouwde werkschema van de Schoonmaak van het Gegevensbestand 0&rbrace; &lbrace;.**

De adressen worden automatisch verwijderd uit de quarantainelijst in de volgende gevallen:

* Adressen in de status **[!UICONTROL With errors]** worden na een geslaagde levering uit de quarantainelijst verwijderd.
* Adressen in een status **[!UICONTROL With errors]** worden uit de quarantainelijst verwijderd als de laatste zachte stuit meer dan 10 dagen geleden plaatsvond. Voor meer op softfoutenbeheer, zie [ deze sectie ](#soft-error-management).
* Adressen in een **[!UICONTROL With errors]** -status die met de **[!UICONTROL Mailbox full]** -fout zijn gemarkeerd, worden na 30 dagen uit de quarantainelijst verwijderd.

De status verandert vervolgens in **[!UICONTROL Valid]** .

>[!CAUTION]
>
>Ontvangers met een adres in de status **[!UICONTROL Quarantine]** of **[!UICONTROL Denylisted]** worden nooit verwijderd, zelfs niet als ze een e-mail ontvangen.

U kunt ook handmatig een adres uit de quarantainelijst verwijderen. Als u een adres uit quarantaine wilt verwijderen, kunt u:

* Wijzig zijn status in **[!UICONTROL Valid]** vanuit het knooppunt **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** .

  ![](assets/tech-quarantine-status.png)

U zou bulkupdates op de quarantainelijst kunnen moeten uitvoeren, bijvoorbeeld in het geval van een ISP stroomonderbreking waarin de e-mails verkeerd als grenzen worden gemerkt omdat zij niet met succes aan hun ontvanger kunnen worden geleverd.

Om dit uit te voeren, creeer een werkschema en voeg een vraag op uw quarantainetabel toe om alle beïnvloede ontvangers uit te filteren zodat zij uit de quarantainelijst kunnen worden verwijderd, en inbegrepen in toekomstige e-mailleveringen van de Campagne.

Hieronder volgen de geadviseerde richtlijnen voor deze vraag:

* **tekst van de Fout (quarantainetekst)** bevat &quot;Momen_Code10_InvalidRecipient&quot;
* **E-maildomein (@domein)** is gelijk aan domain1.com OF **E-maildomein (@domein)** gelijk aan domain2.com OF **E-maildomein (@domein)** gelijk aan domain3.com
* **status van de Update (@lastModified)** op of na `MM/DD/YYYY HH:MM:SS AM`
* **status van de Update (@lastModified)** op of vóór `MM/DD/YYYY HH:MM:SS PM`

Als u de lijst met betrokken ontvangers hebt, voegt u een **[!UICONTROL Update data]** -activiteit toe om hun status in te stellen op **[!UICONTROL Valid]** , zodat ze uit de quarantainelijst worden verwijderd via de **[!UICONTROL Database cleanup]** -workflow. U kunt ze ook gewoon uit de quarantainetabel verwijderen.

