---
product: campaign
title: Deduplicatie
description: Meer informatie over de deduplicatieworkflowactiviteit
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: f79a979d-bd1d-4a86-8844-563886692941
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '1115'
ht-degree: 7%

---

# Deduplicatie{#deduplication}



Deduplicatie verwijdert duplicaten van de resultaten van binnenkomende activiteiten. U kunt deduplicatie uitvoeren op het e-mailadres, telefoonnummer of een ander veld.

De **[!UICONTROL Deduplication]** -activiteit wordt gebruikt voor het verwijderen van dubbele rijen uit een gegevensset. De onderstaande records kunnen bijvoorbeeld als duplicaat worden beschouwd omdat ze hetzelfde e-mailadres en hetzelfde mobiele en/of thuistelefoon hebben.

| Laatste wijzigingsdatum | Voornaam | Achternaam | Email | Mobiele telefoon | Telefoon |
-----|------------|-----------|-------|--------------|------
| 03-02-2020 | Bob | Tisner | bob@mycompany.com | 444-444-4444 | 888-888-888 |
| 19-05-2020 | Robert | Tisner | bob@mycompany.com | 444-444-4444 | 777-777-7777 |
| 22-07-2020 | Bobby | Tisner | bob@mycompany.com | 444-444-4444 | 777-777-7777 |

De **[!UICONTROL Deduplication]** -activiteit kan een hele rij als unieke record bewaren nadat duplicaten zijn geïdentificeerd. Als in het bovenstaande geval bijvoorbeeld de activiteit is geconfigureerd om alleen de record bij de oudste **[!UICONTROL Date]** te houden, is het resultaat:

| Datum | Voornaam | Achternaam | Email | Mobiele telefoon | Telefoon |
-----|----------|------------|-------|--------------|------
| 03-02-2020 | Bob | Tisner | bob@mycompany.com | 444-444-4444 | 888-888-888 |

De geselecteerde hoofdrecord stuurt de gegevens door zonder dat veldgegevens worden samengevoegd met andere relevante gegevens in de dubbele rijen.

Complementeren:

| Datum | Voornaam | Achternaam | Email | Mobiele telefoon | Telefoon |
-----|------------|-----------|-------|--------------|------
| 19-05-2020 | Robert | Tisner | bob@mycompany.com | 444-444-4444 | 777-777-7777 |
| 22-07-2020 | Bobby | Tisner | bob@mycompany.com | 444-444-4444 | 777-777-7777 |

## Best practices {#best-practices}

Tijdens deduplicatie worden inkomende stromen afzonderlijk verwerkt. Als bijvoorbeeld ontvanger A in het resultaat van vraag 1 evenals in het resultaat van vraag 2 wordt gevonden, zullen zij niet worden gededupliceerd.

Deze kwestie moet als volgt worden aangepakt:

