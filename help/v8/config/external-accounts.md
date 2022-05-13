---
title: Campagne voeren over externe rekeningen
description: Campagne voeren over externe rekeningen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 5%

---

# Externe accounts configureren

Adobe Campaign wordt geleverd met een set vooraf gedefinieerde externe accounts. Als u verbindingen met externe systemen wilt instellen, kunt u nieuwe externe accounts maken.

Externe accounts worden gebruikt door technische processen, zoals technische workflows of workflows voor campagnes. Als u bijvoorbeeld een bestandsoverdracht instelt in een workflow of een gegevensuitwisseling met een andere toepassing (Adobe Target, Experience Manager, enzovoort), moet u een externe account selecteren.

U kunt externe accounts openen vanuit Adobe Campaign **[!UICONTROL Explorer]**: bladeren naar **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>In de context van een [Implementatie van ondernemingen (FFDA)](../architecture/enterprise-deployment.md)een specifieke **[!UICONTROL Full FDA]** (ffd bis) externe account beheert verbinding tussen lokale database voor campagne en Cloud-database ([!DNL Snowflake]).
></br>Als Beheerde gebruiker van Cloud Services, wordt deze externe rekening gevormd voor uw instantie door Adobe. Het mag niet gewijzigd worden.

## Campagne-specifieke externe rekeningen

Adobe Campaign gebruikt de volgende technische accounts om specifieke processen in te schakelen en uit te voeren.

![](../assets/do-not-localize/speech.png)  Als Beheerde gebruiker van Cloud Services, vormt Adobe alle campagne-specifieke externe rekeningen voor u.

### Niet bezorgde mails {#bounce-mails-external-account}

>[!NOTE]
>
>De Microsoft Exchange Online OAuth 2.0-verificatie voor POP3-mogelijkheden is beschikbaar vanaf Campagne v8.3. Als u uw versie wilt controleren, raadpleegt u [deze sectie](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

De **Stuitberichten** externe account geeft de externe POP3-account aan die moet worden gebruikt voor verbinding met de e-mailservice. Alle servers die voor POP3 toegang worden gevormd kunnen worden gebruikt om terugkeerpost te ontvangen.

![](../assets/do-not-localize/book.png) Meer informatie over inkomende e-mails in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;}

![](assets/bounce_external_1.png)

Om het **[!UICONTROL Bounce mails (defaultPopAccount)]** externe rekening:

* **[!UICONTROL Server]**

   URL van de POP3-server.

* **[!UICONTROL Port]**

   POP3-poortnummer van verbinding. De standaardpoort is 110.

* **[!UICONTROL Account]**

   Naam van de gebruiker.

* **[!UICONTROL Password]**

   Wachtwoord voor gebruikersaccount.

* **[!UICONTROL Encryption]**

   Type gekozen codering tussen **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** of **[!UICONTROL POP3S]**.
De **Stuitberichten** externe account geeft de externe POP3-account aan die moet worden gebruikt voor verbinding met de e-mailservice. Alle servers die voor POP3 toegang worden gevormd kunnen worden gebruikt om terugkeerpost te ontvangen.

* **[!UICONTROL Function]**

   Binnenkomende e-mail of SOAP-router

![](assets/bounce_external_2.png)

>[!IMPORTANT]
>
>Voordat u uw POP3-externe account configureert met Microsoft OAuth 2.0, moet u uw toepassing eerst registreren in de Azure-portal. Raadpleeg [deze pagina](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) voor meer informatie.

Om POP3 extern te vormen gebruikend Microsoft OAuth 2.0, controleer **[!UICONTROL Microsoft OAuth 2.0]** en vult de volgende velden in:

* **[!UICONTROL Azure tenant]**

   Azure ID (of Directory (huurder) ID) is te vinden in de **Essentiële elementen** vervolgkeuzelijst van het overzicht van uw toepassing in de Azure-portal.

* **[!UICONTROL Azure Client ID]**

   Client-id (of toepassings-id (client)) is te vinden in de **Essentiële elementen** vervolgkeuzelijst van het overzicht van uw toepassing in de Azure-portal.

* **[!UICONTROL Azure Client secret]**:

   Identiteitskaart van het geheim van de cliënt kan in worden gevonden **Clientgegevens** uit de **Certificaten en geheimen** in het Azure-portaal.

