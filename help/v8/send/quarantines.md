---
title: Quarantainebeheer in Campagne
description: Werken met quarantainebeheer in Adobe Campaign
feature: Profiles, Monitoring
role: User, Developer
level: Beginner, Intermediate
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: b783b1444457b3204fea35b613582642499acf65
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 4%

---

# Quarantine {#quarantine-management}

Adobe Campaign beheert een lijst met in quarantaine geplaatste adressen voor onlinekanalen (e-mail, SMS, pushmelding). Sommige internetproviders beschouwen e-mails automatisch als spam als de snelheid van ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat u door deze providers aan de lijst van gewezen personen wordt toegevoegd. Bovendien zijn de verzendkosten voor sms-berichten lager doordat onjuiste telefoonnummers van de levering worden uitgesloten.

Wanneer hun adres of telefoonaantal quarantined is, worden de ontvangers uitgesloten van het doel tijdens leveringsanalyse: u kunt geen marketingberichten, waaronder automatische workflow-e-mails, naar die contactpersonen sturen. Als die quarantined adressen ook in lijsten aanwezig zijn, zullen zij wanneer het verzenden naar die lijsten worden uitgesloten. Een e-mailadres kan in quarantaine worden geplaatst, bijvoorbeeld wanneer de brievenbus volledig is, als het adres niet bestaat, of als de e-mailserver niet beschikbaar is.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**Quarantine** alleen van toepassing op een **adres**, **telefoonnummer** of een **apparaattoken**, maar niet aan het profiel zelf. Een profiel waarvan het e-mailadres in quarantaine is geplaatst, kan bijvoorbeeld zijn profiel bijwerken en een nieuw adres invoeren. Dit profiel kan dan opnieuw worden geactiveerd door leveringsacties. Eveneens, als twee profielen gebeuren om het zelfde telefoonaantal te hebben, zullen zij allebei worden beïnvloed als het aantal quarantined is. De in quarantaine geplaatste adressen of telefoonaantallen worden getoond in [uitsluitingslogboeken](#delivery-quarantines) (voor levering) of in de [quarantainelijst](#non-deliverable-bounces) (voor het gehele platform).

Aan de andere kant kunnen profielen worden ingesteld op **lijst van gewezen personen** zoals na een abonnement (opt-out), voor een bepaald kanaal: dit houdt in dat zij niet langer het doelwit zijn van wie dan ook . Als een profiel op de lijst van gewezen personen voor het e-mailkanaal twee e-mailadressen heeft, worden beide adressen daarom uitgesloten van levering. U kunt controleren of een profiel op de lijst van gewezen personen voor een of meer kanalen in het dialoogvenster **[!UICONTROL No longer contact]** van het profiel **[!UICONTROL General]** tab. [Meer informatie](../audiences/view-profiles.md)

>[!NOTE]
>
>Wanneer de ontvangers uw bericht als spam melden of op een bericht van SMS met een sleutelwoord zoals &quot;STOP&quot;antwoorden, wordt hun adres of telefoonaantal quarantaine geplaatst zoals **[!UICONTROL Denylisted]**. Hun profiel wordt dienovereenkomstig bijgewerkt.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## Waarom wordt een e-mail, telefoon of apparaat verzonden naar quarantaine {#quarantine-reason}

Adobe Campaign beheert quarantaine op basis van het type leveringsfout en de oorzaak ervan. Deze worden toegewezen tijdens de kwalificatie van foutberichten. Meer informatie over beheer van leveringsfouten [op deze pagina](delivery-failures.md).

Er kunnen twee typen of fouten worden vastgelegd:

* **Harde fout**: het e-mailadres, telefoonnummer of apparaat wordt onmiddellijk naar quarantaine verzonden.
* **Zachte fout**: de zachte fouten verhogen een foutenteller, en zouden een e-mail, telefoonaantal of apparatenteken in quarantaine kunnen plaatsen. Campagne voert uit [opnieuw](delivery-failures.md#retries): wanneer de foutenteller de grensdrempel bereikt, wordt het adres, het telefoonaantal of het apparatenteken quarantined. [Meer informatie](delivery-failures.md#retries).

In de lijst van quarantined adressen, **[!UICONTROL Error reason]** geeft aan waarom het geselecteerde adres in quarantaine is geplaatst. [Meer informatie](#identifying-quarantined-addresses-for-the-entire-platform).


Als een gebruiker een e-mail als spam kwalificeert, wordt het bericht automatisch opnieuw gericht naar een technische brievenbus die door Adobe wordt geleid. Het e-mailadres van de gebruiker wordt vervolgens automatisch in quarantaine geplaatst met de status **[!UICONTROL Denylisted]**. Deze status verwijst alleen naar het adres, het profiel staat niet op de lijst van gewezen personen, zodat de gebruiker SMS-berichten en pushberichten blijft ontvangen. Meer informatie over feedbackloops in het dialoogvenster [Handleiding voor aanbevolen werkwijzen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target="_blank"}.

>[!NOTE]
>
>Quarantaine in Adobe Campaign is hoofdlettergevoelig. Zorg dat u de e-mailadressen in kleine letters importeert, zodat ze later niet opnieuw worden getarget.

## Toegang tot quarantineadressen {#access-quarantined-addresses}

De gekwalificeerde adressen kunnen voor een specifieke levering of voor het volledige platform worden getoond.

### Quarantines voor levering{#delivery-quarantines}

Quarantaineadressen worden vermeld tijdens de voorbereidingsfase van de levering, in de leveringslogboeken van het leveringsdashboard.

Voor elke levering kunt u ook de optie **[!UICONTROL Delivery summary]** rapport: het toont het aantal adressen in quarantaine in het leveringsdoel, en toont:

* het aantal adressen dat tijdens de afleveringsanalyse in quarantaine wordt geplaatst;
* Het aantal adressen die in quarantaine na de leveringsactie worden geplaatst.

### Niet-leverbare en stuitbare adressen{#non-deliverable-bounces}

De lijst met in quarantaine geplaatste adressen weergeven **voor het gehele platform**, Campagnebeheerders kunnen bladeren naar  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. Deze sectie maakt een lijst van quarantined elementen voor **email**, **SMS** en **Pushmelding** kanalen.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Het aantal quarantaine neemt met de tijd toe. Als de levensduur van een e-mailadres bijvoorbeeld wordt beschouwd als drie jaar en de tabel met ontvangers elk jaar met 50% toeneemt, kan de toename van quarantaine als volgt worden berekend:
>
>Einde van jaar 1: 1&#42;0,33)/(1+0,5)=22%.
>
>Einde van jaar 2: (1,22)&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Bovendien **[!UICONTROL Non-deliverables and bounces]** een ingebouwd rapport, beschikbaar via de **Rapporten** van deze homepage, toont informatie over de adressen in quarantaine, de types van aangetroffen fout, en een mislukkingsonderbreking door domein. U kunt gegevens filteren voor een specifieke levering, of dit rapport aanpassen zoals nodig.

Meer informatie over stuitadressen vindt u in het dialoogvenster [Handleiding voor best practices voor levering](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}.

### Gegarandeerd e-mailadres {#quarantined-recipient}

U kunt de status van het e-mailadres van elke ontvanger opzoeken.

Selecteer hiertoe het ontvangende profiel en klik op de knop **[!UICONTROL Deliveries]** tab. Voor alle leveringen aan die ontvanger, kunt u te weten komen of het ontbroken adres, tijdens analyse in quarantined, enz. was.

Voor elke map kunt u alleen de ontvangers weergeven van wie het e-mailadres in quarantaine staat, met de **[!UICONTROL Quarantined email address]** ingebouwd filter, zoals hieronder:

![](assets/quarantine-filter.png)


## Een in quarantaine geplaatst adres verwijderen {#remove-a-quarantined-address}

Adressen die aan specifieke voorwaarden voldoen, worden automatisch uit de quarantainelijst verwijderd door de **Database opschonen** ingebouwde workflow.

De adressen worden automatisch verwijderd uit de quarantainelijst in de volgende gevallen:

* Adressen in een **[!UICONTROL With errors]** de status wordt na een geslaagde levering uit de quarantainelijst verwijderd .
* Adressen in een **[!UICONTROL With errors]** de status wordt uit de quarantainelijst verwijderd als de laatste zachte stuit meer dan tien dagen geleden heeft plaatsgevonden . Zie voor meer informatie over softerror management [deze sectie](#soft-error-management).
* Adressen in een **[!UICONTROL With errors]** status die met de **[!UICONTROL Mailbox full]** De fout wordt na 30 dagen uit de quarantainelijst verwijderd.

Hun status verandert vervolgens in **[!UICONTROL Valid]**.

>[!CAUTION]
>
>Ontvangers met een adres in een **[!UICONTROL Quarantine]** of **[!UICONTROL Denylisted]** de status wordt nooit verwijderd, zelfs niet als ze een e-mail ontvangen.

U kunt ook handmatig een adres uit de quarantainelijst verwijderen. Als u een adres uit quarantaine wilt verwijderen, kunt u:

* De status wijzigen in **[!UICONTROL Valid]** van de **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** knooppunt.

   ![](assets/tech-quarantine-status.png)

U zou bulkupdates op de quarantainelijst kunnen moeten uitvoeren, bijvoorbeeld in het geval van een ISP stroomonderbreking waarin de e-mails verkeerd als grenzen worden gemerkt omdat zij niet met succes aan hun ontvanger kunnen worden geleverd.

Om dit uit te voeren, creeer een werkschema en voeg een vraag op uw quarantainetabel toe om alle beïnvloede ontvangers uit te filteren zodat zij uit de quarantainelijst kunnen worden verwijderd, en inbegrepen in toekomstige e-mailleveringen van de Campagne.

Hieronder volgen de geadviseerde richtlijnen voor deze vraag:

* **Fouttekst (quarantainetekst)** bevat &quot;Momen_Code10_InvalidRecipient&quot;
* **E-maildomein (@domein)** is gelijk aan domain1.com OR **E-maildomein (@domein)** is gelijk aan domain2.com OR **E-maildomein (@domein)** is gelijk aan domain3.com
* **Status bijwerken (@lastModified)** op of na MM/DD/YYYY HH:MM:SS AM
* **Status bijwerken (@lastModified)** op of vóór MM/DD/YYYY HH:MM:SS PM

Als u de lijst met betrokken ontvangers hebt, voegt u een **[!UICONTROL Update data]** activiteit om hun status in te stellen op **[!UICONTROL Valid]** zodat zij uit de quarantainelijst worden verwijderd door **[!UICONTROL Database cleanup]** workflow. U kunt ze ook gewoon uit de quarantainetabel verwijderen.

