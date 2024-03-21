---
title: Uw e-mails verzenden en controleren
description: Meer informatie over het bereik en de specifieke kenmerken van het verzenden van e-mails met Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 0%

---


# Uw e-mails verzenden en controleren  {#send-and-monitor-emails}

Wanneer de levering wordt gevormd en klaar om worden verzonden, zorg ervoor u de leveringsanalyse in werking hebt gesteld. [Meer informatie](delivery-analysis.md)

Bevestig de levering om de levering van berichten te starten.

Volg de uitvoering van de levering vanaf de **Aflevering** , toegankelijk via de details van deze levering of via de lijst van leveringen.

## Uw e-mailberichten controleren {#email-monitoring}

Controleer de leveringsstatus in het dialoogvenster **Delivery Dashboard** en toegang tot leveringslogboeken en rapporten om berichten te bevestigen werden correct verzonden.

Van het leveringsdashboard, kunt u de verwerkte berichten en de logboeken van de leveringscontrole controleren. U kunt de status van de berichten in de leveringslogboeken ook controleren.

>[!NOTE]
>
>De leveringsstatus wordt niet in real time weergegeven. Meer informatie over E-mailfeedbackservice [in deze sectie](#email-feedback-service).


[Meer informatie over leveringscontrole in Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}

## Campagne MTA {#mta}

De campagne v8 Mail Transfer Agent (MTA) verstrekt een best-in-klasse verzendende infrastructuur die voor optimale leverability, reputatie, productie, rapportering, stuiterende behandeling, IP grafiek en verbinding het plaatsen beheer toestaat.

Deze service is beschikbaar voor alle klanten van Campagne v8 en garandeert schaalbaarheid, een hoge doorvoer van de levering en helpt u sneller e-mailberichten te verzenden. Dit wordt bereikt met nieuwe adaptieve leveringstechnieken die e-mailverzendende montages in real time veranderen gebaseerd op terugkoppelen van de Dienstverleners van Internet.

### Voordelen

Adobe Campaign gebruikt een Agent van de Overdracht van de Post (MTA) die commerciële e-mail MTA van SparkPost genoemd in werking stelt **Momentum**.

Momentum vertegenwoordigt innovatieve, krachtige MTA-technologie, die slimmere stuiterende behandeling en een geautomatiseerde optimaliseringscapaciteit van de leverbaarheid omvat die afzenders helpt optimale inbusleversnelheden te bereiken en te handhaven.

* De MTA maakt een enorme toename van de totale doorvoersnelheid en een significante vermindering van zachte grenzen mogelijk.
* Het gebruikt de nieuwste MTA technologie om u van de optimale productiesnelheden voor uw e-maillevering te voorzien.
* Door zich direct en automatisch aan te passen aan de feedback die het ontvangt, zorgt het er ook voor dat de e-mail nauwkeuriger en intelligenter wordt geleverd met realtime leveringsgegevens.

### Stuitkwalificatie

Voor **synchroon** De berichten van de mislukkingsfout van de levering, MTA bepaalt het stuitertype en de kwalificatie, en stuurt die informatie terug naar Campagne.

MTA kwalificeert de stuit SMTP en verzendt die kwalificatie terug naar Campaign in de vorm van een stuiterende code die aan een de stuiteringsreden en kwalificatie van de Campagne in kaart wordt gebracht.

>[!NOTE]
>
>Momenteel **asynchroon** de grenzen worden gekwalificeerd door het inMail proces door **[!UICONTROL Inbound email]** regels.

Meer informatie over leveringsfouten in [deze sectie](delivery-failures.md).


### Specifieke MX-regels

MX-regels (Mail eXchanger) zijn de regels die de communicatie tussen een verzendende server en een ontvangende server beheren.

MTA heeft zijn eigen MX regels die het toestaan om uw productie door domein aan te passen die op uw eigen historische e-mailreputatie wordt gebaseerd, en op real time terugkoppelen die uit de domeinen komt waar u e-mails verzendt.

### DKIM-ondertekening

De Sleutels van het domein Identified Mail (DKIM) is een authentificatiemethode die wordt gebruikt om vervalste afzenderadressen (algemeen genoemd spoofing) te ontdekken.

In Adobe Campaign wordt DKIM ondertekenen van e-mailverificatie uitgevoerd door de MTA.

Meer informatie over DKIM in de [Handleiding voor beste praktijken bij de levering van Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.

## E-mailfeedbackservice {#email-feedback-service}

Campagne Email Feedback Service (EFS) geeft aan wat de status is van elke e-maillevering die bij Adobe Campaign wordt verzonden.

Wanneer de levering is gestart, is er geen wijziging in de **[!UICONTROL Success]** percentage wanneer het bericht met succes van Campagne aan MTA wordt afgelost. De leveringslogboeken tonen de **[!UICONTROL Taken into account by the service provider]** status voor elk gericht adres.

Wanneer het bericht werkelijk aan de gerichte profielen wordt geleverd en zodra deze informatie in real time van MTA wordt gemeld, tonen de leveringslogboeken **[!UICONTROL Sent]** status voor elk adres dat met succes het bericht ontving. De **[!UICONTROL Success]** het percentage wordt dienovereenkomstig verhoogd bij elke succesvolle levering.

Wanneer hard-bouncing berichten terug van MTA worden gemeld, verandert hun logboekstatus van **[!UICONTROL Taken into account by the service provider]** tot **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Wanneer de zachte die berichten terug van MTA worden gemeld, blijft hun logboekstatus onveranderd (**[!UICONTROL Taken into account by the service provider]**): alleen de [oorzaak van fout](delivery-failures.md#delivery-failure-reasons) is bijgewerkt<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. De **[!UICONTROL Success]** percentage blijft ongewijzigd. De zachte die berichten bewegen worden dan opnieuw geprobeerd door de levering [geldigheidsperiode](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}:

* Als een nieuwe poging is gelukt vóór het einde van de geldigheidsperiode, verandert de berichtstatus in **[!UICONTROL Sent]** en de **[!UICONTROL Success]** het percentage wordt dienovereenkomstig verhoogd.

* Anders verandert de status in **[!UICONTROL Failed]**. De **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->percentage blijft ongewijzigd.

>[!NOTE]
>
>Zie voor meer informatie over harde en zachte golven [deze sectie](delivery-failures.md#delivery-failure-reasons).
>
>Voor meer informatie over pogingen na een tijdelijke mislukking van de levering, zie [deze sectie](delivery-failures.md#retries).

De lijst toont hieronder hoe KPIs en het verzenden van logboekstatussen bij elke stap van het verzendende proces worden bijgewerkt.

| Stap in het verzendende proces | KPI-overzicht | Status van logboeken verzenden |
|--- |--- |--- |
| Bericht wordt met succes van Campagne aan MTA afgelost | **[!UICONTROL Success]** percentage wordt niet weergegeven (begint bij 0%) | Door de dienstverlener in aanmerking genomen |
| Fel-stuiterende berichten worden gemeld terug van MTA | Geen wijziging in **[!UICONTROL Success]** percentage | Mislukt |
| De zachte die berichten bewegen worden gemeld terug van MTA | Geen wijziging in **[!UICONTROL Success]** percentage | Door de dienstverlener in aanmerking genomen |
| Herhalingen van soft-bouncing berichten zijn succesvol | **[!UICONTROL Success]** percentage wordt dienovereenkomstig verhoogd | Verzonden |
| Herhalingen van soft-bouncing berichten mislukken | Geen wijziging in **[!UICONTROL Success]** percentage | Mislukt |
