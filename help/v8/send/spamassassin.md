---
product: campaign
title: SpamAssassin
description: Leer hoe te opstelling e-mailspamopsporing met SpamAssassin
feature: Email, Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8be6836d-f7dc-4199-b2b2-b6a9cac9d162
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 1%

---

# SpamAssassin{#spamassassin}

Adobe Campaign kan worden gevormd om met [&#x200B; te werken SpamAssassin &#x200B;](https://spamassassin.apache.org){target="_blank"}, een derdedienst die voor het filtreren van e-mailspam wordt gebruikt. Dit staat u toe om e-mailberichten te scoren om te bepalen of een bericht het risico loopt om als spam door de anti-anti-spamhulpmiddelen worden beschouwd die op ontvangstbewijs worden gebruikt.

SpamAssassin maakt gebruik van diverse spamdetectietechnieken, waaronder:

* DNS-gebaseerde en op vage controlesom gebaseerde spamdetectie
* Bayesiaans filteren
* Externe programma&#39;s
* Lijsten van gewezen personen
* Online databases

>[!NOTE]
>
>SpamAssassin moet op de de toepassingsserver van Adobe Campaign worden geïnstalleerd en worden gevormd. Neem hiervoor contact op met uw Adobe-vertegenwoordiger.
>
>De regels die bepalen of een element al dan niet spam is worden beheerd via SpamAssassin en kunnen door een beheerder met voorrechten worden uitgegeven.

## SpamAssassin gebruiken in campagne {#using-spamassassin}

Nadat u de e-maillevering hebt gemaakt en de inhoud ervan hebt gedefinieerd, volgt u de onderstaande stappen om de risico&#39;s te evalueren.

Voor meer bij het creëren van en het ontwerpen van een levering, verwijs naar deze [&#x200B; pagina &#x200B;](defining-the-email-content.md).


1. Ga naar de tab **[!UICONTROL Preview]** .
1. Selecteer een ontvanger om een voorbeeld van uw levering te bekijken.

   ![](assets/s_tn_del_preview_spamassassin_recipient.png)

   >[!NOTE]
   >
   >Als u geen ontvanger selecteert, kan de anti-spamcontrole niet worden uitgevoerd.

1. Het resultaat van de test wordt aangegeven met een waarschuwingsbericht. Als een hoog risiconiveau wordt gedetecteerd, wordt het volgende waarschuwingsbericht weergegeven:

   ![](assets/s_tn_del_preview_spamassassin_ko.png)

1. Klik op de koppeling **[!UICONTROL More...]** naast de waarschuwing.
1. Selecteer het tabblad **[!UICONTROL Anti-spam checking]**. 
1. Ga naar de sectie **[!UICONTROL Points / Rule / Description]** om de redenen voor dit risico te bekijken.

   ![](assets/s_tn_del_msg_spamassassin_ko.png)

>[!NOTE]
>
>Telkens als u **[!UICONTROL Anti-spam checking]** klikt, wordt de dienst SpamAssassin geroepen en het bericht wordt opnieuw geanalyseerd voor anti-spamopsporing. Controleer of u de inhoud hebt gewijzigd voordat u de anti-spamanalyse opnieuw uitvoert.
