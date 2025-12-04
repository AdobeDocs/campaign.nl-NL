---
title: Uw e-mails verzenden en controleren
description: Meer informatie over het bereik en de specifieke kenmerken van het verzenden van e-mails met Adobe Campaign
feature: Email
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: c7f139dd7f139ba421eb034f4d8911671b3b3332
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 0%

---


# Uw e-mails verzenden en controleren  {#send-and-monitor-emails}

Wanneer de levering wordt gevormd en klaar om worden verzonden, zorg ervoor u de leveringsanalyse in werking hebt gesteld. [Meer informatie](delivery-analysis.md)

Bevestig de levering om de levering van berichten te starten.

Spoor de uitvoering van de levering van het **lusje van de Levering**, dat via het detail van deze levering of via de lijst van leveringen toegankelijk is.

## Uw e-mailberichten controleren {#email-monitoring}

Zodra verzonden, controleer uw leveringsstatus in het **dashboard van de Levering** en de logboeken van de toegangslevering en rapporten om berichten te bevestigen werden correct verzonden.

Van het leveringsdashboard, kunt u de verwerkte berichten en de logboeken van de leveringscontrole controleren. U kunt de status van de berichten in de leveringslogboeken ook controleren.

Leer meer over [ leveringsstatussen ](delivery-statuses.md).

