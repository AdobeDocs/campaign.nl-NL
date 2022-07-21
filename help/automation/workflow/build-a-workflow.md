---
product: campaign
title: Een workflow maken
description: Leer hoe u een workflow kunt maken
feature: Workflows
exl-id: a6003fdb-1035-4b80-8831-73f30a0b4fb2
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 4%

---

# Een workflow maken {#build-a-workflow}

## Een nieuwe workflow maken {#create-a-new-workflow}

De workflow voor het maken van werkstromen is afhankelijk van het type werkstroom. U kunt:

* Maken [Workflows voorbereiden](#targeting-workflows) van de **[!UICONTROL Profiles and Targets]** > **[!UICONTROL Jobs]** > **[!UICONTROL Targeting workflows]** knoop van de Ontdekkingsreiziger of van de **[!UICONTROL Profiles and Targets]** tabblad van de homepage, via de **[!UICONTROL Targeting workflows]** subtab.

   ![](assets/create-targeting-wf.png)

* Maken [Workflows voor campagnes](#campaign-workflows) van de **[!UICONTROL Targeting and workflows]** tabblad van een campagne

* Maken [Technische workflows](#technical-workflows) van de **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** knoop van de Ontdekkingsreiziger. U kunt het beste een specifieke werkstroommap maken om uw technische workflows op te slaan.

Klik op de knop **[!UICONTROL New]** boven de lijst met workflows.

![](assets/create_a_wf_icon.png)

Voer een label in en klik op **[!UICONTROL Save]**.

## Activiteiten toevoegen en koppelen {#add-and-link-activities}

U moet nu de verschillende activiteiten definiëren en deze koppelen in het diagram. In dit stadium van de configuratie, kunnen wij het diagrametiket en de werkschemastatus zien (Bewerkt lopend). Het onderste gedeelte van het venster wordt alleen gebruikt voor het bewerken van het diagram. Het bevat een werkbalk, een palet met activiteiten (links) en het diagram zelf (rechts).

![](assets/new-workflow-2.png)

>[!NOTE]
>
>Als het palet niet wordt weergegeven, klikt u op de eerste knop op de werkbalk om het weer te geven.

De activiteiten worden gegroepeerd op categorie in de verschillende tabbladen van het palet. De beschikbare tabbladen en activiteiten kunnen variëren afhankelijk van het type workflow (technisch, doelgericht of campagneworkflow).

* Het eerste tabblad bevat bewerkingen voor het activeren van doelen en gegevens. Deze activiteiten worden nader beschreven in [Gerichte activiteiten](targeting-activities.md).
* Het tweede tabblad bevat de planningsactiviteiten, die hoofdzakelijk worden gebruikt voor de coördinatie van andere activiteiten. Deze activiteiten worden nader beschreven in [Stroombeheeractiviteiten](flow-control-activities.md).
* Het derde tabblad bevat gereedschappen en handelingen die in de workflow kunnen worden gebruikt. Deze activiteiten worden nader beschreven in [Acties](action-activities.md).
* Het vierde tabblad bevat activiteiten die afhankelijk zijn van een bepaalde gebeurtenis, zoals de ontvangst van een e-mail of de aankomst van een bestand op een server. Deze activiteiten worden nader beschreven in [Gebeurtenisactiviteiten](event-activities.md).

Het diagram maken

1. Voeg een activiteit toe door het in het palet te selecteren en het te bewegen aan het diagram gebruikend belemmering-en-dalingsverrichting.

   Voeg een **Start** en vervolgens een **Aflevering** activiteit op het diagram.

   ![](assets/new-workflow-3.png)

1. U kunt de activiteiten aan elkaar koppelen door de **Start** activiteit overgang en het laten vallen van het op **Aflevering** activiteit.

   ![](assets/new-workflow-4.png)

   U kunt een activiteit aan vorige automatisch verbinden door de nieuwe activiteit aan het eind van de overgang te plaatsen.

1. Voeg de activiteiten toe u nodig hebt en verbind hen samen zoals aangetoond in het hieronder diagram.

   ![](assets/new-workflow-5.png)

>[!CAUTION]
>
>U kunt activiteiten kopiëren en plakken binnen dezelfde workflow. We raden echter niet aan plakactiviteiten over verschillende workflows te kopiëren. Sommige instellingen die zijn gekoppeld aan activiteiten zoals Leveringen en Planner kunnen leiden tot conflicten en fouten tijdens het uitvoeren van de doelworkflow. We raden u aan  **Dupliceren** workflows. Zie voor meer informatie [Workflows dupliceren](#duplicate-workflows).

U kunt de weergave en lay-out van het diagram wijzigen met de volgende elementen:

* **De werkbalk gebruiken**

   Met de werkbalk voor diagrambewerking hebt u toegang tot de functies voor lay-out en uitvoering van de workflow.

   ![](assets/wf-toolbar.png)

   Zo kunt u de layout van het bewerkgereedschap aanpassen: de weergave van het palet en het overzicht, de grootte en de uitlijning van grafische objecten.

   ![](assets/s_user_segmentation_toolbar.png)

   Pictogrammen die betrekking hebben op de voortgangsweergave en de logboekweergave worden in de volgende secties beschreven:

   * [Voortgang weergeven](monitor-workflow-execution.md#displaying-progress)
   * [Logboeken weergeven](monitor-workflow-execution.md#displaying-logs)

* **Objectuitlijning**

   Als u pictogrammen wilt uitlijnen, selecteert u de pictogrammen en klikt u op de knop **[!UICONTROL Align vertically]** of **[!UICONTROL Align horizontally]** pictogram.

   Gebruik de **CTRL** sleutel voor het selecteren van meerdere verspreide activiteiten of voor het deselecteren van een of meer activiteiten. Klik op de achtergrond van het diagram om alles te deselecteren.

* **Afbeeldingsbeheer**

   U kunt het achtergrondbeeld van het diagram evenals die aanpassen met betrekking tot de diverse activiteiten. Zie [Activiteitenafbeeldingen wijzigen](change-activity-images.md).

## Activiteiten configureren {#configure-activities}

Dubbelklik op een activiteit om deze te configureren of klik met de rechtermuisknop en selecteer **[!UICONTROL Open...]**.

>[!NOTE]
>
>Campagneworkflowactiviteiten worden beschreven in [deze sectie](activities.md).

Het eerste lusje bevat de basisconfiguratie. De **[!UICONTROL Advanced]** bevat de extra parameters, die met name worden gebruikt voor het definiëren van gedrag wanneer een fout optreedt, het opgeven van de uitvoeringstermijn voor een activiteit en het invoeren van een initialisatiescript.

Voor een beter inzicht in de activiteiten en een betere leesbaarheid van de workflow kunt u opmerkingen invoeren in de activiteiten.

![](assets/example1-comment.png)

Deze commentaren worden automatisch getoond wanneer de exploitanten over de activiteit scrollen.

![](assets/example2-comment.png)


## Workflowsjablonen {#workflow-templates}

De malplaatjes van het werkschema bevatten de algemene configuratie van eigenschappen en misschien een waaier van activiteiten die binnen een diagram worden samengevoegd. Deze configuratie kan opnieuw worden gebruikt voor het maken van nieuwe workflows die een bepaald aantal vooraf geconfigureerde elementen bevatten

U kunt nieuwe werkstroomsjablonen maken op basis van bestaande sjablonen of een workflow rechtstreeks in een sjabloon wijzigen.

Workflowsjablonen worden opgeslagen in het dialoogvenster **[!UICONTROL Resources > Templates > Workflow templates]** knoop van de Ontdekkingsreiziger.

Naast de gebruikelijke workfloweigenschappen kunt u met de sjablooneigenschappen het uitvoeringsbestand opgeven voor workflows die op basis van deze sjabloon worden gemaakt.

![](assets/wf-template-properties.png)

## Workflows dupliceren {#duplicate-workflows}

U kunt verschillende typen workflows dupliceren. Als de workflow eenmaal is gedupliceerd, worden wijzigingen van de workflow niet overgebracht naar de kopie van de workflow.

>[!CAUTION]
>
>Kopiëren en plakken is beschikbaar in workflows, maar u wordt aangeraden het document te gebruiken **Dupliceren**. Zodra een gekopieerde activiteit, zijn volledige configuratie wordt gehouden. Voor leveringsactiviteiten (E-mail, SMS, pushmelding...) wordt het leveringsobject dat aan de activiteit is gekoppeld ook gekopieerd, wat tot een crash kan leiden.

1. Klik met de rechtermuisknop op een workflow.
1. Klikken **Dupliceren**.

   ![](assets/duplicate-workflows.png)

1. Wijzig in het workflowvenster het workflowlabel.
1. Klikken **Opslaan**.

De dubbele functie is niet rechtstreeks beschikbaar in de weergave van een campagne.

U kunt echter een weergave maken om alle workflows op uw exemplaar weer te geven. In deze weergave kunt u workflows dupliceren met **Dupliceren naar**.

**Een weergave maken**

1. In **Verkenner** Ga naar de map waarin u de weergave wilt maken.
1. Klik met de rechtermuisknop en ga naar **Een nieuwe map toevoegen** > **Proces**, selecteert u **Workflows**.

   ![](assets/add-new-folder-workflows.png)

De nieuwe map **Workflows** wordt gemaakt.

1. Klik met de rechtermuisknop en selecteer **Eigenschappen**.
1. In de **Beperking** tab, inschakelen **Deze map is een weergave** en klik op **Opslaan**.

   ![](assets/folder-is-a-view.png)

De map wordt nu gevuld met alle workflows van uw instantie.

**Een campagneworkflow dupliceren**

1. Selecteer een campagneworkflow in de werkstroomweergave.
1. Klikken met rechtermuisknop **Dupliceren naar**.
1. Wijzig het label.
1. Klikken **Opslaan**.

U kunt de gedupliceerde workflow zien in de werkstroomweergave.
