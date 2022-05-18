---
title: Privacy-aanvragen beheren in campagne
description: Leer hoe u privacyverzoeken beheert in Campagne
feature: Audiences
role: Data Engineer
level: Beginner
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 47%

---

# Privacy-aanvragen beheren in campagne {#privacy}

<!--Adobe Campaign is a powerful tool for collecting and processing large volume of data, including personal information and sensitive data. It is therefore essential that you receive and monitor consent from your recipients.-->

>[!NOTE]
>
>Deze mogelijkheid is beschikbaar vanaf Campagne v8.3. Als u uw versie wilt controleren, raadpleegt u [deze sectie](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

Doordat u in Adobe Campaign verzoeken voor toegang en verwijdering kunt afhandelen, kunt u zich gemakkelijker houden aan de privacyregels.

Voor het uitvoeren van deze verzoeken moet u de **Privacy-kernservice**-integratie gebruiken. Verzoeken om toegang tot persoonsgegevens die van de Privacy-kernservice naar alle Experience Cloud-oplossingen worden gepusht, worden door Campaign automatisch behandeld via een speciale workflow. [Meer informatie](#create-privacy-request)

Adobe biedt Data Controllers de hulpmiddelen aan om de verzoeken van de Privacy voor gegevens tot stand te brengen en te verwerken die in Campagne worden opgeslagen. Nochtans, is het uw verantwoordelijkheid als Controlemechanisme van Gegevens om de identiteit van het Onderwerp te verifiëren dat het verzoek indient, en te bevestigen dat de gegevens aan het aanvrager zijn teruggekeerd over het Onderwerp van Gegevens zijn. Meer informatie over persoonlijke gegevens en de verschillende entiteiten die gegevens beheren in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#personal-data){target=&quot;_blank&quot;}.

![](../assets/do-not-localize/speech.png) Meer informatie over de **Recht op toegang** en de **Recht op vergeten** (aanvraag verwijderen) in [Adobe Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#right-access-forgotten){target=&quot;_blank&quot;}.

## Een naamruimte definiëren {#namespaces}

Voordat u een privacyverzoek maakt, moet u **de naamruimte definiëren** gebruikt u. De naamruimte is de sleutel die wordt gebruikt om de betrokkene in de Adobe Campaign-database te identificeren.

>[!NOTE]
>
>Zie voor meer informatie over naamruimten de categorie [Documentatie Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html){target=&quot;_blank&quot;}.

Adobe Campaign biedt momenteel geen ondersteuning voor het importeren van naamruimten uit de service Naamruimte Experience Platform. Daarom moet u, zodra u een namespace op de dienst van Namespace van de Identiteit hebt gecreeerd, manueel het overeenkomstige namespace in de interface van Adobe Campaign tot stand brengen. Volg de onderstaande stappen om dit te doen.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Maak een naamruimte op het tabblad [Naamruimteservice voor identiteiten](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target=&quot;_blank&quot;}.

1. Wanneer [naamruimten weergeven](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target=&quot;_blank&quot;} beschikbaar voor uw organisatie, krijgt u de volgende naamruimte, bijvoorbeeld:

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

1. Ga in Adobe Campaign naar **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** en selecteert u **[!UICONTROL New]**.

   ![](assets/privacy-namespaces-new.png)

1. Voer een **[!UICONTROL Label]** in.

1. Vul de nieuwe naamruimtedetails in zodat deze overeenkomen met de naamruimte die u hebt gemaakt op de service Naamruimte identiteit:

   * de **[!UICONTROL AEC Namespace ID]** moet overeenkomen met het kenmerk &quot;id&quot;;
   * de **[!UICONTROL Internal name]** moet overeenkomen met het kenmerk &quot;code&quot;;
   * de **[!UICONTROL Reconciliation key]** moet overeenkomen met het kenmerk &quot;idType&quot;.

   ![](assets/privacy-namespaces-details.png)

   De **[!UICONTROL Reconciliation key]** wordt gebruikt om het gegevensonderwerp in de Adobe Campaign-database te identificeren.

1. Doeltoewijzing selecteren <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)--> om op te geven hoe de naamruimte in Adobe Campaign moet worden afgestemd.

   >[!NOTE]
   >
   >    Als u verschillende doeltoewijzingen wilt gebruiken, moet u één naamruimte per doeltoewijzing maken.

1. Sla uw wijzigingen op.

U kunt nu verzoeken om toegang tot persoonsgegevens maken op basis van uw nieuwe naamruimte. Als u meerdere naamruimten gebruikt, maakt u één privacyverzoek per naamruimte voor dezelfde reconciliatiewaarde.

## Een privacyverzoek maken {#create-privacy-request}

De **Privacy Core-service** Dankzij de integratie kunt u uw privacyverzoeken automatiseren in een context met meerdere oplossingen via één JSON API-aanroep. Adobe Campaign behandelt automatisch de verzoeken die van de Dienst van de Kern van de Privacy door een specifieke werkschema worden geduwd.

>[!CAUTION]
>
>Voor de verzoeken van de Privacy om worden verwerkt, moet u op uw instantie van Adobe Campaign een namespace tot stand brengen die namespace aanpast die u op de dienst van Namespace van de Identiteit van het Experience Platform creeerde.

Zie de [Privacy Service Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=nl){target=&quot;_blank&quot;} documentatie voor meer informatie over het maken van privacyverzoeken van de Privacy Core Service.

Elke de kernde dienstbaan van de Privacy wordt verdeeld in veelvoudige verzoeken van de Privacy in Adobe Campaign die op hoeveel namespaces worden gebruikt, één verzoek beantwoordt aan één namespace.

Bovendien kan één taak op meerdere instanties worden uitgevoerd. Daarom worden er meerdere bestanden gemaakt voor één taak. Als een verzoek bijvoorbeeld twee naamruimten bevat en op drie instanties wordt uitgevoerd, worden in totaal zes bestanden verzonden. Eén bestand per naamruimte en instantie.

Het patroon voor een bestandsnaam is: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: Campaign-instantienaam
* **NamespaceId**: naamruimte-ID identiteitsservice van de gebruikte naamruimte
* **Afstemmingssleutel**: gecodeerde afstemmingssleutel

>[!CAUTION]
>
>Als u een verzoek wilt indienen met het aangepaste naamruimtetype, gebruikt u de [JSON-methode](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=nl#json){target=&quot;_blank&quot;} en voegt u de namespaceId toe aan het verzoek, of gebruikt u de [API-aanroep](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=nl#access-delete){target=&quot;_blank&quot;} om het verzoek in te dienen.
>
>Gebruik alleen de [Privacy-gebruikersinterface](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=nl#request-builder){target=&quot;_blank&quot;} om verzoeken in te dienen met het standaardnaamruimtetype.

### Tabellen die worden doorzocht bij het verwerken van aanvragen {#list-of-tables}

Bij het uitvoeren van een verzoek om verwijdering of toegang tot persoonsgegevens zoekt Adobe Campaign alle gegevens van de betrokkene op basis van de waarde voor **[!UICONTROL Reconciliation value]** in alle tabellen die een koppeling bevatten naar de ontvangsttabel (eigen type).

Hier volgt de lijst van ingebouwde tabellen waarmee rekening wordt gehouden bij het uitvoeren van verzoeken om toegang tot persoonsgegevens:

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

Hier volgen de verschillende statussen voor privacyverzoeken in Adobe Campaign:

* **[!UICONTROL New]**/**[!UICONTROL Retry pending]**: in uitvoering, de workflow heeft het verzoek nog niet verwerkt.
* **[!UICONTROL Processing]**/**[!UICONTROL Retry in progress]**: de workflow verwerkt het verzoek.
* **[!UICONTROL Delete pending]**: in de workflow zijn alle te verwijderen gegevens van ontvangers geïdentificeerd.
* **[!UICONTROL Delete in progress]**: de workflow verwerkt de verwijdering.
* **[!UICONTROL Complete]**: de verwerking van het verzoek is zonder fout voltooid.
* **[!UICONTROL Error]**: er is een fout opgetreden in de workflow. De reden wordt weergegeven in de kolom **[!UICONTROL Request status]** in de lijst met verzoeken om toegang tot persoonsgegevens. **[!UICONTROL Error data not found]** betekent bijvoorbeeld dat er in de database geen ontvangersgegevens zijn gevonden die overeenkomen met de **[!UICONTROL Reconciliation value]** van de betrokkene.

**Verwante onderwerpen in Campaign Classic v7-documentatie:**

* [Privacy en instemming](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target=&quot;_blank&quot;}

* [Aan de slag met het privacybeheer](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html){target=&quot;_blank&quot;}

* [Regels inzake privacybeheer](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#privacy-management-regulations){target=&quot;_blank&quot;} (GDPR, CCPA, PDPA en LGPD)

* [Uitschakelen voor de verkoop van persoonlijke gegevens](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html){target=&quot;_blank&quot;} (specifiek voor de CCPA)