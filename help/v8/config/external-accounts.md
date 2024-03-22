---
title: Campagne voeren over externe rekeningen
description: Campagne voeren over externe rekeningen
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 3%

---


# Externe accounts configureren {#config-external-accounts}

Adobe Campaign wordt geleverd met een set vooraf gedefinieerde externe accounts. Als u verbindingen met externe systemen wilt instellen, kunt u nieuwe externe accounts maken.

Externe accounts worden gebruikt door technische processen, zoals technische workflows of workflows voor campagnes. Als u bijvoorbeeld een bestandsoverdracht instelt in een workflow of een gegevensuitwisseling met een andere toepassing (Adobe Target, Experience Manager, enzovoort), moet u een externe account selecteren.

U kunt externe accounts openen vanuit Adobe Campaign **[!UICONTROL Explorer]**: blader naar **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>* Als Beheerde gebruiker van Cloud Servicen, worden de externe rekeningen gevormd voor uw geval door Adobe en moeten niet worden gewijzigd.
>
>* In de context van een [Implementatie in het kader van Enterprise (FFDA)](../architecture/enterprise-deployment.md)een specifieke **[!UICONTROL Full FDA]** (ffd bis) externe account beheert verbinding tussen lokale database voor campagne en Cloud-database ([!DNL Snowflake]).
>

## Campagne-specifieke externe rekeningen {#ac-external-accounts}

Adobe Campaign gebruikt de volgende technische accounts om specifieke processen in te schakelen en uit te voeren.

### Stuitberichten {#bounce-mails-external-account}

>[!NOTE]
>
>De Microsoft Exchange Online OAuth 2.0-verificatie voor POP3-mogelijkheden is beschikbaar vanaf Campagne v8.3. Als u uw versie wilt controleren, raadpleegt u [deze sectie](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

De **Stuitberichten** externe account geeft de externe POP3-account aan die moet worden gebruikt voor verbinding met de e-mailservice. Alle servers die voor POP3 toegang worden gevormd kunnen worden gebruikt om terugkeerpost te ontvangen.

Meer informatie over inkomende e-mails in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html){target="_blank"}.

![](assets/bounce_external_1.png)

Om te vormen **[!UICONTROL Bounce mails (defaultPopAccount)]** externe rekening:

* **[!UICONTROL Server]** - URL van de POP3-server.

* **[!UICONTROL Port]** - POP3-poortnummer van de verbinding. De standaardpoort is 10.

* **[!UICONTROL Account]** - Naam van de gebruiker.

* **[!UICONTROL Password]** - Wachtwoord voor gebruikersaccount.

* **[!UICONTROL Encryption]** - Type gekozen codering tussen **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** of **[!UICONTROL POP3S]**.

  De **Stuitberichten** externe account geeft de externe POP3-account aan die moet worden gebruikt voor verbinding met de e-mailservice. Alle servers die voor POP3 toegang worden gevormd kunnen worden gebruikt om terugkeerpost te ontvangen.

