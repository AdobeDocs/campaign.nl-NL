---
title: Campagne voeren over externe rekeningen
description: Campagne voeren over externe rekeningen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 4%

---

# Externe accounts configureren

Adobe Campaign wordt geleverd met een set vooraf gedefinieerde externe accounts. Als u verbindingen met externe systemen wilt instellen, kunt u nieuwe externe accounts maken.

Externe accounts worden gebruikt door technische processen, zoals technische workflows of workflows voor campagnes. Als u bijvoorbeeld een bestandsoverdracht instelt in een workflow of een gegevensuitwisseling met een andere toepassing (Adobe Target, Experience Manager, enzovoort), moet u een externe account selecteren.

U kunt externe accounts openen vanuit Adobe Campaign **[!UICONTROL Explorer]**: Blader naar **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>Een specifieke **[!UICONTROL Full FDA]** (ffda) externe account beheert de verbinding tussen de lokale database van Campagne en de Cloud-database ([!DNL Snowflake]).
>
>Als Beheerde gebruiker van Cloud Services, wordt deze externe rekening gevormd voor uw instantie door Adobe. Het mag niet gewijzigd worden.


## Campagne-specifieke externe rekeningen

Adobe Campaign gebruikt de volgende technische accounts om specifieke processen in te schakelen en uit te voeren.

?? Als Beheerde gebruiker van Cloud Services, vormt Adobe alle campagne-specifieke externe rekeningen voor u.

* **Stuitberichten (POP3)**

   Met de externe account **Bounce mails** wordt de externe POP3-account opgegeven die moet worden gebruikt om verbinding te maken met de e-mailservice. Alle servers die voor POP3 toegang worden gevormd kunnen worden gebruikt om terugkeerpost te ontvangen.

   ↗️ meer informatie over binnenkomende e-mails in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html){target=&quot;_blank&quot;

* **Routering**

   Met de externe account **[!UICONTROL Routing]** kunt u elk kanaal dat beschikbaar is in Adobe Campaign configureren, afhankelijk van de geïnstalleerde pakketten.

   >[!CAUTION]
   >
   >De **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) externe account **mag niet** zijn ingeschakeld in Adobe Campaign v8.

