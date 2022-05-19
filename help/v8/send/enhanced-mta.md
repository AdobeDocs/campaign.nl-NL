---
title: Informatie over de verbeterde MTA in Adobe Campaign
description: Meer informatie over de reikwijdte en de specifieke kenmerken van het verzenden van e-mails met de Adobe Campaign Enhanced MTA
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 3%

---

# Informatie over de verbeterde MTA {#sending-with-enhanced-mta}

De **Adobe Campaign Enhanced MTA** (De Agent van de Overdracht van de Post) verstrekt een bevorderde verzendende infrastructuur die voor optimale levering, reputatie, productie, rapportering, stuitbehandeling, IP oprijplaat en verbinding plaatsend beheer toestaat.

Het is geïmplementeerd voor alle klanten van Campagne v8 om de schaalbaarheid te verbeteren, de doorvoer van de levering te verhogen en meer e-mails sneller te verzenden. Dit wordt bereikt met nieuwe adaptieve leveringstechnieken die e-mailverzendende montages in real time veranderen gebaseerd op terugkoppelen van de Dienstverleners van Internet.

## Gebruik en voordelen

**Wat is de verbeterde MTA?**

Adobe Campaign gebruikt een Agent van de Overdracht van de Post (MTA) die commerciële e-mail MTA van SparkPost genoemd in werking stelt **Momentum**.

Momentum vertegenwoordigt innovatieve, krachtige MTA-technologie, die slimmere stuiterende behandeling en een geautomatiseerde optimaliseringscapaciteit van de leverbaarheid omvat die afzenders helpt optimale inbusleversnelheden te bereiken en te handhaven.

**Wat zijn de voordelen?**

* De verbeterde MTA maakt een enorme toename van de totale productiesnelheid en een significante vermindering van zachte grenzen mogelijk.
* Het gebruikt de nieuwste MTA technologie om u van de optimale productiesnelheden voor uw e-maillevering te voorzien.
* Door zich direct en automatisch aan te passen aan de feedback die het ontvangt, zorgt het er ook voor dat de e-mail nauwkeuriger en intelligenter wordt geleverd met realtime leveringsgegevens.

## Verbeterde specifieke kenmerken van MTA {#enhanced-mta-impacts}

### Stuitkwalificatie

Voor **synchroon** De berichten van de de mislukkingsfout van de levering, Verbeterde MTA bepaalt het stuittype en de kwalificatie, en stuurt die informatie terug naar Campagne.

Verbeterde MTA kwalificeert de stuit SMTP en verzendt die kwalificatie terug naar Campagne in de vorm van een stuitercode die aan een de stuiteringsreden en kwalificatie van de Campagne in kaart wordt gebracht.

