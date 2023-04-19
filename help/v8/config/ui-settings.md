---
title: Instellingen voor camerainterface
description: Leer hoe u de instellingen van de campagneinterface kunt aanpassen
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 0b4483e0f16f14582a1a4bc28b0e1ff719823ef3
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# Instellingen voor de gebruikersinterface voor campagnes {#ui-settings}

## Opsommingen {#enumerations}

Een opsomming (ook wel &#39;gespecificeerde lijst&#39; genoemd) is een lijst met waarden die door het systeem worden voorgesteld om velden te vullen. Gebruik opsommingen om de waarden van deze velden te standaardiseren, hulp bij gegevensinvoer of gebruik binnen query&#39;s.

De lijst met waarden wordt weergegeven als een vervolgkeuzelijst waaruit u de waarde kunt selecteren die in het veld moet worden ingevoerd. In de vervolgkeuzelijst is ook voorspellende invoer mogelijk: Voer de eerste letters in en de rest wordt door de toepassing ingevuld.

De waarden voor dit type veld worden gedefinieerd en het algemene beheer van deze velden (het toevoegen/verwijderen van een waarde) wordt uitgevoerd via de **[!UICONTROL Administration > Platform > Enumerations]** knooppunt van de structuur.

![Opsommingen openen](assets/enumerations-menu.png)

### Soorten opsommingen {#types-of-enum}

Opsommingen worden opgeslagen in de **[!UICONTROL Administration > Platform > Enumerations]** map van de verkenner.

Ze kunnen: Open, Systeem, Emoticon of Gesloten.

* An **Openen** Met opsomming kunnen gebruikers rechtstreeks nieuwe waarden toevoegen in de velden die op deze opsomming zijn gebaseerd.
* A **Gesloten** de opsomming heeft een vaste lijst met waarden die alleen vanuit de **[!UICONTROL Administration > Platform > Enumerations]** map van de verkenner.
* An **Emoticon** de opsomming wordt gebruikt om de emoticonlijst bij te werken. Meer informatie
* A **Systeem** opsomming is gekoppeld aan systeemvelden en wordt aangeduid met een interne naam.

Voor **Openen** en **Gesloten** opsommingen, specifieke opties zijn beschikbaar:

* **Eenvoudige opsomming** is het standaardstandaardtype.
* **Aliasreiniging** de opsomming wordt gebruikt om de in de database opgeslagen opsommingswaarden te harmoniseren. [Meer informatie](#alias-cleansing)
* **Gereserveerd voor binden** is een optie waarmee u kubuswaarden aan deze opsomming kunt koppelen. [Meer informatie](../reporting/gs-cubes.md)


### Aliasreiniging {#alias-cleansing}

In de opsommingsvelden kunt u een waarde selecteren of een aangepaste waarde invoeren die niet beschikbaar is in de vervolgkeuzelijst. U kunt aangepaste waarden toevoegen aan de bestaande opsommingswaarden als een nieuwe waarde, in dit geval de **[!UICONTROL Open]** moet geselecteerd zijn. Deze aangepaste waarden kunnen worden gereinigd met gebruik van aliasreinigingsmogelijkheden. Bijvoorbeeld wanneer een gebruiker een `Adob` in plaats van `Adobe`, kan het proces van het zuiveren van alias het automatisch door de correcte termijn vervangen.

>[!CAUTION]
>
>Het zuiveren van gegevens is een kritiek proces dat de gegevens in het gegevensbestand beïnvloedt. Adobe Campaign voert massagegevensupdates uit, wat ertoe kan leiden dat sommige waarden worden verwijderd. Deze bewerking is daarom voorbehouden aan professionele gebruikers.

De optie **[!UICONTROL Alias cleansing]** optie om gegevens te gebruiken zuiverend mogelijkheden voor een opsomming. Als deze optie is geselecteerd, wordt **[!UICONTROL Alias]** wordt onder in het venster weergegeven.

Wanneer een gebruiker een waarde invoert die niet bestaat in een opsomming voor Alias-zuivering, wordt deze toegevoegd aan de lijst **Waarden** lijst. U kunt [aliassen maken op basis van deze waarden](#convert-to-alias), of [nieuwe aliassen maken vanaf nul](#create-alias).

#### Een alias maken{#create-alias}

Voer de volgende stappen uit om een alias te maken:

1. Klikken **[!UICONTROL Add]** van de **[!UICONTROL Alias]** tab.
1. Voer de alias in die u wilt omzetten en selecteer de waarde die u wilt toepassen in de vervolgkeuzelijst.

   ![Een nieuwe alias maken](assets/new-alias.png)

1. Klikken **[!UICONTROL Ok]** en bevestigen.

1. Sla uw wijzigingen op. De vervanging van waarden wordt uitgevoerd door de **Aliasreiniging** workflow die elke nacht wordt uitgevoerd. Zie [Gegevens wissen](#running-data-cleansing).

Voor alle velden die op deze opsomming zijn gebaseerd, wanneer een gebruiker de waarde invoert **Adobe** in een veld &quot;bedrijf&quot; (in de Adobe Campaign-console, in een webformulier) wordt deze automatisch vervangen door de waarde **Adobe**.

#### Een onjuiste waarde omzetten in een alias{#convert-to-alias}

U kunt ook een bestaande opsommingswaarde omzetten in een alias. Dit doet u als volgt:

1. Klik in de lijst met waarden van een opsomming met de rechtermuisknop en blader naar **[!UICONTROL Actions... > Convert values into aliases...]**.

   ![Een waarde omzetten in een alias](assets/convert-into-aliases.png)

1. Selecteer de waarden die u wilt converteren in aliassen en klik op **[!UICONTROL Next]**.
1. Klikken **[!UICONTROL Start]** om de conversie uit te voeren.

   Wanneer de uitvoering is voltooid, worden aliassen toegevoegd aan de lijst, in het dialoogvenster **Alias** tab. U kunt een correcte waarde associëren om verkeerde ingangen te vervangen. Dit doet u als volgt:

1. Selecteer een waarde die u wilt opschonen.
1. Klik op de knop **Details...** knop.
1. Selecteer de nieuwe waarde in de vervolgkeuzelijst.

   ![Een nieuwe alias maken](assets/define-new-alias.png)


>[!NOTE]
>
>U kunt het voorkomen van een alias in volgen **[!UICONTROL Hits]** in de **[!UICONTROL Alias]** subtab. Het aantal keren dat deze waarde is ingevoerd, kan worden weergegeven.  [Meer informatie](#calculate-entry-occurrences).

#### Gegevens wissen {#running-data-cleansing}

De gegevens worden gewist door de **[!UICONTROL Alias cleansing]** technische workflow. Standaard wordt de transactie dagelijks uitgevoerd.

Het opschonen kan ook worden geactiveerd via de **[!UICONTROL Cleanse values...]** koppeling.

De **[!UICONTROL Advanced parameters...]** Met de koppeling kunt u de datum instellen vanaf welke verzamelde waarden in aanmerking worden genomen.

Klik op de knop **[!UICONTROL Start]** om gegevens te wissen.

##### Voorvallen monitoren {#calculate-entry-occurrences}

De **[!UICONTROL Alias]** Het subtabblad van een opsomming kan het aantal exemplaren van een alias weergeven voor alle ingevoerde waarden. Deze informatie is een schatting en wordt weergegeven in de **[!UICONTROL Hits]** kolom.

>[!CAUTION]
>
>Het berekenen van voorvallen van aliasinggegevens kan lang duren.

U kunt de aanraakberekening handmatig uitvoeren via de **[!UICONTROL Cleanse values...]** koppeling. Om dit te doen, klik **[!UICONTROL Advanced parameters...]** koppelen en optie(s) selecteren.

* **[!UICONTROL Update the number of alias hits]**: hiermee kunt u resultaten bijwerken die al zijn berekend op basis van de ingevoerde datum.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: Hiermee kunt u berekeningen uitvoeren op het hele Adobe Campaign-platform.

U kunt ook een specifieke workflow maken, zodat de berekening automatisch gedurende een bepaalde periode wordt uitgevoerd, bijvoorbeeld eenmaal per week.

Hiertoe maakt u een kopie van het **[!UICONTROL Alias cleansing]** de werkstroom, verandert de planner en gebruikt de volgende montages in **[!UICONTROL Enumeration value cleansing]** activiteit:

* **-updateHits** om het aantal aliashits bij te werken,
* **-updateHits:full** om alle aliashits opnieuw te berekenen.
