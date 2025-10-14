---
product: campaign
title: Levering
description: Meer informatie over de workflowactiviteit van het leveringstype
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 58574983-86c7-46f5-b41b-bae90171048d
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 1%

---

# Levering{#delivery}

A **levering** - type activiteit laat u een leveringsactie tot stand brengen. Deze kan worden samengesteld uit invoerelementen.

Om het te vormen, geef de activiteit uit en ga de leveringsopties in.

![](assets/edit_diffusion.png)

1. **Levering**

   U kunt:

   * Akte op de levering in de binnenkomende overgang wordt gespecificeerd die. Selecteer hiertoe de eerste optie in de sectie **[!UICONTROL Delivery]** van het venster.

     Deze optie kan worden gebruikt wanneer een vorige werkstroomactiviteit reeds tot stand heeft gebracht of de levering gespecificeerd. Dit kan, zoals in het onderstaande voorbeeld, door een activiteit van het zelfde type worden gedaan die een uitgaande overgang heeft geproduceerd.

     In het volgende voorbeeld wordt de levering voor het eerst gemaakt. De populatie en de inhoud worden later gedefinieerd. Daarna, wordt de informatie voor deze drie elementen opnieuw ingegaan in een nieuwe leveringsactiviteit gebruikend de binnenkomende overgang zodat dit kan worden verzonden.

     ![](assets/specified_transition_option_exemple.png)

   * Selecteer de betrokken levering rechtstreeks. Selecteer hiertoe de optie **[!UICONTROL Explicit]** en selecteer de levering in de vervolgkeuzelijst van het veld **[!UICONTROL Delivery]** .

     De lijst toont onvoltooide leveringen in de **Geleveringen** omslag door gebrek. Als u andere campagnes wilt openen, klikt u op het pictogram **[!UICONTROL Select link]** .

     ![](assets/diffusion_edit_1.png)

     Selecteer de campagne in de vervolgkeuzelijst van het veld **[!UICONTROL Folder]** of klik op **[!UICONTROL Display sub-levels]** om alle leveringen in submappen weer te geven:

     ![](assets/diffusion_edit_2.png)

     Nadat u de leveringsactie hebt geselecteerd, kunt u de inhoud weergeven door op het pictogram **[!UICONTROL Edit link]** te klikken.

   * Maak een script om de levering te berekenen. Selecteer hiertoe de optie **[!UICONTROL Computed by a script]** en voer het script in. U kunt een invoervenster openen door op de optie **[!UICONTROL Edit...]** te klikken. In het volgende voorbeeld wordt de id van de levering hersteld:

     ![](assets/diffusion_edit_3.png)

   * Maak een nieuwe levering. Selecteer hiertoe de optie **[!UICONTROL New, created from a template]** en selecteer de leveringssjabloon waarop de levering wordt gebaseerd.

     ![](assets/diffusion_edit_4.png)

     Klik op het pictogram **[!UICONTROL Select link]** om door de mappen te bladeren en klik op het pictogram **[!UICONTROL Edit link]** als u de inhoud van de geselecteerde sjabloon wilt weergeven.

1. **Ontvangers**

   Ontvangers kunnen door de binnenkomende gebeurtenissen worden opgegeven, bijvoorbeeld na het importeren van een bestand of in de leveringsactie. Ze kunnen ook in een of meer bestanden worden opgeslagen.

   ![](assets/diffusion_edit_5.png)

1. **Inhoud**

   De inhoud van het bericht kan in de levering of de binnenkomende gebeurtenis worden bepaald.

   ![](assets/diffusion_edit_6.png)

