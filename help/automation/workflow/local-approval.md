---
product: campaign
title: Lokale goedkeuring
description: Lokale goedkeuring
feature: Workflows, Approvals
role: User
exl-id: 172b6827-ddfc-4c6e-87c9-eb49e73ab3ab
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# Lokale goedkeuring{#local-approval}

Wanneer het in een het richten werkschema wordt geïntegreerd, **[!UICONTROL Local approval]** Met activiteit kunt u een goedkeuringsproces voor ontvangers instellen voordat de levering wordt verzonden.

![](assets/local_validation_0.png)

>[!CAUTION]
>
>Om deze activiteit te gebruiken, moet u de Verdeelde module van de Marketing hebben gekocht, die een optie van de Campagne is. Controleer hiervoor uw licentieovereenkomst.

Voor een voorbeeld van het **[!UICONTROL Local approval]** activiteit met een distributiemalplaatje, verwijs naar [De lokale goedkeuringsactiviteit gebruiken](local-approval-activity.md).

Begin door een etiket voor de activiteit in te voeren en **[!UICONTROL Action to execute]** veld:

![](assets/local_validation_1.png)

* Selecteer de **[!UICONTROL Target approval notification]** optie om een bericht te verzenden e-mail naar lokale supervisors vóór de levering, vragend hen om de ontvangers goed te keuren die aan hen worden toegewezen.

* **Incrementele query**: hiermee kunt u een query uitvoeren en de uitvoering ervan plannen. Zie de [Incrementele query](incremental-query.md) sectie.

  ![](assets/local_validation_intro_3.png)

## Doelgoedkeuring {#target-approval-notification}

In dit geval worden de **[!UICONTROL Local approval]** de activiteit wordt geplaatst tussen upstream gericht en de levering:

![](assets/local_validation_2.png)

De velden die moeten worden ingevuld in het geval van een kennisgeving voor goedkeuring als doel zijn:

![](assets/local_validation_3.png)

* **[!UICONTROL Distribution context]**: selecteer de **[!UICONTROL Specified in the transition]** als u een **[!UICONTROL Split]** type activiteit om de doelpopulatie te beperken. In dit geval wordt de distributiesjabloon in de splitsingsactiviteit ingevoerd. Als u de doelpopulatie niet beperkt, selecteert u de optie **[!UICONTROL Explicit]** en voert u hier de distributiesjabloon in **[!UICONTROL Data distribution]** veld.

  Raadpleeg voor meer informatie over het maken van een sjabloon voor gegevensdistributie [Het aantal subsetrecords per gegevensdistributie beperken](split.md#limiting-the-number-of-subset-records-per-data-distribution).

* **[!UICONTROL Approval management]**

   * Selecteer de leveringssjabloon en het onderwerp dat voor het e-mailbericht wordt gebruikt. Er is een standaardsjabloon beschikbaar: **[!UICONTROL Local approval notification]**. U kunt ook een beschrijving toevoegen die boven de lijsten met ontvangers wordt weergegeven in de goedkeurings- en feedbackberichten.
   * Geef de **[!UICONTROL Approval type]** dat overeenkomt met de goedkeuringstermijn (datum of uiterste datum vanaf het begin van de goedkeuring). Op deze datum wordt de workflow opnieuw gestart en wordt bij het bepalen van de doelen geen rekening gehouden met de ontvangers die niet zijn goedgekeurd. Zodra de berichten zijn verzonden, wordt de activiteit een rij gevormd zodat de lokale supervisors hun contacten kunnen goedkeuren.

     >[!NOTE]
     >
     >Wanneer het goedkeuringsproces wordt gestart, wordt de activiteit standaard drie dagen voortgezet.

     U kunt ook een of meer herinneringen toevoegen om lokale toezichthouders te laten weten dat de deadline nadert. Om dit te doen, klik **[!UICONTROL Add a reminder]** koppeling.

* **[!UICONTROL Complementary set]**: de **[!UICONTROL Generate complement]** Met deze optie kunt u een tweede set genereren die alle niet-goedgekeurde doelen bevat.

  >[!NOTE]
  >
  >Deze optie is standaard uitgeschakeld.

## Feedbackrapport leveren {#delivery-feedback-report}

In dit geval worden de **[!UICONTROL Local approval]** activiteit wordt geplaatst na levering:

![](assets/local_validation_4.png)

In het geval van een feedbackrapport voor levering moeten de volgende velden worden ingevuld:

![](assets/local_validation_workflow_4.png)

* Selecteer de **[!UICONTROL Specified in the transition]** als de levering is ingevoerd tijdens een eerdere activiteit. Selecteren **[!UICONTROL Explicit]** om de levering in de lokale goedkeuringsactiviteit te specificeren.
* Selecteer de leveringssjabloon en het object van het e-mailbericht. Er is een standaardsjabloon: **[!UICONTROL Local approval notification]**.

## Voorbeeld: een workflowlevering goedkeuren {#example--approving-a-workflow-delivery}

In dit voorbeeld wordt getoond hoe u een goedkeuringsproces voor workflowlevering instelt. Raadpleeg voor meer informatie over het maken van workflows voor levering de [Voorbeeld: leveringsworkflow](delivery.md#example--delivery-workflow) sectie.

Een exploitant kan een levering op één van twee manieren goedkeuren: het gebruiken van de Web-pagina verbonden in het e-mailbericht, of via de Console van de Cliënt.

* Webgoedkeuring

  Met het e-mailbericht dat naar beheerders van de groep Beheerders wordt verzonden, kunt u het leveringsdoel goedkeuren. Het bericht gebruikt de gedefinieerde tekst en de JavaScript-expressie wordt vervangen door de berekende waarde (in dit geval &#39;574&#39;)

  Als u de levering wilt goedkeuren, klikt u op de desbetreffende koppeling en meldt u zich aan bij de Adobe Campaign Client Console.

  ![](assets/new-workflow-valid-webaccess.png)

  Maak een keuze en klik op de knop **[!UICONTROL Submit]** knop.

  ![](assets/new-workflow-valid-webaccess-confirm.png)

* Goedkeuring via de clientconsole

  In de boomstructuur worden de **[!UICONTROL Administration > Production > Objects created automatically > Approvals pending]** knooppunt bevat de lijst met taken die moeten worden goedgekeurd door de operator die momenteel is verbonden. In de lijst moet één regel worden weergegeven. Dubbelklik op deze regel om te reageren. Het volgende venster wordt weergegeven:

![](assets/new-workflow-7.png)

Selecteren **Ja** en klik vervolgens op **[!UICONTROL Approve]**. U ontvangt een bericht met de mededeling dat de reactie is opgenomen.

Ga terug naar het workflowscherm: Na tien seconden of zo wordt het diagram als volgt weergegeven:

![](assets/new-workflow-8.png)

De workflow heeft de opdracht **[!UICONTROL Delivery control]** taak, wat in dit geval betekent dat de eerder gemaakte levering wordt gestart. De workflow is zonder fouten voltooid.
