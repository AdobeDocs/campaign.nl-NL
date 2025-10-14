---
product: campaign
title: Drukregels configureren
description: Leer hoe te om drukregels te vormen
feature: Fatigue Management, Typology Rules
exl-id: d234db0e-936a-48db-b697-11c6b40bc3ab
source-git-commit: 8272550faefece753636418bcb748b36f989fcb5
workflow-type: tm+mt
source-wordcount: '3126'
ht-degree: 5%

---

# Drukregels{#pressure-rules}

Door het beheer van de verkoopdruk te implementeren, kunt u voorkomen dat de populatie in de database te veel wordt gevraagd, ook wel &#39;marketingmoeheid&#39; genoemd. Om dit te doen, kunt u een maximumaantal berichten per ontvanger bepalen. Ook kunt u arbitrageregels tussen campagnes toepassen, zodat de beste boodschap naar het doelpubliek wordt gestuurd.

**Druk** regels, om marketing vermoeidheid te beheren, bijvoorbeeld, om het aantal brieven te beperken dat naar een bevolking aan twee moet worden verzonden, om de mededeling te selecteren die het best de belangen van een groep abonnees aanpast, om het verzenden van SMS naar een ontevreden klant te vermijden, enz.

De campagnes worden geselecteerd gebaseerd op bepaalde drempels en berichtgewicht.

