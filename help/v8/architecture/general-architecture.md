---
title: Algemene architectuur
description: Meer informatie over Adobe Campaign-architectuur en -onderdelen. Meer informatie over het personaliseren van uw Client Console en omgeving.
feature: Architecture, Deployment
role: Admin, Developer
level: Beginner
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 1%

---

# Algemene architectuur{#general-architecture}

De gebruikelijke Adobe Campaign-implementatie van oplossingen bestaat uit de volgende onderdelen:

* **Gepersonaliseerde Milieu van de Cliënt**

  Intuïtieve grafische interface waarin gebruikers marketingaanbiedingen kunnen communiceren en volgen, campagnes kunnen maken, alle marketingactiviteiten, -programma&#39;s en -plannen (inclusief e-mails, workflows en bestemmingspagina&#39;s) kunnen beoordelen en beheren, en klantprofielen kunnen maken en beheren en een publiek kunnen creëren.

* **Milieu van de Ontwikkeling**

  Server-side software die de marketing campagnes door gekozen communicatie kanalen, met inbegrip van e-mail, SMS, dupberichten, direct mail, Web of sociaal uitvoert, op de regels en de werkschema&#39;s die in het gebruikersinterface worden bepaald.

* **Containers van het Gegevensbestand**

  Op basis van relationele databasetechnologie slaat de Adobe Campaign Cloud-database alle informatie, campagnecomponenten, aanbiedingen, workflows en campagneresultaten op in databasecontainers.

## Persoonlijke clientomgeving {#client-env}

De toepassing kan op verschillende manieren worden benaderd: de gebruikersinterface van het Web, de cliëntconsole (rijke cliënt), Webtoegang (dunne cliënt), of API integratie.

[ Leer meer over het gebruikersinterface van de Campagne ](../start/campaign-ui.md).

## Ontwikkelingsomgeving {#dev-env}

Adobe Campaign is één platform met verschillende toepassingen voor het maken van een open en schaalbare architectuur. Het Adobe Campaign-platform is geschreven op een flexibele toepassingslaag en kan eenvoudig worden geconfigureerd om aan uw bedrijfsbehoeften te voldoen. De verdeelde architectuur verzekert lineaire systeemscalability die van duizenden berichten aan miljoenen berichten schrapt.

Sommige modules van de Campagne werken onophoudelijk, terwijl anderen af en toe begonnen zijn om administratieve taken (b.v. om de gegevensbestandverbinding te vormen) uit te voeren of een terugkomende taak (b.v. het consolideren van het volgen informatie) in werking te stellen.

Er zijn drie typen Adobe Campaign-modules:

* **Multiinstance modules**: één enkel proces wordt in werking gesteld voor alle instanties. Dit geldt voor de volgende modules: web, syslogd, trackinglogd en waakhond.
* **Mono-instance modules**: één proces wordt in werking gesteld per geval. Dit geldt voor de volgende modules: mta, wfserver, inMail, sms en stat.
* **modules van het Nut**: dit zijn modules die nu en dan in werking worden gesteld om occasionele of terugkerende verrichtingen (schoonmaak, config, het downloaden van volgende logboeken, enz.) uit te voeren.

De belangrijkste processen zijn:

* **de server van de Toepassing** (nlserverWeb) - Dit proces stelt de volledige waaier van de functionaliteit van Adobe Campaign via de Diensten APIs van het Web (SOAP / HTTP + XML) bloot. Bovendien kan het de Web-pagina&#39;s dynamisch produceren die voor op HTML-Gebaseerde toegang (rapporten, de vormen van het Web, enz.) worden gebruikt. Hiertoe bevat dit proces een Apache Tomcat JSP-server. Dit is het proces waarmee de Console verbinding maakt.

* **motor van het Werkschema** (nlserver wfserver) - Dit proces voert de werkschemaprocessen uit die in de toepassing worden bepaald. Het behandelt ook periodiek uitgevoerde technische werkschema&#39;s, die omvatten:

   * **het Volgen**: Herstelt en consolideert het volgen logboeken, zodat u de logboeken van de redirection server kunt terugwinnen en de gezamenlijke indicatoren creëren die door de rapporteringsmodule worden gebruikt.
   * **Schoonmaakbeurt**: Schoont het gegevensbestand, en koopt oude verslagen en vermijdt exponentieel het gegevensbestand groeien.
   * **Facturering**: verzendt een activiteitenrapport voor het platform (grootte van het gegevensbestand, aantal marketing acties, enz.).

* **de Server van de Levering** (nlserver mta) - Adobe Campaign heeft inheemse functionaliteit van de e-mailuitzending. Dit proces functioneert als SMTP agent van de postoverdracht (MTA). Het voert &quot;één-op-één&quot;verpersoonlijking van berichten uit en behandelt hun fysieke levering. Het werkt met leveringstaken en handelt automatische pogingen af. Wanneer reeksspatiëring is ingeschakeld, worden de URL&#39;s automatisch vervangen, zodat ze naar de omleidingsserver verwijzen. Dit proces kan de aanpassing en het automatische verzenden naar een derderouter voor SMS, fax en directe post behandelen.

