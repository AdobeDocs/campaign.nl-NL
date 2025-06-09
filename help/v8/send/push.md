---
title: Pushmelding verzenden met Adobe Campaign
description: Aan de slag met pushmeldingen in Campagne
feature: Push
role: User
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: 0b4fc6da8761d2efe57d8eb0ff87cd11d0e2d250
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 4%

---

# Pushmeldingen maken en verzenden{#push-notifications-create}

Met de levering van mobiele apps kunt u meldingen verzenden naar iOS- en Android-apparaten.

Voordat u pushberichten met Adobe Campaign gaat verzenden, moet u ervoor zorgen dat er configuraties en integratie zijn in de mobiele app en voor tags in Adobe Experience Platform. [ leer meer over dupconfiguratie.](push-settings.md).

>[!CAUTION]
>
>Enkele belangrijke wijzigingen in de Android Firebase Cloud Messaging (FCM)-service worden in 2024 gepubliceerd en kunnen van invloed zijn op uw Adobe Campaign-implementatie. De configuratie van uw lidmaatschapsservices voor Android-pushberichten moet mogelijk worden bijgewerkt om deze wijziging te ondersteunen. U kunt al controleren en actie ondernemen. [Meer informatie](../../technotes/upgrades/push-technote.md).

## Uw eerste pushmelding maken {#push-create}

In deze sectie worden de specifieke elementen voor de levering van iOS- en Android-berichten beschreven.

>[!IMPORTANT]
>
>In de context van een [ plaatsing van de Onderneming (FFDA) ](../architecture/enterprise-deployment.md), is de mobiele registratie nu asynchroon ****. [Meer informatie](../architecture/staging.md)


Als u een nieuwe levering wilt maken, bladert u naar het tabblad **[!UICONTROL Campaigns]** , klikt u op **[!UICONTROL Deliveries]** en klikt u op de knop **[!UICONTROL Create]** boven de lijst met bestaande leveringen.

![](assets/delivery_step_1.png)


Adobe Campaign wordt standaard geleverd met twee leveringssjablonen: een voor iOS en een voor Android. U kunt deze dupliceren om uw eigen instellingen te definiëren. De stappen om een duplevering te vormen die op deze malplaatjes wordt gebaseerd zijn hieronder gedetailleerd.

>[!BEGINTABS]

>[!TAB  iOS ]

Voer de volgende stappen uit om berichten op iOS-apparaten te verzenden:

1. Selecteer de leveringssjabloon **[!UICONTROL Deliver on iOS]** .

   ![](assets/push_ios_1.png)

1. Als u het doel van de melding wilt definiëren, klikt u op de koppeling **[!UICONTROL To]** en vervolgens op **[!UICONTROL Add]** .

   ![](assets/push_ios_2.png)

1. Selecteer **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]** , selecteer de service die relevant is voor uw mobiele toepassing en selecteer vervolgens de iOS-versie van de toepassing.

   ![](assets/push_ios_3.png)

1. Kies de **[!UICONTROL Notification type]** tussen **[!UICONTROL General notification (Alert, Sound, Badge)]** of **[!UICONTROL Silent notification]** .

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >De **wijze van de Duw van 0} Zijde** staat een &quot;stil&quot;bericht toe om naar een mobiele toepassing worden verzonden. De gebruiker wordt niet op de hoogte gebracht van de aankomst van de melding. Deze wordt rechtstreeks naar de toepassing overgedragen.

1. Voer in het veld **[!UICONTROL Title]** het label in van de titel die u wilt weergeven in de lijst met meldingen die beschikbaar is in het meldingscentrum.

   Dit gebied staat u toe om de waarde van de **titel** parameter van de het berichtlading van iOS te bepalen.

1. U kunt a **[!UICONTROL Subtitle]**, waarde van de **ondertitel** parameter van de het berichtlading van iOS toevoegen.

1. Voer de inhoud van het bericht in het gedeelte **[!UICONTROL Message content]** van de wizard in.

1. Op het tabblad **[!UICONTROL Sound and Badge]** kunt u de volgende opties bewerken:

   * **[!UICONTROL Clean Badge]**: schakel deze optie in om de waarde van de badge te vernieuwen.

   * **[!UICONTROL Value]** : stel een getal in dat wordt gebruikt om het aantal nieuwe ongelezen gegevens direct op het toepassingspictogram weer te geven.

   * **[!UICONTROL Critical alert mode]**: schakel deze optie in om geluid toe te voegen aan uw melding, zelfs als de telefoon van de gebruiker is ingesteld in de focusmodus of als de iPhone is gedempt.

   * **[!UICONTROL Name]** : selecteer het geluid dat door de mobiele terminal moet worden afgespeeld wanneer het bericht wordt ontvangen.

   * **[!UICONTROL Volume]**: volume van uw geluid van 0 tot 100.

     >[!NOTE]
     > 
     >Geluiden moeten in de toepassing worden opgenomen en worden gedefinieerd wanneer de service wordt gemaakt.
     >

   ![](assets/push_ios_5.png)

1. Vanaf de tab **[!UICONTROL Application variables]** wordt de **[!UICONTROL Application variables]** automatisch toegevoegd. Met deze instructies kunt u bijvoorbeeld het berichtgedrag definiëren. U kunt dan een specifiek toepassingsscherm configureren dat wordt weergegeven wanneer de gebruiker het bericht activeert.

