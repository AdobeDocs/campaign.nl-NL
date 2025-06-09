---
product: campaign
title: Typologieregels toepassen
description: Leer hoe u typologische regels toepast
feature: Typology Rules
exl-id: 4ec3bbe1-fc4c-4b1e-989c-f4dcf8ee8d5e
source-git-commit: a8568e0c1e9af11b533b7d435691dc12cc0a2485
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 7%

---

# Typologieregels toepassen{#applying-rules}

## Een typologie toepassen op een levering {#apply-a-typology-to-a-delivery}

Als u de gemaakte typologieregels wilt toepassen, koppelt u deze aan een typologie en verwijst u naar deze typologie in de levering.

Hiervoor voert u de volgende stappen uit:

1. Maak een campagnetypologie.

   Typologieën zijn toegankelijk via de map **[!UICONTROL Administration > Campaign Management > Typology management]** > **[!UICONTROL Typologies]** van de Campagneverkenner.

1. Ga naar het tabblad **[!UICONTROL Rules]** , klik op de knop **[!UICONTROL Add]** en selecteer de regels die u met deze typologie wilt toepassen.

   ![](assets/campaign_opt_pressure_sample_1_6.png)

1. Sla de typologie op: wordt deze toegevoegd aan de lijst met bestaande typologieën.
1. Open de levering waarop u de regels wilt toepassen.
1. Blader naar de leveringseigenschappen en open het tabblad **[!UICONTROL Typology]** .
1. Selecteer de typologie in de vervolgkeuzelijst.

   ![](assets/campaign_opt_pressure_sample_1_7.png)

   >[!NOTE]
   >
   >De typologie kan in de leveringssjabloon worden gedefinieerd, en wordt dan automatisch toegepast op alle leveringen die met deze sjabloon zijn gemaakt.

## Toepassingsvoorwaarden definiëren {#define-application-conditions}

U kunt het toepassingsgebied van een regel afhankelijk van uw behoeften beperken (behalve controleregels).

Het is mogelijk om typologische regels zodanig te configureren dat deze alleen betrekking hebben op bepaalde leveringen die zij aan elkaar koppelen, of op bepaalde ontvangers onder het doel van een levering.

Klik op de koppeling **[!UICONTROL Edit the rule application conditions...]** op het tabblad **[!UICONTROL General]** om de toepassingsvoorwaarden van een regel te definiëren.

Dan gebruik de vraagredacteur om het filtreren voorwaarden te bepalen. In het volgende voorbeeld heeft de capaciteitsregel alleen betrekking op leveringen met het woord &quot;aanbieding&quot; op het etiket of op leveringen die vóór 1 april 2013 zijn gemaakt.

![](assets/campaign_opt_create_capacity_criterion.png)

