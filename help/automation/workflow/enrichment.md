---
product: campaign
title: Verrijking
description: Meer informatie over de activiteit van de verrijkingsworkflow
feature: Workflows, Enrichment Activity, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 23bfabac-62cc-4f86-a739-a34a0e183c31
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 0%

---

# Verrijking{#enrichment}



Met de activiteit **[!UICONTROL Enrichment]** kunt u informatie toevoegen aan een profiellijst en koppelingen maken naar een bestaande tabel (een nieuwe samenvoeging maken). Er kunnen ook afstemmingscriteria worden gedefinieerd met profielen in de database.

![](assets/enrichment_design.png)

## Definities {#definitions}

Om de verrijkingsactiviteit te gebruiken, moet u met de diverse beschikbare opties vertrouwd zijn wanneer het toevoegen van gegevens.

![](assets/enrichment_edit.png)

Met de optie **[!UICONTROL Data linked to the filtering dimension]** hebt u toegang tot:

* Gegevens van de filterdimensie: toegang tot de gegevens van de werkentabel
* Gegevens gekoppeld aan de filterdimensie: toegang tot gegevens gekoppeld aan de werktabel

![](assets/wf_enrich_linkoptions.png)

Met de optie **[!UICONTROL A link]** kunt u verbinding maken met elke tabel van de database.

![](assets/wf_enrich_linkstype.png)

Er zijn vier typen koppelingen:

* **[!UICONTROL Define a collection]**: hiermee kunt u een koppeling definiëren met een kardinaliteit van 1 N tussen de tabellen.
* **[!UICONTROL Define a link whose target is still available]**: hiermee kunt u een koppeling definiëren met een 1-1-cardinaliteit tussen tabellen. De verbindingsvoorwaarden moeten door één enkele verslag in de doellijst worden bepaald.
* **[!UICONTROL Define a link whose target does not necessarily exist in the base]**: hiermee kunt u een koppeling definiëren met een 0-1-cardinaliteit tussen tabellen. De verbindingsvoorwaarde moet door 0 of 1 (maximum) verslag in de doellijst worden bepaald.

  Deze optie is geconfigureerd op het tabblad **[!UICONTROL Simple Join]** , dat toegankelijk is via de **[!UICONTROL Edit additional data]** koppeling van de **[!UICONTROL Enrichment]** -activiteit.

* **[!UICONTROL Define a link by searching for a reference among several options]** : dit type koppeling definieert een koppeling naar een unieke record. Adobe Campaign maakt een koppeling naar een doeltabel door een externe sleutel toe te voegen aan de doeltabel om een verwijzing naar de unieke record op te slaan.

  Deze optie is geconfigureerd op het tabblad **[!UICONTROL Reconciliation and deduplication]** , dat toegankelijk is via de **[!UICONTROL Edit additional data]** koppeling van de **[!UICONTROL Enrichment]** -activiteit.

In de volgende secties zijn ook gebruiksgevallen te vinden waarin de activiteiten van verrijkingsactiviteiten in hun context worden beschreven:

* [ e-mail verrijking met de gebieden van de douanedatum ](email-enrichment-with-custom-date-fields.md).
* [Gegevens worden verrijkt](enrich-data.md)
* [Een overzichtslijst maken](create-a-summary-list.md)

## Informatie toevoegen {#adding-information}

Gebruik de activiteit **[!UICONTROL Enrichment]** om kolommen aan een het werklijst toe te voegen: deze activiteit kan als aanvulling op een vraagactiviteit worden gebruikt.

