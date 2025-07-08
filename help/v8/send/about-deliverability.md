---
product: campaign
title: Ga aan de slag met de prestaties in Campagne
description: Tips en trucs voor het leveren van informatie
feature: Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: f301b34c-244c-4279-b23f-8224ea8eedbe
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 7%

---

# Wat is afleverbaarheid?{#about-deliverability}

Met de prestaties kunt u het succes meten van uw campagnes die de inbox van uw ontvangers bereiken zonder te stuiteren, of als spam worden gemerkt. [ leer waarom de leverbaarheid ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters){target="_blank"} van belang is.

Meer bepaald, verwijst de e-maillevering naar de reeks eigenschappen die de capaciteit van een bericht bepalen om zijn bestemming, via een persoonlijk e-mailadres, binnen een korte tijd, en met de verwachte kwaliteit in termen van inhoud en formaat te bereiken.

Voor een diepere duik op wat de leverbaarheid is en meer op zeer belangrijke leveringsvoorwaarden, concepten, en benaderingen te leren, verwijs naar de [ Gids van de Beste praktijken van de Levering van Adobe ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"}.

## Hoe te om leverbaarheid te verbeteren {#deliverability-key-points}

De leveringsproblemen houden gewoonlijk verband met maatregelen van bescherming tegen spam die door Internet dienstverleners en de beheerders van de postserver worden uitgevoerd.

* Voor algemene aanbevelingen op hoe te om succesvolle e-mail marketing campagnes te ontwerpen, verwijs naar [ de strategie en de definitie van de Levering ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html){target="_blank"}.

* Adobe raadt u aan de beste praktijken in deze sectie te gebruiken voor specifieke aanbevelingen voor het optimaliseren van de leverbaarheid van uw Adobe Campaign-e-mails.

>[!NOTE]
>
>Omdat ISPs verplicht is voortdurend nieuwe verfijnde het filtreren technieken te ontwikkelen om hun klanten tegen spammers te beschermen, wordt de e-maillevering gekenmerkt door voortdurend veranderende criteria en regels. Zorg ervoor u naar de [ Gids van de Beste praktijken van de Levering van Adobe ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl){target="_blank"} verwijst die regelmatig wordt bijgewerkt.

### Leverbaarheidsgraad

Het leverbaarheidstarief is het aantal berichten die de inboxes van ontvangers vergeleken bij het aantal berichten raakten die werden geleverd. Om de leverbaarheid te verbeteren, kunt u werken aan het verhogen van dit tarief.

Bij Adobe Campaign hangt het leverbrengingscijfer af van een groot aantal factoren, met name:

* Correcte configuratie van uw instanties: neem contact op met uw Adobe-vertegenwoordiger voor hulp.
* Legitieme netwerkconfiguratie: zie [ de opstelling en de strategie van het Domein ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy){target="_blank"}.
* Uw IP adresreputatie: zie [ IP strategie ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy){target="_blank"}.
* De lage [ klachten ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html){target="_blank"} en [ harde stuiteren ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces){target="_blank"} tarieven.
* Uw berichtinhoud: zie [ Controle de e-mailinhoud ](control-message-content.md).
* De authentificatie van het bericht (SPF, DKIM, DMARC): zie [ deze sectie ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.
* De reputatie van de afzender: om te leren hoe hoofd ISPs een afzenderreputatie evalueert, zie [ deze sectie ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html){target="_blank"}.

## Hulpprogramma&#39;s voor het leveren van campagnes {#deliverability-tools}

<!--Adobe Campaign provides a number of tools designed to ensure optimal deliverability.-->
Adobe Campaign biedt verschillende tools om de prestaties van uw platform bij te houden en te verbeteren. Op deze pagina worden ook de belangrijkste beginselen gemarkeerd die u in gedachten moet houden om de prestaties te optimaliseren wanneer u campagne gebruikt.

### Uw bericht zorgvuldig samenstellen

Wanneer het vormen van, het ontwerpen van, en het testen van uw bericht, zorg ervoor u de beste praktijken volgt die in de hieronder vermelde secties worden vermeld. Door gebruik te maken van alle functies die Adobe Campaign biedt, kunt u de leverbaarheid verbeteren.

* [Best practices voor leveringen](../start/delivery-best-practices.md)
* [De e-mailinhoud beheren](control-message-content.md)
* [Inboxrendering](inbox-rendering.md)
* [Een proefafdruk verzenden](preview-and-proof.md#send-proofs)

### Verifieer toestemming door dubbele opt-in {#double-opt-in}

Om te voorkomen dat berichten naar ongeldige adressen worden verzonden, onjuiste communicatie wordt beperkt en de reputatie van de afzender wordt verbeterd, raadt Adobe aan een dubbele opt-in-mechanisme in te voeren. Met deze methode kunt u ervoor zorgen dat de ontvangers zich bewust hebben geabonneerd.

Zie [Een lidmaatschapsformulier maken met dubbele opt-in](https://experienceleague.adobe.com/en/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank} voor meer informatie.

Voor meer op beste praktijken wanneer het verzamelen van gegevens van uw klanten, verwijs naar de [ Gids van de Beste praktijken van de Levering van Adobe ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene){target="_blank"}.

### Gebruik quarantainebeheer

Adobe Campaign beheert een lijst met spamklachten, harde stuitingen en zachte stuitingen die consistent voorkomen.

Om uw leverbaarheid te beschermen, worden de ontvangers van wie adressen op die lijst zijn uitgesloten door gebrek van alle toekomstige leveringen, omdat het verzenden naar deze contacten uw verzendende reputatie zou kunnen schaden.

Sommige internetproviders beschouwen e-mails automatisch als spam als het aantal ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat deze providers aan de lijst van gewezen personen worden toegevoegd.

Raadpleeg de volgende secties voor meer informatie hierover:

* [Leveringsfouten begrijpen](delivery-failures.md)
* [Quarantainebeheer begrijpen](quarantines.md)
* [Quarantine versus lijst van gewezen personen](quarantines.md)

### Gereedschappen voor bewaking en rapportage gebruiken

Gebruik de functies die Adobe Campaign biedt om de prestaties te controleren.

Met Adobe Campaign kunt u controleren hoe uw leveringen presteren aan de hand van een reeks ingebouwde real-time indicatoren en rapporten voor een verbeterde insight voor uw leveringen.

Raadpleeg de volgende secties voor meer informatie hierover:

* [Te leveren items bewaken](monitoring-deliverability.md)
* [ worden begonnen met levering controle in de documentatie van Campaign Classic v7 ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}
* [Ga aan de slag met ingebouwde campagnerapporten](../reporting/built-in-reports.md)