>[!NOTE]
>
>De leveringsstatus wordt niet in real time weergegeven. Leer meer over de Dienst van de Terugkoppeling E-mail [ in deze sectie ](#email-feedback-service).

## Campagne MTA {#mta}

De campagne v8 Mail Transfer Agent (MTA) verstrekt een best-in-klasse verzendende infrastructuur die voor optimale leverability, reputatie, productie, rapportering, stuiterende behandeling, IP grafiek en verbinding het plaatsen beheer toestaat.

Deze service is beschikbaar voor alle klanten van Campagne v8 en garandeert schaalbaarheid, een hoge doorvoer van de levering en helpt u sneller e-mailberichten te verzenden. Dit wordt bereikt met nieuwe adaptieve leveringstechnieken die e-mailverzendende montages in real time veranderen gebaseerd op terugkoppelen van de Dienstverleners van Internet.

### Voordelen

Adobe Campaign gebruikt een Agent van de Overdracht van de Post (MTA) die commerciële e-mail MTA van SparkPost genoemd **Momentum** in werking stelt.

Momentum vertegenwoordigt innovatieve, krachtige MTA-technologie, die slimmere stuiterende behandeling en een geautomatiseerde optimaliseringscapaciteit van de leverbaarheid omvat die afzenders helpt optimale inbusleversnelheden te bereiken en te handhaven.

* De MTA maakt een enorme toename van de totale doorvoersnelheid en een significante vermindering van zachte grenzen mogelijk.
* Het gebruikt de nieuwste MTA technologie om u van de optimale productiesnelheden voor uw e-maillevering te voorzien.
* Door zich direct en automatisch aan te passen aan de feedback die het ontvangt, zorgt het er ook voor dat de e-mail nauwkeuriger en intelligenter wordt geleverd met realtime leveringsgegevens.

### Stuitkwalificatie

Voor **synchrone** berichten van de mislukkingsfout van de levering, bepaalt MTA het stuittype en de kwalificatie, en stuurt terug die informatie naar Campagne.

MTA kwalificeert de stuit SMTP en verzendt die kwalificatie terug naar Campaign in de vorm van een stuiterende code die aan een de stuiteringsreden en kwalificatie van de Campagne in kaart wordt gebracht.

>[!NOTE]
>
>Momenteel **asynchrone** grenzen worden gekwalificeerd door het proces InMail door de **[!UICONTROL Inbound email]** regels.

Leer meer op leveringsmislukkingen in [ deze sectie ](delivery-failures.md).


### Specifieke MX-regels

MX-regels (Mail eXchanger) zijn de regels die de communicatie tussen een verzendende server en een ontvangende server beheren.

MTA heeft zijn eigen MX regels die het toestaan om uw productie door domein aan te passen die op uw eigen historische e-mailreputatie wordt gebaseerd, en op real time terugkoppelen die uit de domeinen komt waar u e-mails verzendt.

### DKIM-ondertekening

Domain Keys Identified Mail (DKIM) is een verificatiemethode waarmee vervalste afzenderadressen (vaak spoofing genoemd) worden gedetecteerd.

In Adobe Campaign wordt de ondertekening van DKIM-e-mailverificatie uitgevoerd door de MTA.

Leer meer op DKIM in de [ Gids van de Beste praktijken van de Levering van Adobe ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.

## E-mailfeedbackservice {#email-feedback-service}

Campagne Email Feedback Service (EFS) geeft aan wat de status is van elke e-maillevering die bij Adobe Campaign wordt verzonden.

Zodra de levering is begonnen, is er geen verandering in het **[!UICONTROL Success]** percentage wanneer het bericht met succes van Campagne aan MTA wordt afgelost. In de leveringslogboeken wordt de status **[!UICONTROL Taken into account by the service provider]** voor elk doeladres weergegeven.

Wanneer het bericht werkelijk aan de gerichte profielen wordt geleverd en zodra deze informatie in echt - tijd van MTA wordt gemeld, tonen de leveringslogboeken de **[!UICONTROL Sent]** status voor elk adres dat met succes het bericht ontving. Het percentage **[!UICONTROL Success]** wordt dienovereenkomstig verhoogd bij elke succesvolle levering.

Wanneer hard-bouncing berichten van MTA worden gemeld, verandert hun logboekstatus van **[!UICONTROL Taken into account by the service provider]** in **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Wanneer de zachte-stuiterende berichten terug van MTA worden gemeld, blijft hun logboekstatus onveranderd (**[!UICONTROL Taken into account by the service provider]**): slechts wordt de [ foutenreden ](delivery-failures.md#delivery-failure-reasons) bijgewerkt <!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. Het percentage **[!UICONTROL Success]** blijft ongewijzigd. De soft-bouncing berichten worden dan opnieuw geprobeerd door de levering [ geldigheidsperiode ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/communication-channels){target="_blank"}:

* Als het opnieuw proberen is gelukt vóór het einde van de geldigheidsperiode, verandert de berichtstatus in **[!UICONTROL Sent]** en wordt het **[!UICONTROL Success]** percentage dienovereenkomstig verhoogd.

* Anders verandert de status in **[!UICONTROL Failed]** . Het **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** --> percentage blijft onveranderd.

>[!NOTE]
>
>Voor meer op harde en zachte grenzen, zie [ deze sectie ](delivery-failures.md#delivery-failure-reasons).
>
>Voor meer op herpogingen na een tijdelijke mislukking van de levering, zie [ deze sectie ](delivery-failures.md#retries).

De lijst toont hieronder hoe KPIs en het verzenden van logboekstatussen bij elke stap van het verzendende proces worden bijgewerkt.

| Stap in het verzendende proces | KPI-overzicht | Status van logboeken verzenden |
|--- |--- |--- |
| Bericht wordt met succes van Campagne aan MTA afgelost | **[!UICONTROL Success]** percentage wordt niet weergegeven (begint bij 0%) | Door de dienstverlener in aanmerking genomen |
| Fel-stuiterende berichten worden gemeld terug van MTA | Geen wijziging in **[!UICONTROL Success]** percentage | Mislukt |
| De zachte die berichten bewegen worden gemeld terug van MTA | Geen wijziging in **[!UICONTROL Success]** percentage | Door de dienstverlener in aanmerking genomen |
| Herhalingen van soft-bouncing berichten zijn succesvol | **[!UICONTROL Success]** percentage wordt dienovereenkomstig verhoogd | Verzonden |
| Herhalingen van soft-bouncing berichten mislukken | Geen wijziging in **[!UICONTROL Success]** percentage | Mislukt |