* Creeer a **activiteit 0} van de Unie {om elke binnenkomende stroom te verenigen.**
* Creeer a **Deduplicatie** activiteit na de **Vereniging** activiteit.

![](assets/dedup-best-practice.png)

## Configuratie {#configuration}

Als u een deduplicatie wilt configureren, voert u het label, de methode en de criteria voor deduplicatie in en de opties voor het resultaat.

1. Klik op de koppeling **[!UICONTROL Edit configuration...]** om de deduplicatiemodus te definiëren.

   ![](assets/s_user_segmentation_dedup_param.png)

1. Selecteer het type doel voor deze activiteit (deduplicatie is standaard gekoppeld aan ontvangers) en het te gebruiken criterium, d.w.z. het veld waarvoor identieke waarden u in staat stellen duplicaten te identificeren.

   >[!NOTE]
   >
   >Als u externe gegevens gebruikt als invoer, bijvoorbeeld uit een extern bestand, moet u de optie **[!UICONTROL Temporary schema]** selecteren.
   >
   >In de volgende stap kunt u met de optie **[!UICONTROL Other]** het criterium of de criteria selecteren die u wilt gebruiken:

   ![](assets/s_user_segmentation_dedup_param2.png)

1. In de volgende stap kunt u met de optie **[!UICONTROL Other]** het criterium of de criteria selecteren die moeten worden gebruikt in het geval van identieke waarden.

   ![](assets/s_user_segmentation_dedup_param3.png)

1. Selecteer in de vervolgkeuzelijst de deduplicatiemethode die u wilt gebruiken en voer het aantal duplicaten in dat u wilt behouden.

   ![](assets/s_user_segmentation_dedup_param4.png)

   De volgende methoden zijn beschikbaar:

   * **[!UICONTROL Choose for me]**: Hiermee selecteert u willekeurig de record die u uit de duplicaten wilt houden.
   * **[!UICONTROL Following a list of values]**: Hiermee kunt u een waardeprioriteit voor een of meer velden definiëren. Als u de waarden wilt definiëren, selecteert u een veld of maakt u een expressie en vervolgens voegt u de waarde(n) toe aan de desbetreffende tabel. Als u een nieuw veld wilt definiëren, klikt u op de knop **[!UICONTROL Add]** boven de lijst met waarden.

     ![](assets/s_user_segmentation_dedup_param5.png)

   * **[!UICONTROL Non-empty value]**: Hiermee kunt u records waarvoor de waarde van de geselecteerde expressie niet leeg is als prioriteit behouden.

     ![](assets/s_user_segmentation_dedup_param6.png)

   * **[!UICONTROL Using an expression]**: hiermee kunt u records met de laagste (of hoogste) waarde van de opgegeven expressie bijhouden.

     ![](assets/s_user_segmentation_dedup_param7.png)

   >[!NOTE]
   >
   >Met de functie **[!UICONTROL Merge]** , die toegankelijk is via de koppeling **[!UICONTROL Advanced parameters]** , kunt u een set regels configureren om een veld of groep velden samen te voegen tot één gegevensrecord. Voor meer op dit, zie [ het samenvoegen van gebieden in één enkel verslag ](#merging-fields-into-single-record).

1. Klik op **[!UICONTROL Finish]** om de geselecteerde deduplicatiemethode goed te keuren.

   Het middelste gedeelte van het venster geeft een overzicht van de gedefinieerde configuratie.

   In de onderste sectie van het venster van de activiteitenredacteur, kunt u het etiket voor de uitgaande overgang van het grafische voorwerp wijzigen en een segmentcode ingaan die met het resultaat van de activiteit zal worden geassocieerd. Deze code kan later als het richten criterium worden gebruikt.

   ![](assets/s_user_segmentation_dedup_param8.png)

1. Schakel de optie **[!UICONTROL Generate complement]** in als u de resterende populatie wilt benutten. Het complement bestaat uit alle duplicaten. Vervolgens wordt als volgt een aanvullende overgang aan de activiteit toegevoegd:

   ![](assets/s_user_segmentation_dedup_param9.png)

## Voorbeeld: de duplicaten identificeren vóór levering {#example--identify-the-duplicates-before-a-delivery}

In het volgende voorbeeld betreft de deduplicatie de samenvoeging van drie vragen.

Het doel van de workflow is om het doel voor een levering te bepalen door duplicaten uit te sluiten, zodat deze niet meerdere keren naar dezelfde ontvanger worden gestuurd.

De geïdentificeerde duplicaten worden ook geïntegreerd in een speciale lijst met duplicaten die indien nodig opnieuw kan worden gebruikt.

![](assets/deduplication_example.png)

1. Voeg de verschillende activiteiten toe en koppel deze die nodig zijn om de workflow te laten werken, zoals hierboven wordt weergegeven.

   De vakbondsactiviteit wordt hier gebruikt om de drie vragen in één enkele overgang te &quot;verenigen&quot;. Op deze manier werkt deduplicatie niet voor elke query afzonderlijk, maar voor de gehele query. Voor meer op dit onderwerp, verwijs naar [ Beste praktijken ](#best-practices).

1. Open de deduplicatieactiviteit en klik vervolgens op de koppeling **[!UICONTROL Edit configuration...]** om de deduplicatiemodus te definiëren.
1. Selecteer **[!UICONTROL Database schema]** in het nieuwe venster.
1. Selecteer **Ontvangers** als het richten en het filtreren dimensies.
1. Selecteer het veld Id voor de duplicaten van **[!UICONTROL Email]** als u de levering slechts eenmaal naar elk e-mailadres wilt verzenden en klik op **[!UICONTROL Next]** .

   Als u de dubbele id&#39;s wilt baseren op een specifiek veld, selecteert u **[!UICONTROL Other]** om de lijst met beschikbare velden te openen.

1. Kies ervoor om slechts één item bij te houden wanneer hetzelfde e-mailadres wordt geïdentificeerd voor meerdere ontvangers.
1. Selecteer de deduplicatiemodus **[!UICONTROL Choose for me]** , zodat de records die worden opgeslagen in het geval van geïdentificeerde duplicaten willekeurig worden gekozen en klik vervolgens op **[!UICONTROL Finish]** .

Bij het uitvoeren van de workflow worden alle ontvangers die als duplicaten zijn geïdentificeerd, uitgesloten van het resultaat (en dus van de levering) en toegevoegd aan de lijst met duplicaten. Deze lijst kan opnieuw worden gebruikt in plaats van de duplicaten opnieuw te moeten identificeren.

## Velden samenvoegen tot één gegevensrecord {#merging-fields-into-single-record}

Met de functie **[!UICONTROL Merge]** kunt u een set regels voor deduplicatie configureren om een veld of groep velden te definiëren die moeten worden samengevoegd in één gegevensrecord.

Met een set dubbele records kunt u bijvoorbeeld het oudste telefoonnummer of de meest recente naam behouden.

Een gebruiksgeval leveraging deze eigenschap is beschikbaar in [ deze sectie ](deduplication-merge.md).

Ga als volgt te werk om dit te doen:

1. Klik in de selectiestap van **[!UICONTROL Deduplication method]** op de koppeling **[!UICONTROL Advanced Parameters]** .

   ![](assets/dedup1.png)

1. Selecteer de optie **[!UICONTROL Merge records]** om de functionaliteit te activeren.

   Als u meerdere gegevensvelden in elke samenvoegvoorwaarde wilt groeperen, activeert u de optie **[!UICONTROL Use several record merging criteria]** .

   ![](assets/dedup2.png)

1. Nadat de functionaliteit is geactiveerd, wordt een tabblad **[!UICONTROL Merge]** toegevoegd aan de **[!UICONTROL Deduplication]** -activiteit. Hiermee kunt u groepen velden definiëren die moeten worden samengevoegd en de bijbehorende regels.

   Voor meer op dit, verwijs naar het specifieke gebruiksgeval beschikbaar in [ deze sectie ](deduplication-merge.md).

## Invoerparameters {#input-parameters}

* tableName
* schema

Elke binnenkomende gebeurtenis moet een doel specificeren dat door deze parameters wordt bepaald.

## Uitvoerparameters {#output-parameters}

* tableName
* schema
* recCount

Deze reeks van drie waarden identificeert het doel dat uit de deduplicatie voortvloeit. **[!UICONTROL tableName]** is de naam van de tabel die doel-id&#39;s opslaat. **[!UICONTROL schema]** is het schema van de populatie (gewoonlijk nms:ontvanger) en **[!UICONTROL recCount]** is het aantal elementen in de tabel.

De overgang verbonden aan het complement heeft de zelfde parameters.
