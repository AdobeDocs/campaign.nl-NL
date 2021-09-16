---
title: Algemene architectuur
description: Meer informatie over campagnearchitectuur en -componenten
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 0%

---

# Algemene architectuur{#general-architecture}

De gebruikelijke Adobe Campaign-implementatie van oplossingen bestaat uit de volgende onderdelen:

* **Persoonlijke clientomgeving**

   Intuïtieve grafische interface waarin gebruikers marketingaanbiedingen kunnen communiceren en volgen, campagnes kunnen maken, alle marketingactiviteiten, -programma&#39;s en -plannen (inclusief e-mails, workflows en bestemmingspagina&#39;s) kunnen beoordelen en beheren, en klantprofielen kunnen maken en beheren en een publiek kunnen creëren.

* **Ontwikkelingsomgeving**

   Server-side software die de marketing campagnes door gekozen communicatie kanalen, met inbegrip van e-mail, SMS, dupberichten, direct mail, Web of sociaal uitvoert, op de regels en de werkschema&#39;s die in het gebruikersinterface worden bepaald.

* **Databasecontainers**

   Op basis van relationele databasetechnologie slaat de Adobe Campaign Cloud-database alle klantgegevens, campagnecomponenten, aanbiedingen en workflows op, evenals de campagneresultaten in databasecontainers van de klant.

## Persoonlijke clientomgeving {#client-env}

De toepassing kan op verschillende manieren worden benaderd: Rich client-, thin client- of API-integratie.

* **Clientconsole**: De hoofdgebruikersinterface van de toepassing is een native toepassing (in Windows) die communiceert met de Adobe Campaign-toepassingsserver met standaard internetprotocollen (SOAP, HTTP, enz.). Adobe Campaign Client Console biedt geweldige gebruiksvriendelijkheid voor productiviteit, gebruikt zeer weinig bandbreedte (door het gebruik van een lokale cache) en is ontworpen voor eenvoudige implementatie. Deze console kan vanuit een internetbrowser worden geïmplementeerd, kan automatisch worden bijgewerkt en vereist geen specifieke netwerkconfiguratie omdat alleen HTTP(S)-verkeer wordt gegenereerd.

   ?? [Meer informatie over Campagne-clientconsole](../start/connect.md).

* **Webtoegang**: delen van de toepassing zijn toegankelijk via een eenvoudige webbrowser met behulp van een HTML-gebruikersinterface, zoals de rapportmodule, de goedkeuringsfasen voor levering, de controle van instanties, enz.

   ?? [Meer informatie over de Toegang van het Web van de Campagne](../start/connect.md).

