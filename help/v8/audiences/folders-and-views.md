---
title: Mappen en weergaven
description: Leer hoe u mappen en weergaven beheert in de Campagneverkenner
feature: Audiences, Profiles, Application Settings
role: User
level: Beginner, Intermediate
exl-id: 762dcacc-4aeb-4990-af01-7f793bd69170
version: Campaign v8, Campaign Classic v7
source-git-commit: 567ca1cd8fa6e4f03c8871488152710753ea02f1
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# Mappen en weergaven beheren {#folders-and-views}

De omslagen van de campagne zijn knopen in de ontdekkingsboomstructuur. Gebaseerd op hun type, bevatten zij bepaalde soorten gegevens.

Een weergave is een specifieke map die geen gegevens bevat, maar die gegevens weergeeft die fysiek zijn opgeslagen in andere mappen van hetzelfde type. Als u bijvoorbeeld een leveringsmap naar een weergave stuurt, worden in deze map alle leveringen weergegeven. Deze gegevens kunnen vervolgens worden gefilterd.


>[!NOTE]
>
>Als u weergaven wilt onderscheiden van standaardmappen, wordt hun naam weergegeven in lichtblauw in plaats van zwart.

U kunt machtigingen toewijzen aan mappen om de toegang tot bepaalde gegevens te beperken. [Meer informatie](#restrict-access-to-a-folder)

## Tips en trucs bij het werken met mappen{#best-practices-folders}

* **Gebruik ingebouwde omslagen** om het voor elke betrokken persoon in het project gemakkelijker te maken om de toepassing te gebruiken, te handhaven en problemen op te lossen. Vermijd het creëren van douaneomslagstructuren voor ontvangers, lijsten, leveringen, enz., maar gebruik de standaardomslagen zoals **Beleid**, **Profielen &amp; Doelen**, **het beheer van de Campagne**.

* **creeer subfolders**, bijvoorbeeld sparen uw technische werkschema&#39;s onder de ingebouwde omslag: **[!UICONTROL Administration > Production > Technical Workflows]**, en creeer subfolders per werkschematype.

* **bepaalt en past een noemende overeenkomst** toe, bijvoorbeeld kunt u de werkschema&#39;s in alfabetische orde noemen, zodat zij in de orde van uitvoering, zoals verschijnen:

  A1 - ontvangers van de invoer, begint om 10:00;
A2 - Importopdrachten beginnen om 11.00 uur.

## Een map maken{#create-a-folder}

Als u een map wilt maken, klikt u met de rechtermuisknop op een bestaande map en gebruikt u het contextmenu.

Als u hetzelfde type map wilt maken als de map die u hebt geselecteerd, kiest u de eerste optie in het contextmenu. Selecteer bijvoorbeeld **[!UICONTROL Create a new 'Recipients' folder]** in een map Ontvangers.

![](assets/create-recipient-folder.png)

U kunt de nieuwe map slepen en neerzetten om de boomstructuur van de Campagneverkenner naar wens in te delen.

Als u een ander type map wilt maken, klikt u met de rechtermuisknop op een bestaande map en selecteert u **[!UICONTROL Add new folder]** . U kunt alle typen mappen maken, afhankelijk van de gegevens die moeten worden opgeslagen.

![](assets/add-new-folder.png)

>[!CAUTION]
>
>Deze wijzigingen gelden voor alle campagnegebruikers.

## Een map weergeven{#turn-a-folder-to-a-view}

Een weergave is een specifieke map die geen gegevens bevat, maar die gegevens weergeeft die fysiek zijn opgeslagen in andere mappen van hetzelfde type.

U kunt elke map naar een weergave verplaatsen, maar de map moet leeg zijn. Alle gegevens die in de map zijn opgeslagen, worden verwijderd wanneer u de map naar een weergave verplaatst.

>[!IMPORTANT]
>
>Uit de vakmappen mag niet worden omgezet in een weergave.


>[!CAUTION]
>
>In een weergave worden gegevens weergegeven en hebt u toegang tot deze gegevens, zelfs als de gegevens niet fysiek zijn opgeslagen in de weergavemap. Om toegang tot de inhoud te hebben, moet de exploitant de aangewezen toestemmingen in de bronomslagen, minstens Gelezen toegang hebben.
>
>Als u toegang tot een weergave wilt verlenen zonder toegang tot de bronmap te verlenen, verleent u geen leestoegang tot het bovenliggende knooppunt van de bronmap.

In het onderstaande voorbeeld maken we een nieuwe map waarin alleen Amerikaanse leveringen worden weergegeven op basis van hun interne naam.

1. Creeer a **[!UICONTROL Deliveries]** omslag, en noem het **Leveringen van de V.S.**.
1. Klik met de rechtermuisknop op deze map en selecteer **[!UICONTROL Properties...]** .
1. Selecteer op het tabblad **[!UICONTROL Restriction]** de optie **[!UICONTROL This folder is a view]** . Alle leveringen in het gegevensbestand zullen dan worden getoond.

   ![](assets/this-folder-is-a-view.png)

1. Definieer de filtercriteria van de query-editor in het centrale gedeelte van het venster: alleen de leveringen die overeenkomen met het filter worden weergegeven in de map.

   ![](assets/filter-view.png)

   >[!NOTE]
   >
   >Leer hoe te om vragen in [&#x200B; te ontwerpen deze pagina &#x200B;](create-filters.md#advanced-filters)


>[!CAUTION]
>
>Wanneer het beheren van [&#x200B; transactieoverseinen &#x200B;](../send/transactional.md) gebeurtenissen, moeten de **[!UICONTROL Real time events]** of **[!UICONTROL Batch events]** omslagen niet als meningen op de uitvoeringsinstanties worden geplaatst, aangezien dit tot toestemmingskwesties zou kunnen leiden.

## Uw mappen ordenen{#organize-your-folders}

Standaard wordt boven aan de hiërarchie een nieuwe map toegevoegd.

Blader het **sub-omslagen** lusje van een omslageigenschappen om zijn sub-omslagen te organiseren.

U kunt de mappen verplaatsen met de pijlen aan de rechterkant of de optie **[!UICONTROL Sort the sub-folders in alphabetical order]** selecteren om ze automatisch te sorteren.

![](assets/sort-folders.png)


## Gegevens in een map filteren{#filter-data-in-a-folder}

Als u gegevens wilt filteren die in een map zijn opgeslagen, opent u de eigenschappen van de map en selecteert u het tabblad Beperking.

De map hieronder bevat bijvoorbeeld alleen contactpersonen met een e-mailadres en waarvan de oorsprong niet als &#39;Extern&#39; is gemarkeerd of leeg is.

![](assets/add-a-filter-to-a-folder.png)


## Toegang tot een map beperken{#restrict-access-to-a-folder}

De toestemmingen van het gebruik op omslagen om toegang tot de gegevens van de Campagne te organiseren en te controleren. Leer meer over toestemmingen op omslagen in [&#x200B; deze sectie &#x200B;](../start/folder-permissions.md).
