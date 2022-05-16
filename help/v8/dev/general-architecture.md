---
title: Algemene architectuur
description: Meer informatie over campagnearchitectuur en -componenten
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 0%

---

# Algemene architectuur{#general-architecture}

De gebruikelijke Adobe Campaign-implementatie van oplossingen bestaat uit de volgende onderdelen:

* **Persoonlijke clientomgeving**

   Intuïtieve grafische interface waarin gebruikers marketingaanbiedingen kunnen communiceren en volgen, campagnes kunnen maken, alle marketingactiviteiten, -programma&#39;s en -plannen (inclusief e-mails, workflows en bestemmingspagina&#39;s) kunnen beoordelen en beheren, en klantprofielen kunnen maken en beheren en een publiek kunnen creëren.

* **Ontwikkelingsomgeving**

   Server-side software die de marketing campagnes door gekozen communicatie kanalen, met inbegrip van e-mail, SMS, dupberichten, direct mail, Web of sociaal uitvoert, op de regels en de werkschema&#39;s die in het gebruikersinterface worden bepaald.

* **Databasecontainers**

   Op basis van relationele databasetechnologie slaat de Adobe Campaign Cloud-database alle informatie, campagnecomponenten, aanbiedingen, workflows en campagneresultaten op in databasecontainers.

## Persoonlijke clientomgeving {#client-env}

De toepassing kan op verschillende manieren worden benaderd: Rich client, thin client of API-integratie.

![](../assets/do-not-localize/glass.png) [Meer informatie over de presentatielaag voor campagnes](../start/ac-components.md).

## Ontwikkelingsomgeving {#dev-env}

Adobe Campaign is één platform met verschillende toepassingen voor het maken van een open en schaalbare architectuur. Het Adobe Campaign-platform is geschreven op een flexibele toepassingslaag en kan eenvoudig worden geconfigureerd om aan uw bedrijfsbehoeften te voldoen. De verdeelde architectuur verzekert lineaire systeemscalability die van duizenden berichten aan miljoenen berichten schrapt.

Sommige modules van de Campagne werken onophoudelijk, terwijl anderen af en toe begonnen zijn om administratieve taken (b.v. om de gegevensbestandverbinding te vormen) uit te voeren of een terugkomende taak (b.v. het consolideren van het volgen informatie) in werking te stellen.

Er zijn drie typen Adobe Campaign-modules:

* **Modules met meerdere instanties**: er wordt één proces voor alle instanties uitgevoerd. Dit geldt voor de volgende modules: web, syslogd, trackinglogd en waakhond.
* **Monoinstantiemodules**: één proces wordt per instantie uitgevoerd. Dit geldt voor de volgende modules: mta, wfserver, inMail, sms en stat.
* **Hulpmodules**: dit zijn modules die af en toe in werking worden gesteld om af en toe of terugkerende verrichtingen (schoonmaak, config, het downloaden het volgen logboeken, enz.) uit te voeren.

De belangrijkste processen zijn:

**Toepassingsserver** (nlserver-web)

Dit proces stelt de volledige waaier van de functionaliteit van Adobe Campaign via de APIs van de Diensten van het Web (ZEEP / HTTP + XML) bloot. Bovendien kan het de Web-pagina&#39;s dynamisch produceren die voor op HTML-Gebaseerde toegang (rapporten, de vormen van het Web, enz.) worden gebruikt. Hiertoe bevat dit proces een Apache Tomcat JSP-server. Dit is het proces waarmee de Console verbinding maakt.

**Workflow-engine** (nlserver wfserver)

Het voert de werkschemaprocessen uit die in de toepassing worden bepaald.

Het behandelt ook periodiek uitgevoerde technische werkschema&#39;s, die omvatten:

* **Tekstspatiëring**: Herstelt en consolideert het volgen logboeken, zodat u de logboeken van de omleidingsserver kunt terugwinnen en de gezamenlijke indicatoren creëren die door de rapportmodule worden gebruikt.
* **Overbodig verwijderen**: Hiermee wist u de database, wist u oude records en voorkomt u dat de database exponentieel toeneemt.
* **Facturering**: Hiermee wordt een activiteitenrapport voor het platform verzonden (grootte van de database, aantal marketingacties, enz.).

**Leveringsserver** (nlserver mta)

Adobe Campaign heeft native functionaliteit voor e-mailuitzending. Dit proces functioneert als SMTP agent van de postoverdracht (MTA). Het voert &quot;één-op-één&quot;verpersoonlijking van berichten uit en behandelt hun fysieke levering. Het werkt met leveringstaken en verwerkt automatische pogingen. Wanneer reeksspatiëring is ingeschakeld, worden de URL&#39;s automatisch vervangen, zodat ze naar de omleidingsserver verwijzen.

