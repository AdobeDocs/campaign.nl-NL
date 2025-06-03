---
title: Privacy-aanvragen beheren in campagne
description: Leer hoe u privacyverzoeken beheert in Campagne
feature: Privacy
role: Admin
level: Beginner
exl-id: 0f81d318-dbfd-45c8-b391-b1d14d23e9c8
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 33%

---

# Privacy-aanvragen beheren in campagne {#privacy}

Afhankelijk van de aard van uw bedrijf en de rechtsgebieden waaronder het werkt, zijn uw gegevensbewerkingen mogelijk onderworpen aan wettelijke privacyregels. Deze verordeningen geven uw klanten vaak het recht om toegang tot de gegevens te verzoeken u van hen verzamelt, en het recht om de schrapping van die opgeslagen gegevens te verzoeken. Deze verzoeken van klanten om hun persoonlijke gegevens worden bedoeld als &quot;verzoeken van de Privacy&quot;door de documentatie.

Adobe biedt Data Controllers de hulpmiddelen om de verzoeken van de Privacy voor gegevens tot stand te brengen en te verwerken die in Campaign worden opgeslagen. Nochtans, is het uw verantwoordelijkheid als Controlemechanisme van Gegevens om de identiteit van het Onderwerp te verifiëren dat het verzoek indient, en te bevestigen dat de gegevens aan het aanvrager zijn teruggekeerd over het Onderwerp van Gegevens zijn. Leer meer over persoonlijke gegevens en de verschillende entiteiten die gegevens in [ Adobe Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=nl-NL#personal-data){target="_blank"} beheren.


Om het verzoek van de Privacy in Campagne te beheren, moet u eerst [ een namespace ](#namespaces) bepalen. U kunt vervolgens privacyverzoeken maken en beheren. Om privacyverzoeken uit te voeren, gebruik de **Adobe Privacy Service** integratie. De privacyverzoeken die van Privacy Service aan alle oplossingen van Adobe Experience Cloud worden geduwd worden automatisch behandeld door Campaign via een specifieke workflow. [Meer informatie](#create-privacy-request)

Leer over het **recht op Toegang** en het **Recht worden vergeten** (schrappingsverzoek) in [ Adobe Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=nl-NL#right-access-forgotten){target="_blank"}.


>[!NOTE]
>
>Deze mogelijkheid is beschikbaar vanaf Campagne v8.3. Om uw versie te controleren, verwijs naar [ deze sectie ](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

## Een naamruimte definiëren {#namespaces}

Alvorens een verzoek van de Privacy tot stand te brengen, moet u **namespace** bepalen om te gebruiken. Namespace is de sleutel die wordt gebruikt om het Onderwerp van Gegevens in het gegevensbestand te identificeren.

>[!NOTE]
>
>Leer meer over identiteit namespaces in [ documentatie van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=nl){target="_blank"}.

Adobe Campaign biedt momenteel geen ondersteuning voor het importeren van naamruimten uit de service Experience Platform Identity Namespace. Daarom moet u, zodra u een namespace op de dienst van Namespace van de Identiteit hebt gecreeerd, manueel het overeenkomstige namespace in de interface van Adobe Campaign tot stand brengen. Volg de onderstaande stappen om dit te doen.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Creeer een namespace op de [ dienst Namespace van de Identiteit ](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target="_blank"}.

1. Wanneer [ een lijst makend van de identiteit namespaces ](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target="_blank"} beschikbaar voor uw organisatie, krijgt u namespace volgende details, bijvoorbeeld:

   ```
   {
           "updateTime": 1632903236731,
           "code": "lumanamespace",
           "status": "ACTIVE",
           "description": "new namespace for Luma privacy requests",
           "id": 10998717,
           "createTime": 1632903236731,
           "idType": "Email",
           "namespaceType": "Custom",
           "name": "Luma Namespace",
           "custom": true
   }
   ```

1. Blader in Adobe Campaign naar **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** en selecteer **[!UICONTROL New]** .

   ![](assets/privacy-namespaces-new.png)

1. Voer een **[!UICONTROL Label]** in.

1. Vul de nieuwe naamruimtedetails in zodat deze overeenkomen met de naamruimte die u hebt gemaakt op de service Naamruimte identiteit:

   * moet **[!UICONTROL AEC Namespace ID]** overeenkomen met het kenmerk &quot;id&quot;
   * **[!UICONTROL Internal name]** moet overeenkomen met het kenmerk &quot;code&quot;
   * moet **[!UICONTROL Reconciliation key]** overeenkomen met het kenmerk &quot;idType&quot;

   ![](assets/privacy-namespaces-details.png)

   Het veld **[!UICONTROL Reconciliation key]** wordt gebruikt om het gegevensonderwerp in de Adobe Campaign-database te identificeren.

1. Selecteer een doeltoewijzing <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)--> om op te geven hoe de naamruimte in Adobe Campaign moet worden afgestemd.

   >[!NOTE]
   >
   >Als u meerdere doeltoewijzingen moet gebruiken, maakt u één naamruimte per doeltoewijzing.

1. Sla uw wijzigingen op.

U kunt nu verzoeken om toegang tot persoonsgegevens maken op basis van uw nieuwe naamruimte. Als u meerdere naamruimten gebruikt, maakt u één privacyverzoek per naamruimte voor dezelfde reconciliatiewaarde.

## Een privacyverzoek maken {#create-privacy-request}

Dankzij de integratie van **[!DNL Adobe Experience Platform Privacy Service]** kunt u uw privacyverzoeken automatiseren in een context met meerdere oplossingen via één JSON API-aanroep. Adobe Campaign behandelt automatisch de verzoeken die vanuit de Privacy Service worden ingediend via een speciale workflow.

Raadpleeg de documentatie bij de [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=nl){target="_blank"} om te ontdekken hoe u verzoeken om toegang tot persoonsgegevens kunt maken vanuit de Privacy-kernservice.

Elke **[!DNL Privacy Service]** -taak wordt opgedeeld in meerdere Privacy-aanvragen in Adobe Campaign op basis van het aantal naamruimten dat wordt gebruikt, één aanvraag die overeenkomt met één naamruimte.

Bovendien kan één taak op meerdere instanties worden uitgevoerd. Daarom worden er meerdere bestanden gemaakt voor één taak. Als een verzoek bijvoorbeeld twee naamruimten bevat en op drie instanties wordt uitgevoerd, worden in totaal zes bestanden verzonden. Eén bestand per naamruimte en instantie.

Het patroon voor een bestandsnaam is: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: Campaign-instantienaam
* **NamespaceId**: naamruimte-ID identiteitsservice van de gebruikte naamruimte
* **Afstemmingssleutel**: gecodeerde afstemmingssleutel

>[!CAUTION]
>
>Om een verzoek voor te leggen gebruikend het type van douanenamespace, hefboomwerking de [ methode JSON ](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=nl#json){target="_blank"} en namespaceId toe te voegen aan het verzoek, of de [ API vraag ](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=nl#access-delete){target="_blank"} te gebruiken om het verzoek te doen.
>
>Gebruik slechts het [ gebruikersinterface van de Privacy ](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=nl#request-builder){target="_blank"} om verzoeken voor te leggen gebruikend het standaardnamespacetype.

### Tabellen die worden doorzocht bij het verwerken van aanvragen {#list-of-tables}

Bij het uitvoeren van een verzoek om verwijdering of toegang tot persoonsgegevens zoekt Adobe Campaign alle gegevens van de betrokkene op basis van de waarde voor **[!UICONTROL Reconciliation value]** in alle tabellen die een koppeling bevatten naar de ontvangsttabel (eigen type).

De lijst van ingebouwde lijsten die in rekening worden gebracht wanneer het uitvoeren van de verzoeken van de Privacy is:

* Ontvangers (recipient)
* Verzendingslog ontvangers (broadLogRcp)
* Trackinglog ontvangers (trackingLogRcp)
* Verzendingslog gearchiveerde gebeurtenis (broadLogEventHisto)
* Content van lijst met ontvangers (rcpGrpRel)
* Aanbiedingsvoorstel voor bezoeker (propositionVisitor)
* Bezoekers (visitor)
* Lidmaatschapsgeschiedenis (subHisto)
* Lidmaatschappen (subscription)
* Aanbiedingsvoorstel voor ontvanger (propositionRcp)

Als u aangepaste tabellen hebt gemaakt met een koppeling naar de ontvangsttabel (eigen type), wordt hiermee ook rekening gehouden. Als u bijvoorbeeld een transactietabel hebt met een koppeling naar de ontvangsttabel en een transactiedetailtabel met een koppeling naar de transactietabel, wordt met beide rekening gehouden.
<!--
>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.-->

### Statussen van privacyverzoeken {#privacy-request-statuses}

Hieronder vindt u de verschillende statussen voor privacyverzoeken in Adobe Campaign en hoe u deze kunt interpreteren:

* **[!UICONTROL New]**/**[!UICONTROL Retry pending]**: in uitvoering, de workflow heeft het verzoek nog niet verwerkt.
* **[!UICONTROL Processing]**/**[!UICONTROL Retry in progress]**: de workflow verwerkt het verzoek.
* **[!UICONTROL Delete pending]**: in de workflow zijn alle te verwijderen gegevens van ontvangers geïdentificeerd.
* **[!UICONTROL Delete in progress]**: de workflow verwerkt de verwijdering.
* **[!UICONTROL Complete]**: de verwerking van het verzoek is zonder fout voltooid.
* **[!UICONTROL Error]**: er is een fout opgetreden in de workflow. De reden wordt weergegeven in de kolom **[!UICONTROL Request status]** in de lijst met verzoeken om toegang tot persoonsgegevens. **[!UICONTROL Error data not found]** betekent bijvoorbeeld dat er in de database geen ontvangersgegevens zijn gevonden die overeenkomen met de **[!UICONTROL Reconciliation value]** van de betrokkene.

**Verwante onderwerpen in de documentatie van Campaign Classic v7:**

* [Privacy en instemming](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=nl-NL){target="_blank"}

* [ Aan de slag met het Beheer van de Privacy ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=nl){target="_blank"}

* [ Verordeningen op het beheer van de Privacy ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=nl-NL#privacy-management-regulations){target="_blank"} (GDPR, CCPA, PDPA, en LGPD)

* [ Opt-out voor de Verkoop van Persoonlijke Informatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html?lang=nl-NL){target="_blank"} (specifiek voor CCPA)