* **Campagne-API&#39;s**: In bepaalde gevallen, kan het systeem van externe toepassing worden geroepen gebruikend de Diensten APIs van het Web die via het protocol van de ZEEP worden blootgesteld.

   ?? [Meer informatie over campagne-API&#39;s](../dev/api.md).

## Ontwikkelingsomgeving {#dev-env}

Adobe Campaign is één platform met verschillende toepassingen voor het maken van een open en schaalbare architectuur. Het Adobe Campaign-platform is geschreven op een flexibele toepassingslaag en kan eenvoudig worden geconfigureerd om aan uw bedrijfsbehoeften te voldoen. De verdeelde architectuur verzekert lineaire systeemscalability die van duizenden berichten aan miljoenen berichten schrapt.

Sommige modules van de Campagne werken onophoudelijk, terwijl anderen af en toe begonnen zijn om administratieve taken (b.v. om de gegevensbestandverbinding te vormen) uit te voeren of een terugkomende taak (b.v. het consolideren van het volgen informatie) in werking te stellen.

Er zijn drie typen Adobe Campaign-modules:

* **Modules** met meerdere instanties: er wordt één proces voor alle instanties uitgevoerd. Dit geldt voor de volgende modules: web, syslogd, trackinglogd en waakhond.
* **Monoinstantiemodules**: één proces wordt per instantie uitgevoerd. Dit geldt voor de volgende modules: mta, wfserver, inMail, sms en stat.
* **Hulpprogrammamodules**: dit zijn modules die af en toe in werking worden gesteld om af en toe of terugkerende verrichtingen (schoonmaak, config, het downloaden het volgen logboeken, enz.) uit te voeren.

De belangrijkste processen zijn:

**Toepassingsserver**  (extern web)

Dit proces stelt de volledige waaier van de functionaliteit van Adobe Campaign via de APIs van de Diensten van het Web (ZEEP / HTTP + XML) bloot. Bovendien kan het de Web-pagina&#39;s dynamisch produceren die voor op HTML-Gebaseerde toegang (rapporten, de vormen van het Web, enz.) worden gebruikt. Hiertoe bevat dit proces een Apache Tomcat JSP-server. Dit is het proces waarmee de Console verbinding maakt.

**Workflow-engine**  (nlserver wfserver)

Het voert de werkschemaprocessen uit die in de toepassing worden bepaald.

Het behandelt ook periodiek uitgevoerde technische werkschema&#39;s, die omvatten:

* **Tekstspatiëring**: Trackinglogboeken herstellen en consolideren. Het laat u de logboeken van de omleidingsserver terugwinnen en de gezamenlijke indicatoren creëren die door de rapporteringsmodule worden gebruikt.
* **Overbodig verwijderen**: Database reinigen. Wordt gebruikt om oude records leeg te maken en te voorkomen dat de database exponentieel groeit.
* **Facturering**: Automatisch verzenden van een activiteitenverslag voor het platform (databasegrootte, aantal marketingacties, enz.).

**Leveringsserver**  (nlserver-mta)

Adobe Campaign heeft native functionaliteit voor e-mailuitzending. Dit proces functioneert als SMTP agent van de postoverdracht (MTA). Het voert &quot;één-op-één&quot;verpersoonlijking van berichten uit en behandelt hun fysieke levering. Het werkt met leveringstaken en verwerkt automatische pogingen. Wanneer reeksspatiëring is ingeschakeld, worden de URL&#39;s automatisch vervangen, zodat ze naar de omleidingsserver verwijzen.

Dit proces kan de aanpassing en het automatische verzenden naar een derderouter voor SMS, fax en directe post behandelen.

**Redirection server**  (nlserver webmdl)

Voor e-mail, behandelt Adobe Campaign automatisch open en klikt het volgen (transactie het volgen op het niveau van de Website is een verdere mogelijkheid). Hiertoe worden de URL&#39;s die in de e-mailberichten zijn opgenomen, herschreven zodat ze naar deze module verwijzen. Deze module registreert het doorgeven van de internetgebruiker voordat deze naar de vereiste URL wordt doorgestuurd.

Om de hoogste beschikbaarheid te garanderen, is dit proces volledig onafhankelijk van het gegevensbestand: de andere serverprocessen communiceren ermee met behulp van alleen SOAP-aanroepen (HTTP, HTTP(S) en XML). Technisch, wordt deze functionaliteit uitgevoerd in een uitbreidingsmodule van een server van HTTP (ISAPI uitbreiding in IIS, of een module van DSO Apache, enz.) en is alleen beschikbaar in Windows.

Er zijn ook andere meer technische processen beschikbaar:

**Bounce-e-mailberichten**  beheren (nlserver inMail)

Dit proces laat u toe om e-mail van brievenbussen automatisch op te nemen die worden gevormd om teruggestuurde berichten te ontvangen die in het geval van leveringsmislukking zijn teruggekeerd. Deze berichten worden dan op regel-gebaseerde verwerking ondergaan om de redenen voor niet levering (onbekende ontvanger, quota overschreden, etc.) te bepalen en de leveringsstatus in de database bij te werken.

Al deze verrichtingen zijn volledig automatisch en vooraf gevormd.

**Leveringsstatus**  van SMS (nlserver sms)

Dit proces pollt de router van SMS om vooruitgangsstatus te verzamelen en het gegevensbestand bij te werken.

**Logberichten**  schrijven (nlserver-syslogd)

Dit technische proces vangt logboekberichten en sporen die door de andere processen worden geproduceerd en schrijft hen aan de harde schijf. Dit maakt ruime informatie beschikbaar voor diagnose in het geval van problemen.

**Logboeken**  voor het bijhouden van gegevens schrijven (logd voor reeksspatiëring)

Dit proces bewaart aan schijf de volgende logboeken die door het omleidingsproces worden geproduceerd.

**Inbound-gebeurtenissen**  schrijven (nlserver-interactie)

Dit proces verzekert de opname aan de schijf van binnenkomende gebeurtenissen, binnen het kader van Interactie.

**Controlemodules**  (nlserver watchdog)

Dit technische proces fungeert als een primair proces dat de anderen voortbrengt. Het bewaakt ze ook en start ze automatisch opnieuw in geval van incidenten, zodat het systeem maximaal uptime kan blijven.

**Statistische server**  (nlserver stat)

Dit proces handhaaft statistieken over het aantal verbindingen, de berichten die voor elke postserver worden verzonden die berichten worden verzonden naar, evenals hun beperkingen (hoogste aantal gelijktijdige verbindingen, berichten per uur/en of verbinding). Het laat u ook verscheidene instanties of machines federeren als zij de zelfde openbare IP adressen delen.

## Databasecontainers {#db-containers}

De Adobe Campaign Cloud-database is gebaseerd op [!DNL Snowflake], die de functionele gegevens (profielen, abonnementen, inhoud, enz.), de technische gegevens (taken en logbestanden voor levering, logbestanden bijhouden, enz.) bevat en de werkgegevens (aankopen, leads) voor de oplossing, en alle Adobe Campaign-componenten communiceren met de database om hun specifieke taken uit te voeren.

Klanten kunnen Adobe Campaign implementeren met behulp van de vooraf gedefinieerde database en schema&#39;s en indien nodig kan deze vooraf gedefinieerde omgeving worden uitgebreid. Alle gegevens binnen de datamarkt worden betreden door Adobe Campaign via SQL vraag. Adobe Campaign biedt ook een volledige aanvulling op de ETL-gereedschappen (Extract Transform and Load) voor het importeren en exporteren van gegevens naar en vanuit het systeem.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Met **Beheerde Cloud Services van de Campagne**, zijn uw milieu en aanvankelijke configuratie geplaatst door Adobe, volgens de termijnen van uw vergunningsovereenkomst. U mag geïnstalleerde ingebouwde pakketten, ingebouwde schema&#39;s of rapporten niet wijzigen.
>
>Als u een toe:voegen-op van de Campagne of een specifiek vermogen moet gebruiken dat niet voor u is provisioned, moet u **Adobe de Zorg van de Klant** contacteren.