Dit proces kan de aanpassing en het automatische verzenden naar een derderouter voor SMS, fax en directe post behandelen.

**Redirection-server** (nlserver-webmdl)

Voor e-mail, behandelt Adobe Campaign automatisch open en klikt het volgen (transactie het volgen op het niveau van de Website is een verdere mogelijkheid). Hiertoe worden de URL&#39;s die in de e-mailberichten zijn opgenomen, herschreven zodat ze naar deze module verwijzen. Deze module registreert het doorgeven van de internetgebruiker voordat deze naar de vereiste URL wordt doorgestuurd.

Om de hoogste beschikbaarheid te garanderen, is dit proces volledig onafhankelijk van het gegevensbestand: de andere serverprocessen communiceren ermee met behulp van alleen SOAP-aanroepen (HTTP, HTTP(S) en XML). Technisch, wordt deze functionaliteit uitgevoerd in een uitbreidingsmodule van een server van HTTP (ISAPI uitbreiding in IIS, of een module van DSO Apache, enz.) en is alleen beschikbaar in Windows.

Er zijn ook andere meer technische processen beschikbaar:

**Bounce-e-mails beheren** (nlserver inMail)

Dit proces laat u toe om e-mail van brievenbussen automatisch op te nemen die worden gevormd om teruggestuurde berichten te ontvangen die in het geval van leveringsmislukking zijn teruggekeerd. Deze berichten worden dan op regel-gebaseerde verwerking ondergaan om de redenen voor niet levering (onbekende ontvanger, quota overschreden, etc.) te bepalen en de leveringsstatus in de database bij te werken.

Al deze verrichtingen zijn volledig automatisch en vooraf gevormd.

**Status van SMS-verzending** (nlserver sms)

Dit proces pollt de router van SMS om vooruitgangsstatus te verzamelen en het gegevensbestand bij te werken.

**Logboekberichten schrijven** (nlserver-syslogd)

Dit technische proces vangt logboekberichten en sporen die door de andere processen worden geproduceerd en schrijft hen aan de harde schijf. Dit maakt ruime informatie beschikbaar voor diagnose in het geval van problemen.

**Logbestanden voor bijhouden schrijven** (nlserver trackinglogd)

Dit proces bewaart aan schijf de volgende logboeken die door het omleidingsproces worden geproduceerd.

**Inkomende gebeurtenissen schrijven** (Nlserver-interactief)

Dit proces verzekert de opname aan de schijf van binnenkomende gebeurtenissen, binnen het kader van Interactie.

**Toezichtmodules** (nlserver waakhond)

Dit technische proces fungeert als een primair proces dat de anderen voortbrengt. Het bewaakt ze ook en start ze automatisch opnieuw in geval van incidenten, zodat het systeem maximaal uptime kan blijven.

**Statistische server** (nlserver-status)

Dit proces handhaaft statistieken over het aantal verbindingen, de berichten die voor elke postserver worden verzonden die berichten worden verzonden naar, evenals hun beperkingen (hoogste aantal gelijktijdige verbindingen, berichten per uur/en of verbinding). Het laat u ook verscheidene instanties of machines federeren als zij de zelfde openbare IP adressen delen.

## Databasecontainers {#db-containers}

De Adobe Campaign Cloud-database is afhankelijk van [!DNL Snowflake] die de functionele gegevens (profielen, abonnementen, inhoud, enz.), de technische gegevens (leverings- en logboekgegevens, trackinglogboeken enz.) bevat en de werkgegevens (aankopen, leads) voor de oplossing, en alle Adobe Campaign-componenten communiceren met de database om hun specifieke taken uit te voeren.

U kunt Adobe Campaign implementeren met behulp van de vooraf gedefinieerde database en schema&#39;s en indien nodig kan deze vooraf gedefinieerde omgeving worden uitgebreid. Alle gegevens binnen de datamarkt worden betreden door Adobe Campaign via SQL vraag. Adobe Campaign biedt ook een volledige aanvulling op de ETL-gereedschappen (Extract Transform and Load) voor het importeren en exporteren van gegevens naar en vanuit het systeem.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Met **Door campagne beheerde Cloud Services**, uw omgeving en initiële configuratie zijn ingesteld door Adobe, volgens de bepalingen van uw licentieovereenkomst. U mag geïnstalleerde ingebouwde pakketten, ingebouwde schema&#39;s of rapporten niet wijzigen.
>
>Als u een toe:voegen-op van de Campagne of een specifiek vermogen moet gebruiken dat niet voor u is provisioned, moet u contact opnemen **Adobe Klantenservice**.