1. **uit te voeren Actie**

   U kunt de levering maken, voorbereiden, starten, het doel schatten of een proefdruk verzenden.

   ![](assets/diffusion_edit_7.png)

   Selecteer het type actie dat moet worden uitgevoerd:

   * **[!UICONTROL Save]** : met deze optie kunt u de levering maken en opslaan. Het zal het niet analyseren of leveren.
   * **[!UICONTROL Estimate the target]**: met deze optie kunt u het leveringsdoel berekenen om het potentieel (eerste analysefase) te beoordelen. Deze actie is het equivalent van het selecteren van de **[!UICONTROL Estimate the population to be targeted]** optie en het klikken **[!UICONTROL Analyze]** wanneer het verzenden van een levering naar het belangrijkste doel via **Levering**.
   * **[!UICONTROL Prepare]** : met deze optie kunt u het volledige analyseproces uitvoeren (doelberekening en inhoudsvoorbereiding). De levering wordt niet verzonden. Deze actie is het equivalent van het selecteren van de **[!UICONTROL Deliver as soon as possible]** optie en het klikken **[!UICONTROL Analyze]** wanneer het verzenden van een levering naar het belangrijkste doel met **Levering**.
   * **[!UICONTROL Send a proof]** : met deze optie kunt u een bewijs van de levering verzenden. Deze actie is het equivalent van het klikken van de **[!UICONTROL Send a proof]** knoop in de toolbar van een levering met **Levering**
   * **[!UICONTROL Prepare and start]** : met deze optie wordt het volledige analyseproces gestart (doelberekening en inhoudsvoorbereiding) en wordt de levering verzonden. Deze actie is het equivalent van het klikken **[!UICONTROL Deliver as soon as possible]**, **[!UICONTROL Analyze]**, en **[!UICONTROL Confirm delivery]** optie wanneer het verzenden van een levering naar het belangrijkste doel met **Levering**.

   Met de **[!UICONTROL Act on a delivery]** -activiteit die verderop in de workflow wordt gebruikt, kunt u alle resterende stappen starten die vereist zijn voor het starten van de levering (doelberekening, inhoudsvoorbereiding, levering). Voor meer op dit, verwijs naar [&#x200B; controle van de Levering &#x200B;](delivery-control.md).

   De volgende opties zijn ook beschikbaar:

   * **[!UICONTROL Generate an outbound transition]**

     Creeert een uitgaande overgang die aan het eind van uitvoering zal worden geactiveerd. U kunt kiezen al dan niet om het doel van de uitgaande levering terug te winnen.

   * **[!UICONTROL Do not recover target]**

     Herstelt niet het doel van de uitgaande leveringsactie.

   * **[!UICONTROL Processing errors]**

     Verwijs naar [&#x200B; de controle van de Levering &#x200B;](delivery-control.md).

   Het **manuscript** lusje laat u de leveringsparameters wijzigen.

   ![](assets/edit_diffusion_fil_script.png)

## Voorbeeld: leveringsworkflow {#example--delivery-workflow}

Maak een nieuwe workflow en voeg activiteiten toe zoals in de onderstaande afbeelding wordt getoond:

![](assets/new-workflow-5.png)

Open de **activiteit van de Levering** en bepaal de eigenschappen als volgt:

* Selecteer **[!UICONTROL New, created from a template]** in de sectie **[!UICONTROL Delivery]** en selecteer een leveringssjabloon.
* Selecteer **[!UICONTROL Specified in the delivery]** in de sectie **[!UICONTROL Recipients]** .
* Houd de optie **[!UICONTROL Prepare]** in de sectie **[!UICONTROL Action to execute]** .

![](assets/new-workflow-param-delivery.png)

Klik op **[!UICONTROL OK]** om het eigenschappenvenster te sluiten. U hebt net een activiteit gevormd die bestaat uit het creëren van en het voorbereiden van een nieuwe levering die op een leveringsmalplaatje wordt gebaseerd het waarvan doel binnen het zal worden gespecificeerd.

Open de **activiteit van de Goedkeuring** en bepaal de eigenschappen als volgt:

1. Selecteer in het veld **[!UICONTROL Assignment type]** een groep waarin u bent geregistreerd. Als u verbinding hebt via de account &#39;admin&#39;, selecteert u de groep Beheer.
1. Voer vervolgens een titel in en voeg de volgende tekst in de berichttekst in:

   ```
   Do you wish to approve delivery (<%= vars.recCount %> recipient(s))?
   ```

   Dit is een bericht dat een expressie bevat die in JavaScript is geschreven: **[!UICONTROL vars.recCount]** geeft het aantal ontvangers aan waarvoor de vorige taak is uitgevoerd. Voor verdere informatie over de uitdrukkingen van JavaScript, verwijs naar [&#x200B; manuscripten en malplaatjes van JavaScript &#x200B;](javascript-scripts-and-templates.md).

   ![](assets/new-workflow-param-validation.png)

   De taak van de Goedkeuring is gedetailleerd in [&#x200B; Goedkeuring &#x200B;](approval.md).

## Invoerparameters {#input-parameters}

Leverings-id als de optie **[!UICONTROL Specified in the transition]** is geselecteerd in de sectie **[!UICONTROL Delivery]** .

* deliveryId
* tableName
* schema

Elke binnenkomende gebeurtenis moet een doel specificeren dat door deze parameters wordt bepaald.

>[!NOTE]
>
>Deze parameter wordt alleen weergegeven als de optie **[!UICONTROL Specified by inbound event(s)]** is geselecteerd in de sectie **[!UICONTROL Recipients]** .

* filename

  Volledige naam van het gegenereerde bestand als de optie **[!UICONTROL File(s) specified by inbound event(s)]** is geselecteerd in de sectie **[!UICONTROL Recipients]** .

* contentId

  Inhoud-id als de optie **[!UICONTROL Specified by inbound events]** is geselecteerd in de sectie **[!UICONTROL Content]** .

## Uitvoerparameters {#output-parameters}

* tableName
* schema
* recCount

Deze reeks van drie waarden identificeert het doel resulterend uit de levering. **[!UICONTROL tableName]** is de naam van de tabel die de id&#39;s van het doel memoriseert, **[!UICONTROL schema]** is het schema van de populatie (gewoonlijk nms:ontvanger) en **[!UICONTROL recCount]** is het aantal elementen in de tabel.

De overgang verbonden aan het complement heeft de zelfde parameters.

>[!NOTE]
>
>Er zijn geen uitvoerparameters wanneer de optie **[!UICONTROL Do not recover target]** is geselecteerd.