* **Redirection server** (nlserver webmdl) - voor e-mail, behandelt Adobe Campaign automatisch open en klikt het volgen (transactie het volgen op het niveau van de Website is een verdere mogelijkheid). Hiertoe worden de URL&#39;s die in de e-mailberichten zijn opgenomen, herschreven zodat ze naar deze module verwijzen. Deze module registreert het doorgeven van de internetgebruiker voordat deze naar de vereiste URL wordt doorgestuurd.

  Om de hoogste beschikbaarheid te garanderen, is dit proces volledig onafhankelijk van de database: de andere serverprocessen communiceren ermee met alleen SOAP-aanroepen (HTTP, HTTP(S) en XML). Technisch gezien, wordt deze functionaliteit uitgevoerd in een uitbreidingsmodule van een server van HTTP (ISAPI uitbreiding in IIS, of een module van DSO Apache, enz.) en is beschikbaar in slechts Vensters.

Er zijn ook andere meer technische processen beschikbaar:

* **het Leiden stuiteren e-mails** (nlserver inMail) - Dit proces laat u toe om e-mail van brievenbussen automatisch op te nemen die worden gevormd om teruggestuurde berichten te ontvangen die in het geval van leveringsmislukking zijn teruggekeerd. Deze berichten ondergaan dan regel-gebaseerde verwerking om de redenen voor niet levering (onbekende ontvanger, quota overschreden, enz.) te bepalen en de leveringsstatus in het gegevensbestand bij te werken. Al deze verrichtingen zijn volledig automatisch en vooraf gevormd.

* **de leveringsstatus van SMS** (nlserver sms) - Dit proces pollt de router van SMS om vooruitgangsstatus te verzamelen en het gegevensbestand bij te werken.

* **het Schrijven van logboekberichten** (nlserver syslogd) - Dit technische proces vangt logboekberichten en sporen die door de andere processen worden geproduceerd en schrijft hen aan de harde schijf. Dit maakt ruime informatie beschikbaar voor diagnose in het geval van problemen.

* **het Schrijven het volgen logboeken** (nlserver het volgen logd) - dit proces bewaart aan schijf de volgende logboeken die door het omleidingsproces worden geproduceerd.

* **het Schrijven van binnenkomende gebeurtenissen** (nlserver interactie) - Dit proces verzekert de opname aan de schijf van binnenkomende gebeurtenissen, binnen het kader van Interactie.

* **het Toezien modules** (nlserver waakhond) - Dit technische proces handelt als primair proces dat anderen paait. Het bewaakt ze ook en start ze automatisch opnieuw in geval van incidenten, zodat het systeem maximaal uptime kan blijven.

* **de server van Statistieken** (nlserver staat) - Dit proces handhaaft statistieken over het aantal verbindingen, de berichten die voor elke postserver worden verzonden die berichten worden verzonden, evenals hun beperkingen (hoogste aantal gelijktijdige verbindingen, berichten per uur/ en of verbinding). Het laat u ook verscheidene instanties of machines federeren als zij de zelfde openbare IP adressen delen.


## Databasecontainers {#db-containers}

In zijn [ plaatsing van de Onderneming (FFDA) ](enterprise-deployment.md), baseert het gegevensbestand van de Wolk van Adobe Campaign zich op [!DNL Snowflake] die de functionele gegevens (profielen, abonnementen, inhoud, enz.), de technische gegevens (leveringsbanen en logboeken, het volgen logboeken, enz.) en de het werkgegevens (aankopen, leiden) voor de oplossing bevat, en alle componenten van Adobe Campaign communiceren met het gegevensbestand om hun specifieke taken uit te voeren.

U kunt Adobe Campaign implementeren met behulp van de vooraf gedefinieerde database en schema&#39;s en indien nodig kan deze vooraf gedefinieerde omgeving worden uitgebreid. Alle gegevens binnen de datamarkt worden betreden door Adobe Campaign via SQL vraag. Adobe Campaign biedt ook een volledige aanvulling op de ETL-gereedschappen (Extract Transform and Load) voor het importeren en exporteren van gegevens naar en vanuit het systeem.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Met **Beheerde de Diensten van de Wolk van de Campagne**, zijn uw milieu en aanvankelijke configuratie geplaatst door Adobe, volgens de termijnen van uw vergunningsovereenkomst. U mag geïnstalleerde ingebouwde pakketten, ingebouwde schema&#39;s of rapporten niet wijzigen.
>
>Als u een toe:voegen-op van de Campagne of een specifiek vermogen moet gebruiken dat niet voor u is provisioned, moet u **de Zorg van de Klant van 0&rbrace; Adobe contacteren.**

## Databaseopslag {#db-storage}

De totale opslagruimte wordt verdeeld tussen de hoofddatabase en de (facultatieve) secundaire Snowflake-database. Waar de gegevens worden opgeslagen zou op implementatie of verbeteringstijd, afhankelijk van klant-specifieke gebruiks-gevallen moeten worden bepaald.

Leer hoe te om uw gegevensbestandgebruik in [ documentatie van het Controlebord van de Campagne te controleren ](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring.html){target="_blank"}.