>[!NOTE]
>
>Momenteel **asynchroon** De grenzen worden niet gekwalificeerd door Verbeterde MTA maar door het proces inMail door **[!UICONTROL Inbound email]** regels. Raadpleeg voor meer informatie hierover [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

Meer informatie over leveringsfouten in [deze sectie](delivery-failures.md).

### Geldigheidsperiode

De geldigheidsperiode die in uw campagneleveringen wordt ingesteld, wordt alleen door de verbeterde MTA gebruikt als deze is ingesteld op **3,5 dagen of minder**. Als u in Campagne een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.

Bijvoorbeeld, als de geldigheidsperiode aan de standaardwaarde van 5 dagen in Campagne wordt geplaatst, zullen de zachte-stuiterende berichten in de Verbeterde MTA hertry rij gaan en slechts 3.5 dagen worden opnieuw geprobeerd vanaf toen dat bericht Verbeterde MTA bereikte. In dat geval wordt de waarde die is ingesteld in Campaign niet gebruikt.

Wanneer een bericht gedurende 3,5 dagen in de wachtrij van de Enhanced MTA heeft gestaan en niet is geleverd, treedt er een time-out op en zal de status van het bericht worden bijgewerkt van **[!UICONTROL Sent]** naar **[!UICONTROL Failed]** in de leveringslogboeken.

Voor meer informatie over de geldigheidsperiode raadpleegt u de [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}.

### Hernieuwde pogingen

De zachte stuitpogingen en de tijdsduur tussen hen worden bepaald door Verbeterde MTA gebaseerd op het type en de strengheid van de stuiteringsreacties die van het e-maildomein van het bericht terugkomen.

>[!NOTE]
>
>De retry-instellingen in de leveringseigenschappen worden niet gebruikt door Campagne.

Meer informatie over nieuwe pogingen in [deze sectie](delivery-failures.md#retries).

### Specifieke MX-regels

MX-regels (Mail eXchanger) zijn de regels die de communicatie tussen een verzendende server en een ontvangende server beheren.

Verbeterde MTA heeft zijn eigen MX regels die het toestaan om uw productie door domein aan te passen die op uw eigen historische e-mailreputatie wordt gebaseerd, en op real time terugkoppelen die uit de domeinen komt waar u e-mails verzendt.

### DKIM-ondertekening

De Sleutels van het domein Identified Mail (DKIM) is een authentificatiemethode die wordt gebruikt om vervalste afzenderadressen (algemeen genoemd spoofing) te ontdekken.

In Adobe Campaign wordt DKIM ondertekenen van e-mailverificatie uitgevoerd door de Enhanced MTA.

Meer informatie over DKIM in de [Adobe Handleiding voor beste praktijken voor aflevering](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target=&quot;_blank&quot;}.

## E-mailfeedbackservice {#email-feedback-service}

Met de e-mailfeedbackservice (EFS) wordt de status van elke e-mail correct gerapporteerd, omdat feedback rechtstreeks wordt vastgelegd via de Enhanced MTA (Message Transfer Agent).

Wanneer de levering is gestart, is er geen wijziging in de **[!UICONTROL Success]** percentage wanneer het bericht met succes van Campagne aan Verbeterde MTA wordt afgelost.

De leveringslogboeken tonen de **[!UICONTROL Taken into account by the service provider]** status voor elk gericht adres.

Wanneer het bericht werkelijk aan de gerichte profielen wordt geleverd en zodra deze informatie in echt - tijd van Verbeterde MTA wordt gemeld, tonen de leveringslogboeken **[!UICONTROL Sent]** status voor elk adres dat met succes het bericht ontving. De **[!UICONTROL Success]** het percentage wordt dienovereenkomstig verhoogd bij elke succesvolle levering.

Wanneer hard-bouncing berichten terug van Verbeterde MTA worden gemeld, verandert hun logboekstatus van **[!UICONTROL Taken into account by the service provider]** tot **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Wanneer de zachte die berichten terug van Verbeterde MTA worden gemeld, blijft hun logboekstatus onveranderd (**[!UICONTROL Taken into account by the service provider]**): alleen [oorzaak van fout](delivery-failures.md#delivery-failure-reasons) is bijgewerkt<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. De **[!UICONTROL Success]** percentage blijft ongewijzigd. De zachte die berichten bewegen worden dan opnieuw geprobeerd door de levering [geldigheidsperiode](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

* Als een nieuwe poging is gelukt vóór het einde van de geldigheidsperiode, verandert de berichtstatus in **[!UICONTROL Sent]** en de **[!UICONTROL Success]** het percentage wordt dienovereenkomstig verhoogd.

* Anders verandert de status in **[!UICONTROL Failed]**. De **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->percentage blijft ongewijzigd.

>[!NOTE]
>
>Zie voor meer informatie over harde en zachte golven [deze sectie](delivery-failures.md#delivery-failure-reasons).
>
>Voor meer informatie over pogingen na een tijdelijke mislukking van de levering, zie [deze sectie](delivery-failures.md#retries).

De lijst toont hieronder hoe KPIs en het verzenden logboekstatussen bij elke stap van het verzendende proces met het vermogen EFS worden bijgewerkt.

| Stap in het verzendende proces | KPI-overzicht | Status van logboeken verzenden |
|--- |--- |--- |
| Het bericht wordt met succes afgelost van Campagne aan Verbeterde MTA | **[!UICONTROL Success]** percentage wordt niet weergegeven (begint bij 0%) | Door de dienstverlener in aanmerking genomen |
| Fel-stuiterende berichten worden gemeld terug van Verbeterde MTA | Geen wijziging in **[!UICONTROL Success]** percentage | Mislukt |
| De zachte die berichten bewegen worden gemeld terug van Verbeterde MTA | Geen wijziging in **[!UICONTROL Success]** percentage | Door de dienstverlener in aanmerking genomen |
| Opnieuw proberen van zachte berichten is geslaagd | **[!UICONTROL Success]** percentage dienovereenkomstig verhoogd | Verzonden |
| Opnieuw proberen van zachte berichten mislukt | Geen wijziging in **[!UICONTROL Success]** percentage | Mislukt |