De configuratie van extra kolommen wordt gedetailleerd in [ Toevoegend gegevens ](query.md#adding-data).

In het veld **[!UICONTROL Primary set]** kunt u de binnenkomende overgang selecteren: de gegevens van de werktabel van deze activiteit worden verrijkt.

Klik op de koppeling **[!UICONTROL Add data]** en selecteer het type gegevens dat u wilt toevoegen. De lijst met aangeboden gegevenstypen is afhankelijk van de modules en opties die op uw platform zijn geïnstalleerd. In een minimale configuratie, kunt u gegevens altijd toevoegen verbonden aan de het filtreren afmeting en een verbinding.

![](assets/enrichment_edit.png)

In het onderstaande voorbeeld wordt de uitgaande overgang verrijkt met informatie over de leeftijd van de doelprofielen.

![](assets/enrichment_add_data.png)

Klik met de rechtermuisknop op de inkomende overgang van de verrijkingsactiviteit om de gegevens vóór het verrijkingsstadium weer te geven.

![](assets/enrichment_content_before.png)

De werktabel bevat de volgende gegevens en het bijbehorende schema:

![](assets/enrichment_content_before_a.png)

Herhaal deze bewerking in het verrijkingswerkgebied.

![](assets/enrichment_content_after.png)

U ziet dat de gegevens met betrekking tot profielpagina&#39;s zijn toegevoegd:

![](assets/enrichment_content_after_a.png)

Het overeenkomende schema is ook verrijkt.

## Aanvullende gegevens beheren {#managing-additional-data}

Schakel de optie **[!UICONTROL Keep all additional data from the main set]** uit als u de eerder gedefinieerde aanvullende gegevens niet wilt behouden. In dit geval worden alleen de extra kolommen die in de verrijkingsactiviteit zijn geselecteerd, toegevoegd aan de uitgaande werktabel. De aanvullende informatie die upstream aan de activiteiten wordt toegevoegd, wordt niet opgeslagen.

![](assets/enrichment_edit_without_additional.png)

De gegevens en het schema in de verrijkingsfase zijn als volgt:

![](assets/enrichment_content_after_without_additional.png)

## Koppelingen maken {#creating-a-link}

U kunt de verrijkingsactiviteit gebruiken om een verbinding tussen de het werk gegevens en het gegevensbestand van Adobe Campaign tot stand te brengen: dit zal een lokale verbinding aan het werkschema tussen de binnenkomende gegevens zijn.

Als u bijvoorbeeld gegevens laadt van een bestand dat het accountnummer, het land en de e-mail van ontvangers bevat, moet u een koppeling naar de landentabel maken om deze gegevens in hun profielen bij te werken.

Hiervoor voert u de volgende stappen uit:

1. Verzamel en laad het volgende bestandstype:

   ```
   Account number;Country;Email
   18D65;FRANCE;agnes@gmail.com
   243PP;RUSSIA;paul@gmail.com
   55H87;CROATIA;dave@gmail.com
   56U81;USA;susan@gmail.com
   853PI;ITALY;anna@gmail.com
   890LP;FRANCE;robert@gmail.com
   83TY2;SWITZERLAND;mike@gmail.com
   ```

1. Bewerk de verrijkingsactiviteit en klik **toevoegen gegevens...** verbinding om te creëren toetreedt met de lijst van het Land.

   ![](assets/enrichment_edit_after_file_box.png)

1. Selecteer de optie **[!UICONTROL Link definition]** en klik op de knop **[!UICONTROL Next]** . Geef het type koppeling op dat u wilt maken. In dit voorbeeld willen we het land van de ontvanger van het bestand in overeenstemming brengen met een land in de lijst met beschikbare landen in de specifieke tabel van de database. Kies de optie **[!UICONTROL Define a link by searching for a reference among several options]** . Selecteer de landentabel in het veld **[!UICONTROL Target schema]** .

   ![](assets/enrichment_add_a_link_select_option4.png)

1. Selecteer ten slotte de velden waarmee u de waarden van de bronbestanden kunt koppelen aan die in de database.

   ![](assets/enrichment_add_a_link_select_join.png)

Bij de output van deze verrijkingsactiviteit, zal het tijdelijke schema de verbinding aan de landlijst bevatten:

![](assets/enrichment_external_link_schema.png)

## Gegevensafstemming {#data-reconciliation}

De verrijkingsactiviteit kan worden gebruikt om gegevensverzoening te vormen, met inbegrip van zodra de gegevens in het gegevensbestand zijn geladen. In dit geval kunt u met het tabblad **[!UICONTROL Reconciliation]** de koppeling definiëren tussen de gegevens in de Adobe Campaign-database en de gegevens in de werktabel.

Selecteer de optie **[!UICONTROL Identify the targeting document based on work data]**, specificeer het schema u een verbinding tot stand wilt brengen en de het toetreden voorwaarden bepalen: om dit te doen, selecteer de gebieden die in de het werkgegevens (**[!UICONTROL Source expression]**) en in de het richten dimensie (**[!UICONTROL Destination expression]**) moeten worden in overeenstemming gebracht.

U kunt een of meer verzoeningscriteria gebruiken.

![](assets/enrichment_reconciliations_tab_01.png)

Als er meerdere samenvoegvoorwaarden zijn opgegeven, moeten deze ALLES worden gecontroleerd zodat de gegevens aan elkaar kunnen worden gekoppeld.

## Een voorstel invoegen {#inserting-an-offer-proposition}

Met de verrijkingsactiviteit kunt u aanbiedingen of koppelingen naar aanbiedingen voor ontvangers van de levering toevoegen.

Voor meer informatie over de verrijkingsactiviteit, verwijs naar dit [ sectie ](enrichment.md).

Bijvoorbeeld, kunt u de gegevens voor een ontvankelijke vraag vóór een levering verrijken.

![](assets/int_enrichment_offer1.png)

Na het vormen van uw vraag (verwijs naar deze [ sectie ](query.md)):

1. Voeg een verrijkingsactiviteit toe en open deze.
1. Selecteer op het tabblad **[!UICONTROL Enrichment]** de optie **[!UICONTROL Add data]** .
1. Selecteer **[!UICONTROL An offer proposition]** in de typen gegevens die u wilt toevoegen.

   ![](assets/int_enrichment_offer2.png)

1. Geef een id en een label op voor het voorstel dat wordt toegevoegd.
1. Geef de selectie van de aanbieding op. Hiervoor zijn twee opties mogelijk:

   * **[!UICONTROL Search for the best offer in a category]**: controleer deze optie en geef de parameters op voor de aanroep van de aanbiedingsengine (ruimte, categorie of thema(&#39;s), contactdatum, aantal aanbiedingen dat u wilt behouden). De motor berekent automatisch de aanbieding(en) die volgens deze parameters moet worden toegevoegd. U wordt aangeraden het veld **[!UICONTROL Category]** of **[!UICONTROL Theme]** in te vullen en niet beide tegelijk.

     ![](assets/int_enrichment_offer3.png)

   * **[!UICONTROL A predefined offer]**: controleer deze optie en specificeer een aanbiedingsruimte, een specifieke aanbieding, en een contactdatum om de aanbieding direct te vormen die u, zonder de aanbiedingsmotor te roepen wilt toevoegen.

     ![](assets/int_enrichment_offer4.png)

1. Dan vorm een leveringsactiviteit die aan uw gekozen kanaal beantwoordt. Verwijs naar [ de leveringen van het Kanaal 1&rbrace;.](cross-channel-deliveries.md)

   Het aantal voorstellen dat beschikbaar is voor de voorvertoning is afhankelijk van de configuratie die wordt uitgevoerd in de verrijkingsactiviteit in plaats van een mogelijke configuratie die rechtstreeks in de levering wordt uitgevoerd.

Als je voorstellen voor aanbiedingen wilt opgeven, kun je ook naar een link naar een voorstel verwijzen. Voor meer op dit, verwijs naar de volgende sectie [ Verwijzend een verbinding aan een aanbieding ](#referencing-a-link-to-an-offer).

## Verwijzen naar een koppeling naar een aanbieding {#referencing-a-link-to-an-offer}

U kunt ook verwijzen naar een koppeling naar een aanbieding in een verrijkingsactiviteit.

Dit doet u als volgt:

1. Selecteer **[!UICONTROL Add data]** op het tabblad **[!UICONTROL Enrichment]** van de activiteit.
1. Selecteer **[!UICONTROL A link]** in het venster waarin u het type gegevens kiest dat u wilt toevoegen.
1. Selecteer het type koppeling dat u wilt maken en het doel ervan. In dit geval is het doel het aanbiedingsschema.

   ![](assets/int_enrichment_link1.png)

1. Specificeer zich tussen de binnenkomende lijstgegevens in de verrijkingsactiviteit (hier de ontvankelijke lijst) en de aanbiedingstabel aan. U kunt bijvoorbeeld een aanbiedingscode koppelen aan een ontvanger.

   ![](assets/int_enrichment_link2.png)

1. Dan vorm een leveringsactiviteit die aan uw gekozen kanaal beantwoordt. Verwijs naar [ de leveringen van het Kanaal 1&rbrace;.](cross-channel-deliveries.md)

   >[!NOTE]
   >
   >Het aantal voorvertoningen dat beschikbaar is voor de voorvertoning, is afhankelijk van de configuratie die in de levering wordt uitgevoerd.

## Opslaan van rankings- en gewichten voor aanbiedingen {#storing-offer-rankings-and-weights}

Door gebrek, wanneer een **verrijking** activiteit wordt gebruikt om aanbiedingen te leveren, worden hun classificaties en hun gewichten niet opgeslagen in de propositielijst.

Deze informatie wordt standaard opgeslagen door de activiteit **[!UICONTROL Offer engine]** .

U kunt deze gegevens echter als volgt opslaan:

1. Creeer een vraag aan de aanbiedingsmotor in een verrijkingsactiviteit die na een vraag en vóór een leveringsactiviteit wordt geplaatst.
1. Selecteer **[!UICONTROL Edit additional data...]** in het hoofdvenster van de activiteit.

   ![](assets/ita_enrichment_rankweight_1.png)

1. Voeg de kolommen **[!UICONTROL @rank]** toe voor de positie en **[!UICONTROL @weight]** voor het gewicht van de aanbieding.

   ![](assets/ita_enrichment_rankweight_2.png)

1. Bevestig uw toevoeging en sla uw workflow op.

De levering slaat automatisch de rangschikking en het gewicht van de aanbiedingen op. Deze informatie is zichtbaar op het tabblad **[!UICONTROL Offers]** van de levering.
