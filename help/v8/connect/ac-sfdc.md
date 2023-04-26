---
title: Werken met campagne en SFDC
description: Leer hoe u kunt werken met Campagne en Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Werken met campagne en SFDC{#crm-sfdc}

Leer hoe u de Campagne CRM-connector configureert om Campagne v8 aan te sluiten op **Salesforce.com**.

Zodra configuratie wordt gedaan, wordt de gegevenssynchronisatie tussen systemen uitgevoerd via een specifieke werkschemaactiviteit. [Meer informatie](crm-data-sync.md).

>[!NOTE]
>
>Ondersteunde SFDC-versies worden gedetailleerd beschreven in Campagne [Compatibiliteitsmatrix](../start/compatibility-matrix.md).

Voer de onderstaande stappen uit om een speciale externe account te configureren voor het importeren en exporteren van Salesforce-gegevens naar Adobe Campaign.

## Verbinding maken{#new-sfdc-external-account}

Ten eerste moet u de externe account van Salesforce maken.

1. Bladeren in het dialoogvenster **[!UICONTROL Administration > Platform > External accounts]** van de Campagneverkenner en maak een externe account.
1. Selecteren **[!UICONTROL Salesforce.com]** externe rekening in de **Type** sectie.
1. Voer instellingen in om de verbinding in te schakelen.

   ![](assets/sfdc-external-account.png)

   Om de externe rekening van Salesforce CRM te vormen om met Adobe Campaign te werken, moet u de volgende details verstrekken:

   * Geef uw Salesforce-aanmelding op in het dialoogvenster **[!UICONTROL Account]** veld.
   * Voer uw Salesforce-wachtwoord in.
   * U kunt de **[!UICONTROL Client identifier]** veld.
   * Uw Salesforce kopiëren/plakken **[!UICONTROL Security token]**
   * Selecteer uw **[!UICONTROL API version]**. Ondersteunde SFDC API-versies worden vermeld in campagne [Compatibiliteitsmatrix](../start/compatibility-matrix.md).

1. Selecteer **Inschakelen** om het account te activeren in Campagne.

>[!NOTE]
>
>Als u de installatie wilt goedkeuren, moet u zich afmelden en weer terugzetten op de Adobe Campaign-console.

## Tabellen selecteren om te synchroniseren{#sfdc-create-tables}

U kunt nu tabellen configureren om te synchroniseren.

1. Klik op de knop **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. Selecteer de tabellen die u wilt synchroniseren en start het proces.
1. Controleer het schema dat in Adobe Campaign is gegenereerd in het dialoogvenster **[!UICONTROL Administration > Configuration > Data schemas]** knooppunt.

   Voorbeeld van een **Salesforce** schema geïmporteerd in campagne:

   ![](assets/sfdc-schemas.png)

## Opsommingen synchroniseren{#sfdc-enum-sync}

Als het schema eenmaal is gemaakt, kunt u opsommingen automatisch synchroniseren van Salesforce naar Adobe Campaign.

1. Open de assistent vanuit de  **[!UICONTROL Synchronizing enumerations...]** koppeling.
1. Selecteer de opsomming van Adobe Campaign die de opsomming Salesforce aanpast.
U kunt alle waarden van een opsomming van Adobe Campaign door die van CRM vervangen: Selecteer **[!UICONTROL Yes]** in de **[!UICONTROL Replace]** kolom.

   ![](assets/sfdc-enum.png)

1. Klikken **[!UICONTROL Next]** en vervolgens **[!UICONTROL Start]** om de opsommingen te importeren.

1. Bladeren in het dialoogvenster **[!UICONTROL Administration > Platform > Enumerations]** knooppunt om geïmporteerde waarden te controleren. Meer informatie over opsommingen vindt u in [deze pagina](../config/ui-settings.md#enumerations).

Adobe Campaign en Salesforce.com zijn nu verbonden. U kunt gegevenssynchronisatie tussen de twee systemen instellen.

Als u gegevens wilt synchroniseren tussen Adobe Campaign-gegevens en SFDC, maakt u een workflow en gebruikt u de opdracht **[!UICONTROL CRM connector]** activiteit.

Meer informatie over gegevenssynchronisatie [op deze pagina](crm-data-sync.md).
