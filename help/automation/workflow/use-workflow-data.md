---
title: Workflowgegevens gebruiken
description: Leer hoe u workflowgegevens gebruikt
feature: Workflows, Data Management
version: Campaign v8, Campaign Classic v7
exl-id: 5014c2ed-2a74-4122-b7b9-d3703db7ab12
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 2%

---

# Workflowgegevens gebruiken{#how-to-use-workflow-data}

Met workflowactiviteiten kunt u meerdere taken uitvoeren. Hieronder vindt u voorbeelden van het gebruik om de database bij te werken door lijsten te maken, abonnementen te beheren, berichten te verzenden via een workflow of uw leveringen en het publiek te verrijken.

Een reeks gevallen van het werkschemagebruik is beschikbaar in [ deze sectie ](workflow-use-cases.md).

## Levenscyclus van gegevens {#data-life-cycle}

### Tijdelijke werktabel voor workflows {#work-table}

In werkstromen, worden de gegevens die van één activiteit aan een andere worden vervoerd opgeslagen in een tijdelijke het werklijst.

Deze gegevens kunnen worden weergegeven en geanalyseerd door met de rechtermuisknop op de juiste overgang te klikken.

![](assets/wf-right-click-analyze.png)

Selecteer hiertoe het relevante menu:

* **[!UICONTROL Display the target...]**

  In dit menu worden de beschikbare gegevens van de doelpopulatie weergegeven.

  ![](assets/wf-right-click-display.png)

  U hebt toegang tot de structuur van de werktabel op het tabblad **[!UICONTROL Schema]** .

  ![](assets/wf-right-click-schema.png)

  Raadpleeg [deze sectie](monitor-workflow-execution.md#worktables-and-workflow-schema) voor meer informatie.

* **[!UICONTROL Analyze target...]**

  Gebruik dit menu om toegang te krijgen tot de beschrijvende analysewizard waarmee u statistieken en rapporten over de overgangsgegevens kunt genereren.

  Leer hoe te om de beschrijvende analysetovenaar in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/analyzing-populations/about-descriptive-analysis.html){target="_blank"} te gebruiken.

De doelgegevens worden gewist terwijl de workflow wordt uitgevoerd. Alleen de laatste werktabel is toegankelijk. U kunt de workflow zodanig configureren dat alle werktabellen toegankelijk blijven: controleer de optie **[!UICONTROL Keep the result of interim populations between two executions]** in de workfloweigenschappen.

![](assets/wf-purge-data-option.png)

>[!CAUTION]
>
>Deze optie moet **nooit** in a **productie** werkschema worden gecontroleerd. Deze optie wordt gebruikt om de resultaten te analyseren en is alleen ontworpen voor testdoeleinden en moet daarom alleen worden gebruikt in ontwikkelings- of testomgevingen.


### Gebruik van doelgegevens {#target-data}

De gegevens die in de tijdelijke werkstroomlijst worden opgeslagen, zijn beschikbaar voor verpersoonlijkingstaken. De gegevens kunnen in de [ verpersoonlijkingsgebieden ](../../v8/send/personalization-fields.md) worden gebruikt.

Hiermee kunt u gegevens die via een lijst zijn verzameld, bijvoorbeeld in een levering gebruiken. Hiervoor gebruikt u de volgende syntaxis:

```
%= targetData.FIELD %
```

Aanmaakelementen van het type **[!UICONTROL Target extension]** (targetData) zijn niet beschikbaar voor workflows als doel. Het leveringsdoel moet in het werkschema worden gebouwd en in de binnenkomende overgang van de levering worden gespecificeerd.

In het volgende voorbeeld, verzamelt u een lijst van informatie over klanten, die in gepersonaliseerde e-mail moet worden gebruikt. Voer de volgende stappen uit:

1. Maak een workflow voor het verzamelen van informatie, pas deze aan met de gegevens die al in de database staan en start vervolgens een levering.

   ![](assets/wf-targetdata-sample-1.png)