* **[!UICONTROL Azure Redirect URL]**:

   De omleidings-URL vindt u in het dialoogvenster **Verificatie** in het Azure-portaal. Het moet eindigen met de volgende syntaxis `nl/jsp/oauth.jsp`, bijvoorbeeld `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

Nadat u de andere gegevens hebt ingevoerd, kunt u op **[!UICONTROL Setup the connection]** om de configuratie van uw externe account te voltooien.

### Routering {#routing}

De **[!UICONTROL Routing]** met een externe account kunt u elk kanaal dat beschikbaar is in Adobe Campaign configureren, afhankelijk van de geïnstalleerde pakketten.

>[!CAUTION]
>
>De **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) externe account **mogen** moet zijn ingeschakeld in Adobe Campaign v8.

### Uitvoeringsinstantie {#execution-instance}

In de context van transactioneel overseinen, zijn de uitvoeringsinstanties verbonden met de controleinstantie en hen verbinden. Transactionele berichtmalplaatjes worden opgesteld aan de uitvoeringsinstantie.

![](../assets/do-not-localize/glass.png) Meer informatie over de architectuur van Message Center in [deze pagina](../architecture/architecture.md#transac-msg-archi).

## Toegang tot externe rekeningen van externe systemen

* **Externe database (FDA)**

   Gebruik de **Externe database** Typ een externe account om via FDA verbinding te maken met een externe database.

   Externe databases die compatibel zijn met Adobe Campaign v8, worden vermeld in de [Compatibiliteitsmatrix](../start/compatibility-matrix.md)

   ![](../assets/do-not-localize/glass.png) Meer informatie over de FDA-optie (Federated Data Access) vindt u in [deze sectie](../connect/fda.md).

## Externe accounts voor integratie van Adobe-oplossingen

* **Adobe Experience Cloud**

   De **[!UICONTROL Adobe Experience Cloud]** Met een externe account wordt Adobe IMS geïmplementeerd om verbinding te maken met de Adobe Campaign-console via een Adobe ID.

   ![](../assets/do-not-localize/glass.png) Meer informatie over Adobe Identity Management Service (IMS) in [deze sectie](../start/connect.md#connect-ims).

* **Web Analytics**

   Gebruik de **[!UICONTROL Web Analytics (Adobe Analytics)]** externe account voor het configureren van gegevensoverdracht van Adobe Analytics naar Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Meer informatie over de integratie van Adobe Campaign en Adobe Analytics in [deze pagina](../connect/ac-aa.md).

   ![](../assets/do-not-localize/speech.png)  Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support) om Adobe Analytics te integreren met Campagne.

   * **Adobe Experience Manager**
   De **[!UICONTROL AEM]** Met een extern account kunt u de inhoud van uw e-mailleveringen en uw formulieren rechtstreeks in Adobe Experience Manager beheren.

   ![](../assets/do-not-localize/glass.png) Meer informatie over de integratie van Adobe Campaign en Adobe Analytics in [deze pagina](../connect/ac-aem.md).

   ![](../assets/do-not-localize/speech.png)  Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support) Adobe Experience Manager integreren met Adobe Campaign.


## CRM-connector externe accounts

* **Microsoft Dynamics CRM**

   De **[!UICONTROL Microsoft Dynamics CRM]** Met een externe account kunt u Microsoft Dynamics-gegevens importeren en exporteren naar Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Meer informatie over de integratie van Adobe Campaign - Microsoft Dynamics CRM in [deze pagina](../connect/ac-ms-dyn.md).

* **Salesforce.com**

   De **[!UICONTROL Salesforce CRM]** Met een externe account kunt u Salesforce-gegevens importeren en exporteren naar Adobe Campaign.

   ![](../assets/do-not-localize/glass.png) Meer informatie over de integratie van Adobe Campaign - Salesforce.com CRM in [deze pagina](../connect/ac-sfdc.md).

## Externe rekeningen voor gegevensoverdracht

Deze externe accounts kunnen worden gebruikt voor het importeren of exporteren van gegevens naar Adobe Campaign met behulp van een **[!UICONTROL Transfer file]** workflowactiviteit.

![](../assets/do-not-localize/book.png) Meer informatie over bestandsoverdracht in workflows in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;}

* **FTP en SFTP**

   De **FTP** Met een externe account kunt u toegang tot een server buiten Adobe Campaign configureren en testen. Als u verbindingen wilt instellen met externe systemen, zoals SFTP- of FTP-servers 898 die worden gebruikt voor bestandsoverdracht, kunt u uw eigen externe accounts maken.
Hiertoe geeft u in deze externe account het adres en de referenties op die worden gebruikt om de verbinding met de SFTP- of FTP-server tot stand te brengen.

* **Amazon Simple Storage Service (S3)**

   De **AWS S3** -connector kan worden gebruikt om gegevens te importeren of naar Adobe Campaign te exporteren met behulp van een **[!UICONTROL Transfer file]** workflowactiviteit. Wanneer u dit nieuwe externe account instelt, moet u de volgende data opgeven:

   * **[!UICONTROL AWS S3 Account Server]**: URL van uw server, als volgt ingevuld:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: Meer informatie over het vinden van je AWS-toegangs-id in [Amazon-documentatie](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

   * **[!UICONTROL Secret access key to AWS]**: Meer informatie over hoe je geheime toegangssleutel voor AWS kunt vinden in [Amazon-documentatie](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

   * **[!UICONTROL AWS Region]**: Meer informatie over AWS-regio&#39;s in [Amazon-documentatie](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

   * De **[!UICONTROL Use server side encryption]** kunt u het bestand opslaan in de gecodeerde modus van S3. Leer hoe u de toegangstoets-id en de geheime toegangssleutel kunt vinden in [Amazon-documentatie](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Azure Blob Storage**

   De **Azure** een externe account kan worden gebruikt om gegevens naar Adobe Campaign te importeren of te exporteren met behulp van een **[!UICONTROL Transfer file]** workflowactiviteit. Om het **Azure** Als u met Adobe Campaign wilt werken, moet u de volgende gegevens opgeven:

   * **[!UICONTROL Server]**: URL van uw Azure Blob-opslagserver.

   * **[!UICONTROL Encryption]**: Type codering tussen **[!UICONTROL None]** of **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Leer hoe u uw **[!UICONTROL Access key]** in [Microsoft-documentatie](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).