* **[!UICONTROL Function]** - Binnenkomende e-mail of SOAP-router

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Voordat u uw POP3-externe account configureert met Microsoft OAuth 2.0, moet u uw toepassing eerst registreren in de Azure-portal. Raadpleeg voor meer informatie deze [page](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.
>

Om POP3 extern te vormen gebruikend Microsoft OAuth 2.0, controleer **[!UICONTROL Microsoft OAuth 2.0]** en vult de volgende velden in:

* **[!UICONTROL Azure tenant]** - Azure ID (of Directory (huurder) ID) is te vinden in de **Essentiële elementen** vervolgkeuzelijst van het overzicht van uw toepassing in de Azure-portal.

* **[!UICONTROL Azure Client ID]** - Client-id (of toepassings-(client)id) is te vinden in de **Essentiële elementen** vervolgkeuzelijst van het overzicht van uw toepassing in de Azure-portal.

* **[!UICONTROL Azure Client secret]** - De geheime ID van de cliënt kan in worden gevonden **Clientgeheimen** kolom van de **Certificaten en geheimen** in het Azure-portaal.

* **[!UICONTROL Azure Redirect URL]** - De omleidings-URL vindt u in het dialoogvenster **Verificatie** in het Azure-portaal. Het moet eindigen met de volgende syntaxis `nl/jsp/oauth.jsp`, bijvoorbeeld `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

  Nadat u de andere gegevens hebt ingevoerd, kunt u op **[!UICONTROL Setup the connection]** om de configuratie van uw externe account te voltooien.

### Routering {#routing}

De **[!UICONTROL Routing]** met een externe account kunt u elk kanaal dat beschikbaar is in Adobe Campaign configureren, afhankelijk van de geïnstalleerde pakketten.

### Uitvoeringsinstantie {#execution-instance}

In de context van transactioneel overseinen, zijn de uitvoeringsinstanties verbonden met de controleinstantie en hen verbinden. Transactionele berichtmalplaatjes worden opgesteld aan de uitvoeringsinstantie. Meer informatie over de architectuur van Message Center in [deze pagina](../architecture/architecture.md#transac-msg-archi).

## Toegang tot externe rekeningen van externe systemen {#external-syst-external-accounts}

* **Externe database (FDA)** - de **Externe database** type external account wordt gebruikt om verbinding te maken met een externe database via Federated Data Access (FDA). Meer informatie over FDA (Federated Data Access) in [deze sectie](../connect/fda.md).

  Externe databases die compatibel zijn met Adobe Campaign v8, worden vermeld in de [Compatibiliteitsmatrix](../start/compatibility-matrix.md)

* **X (voorheen bekend als Twitter)** - de **Twitter** type external account wordt gebruikt om campagne aan te sluiten op uw X account, om berichten namens u te posten. Meer informatie over X-integratie in [deze sectie](../connect/ac-tw.md).

## Adobe Solution Integration externe accounts {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - de **[!UICONTROL Adobe Experience Cloud]** Met een externe account wordt Adobe Identity Management Service (IMS) geïmplementeerd om verbinding te maken met de Adobe Campaign. Meer informatie over Adobe Identity Management Service (IMS) in [deze sectie](../start/connect.md#logon-to-ac).

* **Webanalyse** - de **[!UICONTROL Web Analytics (Adobe Analytics)]** externe account wordt gebruikt om gegevensoverdracht van Adobe Analytics naar Adobe Campaign te configureren. Meer informatie over de integratie van Adobe Campaign en Adobe Analytics in [deze pagina](../connect/ac-aa.md).

* **Adobe Experience Manager** - de **[!UICONTROL AEM]** Met een extern account kunt u de inhoud van uw e-mailleveringen en uw formulieren rechtstreeks in Adobe Experience Manager beheren. Meer informatie over de integratie van Adobe Campaign en Adobe Analytics in [deze pagina](../connect/ac-aem.md).


## Externe CRM-connectorrekeningen {#crm-external-accounts}

* **Microsoft Dynamics CRM** - de **[!UICONTROL Microsoft Dynamics CRM]** Met een externe account kunt u Microsoft Dynamics-gegevens importeren en exporteren naar Adobe Campaign. Meer informatie over de integratie van Adobe Campaign - Microsoft Dynamics CRM in [deze pagina](../connect/ac-ms-dyn.md).

* **Salesforce.com** - de **[!UICONTROL Salesforce CRM]** Met een externe account kunt u Salesforce-gegevens importeren en exporteren naar Adobe Campaign. Meer informatie over Adobe Campaign - Salesforce.com CRM-integratie in [deze pagina](../connect/ac-sfdc.md).

## Externe rekeningen voor gegevensoverdracht {#transfer-data-external-accounts}

Deze externe accounts kunnen worden gebruikt voor het importeren of exporteren van gegevens naar Adobe Campaign met behulp van een **[!UICONTROL Transfer file]** workflowactiviteit. Meer informatie over **Bestandsoverdracht** in workflows in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html){target="_blank"}.

* **FTP en SFTP** - de **FTP** Met een externe account kunt u toegang tot een server buiten Adobe Campaign configureren en testen. Als u verbindingen wilt instellen met externe systemen, zoals SFTP- of FTP-servers 898 die worden gebruikt voor bestandsoverdracht, kunt u uw eigen externe accounts maken.

  Hiertoe geeft u in deze externe account het adres en de referenties op die worden gebruikt om de verbinding met de SFTP- of FTP-server tot stand te brengen.

  >[!NOTE]
  >
  >Vanaf versie 8.5 kunt u nu veilig verifiëren met een persoonlijke sleutel wanneer u uw SFTP-externe account configureert. [Meer informatie over sleutelbeheer](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html){target="_blank"}.

* **Amazon Simple Storage Service (S3)** - de **AWS S3** -connector kan worden gebruikt om gegevens te importeren of naar Adobe Campaign te exporteren met behulp van een **[!UICONTROL Transfer file]** workflowactiviteit. Wanneer u dit nieuwe externe account instelt, moet u de volgende data opgeven:

   * **[!UICONTROL AWS S3 Account Server]**: URL van de server, als volgt ingevuld:   `<S3bucket name>.s3.amazonaws.com/<s3object path>`

   * **[!UICONTROL AWS access key ID]**: Meer informatie over het zoeken naar je AWS-toegangs-id in [Amazon-documentatie](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

   * **[!UICONTROL Secret access key to AWS]**: Meer informatie over het zoeken naar je geheime toegangssleutel tot AWS in [Amazon-documentatie](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

   * **[!UICONTROL AWS Region]**: Meer informatie over AWS-regio&#39;s in [Amazon-documentatie](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * De **[!UICONTROL Use server side encryption]** kunt u het bestand opslaan in de gecodeerde modus van S3. Leer hoe u de toegangstoets-id en de geheime toegangssleutel kunt vinden in [Amazon-documentatie](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Azure Blob Storage** - de **Azure** een externe account kan worden gebruikt om gegevens te importeren of naar Adobe Campaign te exporteren met behulp van een **[!UICONTROL Transfer file]** workflowactiviteit. Om te vormen **Azure** Als u met Adobe Campaign wilt werken, moet u de volgende gegevens opgeven:

   * **[!UICONTROL Server]**: URL van uw Azure Blob-opslagserver.

   * **[!UICONTROL Encryption]**: Type codering tussen **[!UICONTROL None]** of **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Leer hoe u uw **[!UICONTROL Access key]** in [Microsoft-documentatie](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
