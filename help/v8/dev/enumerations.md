---
title: Opsommingen beheren
description: Leer hoe u met opsommingen werkt
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 428de72e0459b95a6db0b06ec8541d0475b72fdd
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Opsommingen beheren {#manage-enumerations}

Een opsomming (ook wel een gedetailleerde lijst genoemd) is een vooraf gedefinieerde lijst met waarden die u kunt gebruiken om bepaalde velden in te vullen. Opsommingen helpen bij het standaardiseren van veldwaarden, het consistenter maken van gegevens en het vereenvoudigen van query&#39;s.

Indien beschikbaar worden de waarden weergegeven in een vervolgkeuzelijst. U kunt een waarde rechtstreeks selecteren of beginnen te typen. Bij voorspellende invoer worden overeenkomende waarden voorgesteld en automatisch ingevuld.

![](assets/enum_values.png)

Sommige consolevelden worden gevormd met opsommingen. Als een opsomming **open** is, kunt u nieuwe waarden op het gebied ook direct toevoegen.

## Opsommingen openen

De waarden die in deze velden worden gebruikt, worden centraal beheerd. U kunt hen toevoegen, uitgeven, bijwerken of schrappen van de boom van de Ontdekkingsreiziger, onder **Beleid** `>` **Platform** `>` **Opsommingen**.

* De bovenste sectie bevat een lijst met velden waarvoor een opsomming is gedefinieerd.
* In de onderste sectie worden de beschikbare waarden weergegeven.

Wanneer een opsomming **[!UICONTROL Open]** is, kunnen gebruikers een nieuwe waarde direct in het overeenkomstige gebied in het gebruikersinterface ingaan.

Wanneer een opsomming **[!UICONTROL Closed]** is, kunnen de nieuwe waarden slechts van het **Opsommings** menu worden toegevoegd.

## Een nieuwe waarde toevoegen

Als u een nieuwe opsommingswaarde wilt maken, klikt u op de knop **[!UICONTROL Add]** .

![](assets/enumeration_screen.png)

Voer het label van de waarde in.


## Aliasreiniging {#alias-cleansing}

In de opsommingsgebieden, kunt u waarden buiten opsommingswaarden ingaan. Deze kunnen worden opgeslagen zoals ze zijn of worden gereinigd.

>[!CAUTION]
>
>Het zuiveren van gegevens is een kritiek proces dat de gegevens in het gegevensbestand beïnvloedt. Adobe Campaign voert massagegevensupdates uit, wat ertoe kan leiden dat sommige waarden worden verwijderd. Deze bewerking is daarom voorbehouden aan professionele gebruikers.

De ingevoerde waarde is dan:

* Toegevoegd aan de gespecificeerde lijstwaarden: in dit geval moet de **[!UICONTROL Open]** optie worden geselecteerd,
* of automatisch vervangen door de bijbehorende alias: in dit geval moet dit geval worden gedefinieerd op het tabblad **[!UICONTROL Alias]** van de gespecificeerde lijst,
* of wordt opgeslagen in de lijst met aliassen: er wordt later een alias aan toegewezen.

### Een alias maken {#creating-an-alias}

Met de optie **[!UICONTROL Alias cleansing]** kunt u aliassen gebruiken voor de geselecteerde gespecificeerde lijst. Als deze optie is geselecteerd, wordt de tab **[!UICONTROL Alias]** onder in het venster weergegeven.

Voer de volgende stappen uit om een alias te maken:

1. Blader naar de opsomming die u wilt bijwerken als u op **[!UICONTROL Add]** klikt.

   ![](assets/enumeration_alias_create.png)

1. Voer de alias die u wilt omzetten en de waarde in die u wilt toepassen en klik op **[!UICONTROL Ok]** .

1. Controleer parameters voordat u deze bewerking bevestigt.

>[!CAUTION]
>
>Zodra deze stap is bevestigd, kunnen de vorige waarden niet meer worden teruggewonnen: ze worden vervangen.

Aldus, wanneer een gebruiker de waarde **NEILSEN** op een &quot;bedrijf&quot;gebied (in de console van Adobe Campaign of in een vorm) ingaat, wordt het automatisch vervangen door de waarde **NIELSEN Ltd**. De waardevervanging wordt uitgevoerd door het **Alias zuiverend** werkschema. Verwijs naar [&#x200B; gegevens van de Looppas zuiverend &#x200B;](#running-data-cleansing).

![](assets/enumeration_alias_use.png)

### Waarden omzetten in aliassen {#values-into-aliases}

U kunt bestaande waarden omzetten in aliassen. Voer de volgende stappen uit om dit te doen:

1. Klik met de rechtermuisknop in de lijst met waarden en kies **[!UICONTROL Convert values into aliases...]** .

1. Kies de waarden die u wilt omzetten en klik op **[!UICONTROL Next]** .

1. Klik op **[!UICONTROL Start]** om de conversie uit te voeren.

Zodra de uitvoering is voltooid, wordt de alias toegevoegd aan de lijst met aliassen.

### Aliasresultaten ophalen {#alias-hits}

Wanneer gebruikers waarden invoeren die niet in de opsomming zijn opgenomen, worden deze opgeslagen op het tabblad **[!UICONTROL Alias]** .

Het **Alias zuiveren** technische werkschema herstelt deze waarden elke nacht om de opsomming bij te werken. Verwijs naar [&#x200B; gegevens van de Looppas zuiverend &#x200B;](#running-data-cleansing)

Indien nodig kan in de kolom **[!UICONTROL Hits]** het aantal keren worden weergegeven dat deze waarde is ingevoerd. Het berekenen van deze waarde kan echter zowel tijdrovend zijn als geheugenverbruikend. Voor meer op dit, verwijs naar [&#x200B; berekent ingangsvoorkomen &#x200B;](#calculating-entry-occurrences).

### Gegevens wissen {#run-data-cleansing}

De gegevens worden gewist door de technische workflow van **[!UICONTROL Alias cleansing]** . De configuraties die voor opsommingen worden gedefinieerd, worden tijdens de uitvoering toegepast. Verwijs naar [&#x200B; Alias het zuiveren werkschema &#x200B;](#alias-cleansing-workflow).

Het opschonen kan worden geactiveerd via de koppeling **[!UICONTROL Cleanse values...]** .

Met de koppeling **[!UICONTROL Advanced parameters...]** kunt u de datum instellen vanaf welke verzamelde waarden in aanmerking worden genomen.

Klik op de knop **[!UICONTROL Start]** om gegevens te wissen.

### Voorvallen van item berekenen {#entry-occurrences}

Het subtabblad **[!UICONTROL Alias]** van een gespecificeerde lijst kan het aantal exemplaren van een alias weergeven voor alle ingevoerde waarden. Deze informatie is een schatting en wordt weergegeven in de kolom **[!UICONTROL Hits]** .

>[!CAUTION]
>
>Het berekenen van voorvallen van aliasinggegevens kan lang duren. Daarom is voorzichtigheid geboden wanneer het gebruiken van deze functie.

U kunt de aanraakberekening handmatig uitvoeren via de koppeling **[!UICONTROL Cleanse values...]** . Klik hiertoe op de koppeling **[!UICONTROL Advanced parameters...]** en selecteer de gewenste optie(s).

* **[!UICONTROL Update the number of alias hits]** : hiermee kunt u treffers bijwerken die al zijn berekend op basis van de ingevoerde datum.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: hiermee kunt u berekeningen uitvoeren op het hele Adobe Campaign-platform.

U kunt ook een specifieke workflow maken, zodat de berekening automatisch gedurende een bepaalde periode wordt uitgevoerd, bijvoorbeeld eenmaal per week.

Hiertoe maakt u een kopie van de **[!UICONTROL Alias cleansing]** -workflow, wijzigt u de planner en gebruikt u de volgende instellingen in de **[!UICONTROL Enumeration value cleansing]** -activiteit:

* **- updateHits** om het aantal aliashits bij te werken,
* **- updateHits:full** om alle aliashits opnieuw te berekenen.

### Workflow voor Aliasverwijdering {#alias-cleansing-workflow}

Het **Alias zuiveren** werkschema stelt opsommingswaarde het zuiveren in werking. Standaard wordt de transactie dagelijks uitgevoerd.

Het wordt benaderd via het knooppunt **[!UICONTROL Administration > Production > Technical workflows]** .