* **Uitvoeringsinstantie**

   In de context van transactioneel overseinen, zijn de uitvoeringsinstanties verbonden met de controleinstantie en hen verbinden. Transactionele berichtmalplaatjes worden opgesteld aan de uitvoeringsinstantie.

   ?? Meer informatie over de architectuur van het Centrum van het Bericht in [deze pagina](../dev/architecture.md#transac-msg-archi).

## Toegang tot externe rekeningen van externe systemen

* **Externe database (FDA)**

   Gebruik de **External database** type external account om verbinding te maken met een externe database via FDA.

   Externe databases die compatibel zijn met Adobe Campaign v8, worden vermeld in de [Compatibility matrix](../start/compatibility-matrix.md)

   ?? Meer informatie over de optie Federated Data Access (FDA) in [deze sectie](../connect/fda.md).

## Externe accounts voor integratie van Adobe-oplossingen

* **Adobe Experience Cloud**

   De externe **[!UICONTROL Adobe Experience Cloud]**-account wordt gebruikt om Adobe IMS te implementeren voor verbinding met de Adobe Campaign-console met behulp van een Adobe ID.

   ?? Meer informatie over Adobe Identity Management Service (IMS) vindt u in [deze sectie](../start/connect.md#connect-ims).

* **Web Analytics**

   Met de externe **[!UICONTROL Web Analytics (Adobe Analytics)]**-account kunt u gegevensoverdracht van Adobe Analytics naar Adobe Campaign configureren.

   ?? Meer informatie over Adobe Campaign - Adobe Analytics integratie in [deze pagina](../connect/ac-aa.md).

   ?? Als Beheerde gebruiker van Cloud Services, [contact Adobe](../start/campaign-faq.md#support) om Adobe Analytics met Campagne te integreren.

   * **Adobe Experience Manager**
   Met de externe account **[!UICONTROL AEM]** kunt u de inhoud van uw e-mailleveringen en uw formulieren rechtstreeks in Adobe Experience Manager beheren.

   ?? Meer informatie over Adobe Campaign - Adobe Analytics integratie in [deze pagina](../connect/ac-aem.md).

   ?? Als Beheerde gebruiker van Cloud Services, [contacteer Adobe](../start/campaign-faq.md#support) om Adobe Experience Manager met Adobe Campaign te integreren.


## Externe CRM-connectorrekeningen

* **Microsoft Dynamics CRM**

   Met de externe account **[!UICONTROL Microsoft Dynamics CRM]** kunt u Microsoft Dynamics-gegevens importeren en exporteren naar Adobe Campaign.

   ?? Meer informatie over de integratie van Adobe Campaign - Microsoft Dynamics CRM in [deze pagina](../connect/crm.md).

   Met **[!UICONTROL Web API]** plaatsingstype en **[!UICONTROL Password credentials]** authentificatie, moet u de volgende details verstrekken:

   * **[!UICONTROL Account]**: Account gebruikt om u aan te melden bij Microsoft CRM.

   * **[!UICONTROL Server]**: URL van uw Microsoft CRM-server.

   * **[!UICONTROL Client identifier]**: Client-id die u kunt vinden op de Microsoft Azure-beheerportal in de  **[!UICONTROL Update your code]** categorie,  **[!UICONTROL Client ID]** het veld.

   * **[!UICONTROL CRM version]**: Versie van de CRM tussen  **[!UICONTROL Dynamics CRM 2007]**,  **[!UICONTROL Dynamics CRM 2015]** of  **[!UICONTROL Dynamics CRM 2016]**.
   Met **[!UICONTROL Web API]** plaatsingstype en **[!UICONTROL Certificate]** authentificatie, moet u de volgende details verstrekken:

   * **[!UICONTROL Server]**: URL van uw Microsoft CRM-server.

   * **[!UICONTROL Private Key (Base64 encoded)]**: Persoonlijke sleutel die aan Base64 wordt gecodeerd

   * **[!UICONTROL Custom Key identifier]**

   * **[!UICONTROL Key ID]**

   * **[!UICONTROL Client identifier]**: Client-id die u kunt vinden op de Microsoft Azure-beheerportal in de  **[!UICONTROL Update your code]** categorie,  **[!UICONTROL Client ID]** het veld.

   * **[!UICONTROL CRM version]**: Versie van de CRM tussen  **[!UICONTROL Dynamics CRM 2007]**,  **[!UICONTROL Dynamics CRM 2015]** of  **[!UICONTROL Dynamics CRM 2016]**.


* **Salesforce.com**

   Met de externe account **[!UICONTROL Salesforce CRM]** kunt u Salesforce-gegevens importeren en exporteren naar Adobe Campaign.

   Om de externe rekening van Salesforce CRM te vormen om met Adobe Campaign te werken, moet u de volgende details verstrekken:

   * **[!UICONTROL Account]**: Account gebruikt om u aan te melden bij Salesforce CRM.

   * **[!UICONTROL Password]**: Wachtwoord gebruikt om u aan te melden bij Salesforce CRM.

   * **[!UICONTROL Client identifier]**: Leer hoe u uw client-id kunt vinden op  [deze pagina](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL Security token]**: Leer hoe u uw beveiligingstoken kunt vinden op  [deze pagina](https://help.salesforce.com/articleView?id=000205876&amp;type=1).

   * **[!UICONTROL API version]**: Selecteer de versie van de API. Voor deze externe rekening, moet u u Salesforce CRM met de configuratietovenaar vormen.

## Externe rekeningen voor gegevensoverdracht

Deze externe accounts kunnen worden gebruikt voor het importeren of exporteren van gegevens naar Adobe Campaign met behulp van een **[!UICONTROL Transfer file]**-workflowactiviteit.

↗️ Meer informatie over bestandsoverdracht in workflows in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html){target=&quot;_blank&quot;

* **FTP en SFTP**

   Met de externe account **FTP** kunt u toegang tot een server buiten Adobe Campaign configureren en testen. Als u verbindingen wilt instellen met externe systemen, zoals SFTP- of FTP-servers 898 die worden gebruikt voor bestandsoverdracht, kunt u uw eigen externe accounts maken.
Hiertoe geeft u in deze externe account het adres en de referenties op die worden gebruikt om de verbinding met de SFTP- of FTP-server tot stand te brengen.

* **Amazon Simple Storage Service (S3)**

   De **AWS S3**-connector kan worden gebruikt om gegevens te importeren of naar Adobe Campaign te exporteren met behulp van een **[!UICONTROL Transfer file]**-workflowactiviteit. Wanneer u dit nieuwe externe account instelt, moet u de volgende data opgeven:

   * **[!UICONTROL AWS S3 Account Server]**: URL van uw server, als volgt ingevuld:    ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

   * **[!UICONTROL AWS access key ID]**: Leer hoe u uw AWS-toegangstoets-id kunt vinden in de documentatie [ van ](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) Amazon.

   * **[!UICONTROL Secret access key to AWS]**: Leer hoe u in de documentatie [ van ](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/)Amazon uw geheime toegangssleutel tot AWS vindt.

   * **[!UICONTROL AWS Region]**: Meer informatie over AWS-gebieden vindt u in de documentatie [ van ](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)Amazon.

   * Met het selectievakje **[!UICONTROL Use server side encryption]** kunt u het bestand opslaan in de gecodeerde modus van S3. Leer hoe te om toegangs belangrijkste identiteitskaart en geheime toegangssleutel in [Amazon documentatie](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) te vinden.

* **Azure Blob Storage**

   De **Azure** externe account kan worden gebruikt voor het importeren of exporteren van gegevens naar Adobe Campaign met behulp van een **[!UICONTROL Transfer file]**-workflowactiviteit. Als u de externe **Azure**-account wilt configureren om met Adobe Campaign te werken, moet u de volgende gegevens opgeven:

   * **[!UICONTROL Server]**: URL van uw Azure Blob-opslagserver.

   * **[!UICONTROL Encryption]**: Type codering tussen  **[!UICONTROL None]** of  **[!UICONTROL SSL]**.

   * **[!UICONTROL Access key]**: Leer hoe u  **[!UICONTROL Access key]** in de documentatie [ van ](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)Microsoft kunt vinden.