1. Op het tabblad **[!UICONTROL Advanced]** kunt u de volgende algemene opties bewerken:

   * **[!UICONTROL Mutable content]** : schakel deze optie in zodat de mobiele toepassing media-inhoud kan downloaden.

   * **[!UICONTROL Thread-id]**: id die wordt gebruikt om gerelateerde meldingen te groeperen.

   * **[!UICONTROL Category]**: naam van de categorie-id waarin de knoppen voor handelingen worden weergegeven. Met deze meldingen kan de gebruiker sneller verschillende taken uitvoeren als reactie op een melding zonder de applicatie te openen of erin te moeten navigeren.

   ![](assets/push_ios_6.png)

1. Voor meldingen met tijdgevoeligheid kunt u de volgende opties opgeven:

   * **[!UICONTROL Target content ID]**: id die wordt gebruikt om aan te geven welk toepassingsvenster moet worden verzonden wanneer de melding wordt geopend.

   * **[!UICONTROL Launch image]**: naam van het bestand met de opstartafbeelding dat moet worden weergegeven. Als de gebruiker ervoor kiest de toepassing te starten, wordt de geselecteerde afbeelding weergegeven in plaats van het startscherm van de toepassing.

   * **[!UICONTROL Interruption level]** :

      * **[!UICONTROL Active]**: standaard ingesteld, geeft het systeem de melding direct weer, licht het scherm op en kan een geluid worden afgespeeld. Meldingen doorbreken niet door de focusmodi.

      * **[!UICONTROL Passive]**: het systeem voegt het bericht toe aan de meldingslijst zonder het scherm te belichten of een geluid af te spelen. Meldingen doorbreken niet door de focusmodi.

      * **[!UICONTROL Time sensitive]** Het systeem geeft de melding direct weer, licht het scherm op, kan een geluid afspelen en de modus Focus doorbreken. Voor dit niveau is geen speciale toestemming van Apple vereist.

      * **[!UICONTROL Critical]** Het systeem geeft de melding direct weer, licht het scherm omhoog en laat de modi voor demoverschakeling of focus voorbijgaan. Voor dit niveau is een speciale machtiging van Apple vereist.

   * **[!UICONTROL Relevance score]** : stel een relevantiescore in van 0 tot 100. Het systeem gebruikt dit om de berichten in het berichtoverzicht te sorteren.

   ![](assets/push_ios_7.png)

1. Nadat het bericht is geconfigureerd, klikt u op het tabblad **[!UICONTROL Preview]** om een voorvertoning van het bericht te bekijken.

   ![](assets/push-ios-preview.png)


>[!TAB  Android ]

Voer de volgende stappen uit om berichten op Android-apparaten te verzenden:

1. Selecteer de leveringssjabloon **[!UICONTROL Deliver on Android (android)]** .

   ![](assets/push-template-android.png)

   >[!NOTE]
   > 
   >Met recentste FCM APIs (HTTP v1), moet u uw **leveringsmalplaatjes** voor de duw berichten van Android bijwerken om het aantal partijberichten te verhogen. Om dit te doen, doorblader aan de eigenschappen van uw Android leveringsmalplaatje en, in het **lusje van de Levering**, plaats de [ Hoeveelheid van de Batch van het Bericht ](../../v8/send/configure-and-send.md#delivery-batch-quantity) aan **256**. Pas deze wijziging toe op alle leveringssjablonen die worden gebruikt voor uw Android-leveringen en op al uw bestaande Android-leveringen.


1. Als u het doel van de melding wilt definiëren, klikt u op de koppeling **[!UICONTROL To]** en vervolgens op **[!UICONTROL Add]** .

   ![](assets/push-android-select-target.png)

1. Selecteer **[!UICONTROL Subscribers of an Android mobile application]**, kies de service die relevant is voor uw mobiele toepassing (in dit geval Neotrips) en selecteer vervolgens de Android-versie van de toepassing.

   ![](assets/push-android-subscribers.png)

1. Voer vervolgens de inhoud voor het bericht in.

   ![](assets/push-android-content.png)

1. Klik op het pictogram **[!UICONTROL Insert emoticon]** om emoticons in te voegen bij uw pushmelding.

1. Voer in het veld **[!UICONTROL Application variables]** de waarde van elke variabele in. U kunt bijvoorbeeld een specifiek toepassingsscherm configureren dat wordt weergegeven wanneer de gebruiker het bericht activeert.

1. Nadat het bericht is geconfigureerd, klikt u op het tabblad **[!UICONTROL Preview]** om een voorvertoning van het bericht te bekijken.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## Uw pushmeldingen testen, verzenden en controleren {#push-test}

Om een bewijs te verzenden en de uiteindelijke levering te verzenden, gebruikt u hetzelfde proces als voor andere leveringen.

Leer hoe te om een levering in [ te bevestigen deze pagina ](preview-and-proof.md).

Leer om de levering in [ te bevestigen en te verzenden deze pagina ](send.md)

Nadat u berichten hebt verzonden, kunt u de leveringen controleren en volgen. Leer meer over de mislukkingsredenen van de pushmelding in [ deze pagina ](delivery-failures.md#push-error-types).

