---
title: Campagne voeren over externe rekeningen
description: Vorm externe rekeningen om Campagne met externe systemen zoals POP3, gegevensbestanden FDA, CRM, opslag, en de oplossingen van Adobe te verbinden.
feature: Application Settings, External Account
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: 776a0e5eead9161b7e2c9d7746c72cba42ea42cb
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 4%

---


# Externe accounts configureren {#config-external-accounts}

Adobe Campaign wordt geleverd met een set vooraf gedefinieerde externe accounts. Als u verbindingen met externe systemen wilt instellen, kunt u nieuwe externe accounts maken.

Externe accounts worden gebruikt door technische processen, zoals technische workflows of workflows voor campagnes. Als u bijvoorbeeld een bestandsoverdracht instelt in een workflow of een gegevensuitwisseling met een andere toepassing (Adobe Target, Experience Manager, enz.), moet u een externe account selecteren.

U kunt externe accounts openen vanuit Adobe Campaign **[!UICONTROL Explorer]** : blader naar **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]** .

![](assets/external-accounts.png)


>[!CAUTION]
>
>* Als gebruiker van Managed Cloud Services worden externe accounts geconfigureerd voor uw exemplaar door Adobe en mogen deze niet worden gewijzigd.
>
>* In de context van een [&#x200B; plaatsing van de Onderneming (FFDA) &#x200B;](../architecture/enterprise-deployment.md), beheert een specifieke **[!UICONTROL Full FDA]** (ffda) externe rekening verbinding tussen het lokale gegevensbestand van de Campagne en het gegevensbestand van de Wolk ([!DNL Snowflake]).
>

## Campagne-specifieke externe rekeningen {#ac-external-accounts}

Adobe Campaign gebruikt de volgende technische accounts om specifieke processen in te schakelen en uit te voeren.

### Stuitberichten {#bounce-mails-external-account}

>[!NOTE]
>
>De Microsoft Exchange Online OAuth 2.0-verificatie voor POP3-mogelijkheden is beschikbaar vanaf Campagne v8.3. Om uw versie te controleren, verwijs naar [&#x200B; deze sectie &#x200B;](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).
>

De **Stuits post** externe rekening specificeert de externe POP3 rekening die moet worden gebruikt om met de e-maildienst te verbinden. Alle servers die voor POP3 toegang worden gevormd kunnen worden gebruikt om terugkeerpost te ontvangen.

Leer meer over binnenkomende e-mails in [&#x200B; deze pagina &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html?lang=nl-NL){target="_blank"}.

![](assets/bounce_external_1.png)

U configureert als volgt de externe account van **[!UICONTROL Bounce mails (defaultPopAccount)]** :

* **[!UICONTROL Server]** - URL van de POP3-server.

* **[!UICONTROL Port]** - POP3-poortnummer van de verbinding. De standaardpoort is 10.

* **[!UICONTROL Account]** - Naam van de gebruiker.

* **[!UICONTROL Password]** - Wachtwoord voor gebruikersaccount.

* **[!UICONTROL Encryption]** - Type gekozen codering tussen **[!UICONTROL By default]** , **[!UICONTROL POP3 + STARTTLS]** , **[!UICONTROL POP3]** of **[!UICONTROL POP3S]** .

* **[!UICONTROL Function]** - Inbound email of SOAP router.

![](assets/bounce_external_2.png)

>[!CAUTION]
>
>Voordat u uw POP3-externe account kunt configureren met Microsoft OAuth 2.0, moet u uw toepassing eerst registreren in de Azure-portal. Raadpleeg [deze pagina](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"} voor meer informatie.
>

Als u een POP3-bestand wilt configureren met Microsoft OAuth 2.0, schakelt u de optie **[!UICONTROL Microsoft OAuth 2.0]** in en vult u de volgende velden in:

* **[!UICONTROL Azure tenant]** - identiteitskaart van Azure (of identiteitskaart van de Folder (huurder)) kan in de **Hoofdzaak** drop-down van uw toepassingsoverzicht in het portaal van Azure worden gevonden.

* **[!UICONTROL Azure Client ID]** - identiteitskaart van de Cliënt (of identiteitskaart van de Toepassing (cliënt) kan in de **Hoofdzaak** drop-down van uw toepassingsoverzicht in het portaal van Azure worden gevonden.

* **[!UICONTROL Azure Client secret]** - identiteitskaart van het geheim van de cliënt kan in de **geheime** kolom van de Cliënt van het **Certificaten &amp; geheimen** menu van uw toepassing in het portaal van Azure worden gevonden.

* **[!UICONTROL Azure Redirect URL]** - Redirect URL kan in het **Authentificatie** menu van uw toepassing in het portaal van Azure worden gevonden. Deze moet eindigen met de volgende syntaxis `nl/jsp/oauth.jsp`, bijvoorbeeld `https://redirect.adobe.net/nl/jsp/oauth.jsp` .

Nadat u uw referenties hebt ingevoerd, klikt u op **[!UICONTROL Setup the connection]** om de configuratie van uw externe account te voltooien.

### Routering {#routing}

Met de externe account van **[!UICONTROL Routing]** kunt u elk kanaal dat beschikbaar is in Adobe Campaign configureren, afhankelijk van de geïnstalleerde pakketten.

Leer meer over extern rekeningsbeheer en leveringsuitvoering in [&#x200B; deze sectie &#x200B;](../architecture/architecture.md#split).

### Uitvoeringsinstantie {#execution-instance}

In de context van transactioneel overseinen, wordt de uitvoeringsinstantie verbonden met de controleinstantie en verbindt hen. Transactionele berichtmalplaatjes worden opgesteld aan de uitvoeringsinstantie. Leer meer over de architectuur van het Centrum van het Bericht in [&#x200B; deze pagina &#x200B;](../architecture/architecture.md#transac-msg-archi).

## Toegang tot externe rekeningen van externe systemen {#external-syst-external-accounts}

### Federated Data Access (FDA) {#fda-external-accounts}

Het **Externe gegevensbestand** type externe rekening wordt gebruikt om met een extern gegevensbestand via Federated Toegang van Gegevens (FDA) te verbinden. Leer meer over de Federatieve optie van de Toegang van Gegevens (FDA) in [&#x200B; deze sectie &#x200B;](../connect/fda.md).

>[!NOTE]
>
>De externe gegevensbestanden compatibel met Adobe Campaign v8 zijn vermeld in de [&#x200B; matrijs van de Verenigbaarheid &#x200B;](../start/compatibility-matrix.md). Voor FDA-verbindingen worden ODBC-stuurprogramma&#39;s gebruikt. Voor Adobe Campaign Managed Cloud Services worden het ODBC-stuurprogramma en de configuratie van de externe account door Adobe ingesteld.

De instellingen voor externe accountconfiguratie zijn afhankelijk van de database-engine. Bij Adobe Campaign Managed Cloud Services wordt de configuratie van externe accounts uitgevoerd door Adobe. Leer meer over deze configuratie in [&#x200B; Adobe Campaign Classic v7 documentatie &#x200B;](https://experienceleague.adobe.com/nl/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts){target="_blank"}.

#### Externe account voor databases {#databricks-external-accounts}

De verbinding van Databricks FDA gebruikt de bestuurder van Databricks ODBC. Vanaf Campagne v8.9.1 ondersteunen Databricks externe accounts OAuth2-verificatie via service principal (niet-interactieve gegevensstroom van client), waardoor beveiligde verificatie voor gefedereerde gegevenstoegang mogelijk is.

Leer meer over de diensthoofden in [&#x200B; documentatie van Microsoft &#x200B;](https://learn.microsoft.com/en-us/azure/databricks/admin/users-groups/service-principals){target="_blank"}.

Om OAuth2 authentificatie via de diensthoofd in Campagne te vormen:

1. De beheerder van de werkruimte van Databases laat de diensthoofden op de werkruimte van Databases toe en produceert geloofsbrieven. Om toegang tot uw gegevensbestanden van Azure met OAuth toe te staan, creeer een geheim OAuth (dat wordt gebruikt om OAuth toegangstokens voor authentificatie te produceren).
2. In Adobe Campaign, creeer of geef een Externe rekening van Gegevensbestanden uit en open **OAuth** tabel.
3. Plak de gegevens in de velden op het tabblad OAuth van de externe account van Databases.
4. Gebruik **[!UICONTROL Test the connection]** om de configuratie te valideren.

### X (voorheen bekend als Twitter) {#twitter-external-account}

Het **Twitter** type externe rekening wordt gebruikt om Campagne met uw rekening van X te verbinden, om berichten namens u te posten. Leer meer over de integratie van X in [&#x200B; deze sectie &#x200B;](../connect/ac-tw.md).

## Externe accounts bij integratie van Adobe-oplossingen {#adobe-integration-external-accounts}

* **Adobe Experience Cloud** - de **[!UICONTROL Adobe Experience Cloud]** externe rekening wordt gebruikt om de Dienst van Identity Management van Adobe (IMS) uit te voeren om met Adobe Campaign te verbinden. Leer meer over de Dienst van Adobe Identity Management (IMS) in [&#x200B; deze sectie &#x200B;](../start/connect.md#logon-to-ac).

* **Analytics van het Web** - de **[!UICONTROL Web Analytics (Adobe Analytics)]** externe rekening wordt gebruikt om gegevensoverdracht van Adobe Analytics aan Adobe Campaign te vormen. Leer meer over Adobe Campaign - de integratie van Adobe Analytics in [&#x200B; deze pagina &#x200B;](../connect/ac-aa.md).

* **Adobe Experience Manager** - de **[!UICONTROL AEM]** externe rekening staat u toe om de inhoud van uw e-mailleveringen evenals uw formulieren direct in Adobe Experience Manager te beheren. Leer meer over Adobe Campaign - de integratie van Adobe Experience Manager in [&#x200B; deze pagina &#x200B;](../connect/ac-aem.md).


## Externe CRM-connectorrekeningen {#crm-external-accounts}

* **Microsoft Dynamics CRM** - de **[!UICONTROL Microsoft Dynamics CRM]** externe rekening staat u toe om de gegevens van Microsoft Dynamics in Adobe Campaign in te voeren en uit te voeren. Leer meer over Adobe Campaign - de integratie van Microsoft Dynamics CRM in [&#x200B; deze pagina &#x200B;](../connect/ac-ms-dyn.md).

* **Salesforce.com** - de **[!UICONTROL Salesforce CRM]** externe rekening staat u toe om de gegevens van Salesforce in Adobe Campaign in te voeren en uit te voeren. Leer meer over Adobe Campaign - Salesforce.com de integratie van CRM in [&#x200B; deze pagina &#x200B;](../connect/ac-sfdc.md).

## Externe rekeningen voor gegevensoverdracht {#transfer-data-external-accounts}

Deze externe accounts kunnen worden gebruikt om gegevens te importeren of te exporteren naar Adobe Campaign met behulp van een **[!UICONTROL Transfer file]** -workflowactiviteit. Leer meer over **overdracht van het Dossier** in werkschema&#39;s in [&#x200B; deze pagina &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html?lang=nl-NL){target="_blank"}.

* **FTP en SFTP** - de **FTP** externe rekening laat u toegang tot een server buiten Adobe Campaign vormen en testen. Als u verbindingen wilt instellen met externe systemen, zoals SFTP- of FTP-servers die worden gebruikt voor bestandsoverdracht, kunt u uw eigen externe accounts maken.

  Hiertoe geeft u in deze externe account het adres en de referenties op die worden gebruikt om de verbinding met de SFTP- of FTP-server tot stand te brengen.

  >[!NOTE]
  >
  >Vanaf versie 8.5 kunt u nu veilig verifiëren met een persoonlijke sleutel wanneer u uw SFTP-externe account configureert. [&#x200B; Leer meer op zeer belangrijk beheer &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=nl-NL){target="_blank"}.

* **de Eenvoudige Dienst van de Opslag van Amazon (S3)** - de **schakelaar van AWS S3** kan worden gebruikt om gegevens in te voeren of uit te voeren naar Adobe Campaign gebruikend de activiteit van het a **[!UICONTROL Transfer file]** werkschema. Wanneer u dit nieuwe externe account instelt, moet u de volgende data opgeven:

   * **[!UICONTROL AWS S3 Account Server]**: URL van uw server, in de vorm `<S3bucket name>.s3.amazonaws.com/<s3object path>` .

   * **[!UICONTROL AWS access key ID]**: Leer hoe te om uw de toegangs belangrijkste identiteitskaart van AWS in [&#x200B; documentatie van Amazon &#x200B;](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"} te vinden.

   * **[!UICONTROL Secret access key to AWS]**: Leer hoe te om uw geheime toegangstoets aan AWS in [&#x200B; documentatie van Amazon &#x200B;](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"} te vinden.

   * **[!UICONTROL AWS Region]**: Leer meer op de gebieden van AWS in [&#x200B; documentatie van Amazon &#x200B;](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

   * Met het selectievakje **[!UICONTROL Use server side encryption]** kunt u het bestand opslaan in de modus S3-versleuteling. Leer hoe te om toegangs zeer belangrijke identiteitskaart en geheime toegangssleutel in [&#x200B; documentatie van Amazon &#x200B;](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"} te vinden.

* **de Opslag van Azure Blob** - de **Azure** externe rekening kan worden gebruikt om gegevens in te voeren of naar Adobe Campaign uit te voeren gebruikend een **[!UICONTROL Transfer file]** werkschemaactiviteit. Om de **Azure** externe rekening te vormen om met Adobe Campaign te werken, moet u de volgende details verstrekken:

   * **[!UICONTROL Server]**: URL van uw Azure Blob-opslagserver.

   * **[!UICONTROL Encryption]**: Type codering: **[!UICONTROL None]** of **[!UICONTROL SSL]** .

   * **[!UICONTROL Access key]**: Leer hoe te om uw **[!UICONTROL Access key]** in [&#x200B; documentatie van Microsoft &#x200B;](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"} te vinden.

* **de Stof van Microsoft** - de **&#x200B;**&#x200B;externe rekening van de Stof van Microsoft staat u toe om gegevens tussen de Stof van Microsoft en Adobe Campaign in te voeren gebruikend de **[!UICONTROL Transfer file]** werkschemaactiviteit. Voer de volgende gegevens in om deze integratie te configureren:

   * **[!UICONTROL Server]**: URL van uw Microsoft Fabric-opslagserver.

   * **[!UICONTROL Application ID]**: De unieke id van de toepassing die wordt gebruikt om Microsoft Fabric-bronnen te verifiëren en te openen.

   * **[!UICONTROL Client secret]**: De verificatiesleutel of het wachtwoord die aan de toepassing is gekoppeld en die nodig is om veilig verbinding te maken met Microsoft Fabric.