1. In ons voorbeeld ziet de bestandsinhoud er als volgt uit:

   ```
   Music,First name,Last name,Account,CD/DVD,Card
   Pop,David,BLAIR,4323,CD,0
   Rock,Daniel,ARCARI,3222,DVD,1
   Disco,Uma,ALTON,0488,DVD,0
   Jazz,Paul,BOLES,6475,CD,1
   Jazz,David,BOUKHARI,0841,DVD,1
   [...]
   ```

   Als u het bestand wilt laden, configureert u de **[!UICONTROL Data loading (file)]** -activiteit als volgt:

   ![](assets/wf-targetdata-sample-2.png)

1. Configureer de **[!UICONTROL Enrichment]** -activiteit om de verzamelde gegevens te combineren met de gegevens die al in de Adobe Campaign-database staan. Hier is de afstemmingssleutel het rekeningnummer:

   ![](assets/wf-targetdata-sample-3.png)

1. Configureer vervolgens de **[!UICONTROL Delivery]** : deze wordt gemaakt op basis van een sjabloon en de ontvangers worden opgegeven door de binnenkomende overgang.

   ![](assets/wf-targetdata-sample-4.png)

   >[!CAUTION]
   >
   >Alleen gegevens in de overgang mogen worden gebruikt om de levering aan te passen. **targetData** typeverpersoonlijkingsgebieden zijn slechts beschikbaar voor de binnenkomende bevolking van de **[!UICONTROL Delivery]** activiteit.

1. In het leveringsmalplaatje, gebruik de gebieden die in het werkschema worden verzameld.

   Voeg daartoe **[!UICONTROL Target extension]** -typefilms in.

   ![](assets/wf-targetdata-sample-5.png)

   Hier willen we het favoriete muziekgenre en mediatype (CD of DVD) van de klant invoegen, zoals vermeld in het bestand dat tijdens de workflow wordt verzameld.

   Als plus gaan we een coupon toevoegen voor houders van een getrouwde kaart, dat wil zeggen ontvangers voor wie de waarde van de &#39;Kaart&#39; gelijk is aan 1.

   ![](assets/wf-targetdata-sample-6.png)

   Gegevens van het type **[!UICONTROL Target extension]** (targetData) worden in leveringen ingevoegd met dezelfde kenmerken als alle verpersoonlijkingsvelden. Ze kunnen ook worden gebruikt in het onderwerp, koppelingslabels of de koppelingen zelf.


## De database bijwerken {#update-the-database}

Alle verzamelde gegevens kunnen worden gebruikt om de database bij te werken, of in leveringen. U kunt bijvoorbeeld de personalisatiemogelijkheden voor berichtinhoud verruimen (bijvoorbeeld het aantal contracten in het bericht, het gemiddelde winkelwagentje in het afgelopen jaar specificeren, enz.) of de doelgroep specificeren (een bericht sturen naar contractdeelnemers, richten de 1.000 beste abonnees aan online diensten, enz.). Deze gegevens kunnen ook worden geëxporteerd of gearchiveerd in een lijst.

### Lijsten bijwerken  {#list-updates}

De gegevens van de Adobe Campaign-databank en de bestaande lijsten kunnen worden bijgewerkt met behulp van twee specifieke activiteiten:

* Met de activiteit **[!UICONTROL List update]** kunt u werktabellen opslaan in een datalist.

  U kunt een bestaande lijst selecteren of maken. In dit geval worden de naam en mogelijk de recordmap berekend.

  ![](assets/s_user_create_list.png)

  Verwijs naar [ update van de Lijst ](list-update.md).

* De **[!UICONTROL Update data]** -activiteit voert een massa-update uit van de velden in de database.

  Voor meer op dit, verwijs naar [ gegevens van de Update ](update-data.md).

### Lidmaatschappen beheren {#subscription-management}

Om te weten te komen over het intekenen van en het opzeggen van ontvangers aan de informatiedienst via een werkschema, verwijs naar [ Diensten van het Abonnement ](subscription-services.md).