* Een drempel is het hoogste aantal leveringen dat binnen een bepaalde periode voor een bepaalde afnemer is toegestaan. De variabele kan ingesteld of variabel zijn. Deze wordt ingesteld of berekend in de instellingen voor de typologieregel. [Meer informatie](#maximum-number-of-messages).
* Met leveringsgewichten kunt u topprioriteit-leveringen identificeren in het kader van drukbeheer. Berichten met het hoogste gewicht hebben prioriteit. [Meer informatie](#message-weight).

Arbitrage bestaat erin ervoor te zorgen dat geplande campagnes met een groter gewicht dan de lopende campagne niet leiden tot excessieve profielopvraging: als dit het geval is, wordt het profiel uitgesloten van de levering.

Arbitragecriteria (gewicht en/of drempel) kunnen variëren op basis van twee soorten informatie:

* voorkeur van de ontvanger, die declaratieve informatie is: abonnementen op nieuwsbrief, status van de ontvanger (klant of vooruitzicht);
* gedrag van de ontvanger: aankopen, bezochte koppelingen, enz.

De arbitrageregel voor het definiëren van in aanmerking komende berichten wordt toegepast tijdens de analysefase. Voor elke ontvanger en voor de betrokken periode, zal het bericht worden verzonden als de volgende formule waar is: **(aantal verzonden berichten) + (aantal berichten met een groter gewicht) &lt; drempel**.

Anders is de ontvanger **[!UICONTROL Excluded by arbitration]** . [Meer informatie](#exclusion-after-arbitration).

## Een drukregel maken {#create-a-pressure-rule}

Aan opstellingsarbitrage tussen campagnes die Adobe Campaign gebruiken, begin door campagnetypologieën te creëren en verbonden typologieregels te bepalen (**Druk** regels).

>[!NOTE]
>
>Om een drukregel correct toe te passen, moet de het richten dimensie van de regel de het richten dimensie van de leveringsafbeelding aanpassen.

Voer de volgende stappen uit om een typologieregel **[!UICONTROL Pressure]** te maken en te configureren:

1. Selecteer in de lijst met typologische regels voor de campagne het pictogram **[!UICONTROL New]** boven de lijst.

   ![](assets/campaign_opt_create_a_rule_01.png)

1. In het **[!UICONTROL General]** lusje van de nieuwe regel, selecteer het type van a **Druk** regel en ga een naam en een beschrijving voor het in.

   ![](assets/campaign_opt_create_a_rule_02.png)

1. Wijzig zo nodig de uitvoeringsvolgorde. Wanneer meerdere typologische regels worden toegepast als een **[!UICONTROL Typology]** -set, worden eerst de onderste geordende regels toegepast. [Meer informatie](apply-rules.md#execution-order).
1. Definieer in de sectie **[!UICONTROL Calculation parameters]** een frequentie als u het opgeven van doelen na de volgende dagelijkse herarbitrageuitvoering wilt opslaan. [Meer informatie](apply-rules.md#adjust-calculation-frequency).
1. Klik op het tabblad **[!UICONTROL Pressure]** en kies de kalenderperiode waarin de typologieregel van toepassing is.

   ![](assets/campaign_opt_create_a_rule_03.png)

   De regel wordt toegepast op leveringen waarvan de contactdatum in de betrokken periode is opgenomen.

   >[!NOTE]
   >
   >In de context van een [&#x200B; plaatsing van de Onderneming (FFDA) &#x200B;](../../v8/architecture/enterprise-deployment.md) van Campagne, worden de gesneden leveringen niet in aanmerking genomen.

1. Definieer de methode voor het berekenen van het hoogste aantal berichten.

   De drempel vertegenwoordigt het hoogste aantal berichten dat tijdens de betrokken periode naar een ontvanger kan worden verzonden.

   Standaard is de drempelwaarde een constante en u moet een maximumaantal berichten aangeven dat door de regel wordt toegestaan.

   ![](assets/campaign_opt_create_a_rule_03b.png)

   Als u een drempelwaarde voor een variabele wilt definiëren, selecteert u de **[!UICONTROL Depends on the recipient]** -waarde in het **[!UICONTROL Type of threshold]** -veld en gebruikt u het pictogram aan de rechterkant om de expressie-editor te openen.

   ![](assets/campaign_opt_create_a_rule_04.png)

   Voor meer op dit, verwijs naar [&#x200B; Maximum aantal berichten &#x200B;](#maximum-number-of-messages).

1. Geef de methode op voor de berekening van het leveringsgewicht.

   Elke levering heeft een gewicht, d.w.z. een waarde die het prioriteitsniveau vertegenwoordigt: dit maakt arbitrage tussen campagnes mogelijk. Het gewicht wordt berekend aan de hand van de formule die is gedefinieerd in de typologieregel en/of in de eigenschappen ervan. [Meer informatie](#message-weight).

1. Standaard worden alle berichten in aanmerking genomen voor de berekening van de drempelwaarde. Op het tabblad **[!UICONTROL Restriction]** kunt u de berichten filteren waarop de typologieregel betrekking heeft:

   * In de bovenste sectie van dit tabblad kunt u de betreffende ontvangers beperken.
   * In de onderste sectie van dit tabblad kunt u de berichten filteren die moeten worden geteld.

     In het volgende voorbeeld, slechts worden de ontvangers bewaard in de **omslag NewContacts** rekening gehouden en de leveringen die met **Newsletter** beginnen betrokken.

   ![](assets/campaign_opt_create_a_rule_05.png)

1. Op het tabblad **[!UICONTROL Typologies]** kunt u de typologieën van de campagne weergeven die deze regel toepassen of de regel koppelen aan een of meer bestaande typologieën. [Meer informatie](campaign-typologies.md#apply-typologies).

## Drempels en gewichten definiëren {#define-thresholds-and-weights}

### Maximum aantal berichten {#maximum-number-of-messages}

Elke drukregel definieert een drempel, d.w.z. het maximumaantal berichten dat gedurende een bepaalde tijdsperiode naar een ontvanger kan worden verzonden. Zodra deze drempelwaarde is bereikt, kunnen tot het einde van de in aanmerking genomen periode geen leveringen meer plaatsvinden. Met dit proces kunt u automatisch een ontvanger uitsluiten van een levering als een bericht de ingestelde drempelwaarde overschrijdt. Op deze manier voorkomt u te veel vragen.

Drempelwaarden kunnen constant zijn of door een formule met variabelen worden berekend. Dit betekent dat de drempels voor een bepaalde periode van de ene ontvanger tot de andere kunnen variëren, of zelfs voor dezelfde ontvanger.

![](assets/campaign_opt_create_a_rule_threshold.png)

>[!CAUTION]
>
>Het ingaan van **0** als drempel verhindert alle leveringen aan de doelbevolking tijdens de beschouwde periode.

**Voorbeeld:**

U kunt het aantal geoorloofde berichten volgens het segment indexeren waartot de ontvanger behoort. Dit betekent dat een ontvanger die tot het websegment behoort meer berichten kan ontvangen dan andere ontvangers. Een **[!UICONTROL Iif (@origin='Web', 5, 3)]** typeformule staat de levering van 5 berichten aan ontvangers en 3 voor andere segmenten toe. De configuratie is als volgt:

![](assets/campaign_opt_pressure_sample.png)

Om de drempel te bepalen, kunt u een afmeting gebruiken verbonden aan de het richten afmeting: bijvoorbeeld, om berichten te omvatten die aan de ontvankelijke profielen worden geleverd in de [&#x200B; bezoekerslijst &#x200B;](../../v8/audiences/target-mappings.md) worden opgeslagen of te vermijden verzendend meer dan één bericht per week naar het zelfde huishouden, (dat naar verscheidene e-mailadressen kan verwijzen) die in een afmeting met die van de ontvangers worden geïdentificeerd.

Selecteer hiertoe de optie **[!UICONTROL Count messages on a linked dimension]** en selecteer vervolgens de bezoeker of de tabel met contactpersonen.

### Berichtgewicht {#message-weight}

Elke levering heeft een gewicht dat overeenkomt met het prioriteitsniveau. Standaard is het gewicht van een levering ingesteld op 5. Aan de hand van drukregels kunt u het gewicht bepalen van de leveringen waarop deze worden toegepast.

U kunt het gewicht instellen of berekenen met behulp van een formule die geschikt is voor de ontvanger. U kunt bijvoorbeeld het gewicht van een levering bepalen op basis van de belangen van de ontvanger.

>[!CAUTION]
>
>Het gewicht dat in een typologieregel wordt gedefinieerd, kan voor elke levering afzonderlijk worden overbelast, op het tabblad **[!UICONTROL Properties]** . Klik op het tabblad **[!UICONTROL Typology]** om de typologie van de campagne te selecteren en geef, indien nodig, het gewicht op dat u wilt toepassen.\
>Nochtans, zal het gewicht dat in een A typologieregel wordt verklaard niet voor de berekening van een B typologieregel worden gebruikt: dit gewicht zal slechts leveringen betreffen die de regel van A gebruiken.

**Voorbeeld:**

In het volgende voorbeeld willen we het gewicht van nieuwsbrieven op muziek koppelen aan de nevenscore van hun ontvangers. Dit doet u als volgt:

1. Maak een nieuw veld waarin u de geschiktheidsscores voor ontvangers kunt opslaan. Het veld **@Music** wordt in dit geval verrijkt met antwoorden op enquêtes en online opiniepeilingen, verzamelde volggegevens, enzovoort.
1. Maak een typologieregel om het gewicht van het bericht te berekenen op basis van dit veld.

   ![](assets/campaign_opt_pressure_weight_sample.png)

1. Pas deze regel op berichten met het volgende onderwerp toe: nieuwsbrieven, speciale aanbiedingen, enz. Het gewicht van deze leveringen, en dus het prioriteitsniveau ervan, zal afhangen van de geschiktheidsscore van elke ontvanger.

## De periode instellen {#setting-the-period}

De regels van de druk worden bepaald in **n** dag het rollen periodes.

De punt wordt gevormd in het **[!UICONTROL Pressure]** lusje van de regel. U kunt het aantal dagen opgeven en, indien nodig, het type groepering selecteren dat u wilt toepassen (dag, week, maand, kwartaal, enz.).

Met het groeperingstype kunt u het veld **[!UICONTROL Period considered]** uitbreiden naar de hele dag, kalenderweek, kalendermaand of kalenderjaar voor datums voor de periode.

Bijvoorbeeld, zal een drukregel die een drempel van 2 berichten per week bepaalt, met een groepering aan elke kalendermaand, de levering van meer dan 2 berichten binnen de zelfde week EN binnen de zelfde kalendermaand verhinderen. Waarschuwing: als de periode twee maanden overlapt, wordt bij de berekening rekening gehouden met de leveringen van deze twee kalendermaanden en kunnen derhalve alle nieuwe leveringen in de tweede maand worden voorkomen.

>[!CAUTION]
>
>Bij de berekening van de drempel wordt alleen rekening gehouden met reeds verzonden leveringen.

Om de leveringen te beperken die in rekening worden gebracht tot een periode van twee weken, ga **15d** op het **[!UICONTROL Concerned period]** gebied in: de leveringen die tot twee weken vóór de datum van de levering worden verzonden waarop de regel wordt toegepast zullen in de berekening worden in aanmerking genomen

De begindatum van de periode is afhankelijk van de configuratie van de database.

Als u bijvoorbeeld een drukregel van 15 dagen toepast zonder te groeperen in een levering van 12/11, wordt rekening gehouden met leveringen tussen 11/27 en 12/12. Indien bij de drukregel rekening wordt gehouden met de leveringen in het voorlopige tijdschema, worden alle tussen 11.27 en 12.27 geplande leveringen in aanmerking genomen. Tot slot als u een groepering per kalendermaand in de regel vormt, zullen alle leveringen in November en December in aanmerking worden genomen voor het berekenen van de drempel (van 11/1 tot 12/31).


**Frequente gevallen**

Om ervoor te zorgen dat geen rekening wordt gehouden met leveringen voor de huidige kalenderweek en om geen risico te lopen, rekening houdend met die van de vorige week voor de berekeningsdrempel, geeft u **[!UICONTROL Period considered]** op &#39;0&#39; en selecteert u &#39;Groepering per kalenderweek&#39; als **[!UICONTROL Period type]** .

Wanneer een periode groter is dan 0 (bijvoorbeeld 1), kan bij de berekening de waarde van de leveringen van de voorgaande dag in aanmerking worden genomen. Indien de vorige dag overeenkomt met de vorige kalenderweek en de gekozen periode &quot;Groepering per kalenderweek&quot; is, wordt derhalve met alle voorafgaande weken rekening gehouden voor de berekeningsdrempel.

**Voorbeeld:**

We willen een drukregel maken die het aanvragen beperkt tot 3 berichten per periode van twee weken, met een groepering tot de kalendermaand.

![](assets/campaign_opt_pressure_period_sample_1a.png)

Laten we zes nieuwsbrieven nemen met hetzelfde gewicht, gepland voor 05/30, 06/3, 06/8, 06/12, 06/22 en 06/30.

![](assets/campaign_opt_pressure_period_sample_0.png)

De voor 12 en 30 juni geplande leveringen zullen niet worden verzonden: de levering 06/12 zou de drempel van 3 berichten per periode van twee weken overschrijden en de 30e levering zou de drempel van toegestane communicatie per kalendermaand overschrijden.

![](assets/campaign_opt_pressure_period_sample_1.png)

Alle ontvangers voor deze leveringen worden tijdens de analysefase door arbitrage uitgesloten:

![](assets/campaign_opt_pressure_period_sample_2.png)

Voor de zelfde regel, als u leveringen per kwart groepeert, zullen de ontvangers van **nieuwsbrief nr.5** ook worden uitgesloten, en het zal niet worden verzonden.

Tot slot als geen groepering wordt geselecteerd, slechts **nieuwsbrief nr.4** zal niet worden verzonden, aangezien het voor de zelfde periode van twee weken zoals eerste drie nieuwsbrieven gepland was.

>[!NOTE]
>
>Wanneer u de definitie van een typologieregel verandert, kunt u a **Simulatie** tot stand brengen om zijn effect op de leveringen te controleren het wordt toegepast op en het effect te controleren dat de leveringen op elkaar hebben. [Meer informatie](campaign-simulations.md).

## Uitsluiting na arbitrage {#exclusion-after-arbitration}

Arbitrage wordt elke avond opnieuw toegepast via de **[!UICONTROL Forecasting]** technische workflow en de **[!UICONTROL Campaign jobs]** -workflow.

De **[!UICONTROL Forecasting]** -workflow berekent de gegevens voor de lopende periode (van de begindatum tot de huidige datum), zodat tijdens de analyse typologische regels kunnen worden toegepast. Ook worden de uitsluitingstellers elke nacht opnieuw berekend voor arbitrage.

Adobe Campaign controleert dus voor elke ontvanger of het aantal te verzenden berichten de drempel niet overschrijdt, rekening houdend met het aantal reeds verzonden berichten voor de betrokken periode. Deze informatie is een **indicator**, aangezien alle berekeningen op het tijdstip van levering worden bijgewerkt.

Als dit aantal de drempel overschrijdt, worden de arbitrageregels toegepast die in de campagnetypologie zijn gedefinieerd en worden de ontvangers uitgesloten van campagnes met een lager gewicht.

![](assets/campaign_opt_pressure_exclusion.png)

>[!NOTE]
>
>Als meerdere leveringen dezelfde scores hebben, wordt de campagne die voor de vroegste datum is gepland, verzonden.

## Gevallen gebruiken voor drukregels {#use-cases-on-pressure-rules}

### Aanpassing van de drempel op basis van criterium {#adapt-the-threshold-based-on-criterion}

Wij willen een typologieregel tot stand brengen om de levering van meer dan 4 berichten per week aan klanten en 2 berichten per week aan vooruitzichten te verhinderen.

Om klanten en vooruitzichten te identificeren, gebruik het **[!UICONTROL Status]** gebied, dat 0 voor vooruitzichten en 1 voor klanten bevat.

Pas de volgende stappen toe om de regel te maken:

1. Creeer een nieuwe **typologische regel van de Druk**.
1. Bewerk het tabblad **[!UICONTROL Pressure]** : in de sectie **[!UICONTROL Maximum number of messages]** willen we een formule maken om de drempel te berekenen, afhankelijk van elke ontvanger. Selecteer de **[!UICONTROL Depends on the recipient]** -waarde in het **[!UICONTROL Threshold type]** -veld en klik vervolgens op **[!UICONTROL Edit expression]** rechts van het **[!UICONTROL Formula]** -veld.

   Klik op de knop **[!UICONTROL Advanced parameters]** om de berekeningsformule te definiëren.

   ![](assets/campaign_opt_pressure_sample_1_1.png)

1. Selecteer de optie **[!UICONTROL Edit the formula using an expression]** en klik op **[!UICONTROL Next]** .

   ![](assets/campaign_opt_pressure_sample_1_2.png)

1. In de lijst van functies, klik de **functie Iif** in de **[!UICONTROL Others]** knoop tweemaal.

   Dan selecteer de ontvangers&#39; **Status** in de **[!UICONTROL Available fields]** sectie.

   ![](assets/campaign_opt_pressure_sample_1_3.png)

   Ga de volgende formule in: **Iif (@status=0,2,4)**

   ![](assets/campaign_opt_pressure_sample_1_4.png)

   Met deze formule kunt u de waarde 2 toewijzen als de status gelijk is aan 0 en de waarde 4 voor alle andere statussen.

   Klik op **[!UICONTROL Finish]** om de formule goed te keuren.

1. Vermeld de periode waarin de regel van toepassing is: 7 dagen in dit geval om het aantal berichten per week te tellen.

   ![](assets/campaign_opt_pressure_sample_1_5.png)

1. Sla de regel op om het maken van de regel goed te keuren.

Koppel nu de regel die u zojuist hebt gemaakt aan een typologie om deze toe te passen op leveringen. Dit doet u als volgt:

1. Maak een campagnetypologie.
1. Ga naar het tabblad **[!UICONTROL Rules]** , klik op de knop **[!UICONTROL Add]** en selecteer de regel die u zojuist hebt gemaakt.

   ![](assets/campaign_opt_pressure_sample_1_6.png)

1. Sla de typologie op: wordt deze toegevoegd aan de lijst met bestaande typologieën.

Als u deze typologie in uw leveringen wilt gebruiken, selecteert u deze in de leveringseigenschappen op het tabblad **[!UICONTROL Typology]** , zoals hieronder wordt weergegeven:

![](assets/campaign_opt_pressure_sample_1_7.png)

>[!NOTE]
>
>De typologie kan in de leveringssjabloon worden gedefinieerd, en wordt dan automatisch toegepast op alle leveringen die met deze sjabloon zijn gemaakt.

Tijdens de leveringsanalyse worden de ontvangers van de levering, indien van toepassing, uitgesloten van de levering, afhankelijk van het aantal reeds aan hen verzonden leveringen. Als u deze gegevens wilt weergeven, kunt u:

* Bekijk het analyseresultaat:

  ![](assets/campaign_opt_pressure_sample_1_8.png)

* Bewerk de levering en klik op de tab **[!UICONTROL Delivery]** en de subtab **[!UICONTROL Exclusions]** :

  ![](assets/campaign_opt_pressure_sample_1_9.png)

* Klik op het tabblad **[!UICONTROL Audit]** en vervolgens op het subtabblad **[!UICONTROL Causes of exclusions]** om het aantal uitsluitingen en de toegepaste typologische regels weer te geven:

  ![](assets/campaign_opt_pressure_sample_1_10.png)

### Het leveringsgewicht berekenen op basis van het gedrag {#calculate-the-delivery-weight-based-on-behavior}

U kunt drukregels definiëren op basis van het gedrag van de ontvanger. Zo kan het gewicht van een levering worden aangepast aan criteria die per ontvanger verschillen. U kunt bijvoorbeeld een bericht verzenden, afhankelijk van de vraag of een ontvanger uw website heeft bezocht, in een bepaald gedeelte van de laatste nieuwsbrief heeft geklikt, zich op een informatieservice heeft geabonneerd of zelfs op basis van antwoorden op een enquête, een online game, enz.

In het volgende voorbeeld willen we een levering maken met een gewicht van 5. Dit gewicht wordt verrijkt met nevenscores op basis van het gedrag van de ontvanger: klanten die al van deze site hebben besteld, hebben een score van 5, terwijl klanten die nog nooit online hebben besteld, een score van 4 hebben.

Om dit type van configuratie uit te voeren, moet u een formule gebruiken om berichtgewicht te bepalen. In het gegevensmodel moet informatie over de populatiescore en enquêteantwoorden beschikbaar zijn. In ons voorbeeld, is het **gebied van de Eigenschap** toegevoegd.

Pas de volgende configuratiestappen toe:

1. Creeer een nieuwe **typologische regel van de Druk**.
1. Bewerk de tab **[!UICONTROL Pressure]** . We willen een drempelformule maken die wordt gebaseerd op elke afzonderlijke ontvanger: klik op het pictogram **[!UICONTROL Edit expression]** rechts van het veld **[!UICONTROL Weight formula]** .

   ![](assets/campaign_opt_pressure_sample_2_1.png)

1. Door gebrek, wordt waarde **5** getoond in de hogere sectie van de uitdrukkingsredacteur. Wij willen de volheidsscore van elke ontvanger aan dit gewicht toevoegen: plaats uw curseur rechts van 5, ga het **+** karakter in en selecteer het **3&rbrace; gebied van de Eigenschap.**

   ![](assets/campaign_opt_pressure_sample_2_2.png)

1. Voeg vervolgens een hogere waarde toe aan ontvangers die al een aankoop hebben gedaan. Voor hen moet het gewicht van de levering met 5 worden verhoogd, voor andere met slechts 4.

   ![](assets/campaign_opt_pressure_sample_2_3.png)

1. Klik op **[!UICONTROL Finish]** om deze regel op te slaan.
1. Koppel de regel aan een campagnetypologie en verwijs deze typologie in een levering om het goed te keuren.

### Alleen de hoogst gewogen berichten verzenden {#send-only-the-highest-weighted-messages}

U wilt niet meer dan 2 berichten binnen de zelfde week, met een grens van 2 berichten per dag, naar elk van uw ontvangers verzenden, en u wilt slechts de berichten met hogere gewichten om worden geleverd.

Hiervoor moet u verschillende leveringen met verschillende gewichten voor dezelfde ontvanger plannen en een drukregel toepassen om de leveringen met een lager gewicht uit te sluiten.

Eerst, vorm de drukregel.

1. Maak een drukregel. [Meer informatie](#create-a-pressure-rule).
1. Selecteer op het tabblad **[!UICONTROL General]** de optie **[!UICONTROL Re-apply the rule at the start of personalization]** .

   ![](assets/campaign_opt_pressure_example_5.png)

   Met deze optie wordt de waarde die in het veld **[!UICONTROL Frequency]** is gedefinieerd, overschreven en wordt de regel tijdens de verpersoonlijkingsfase automatisch toegepast. [Meer informatie](apply-rules.md#adjust-calculation-frequency).

1. Selecteer op het tabblad **[!UICONTROL Pressure]** **[!UICONTROL 7d]** als de **[!UICONTROL Period considered]** en **[!UICONTROL Grouping per day]** als de **[!UICONTROL Period type]** .
1. Koppel op het tabblad **[!UICONTROL Typologies]** de regel aan een campagnetypologie.
1. Sla uw wijzigingen op.

Maak en configureer nu een workflow voor elke levering waarop u de drukregel wilt toepassen.

1. Maak een campagne. [Meer informatie](../campaigns/marketing-campaign-create.md#create-a-campaign).
1. In het **[!UICONTROL Targeting and workflows]** lusje van uw campagne, voeg de activiteit van de a **Vraag** aan uw werkschema toe. Voor meer bij het gebruiken van deze activiteit, verwijs naar [&#x200B; deze sectie &#x200B;](../workflow/query.md).
1. Voeg een **[!UICONTROL Email delivery]** activiteit aan het werkschema toe en open het. Voor meer bij het gebruiken van deze activiteit, verwijs naar [&#x200B; deze sectie &#x200B;](../workflow/delivery.md).
1. Ga naar het tabblad **[!UICONTROL Approvals]** van **[!UICONTROL Delivery properties]** en schakel alle goedkeuringen uit.

   ![](assets/campaign_opt_pressure_example_2.png)

1. Verwijs in het tabblad **[!UICONTROL Typology]** van het **[!UICONTROL Delivery properties]** naar de campagnetypologie waarop u de regel wilt toepassen. Definieer een gewicht voor de levering.

   ![](assets/campaign_opt_pressure_example_3.png)

1. Klik in de levering op **[!UICONTROL Scheduling]** en selecteer **[!UICONTROL Schedule delivery (automatic execution when the scheduled date is reached)]** . Selecteer in dit voorbeeld de optie **[!UICONTROL Use a calculation formula]** .
1. Stel de extractiedatum in op 10 minuten (huidige datum + 10 minuten).
1. Stel de contactdatum in op de volgende dag (huidige datum + 1 dag).

   ![](assets/campaign_opt_pressure_example_4.png)

   Voor de drukregeluitsluitingen die met succes moeten worden geïmplementeerd, moet u de extractiedatum en -tijd vóór de contactdatum en -tijd instellen, evenals voordat de nachtelijke arbitrage opnieuw wordt toegepast. [Meer informatie](#exclusion-after-arbitration).

1. Hef de selectie van de optie **[!UICONTROL Confirm the delivery before sending]** op en sla uw wijzigingen op.
1. Ga op dezelfde manier te werk voor elke levering die u wilt verzenden. Zorg ervoor dat u het gewenste gewicht voor elke levering instelt.
1. Voer de relevante workflows uit om de leveringen voor te bereiden en te verzenden.

Wanneer de nachtelijke arbitrage wordt toegepast, worden de leveringen met de laagste gewichten voor dezelfde afnemer uitgesloten. Alleen leveringen met het hoogste gewicht worden in aanmerking genomen voor verzending. [Meer informatie](#message-weight).

Aangezien er al eerder in de week een e-mailbericht naar de betrokken ontvangers is verzonden, wordt in de onderstaande tabel een voorbeeld weergegeven van de configuraties die kunnen worden toegepast voor nog twee leveringen.

<table> 
 <thead> 
  <tr> 
   <th> Aflevering <br /> </th> 
   <th> Goedkeuringen <br /> </th> 
   <th> Dikte <br /> </th> 
   <th> Uittrekdatum/-tijd <br /> </th> 
   <th> Contactdatum <br /> </th> 
   <th> Begindatum/-tijd van levering <br /> </th> 
   <th> Datum/tijd van uitvoering van de arbitrageworkflow <br /> </th> 
   <th> Leveringsstatus <br /> </th> 
   <th> Verzonden levering (datum/tijd) <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Aflevering 1 <br /> </td> 
   <td> Uitgeschakeld <br /> </td> 
   <td> 5<br /> </td> 
   <td> 3pm<br /> </td> 
   <td> 8am (volgende dag) <br /> </td> 
   <td> 2 pm <br /> </td> 
   <td> Night<br /> </td> 
   <td> Uitgesloten <br /> </td> 
   <td> Uitgesloten <br /> </td> 
  </tr> 
  <tr> 
   <td> Aflevering 2 <br /> </td> 
   <td> Uitgeschakeld <br /> </td> 
   <td> 10 <br /> </td> 
   <td> 4pm<br /> </td> 
   <td> 9am (volgende dag) <br /> </td> 
   <td> 2 pm <br /> </td> 
   <td> Night<br /> </td> 
   <td> Verzonden<br /> </td> 
   <td> 9am (volgende dag) <br /> </td> 
  </tr> 
 </tbody> 
</table>

Nadat de extractiedatum voor de twee leveringen is verstreken, wordt de nachtelijke arbitrage opnieuw toegepast vóór de contactdata van beide leveringen. Op deze manier kunnen alle reeds verzonden leveringen (ontvangers voor wie een levering wordt verwerkt, geregistreerd via de grote logboeken) of geplande leveringen (ontvangers die in aanmerking komen voor een levering, geregistreerd via de voorspelde logboeken) worden gevonden.

Zodra alle verzonden en potentiële leveringen zijn vermeld voor de periode die in de drukregel is bepaald, sorteert Adobe Campaign ze op basis van gewicht, met de hoogste gewogen eerst. Wanneer de in de drukregel vastgestelde drempelwaarde wordt bereikt (hier niet meer dan twee e-mails in dezelfde week), worden de ontvangers uitgesloten van de levering.