>[!NOTE]
>
>Voor filterregels kunt u de toepassingsvoorwaarde van filtercriteria selecteren: deze kunnen afhankelijk zijn van de levering of de leveringscontour. [Meer informatie](filtering-rules.md#condition-a-filtering-rule).

## Rekenfrequentie aanpassen {#adjust-calculation-frequency}

Arbitrages worden elke avond automatisch opnieuw uitgevoerd via de workflow voor het opschonen van databases. Waarden kunnen echter ook na deze periode worden opgeslagen.

Sommige berekeningen gebruiken waarden die niet dagelijks veranderen. Het zou daarom irrelevant zijn om de gegevens elke dag opnieuw te berekenen en de database voor niets te overladen. Bijvoorbeeld, als een proces het marketing gegevensbestand met klantennestscores verrijkt en informatie op een wekelijkse basis koopt, te hoeven de gegevens die op deze waarden worden gebaseerd niet elke dag opnieuw te worden berekend.

Hiervoor definieert u in het veld **[!UICONTROL Frequency]** van het tabblad **[!UICONTROL General]** een maximumperiode waarin het doel wordt opgeslagen. Door gebrek, wijst de waarde **0** erop dat de berekening tot de volgende uitvoering van dagelijkse re-arbitrage geldig blijft.

Als u de resultaten na deze periode wilt opslaan, voert u in het veld **[!UICONTROL Frequency]** een waarde groter dan 12 in. Nadat deze periode is verlopen, worden alle regels opnieuw toegepast.

Met de optie **[!UICONTROL Re-apply the rule at the start of personalization]** kunt u de regel automatisch toepassen tijdens de verpersoonlijkingsfase, ook als de punt in het veld **[!UICONTROL Frequency]** nog steeds geldig is.

## Het selecteren van de fase van de regeltoepassing {#selecting-the-rule-application-phase}

De typologieregels worden in een specifieke volgorde toegepast tijdens de fase waarin de producten waarop zij betrekking hebben, worden gericht, geanalyseerd en gepersonaliseerd.

### Uitvoeringsopdracht {#execution-order}

In de standaardbewerkingsmodus worden de regels in de volgende volgorde toegepast:

1. Controleregels, indien toegepast aan het begin van targeting.
1. Filterregels:

   * Native toepassingsregels voor adreskwalificatie: gedefinieerd adres / niet-geverifieerd adres / adres op de lijst van gewezen personen / in quarantaine geplaatst adres / adreskwaliteit.
   * Filterregels die door de gebruiker zijn gedefinieerd.
   * Deduplicatieregel op het adres of de id (indien nodig toegepast).

1. Drukvoorschriften.
1. Capaciteitsregels.
1. Controleregels, indien toegepast aan het einde van targeting.
1. Regels van de controle, als zij bij het begin van verpersoonlijking worden toegepast. Als de gebruikersregels (filtreren/druk/capacitief) zijn verlopen en moeten opnieuw worden berekend, worden zij toegepast tijdens deze stap.
1. Controlevoorschriften, als zij aan het eind van verpersoonlijking van toepassing zijn.

>[!NOTE]
>
>Als u met de module van de Interactie van de Campagne werkt, aanbiedingsontvankelijkheidsregels worden toegepast tezelfdertijd zoals het filtreren regels (voor aanbiedingen die in de leveringsoverzichten worden gevonden) of tijdens de verpersoonlijkingsfase, tijdens de vraag aan de aanbiedingsmotor.

U kunt de uitvoeringsopeenvolging van regels aanpassen die het zelfde type hebben gebruikend het aangewezen gebied op het **[!UICONTROL General]** lusje van de regel. Wanneer tijdens dezelfde fase van berichtverwerking meerdere regels worden uitgevoerd, kunt u de uitvoeringsvolgorde ervan in het veld **[!UICONTROL Execution sequence]** configureren.

Bijvoorbeeld, wordt een drukregel met een uitvoeringsorde van 20 uitgevoerd vóór een drukregel met een uitvoeringsorde van 30.

### Controleregels {#control-rules}

Voor **[!UICONTROL Control]** -regels kunt u bepalen op welk punt van de levenscyclus van de levering de regel wordt toegepast: voor of na het opgeven van de regel, bij het begin van de personalisatie, aan het einde van de analyse. Selecteer op het tabblad **[!UICONTROL General]** van de typologieregel de waarde die u wilt toepassen in de vervolgkeuzelijst van het veld **[!UICONTROL Phase]** .

![](assets/campaign_opt_define_control_phase.png)

Mogelijke waarden zijn:

* **[!UICONTROL At the start of targeting]**

  Om de verpersoonlijkingsstap te verhinderen in het geval van fouten worden uitgevoerd, kunt u de controleregel hier toepassen.

* **[!UICONTROL After targeting]**

  Als u het volume van het doel moet kennen om de controleregel toe te passen, selecteer deze fase.

  De **[!UICONTROL Check proof size]** -besturingsregel wordt bijvoorbeeld toegepast na elk doelstadium: deze regel voorkomt dat berichten worden gepersonaliseerd als er te veel proefontvangers zijn.

* **[!UICONTROL At the start of personalization]**

  Deze fase moet worden geselecteerd als de controle de goedkeuring van berichtverpersoonlijking betreft. De personalisatie van berichten wordt uitgevoerd tijdens de analysefase.

* **[!UICONTROL At the end of the analysis]**

  Wanneer een controle berichtverpersoonlijking om vereist te zijn volledig, selecteer deze fase.

## Aanvullende configuraties {#additional-configurations}

### Het uitgaande verkeer SMTP van de controle {#control-outgoing-smtp-traffic}

Als optie kunt u het veld **[!UICONTROL Managing affinities with IP addresses]** gebruiken om leveringen te koppelen aan de leveringsserver (MTA) met deze affiniteit. Hiermee kunt u het aantal e-mails voor specifieke leveringen beperken tot computers of uitvoeradressen.

![](assets/campaign_opt_select_ip_affinity.png)

>[!NOTE]
>
>Affinity-beheer is niet van toepassing op **[!UICONTROL Filtering]** -typologieën.

<!--
>Affinities are defined in the instance configuration file, on the Adobe Campaign server. For more on this, refer to [this section](../../installation/using/about-initial-configuration.md).-->

### De Optimalisering van de campagne en Distribute Marketing {#campaign-optimization-and-distributed-marketing}

Op het tabblad **[!UICONTROL Distributed Marketing]** kunt u de typologieën en/of regels die van toepassing zijn wanneer een gedeelde campagne wordt besteld en/of gereserveerd, opnieuw toewijzen. Voor een lokale entiteit gedefinieerde typologieën/regels (gekoppeld aan die welke voor de centrale entiteit zijn gedefinieerd) vervangen regels/typologieën die aan de centrale entiteit zijn gekoppeld. Met Opnieuw toewijzen kunt u de regels van de centrale entiteit aanpassen aan de lokale entiteiten die de campagne bestellen.

![](assets/simu_campaign_opti_distrib_mkg.png)

>[!NOTE]
>
>In typologieën en typologieregels wordt het tabblad **[!UICONTROL Distributed Marketing]** toegevoegd als uw licentie deze optie bevat: controleer de licentieovereenkomst.\
>Voor meer informatie over Verdeelde Marketing, verwijs naar [ deze sectie ](../distributed-marketing/about-distributed-marketing.md).
