---
product: campaign
title: Werken met leveringssjablonen
description: Leer hoe u leveringssjablonen maakt en gebruikt in Campagne
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
source-git-commit: 822d1bee472330b6195ad9527a7e23e90c7650b4
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 7%

---

# Werken met leveringssjabloon{#creating-a-delivery-template}

Gebruik leveringssjablonen om de creatieve vormgeving te standaardiseren, zodat u sneller campagnes kunt uitvoeren en lanceren.

Een sjabloon kan systematisch het volgende bevatten:

* Typologieën
* Afzender en antwoordadressen
* Basisblokken voor personalisatie
* Koppelingen naar spiegelpagina&#39;s en naar het opzeggen van abonnementen koppelingen
* Inhoud, bedrijfslogo of handtekening
* Andere leveringseigenschappen, zoals middelgeldigheid, retry parameters, of quarantaine montages.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#delivery-template-video)

Om een leveringsmalplaatje tot stand te brengen, kunt u een ingebouwde malplaatje dupliceren, een bestaande levering in een malplaatje omzetten of een leveringsmalplaatje van kras tot stand brengen.

## Een bestaande sjabloon kopiëren{#copy-an-existing-template}

De campagne komt met een reeks ingebouwde malplaatjes voor elk kanaal: email, push, SMS, direct mail en nog veel meer.

De gemakkelijkste manier om een leveringsmalplaatje tot stand te brengen is een ingebouwde malplaatje te dupliceren en aan te passen.

Voer de onderstaande stappen uit om een leveringssjabloon te dupliceren:

1. Bladeren naar **[!UICONTROL Resources > Templates > Delivery templates]** in Adobe Campaign.
1. Selecteer een ingebouwde leveringssjabloon. Ingebouwde sjablonen worden in de lijst opgenomen.
1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Duplicate]**.

   ![](assets/duplicate-built-in-template.png)

1. Definieer de sjablooninstellingen en sla de nieuwe sjabloon op.

   ![](assets/delivery-template-new.png)

De sjabloon wordt toegevoegd aan de lijst met leveringssjablonen. U kunt deze nu selecteren wanneer u een nieuwe levering maakt.

![](assets/select-the-new-template.png)

## Een bestaande levering converteren naar een sjabloon {#convert-an-existing-delivery}

Een levering kan in een malplaatje voor nieuwe herhaalde leveringsacties worden omgezet.

Volg onderstaande stappen om een levering naar een sjabloon om te zetten:

1. Selecteer de levering in de leveringslijst, toegankelijk via de **[!UICONTROL Campaign management]** knooppunt van Campaign Explorer.

1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Actions > Save as template...]**.

   ![](assets/save-as-template.png)

1. Bewerk de leveringseigenschappen en selecteer de map waarin de nieuwe sjabloon moet worden opgeslagen (in het menu **[!UICONTROL Folder]** (veld) en de map waarin de op basis van deze sjabloon gemaakte items moeten worden gemaakt (in de **[!UICONTROL Execution folder]** veld).

   ![](assets/template-select-folders.png)

## Een nieuwe sjabloon maken {#create-a-new-template}

>[!NOTE]
>
>Om configuratiefouten te vermijden, adviseert Adobe u [een ingebouwde sjabloon dupliceren](#copy-an-existing-template) en pas de eigenschappen aan in plaats van een nieuwe sjabloon te maken.

Voer de onderstaande stappen uit om een volledig nieuwe leveringssjabloon te configureren:

1. Bladeren naar de **Bronnen** map in Campagneverkenner en selecteer **Sjablonen** dan **Afleveringssjablonen**.
1. Klikken **Nieuw** in de werkbalk om een nieuwe leveringssjabloon te maken.
1. Stel de **Label** en de **Interne naam** van de map.
1. Sla de sjabloon op en open deze opnieuw.
1. Van de **Eigenschappen** aanpassen.
1. In de **Algemeen** de locaties die zijn geselecteerd in het dialoogvenster **Uitvoermap**, **Map**, en **Routering** vervolgkeuzemenu&#39;s.
1. Voltooi de **E-mailparameters** rubriek met je e-mailonderwerp en doelgroep.
1. Voeg uw **HTML-inhoud** om uw sjabloon aan te passen, kunt u een koppeling naar een spiegel en een koppeling naar een abonnement weergeven.
1. Selecteer **Voorvertoning** tab. In de **Aanpassing testen** vervolgkeuzelijst, selecteert u **Ontvanger** om een voorbeeld van de sjabloon weer te geven als het gekozen profiel.
1. Klikken **Opslaan**. Je template is nu klaar om te worden gebruikt in een levering.


## Een levering maken met een sjabloon{#create-a-delivery-from-a-template}

Als u een levering wilt maken op basis van een bestaande sjabloon, selecteert u de sjabloon in de lijst met beschikbare leveringssjablonen.

![](assets/select-the-new-template.png)

Als de sjabloon niet wordt weergegeven, klikt u op de knop **[!UICONTROL Select link]** aan de rechterkant van het veld om door campagnemappen te bladeren.

![](assets/browse-templates.png)

Selecteer de gewenste directory in het menu **[!UICONTROL Folder]** of klik op de knop **[!UICONTROL Display sub-levels]** pictogram om de inhoud van de mappen in de substructuren van de huidige map weer te geven.

Selecteer de leveringssjabloon die u wilt gebruiken en klik op **[!UICONTROL Ok]**.

### Een sjabloon uitvoeren {#execute-a-template}

U kunt de uitvoering van een sjabloon rechtstreeks vanuit de sjabloonlijst starten zonder eerst een levering te maken.

Selecteer hiertoe de sjabloon die u wilt uitvoeren en klik met de rechtermuisknop. Selecteer **[!UICONTROL Actions>Execute the delivery template...]**.

U kunt ook **[!UICONTROL File>Actions>Execute the delivery template...]**.

![](assets/execute-delivery-template.png)

Voer de leveringsparameters in en klik op **[!UICONTROL Send]**.

Deze actie produceert een levering in de omslag verbonden aan het malplaatje. De naam van deze levering is de naam van het leveringsmalplaatje waarvan het werd gecreeerd.


## Tutorialvideo’s {#delivery-template-video}

### Hoe te om een leveringsmalplaatje te vormen

De volgende video toont hoe u een sjabloon voor een ad-hoclevering kunt configureren.

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### Eigenschappen voor leveringssjablonen instellen

In de volgende video ziet u hoe u de eigenschappen van de leveringssjabloon instelt en wordt elke eigenschap in detail uitgelegd.

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### Hoe te om een ad hoc leveringsmalplaatje op te stellen

In deze video wordt uitgelegd hoe u een sjabloon voor ad-hoc e-maillevering kunt implementeren. In deze video wordt het verschil tussen een e-maillevering en een leveringsworkflow uitgelegd.

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

Er zijn aanvullende Campaign Classic-hoe-kan-video&#39;s beschikbaar [hier](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=nl).
