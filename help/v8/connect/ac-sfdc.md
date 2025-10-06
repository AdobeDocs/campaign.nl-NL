---
title: Werken met campagne en SFDC
description: Leer hoe u kunt werken met Campagne en Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: fbde111671fb972f6c96ba45eba4c8a88dbcac64
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# Werken met campagne en SFDC{#crm-sfdc}

Leer hoe te om de schakelaar van CRM van de Campagne te vormen om Campagne v8 aan **te verbinden Salesforce.com**.

Zodra configuratie wordt gedaan, wordt de gegevenssynchronisatie tussen systemen uitgevoerd via een specifieke werkschemaactiviteit. [Meer informatie](crm-data-sync.md).

>[!NOTE]
>
>De gesteunde versies van SFDC zijn gedetailleerd in de matrijs van de Verenigbaarheid van de Campagne [ ](../start/compatibility-matrix.md).

Voer de onderstaande stappen uit om een speciale externe account te configureren voor het importeren en exporteren van Salesforce-gegevens naar Adobe Campaign.

## Verbinding maken{#new-sfdc-external-account}

Eerst moet u de externe Salesforce-account maken.

1. Blader door het knooppunt **[!UICONTROL Administration > Platform > External accounts]** van de Campagneverkenner en maak een extern account.
1. Selecteer **[!UICONTROL Salesforce.com]** externe rekening in de **sectie van het Type**.
1. Voer instellingen in om de verbinding in te schakelen.

   ![](assets/sfdc-external-account.png)

   Als u de externe Salesforce CRM-account wilt configureren voor Adobe Campaign, moet u de volgende gegevens opgeven:

   * Voer uw Salesforce-aanmelding in het veld **[!UICONTROL Account]** in.
   * Voer uw Salesforce-wachtwoord in.
   * U kunt het veld **[!UICONTROL Client identifier]** negeren.
   * Salesforce kopiëren/plakken **[!UICONTROL Security token]**
   * Selecteer de **[!UICONTROL API version]** . De gesteunde versies van SFDC API zijn vermeld in de matrijs van de Verenigbaarheid van de Campagne [ ](../start/compatibility-matrix.md).

1. Selecteer **toelaten** optie om de rekening in Campagne te activeren.

>[!NOTE]
>
>Als u de installatie wilt goedkeuren, moet u zich afmelden en weer aanmelden bij de Adobe Campaign Client Console.

## Tabellen selecteren voor synchronisatie{#sfdc-create-tables}

U kunt nu tabellen configureren voor synchronisatie.

1. Klik op **[!UICONTROL Salesforce CRM configuration wizard...]** .
1. Selecteer de tabellen die u wilt synchroniseren en start het proces.
1. Controleer het schema dat in Adobe Campaign is gegenereerd in het knooppunt **[!UICONTROL Administration > Configuration > Data schemas]** .

   Voorbeeld van a **Salesforce** die schema in Campagne wordt ingevoerd:

   ![](assets/sfdc-schemas.png)

## Opsommingen synchroniseren{#sfdc-enum-sync}

Als het schema eenmaal is gemaakt, kunt u opsommingen automatisch synchroniseren van Salesforce naar Adobe Campaign.

1. Open de assistent via de koppeling **[!UICONTROL Synchronizing enumerations...]** .
1. Selecteer de opsomming van Adobe Campaign die de opsomming van Salesforce aanpast.
U kunt alle waarden van een Adobe Campaign-opsomming vervangen door die van de CRM: hiervoor selecteert u **[!UICONTROL Yes]** in de kolom **[!UICONTROL Replace]** .

   ![](assets/sfdc-enum.png)

1. Klik op **[!UICONTROL Next]** en vervolgens op **[!UICONTROL Start]** om de opsommingen te importeren.

1. Blader door het knooppunt **[!UICONTROL Administration > Platform > Enumerations]** om de geïmporteerde waarden te controleren. Leer meer over opsommingen in [ deze pagina ](../config/ui-settings.md#enumerations).

Adobe Campaign en Salesforce.com zijn nu verbonden. U kunt gegevenssynchronisatie tussen de twee systemen instellen.

Als u gegevens wilt synchroniseren tussen Adobe Campaign-gegevens en SFDC, maakt u een workflow en gebruikt u de **[!UICONTROL CRM connector]** -activiteit.

Leer meer over gegevenssynchronisatie [ in deze pagina ](crm-data-sync.md).

Leer meer over opsommingsbeheer in Campagne [ in deze pagina ](../dev/enumerations.md).
