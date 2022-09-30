---
title: Werken met campagne en Twitter
description: Leer hoe u uw Campagne-omgeving kunt integreren met Twitter
role: User, Admin
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 2%

---

# Werken met campagne en Twitter{#tw-ac-ovv}

De **Beheer van sociale netwerken (sociale marketing)** kunt u via Twitter met uw klanten communiceren. Gebruik deze mogelijkheid om:

* Post berichten en verzend DMs - Gebruik de Sociale Marketing van Adobe Campaign om berichten op Twitter te posten. U kunt ook directe berichten verzenden naar al uw volgers.

* Verzamel nieuwe contacten - Adobe Campaign Social Marketing maakt het ook gemakkelijk om nieuwe contacten te verwerven: Neem contact op met gebruikers en vraag hen of zij hun profielgegevens willen delen. Als ze het accepteren, herstelt Adobe Campaign automatisch de gegevens, waarmee u doelgerichte campagnes kunt voeren en waar mogelijk kanaalstrategieën kunt implementeren.

![](../assets/do-not-localize/speech.png) Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support) om Campagne met Twitter te verbinden. De  **Beheer van sociale netwerken (sociale marketing)** De invoegtoepassing moet in uw omgeving worden geïnstalleerd via het speciale pakket en de externe account van Twitter moet worden geconfigureerd.


Als u Adobe Campaign wilt configureren om tweets te posten naar uw Twitter-accounts, kunt u voor deze accounts schrijfrechten delegeren aan Adobe Campaign. Hiervoor moet u:

1. Maak een Twitter-account en meld u aan voor een ontwikkelaarsaccount. [Meer informatie](#dev-account)
1. (optioneel) Maak een Twitter-testaccount voor het verzenden van proefdrukken. [Meer informatie](#tw-test-account)
1. Maak een Twitter-toepassing (één app per Twitter-account). [Meer informatie](#create-an-app-on-twitter)
1. Nieuwe service maken voor **[!UICONTROL Twitter]** (één service per Twitter-account). [Meer informatie](#create-tw-service)
1. Synchroniseer uw Twitter-account met Campagne. [Meer informatie](#synchro-tw-accounts)

## Twitter Developer Account {#dev-account}

Als u met deze integratie wilt beginnen, moet u zich aanmelden voor een [Twitter Developer Account](https://developer.twitter.com){target=&quot;_blank&quot;}.

De campagne gebruikt versie 1.1 van Twitter API. Om het te gebruiken, moet u voor Verhoogde toegang via het Portaal van de Ontwikkelaar aanvragen. Meer informatie over Twitter Eleved Access [op deze pagina](https://developer.twitter.com/en/portal/products/elevated){target=&quot;_blank&quot;}.

## Een toepassing maken op Twitter {#create-an-app-on-twitter}

Als u eenmaal bent goedgekeurd met Elevated-toegang, maakt u een Twitter-toepassing waarmee Adobe Campaign tweets kan plaatsen op uw Twitter-account. Volg de onderstaande stappen om dit te doen:

1. Meld u aan bij uw Twitter-account.
1. Verbinden met [Twitter Developer Portal](https://developer.twitter.com/en/apps).
1. Selecteren **Een app maken**.
1. Laat de Twitter-assistent u door het proces begeleiden.
1. Als u wilt toestaan dat Adobe Campaign tweets op uw account plaatst, bewerkt u de **Toepassingsmachtigingen** in het gedeelte Gebruikersverificatie instellen van uw app. Selecteren **Berichten lezen, schrijven en direct verzenden**.

   ![](assets/tw-permissions.png)

1. In de **Type app** sectie, selecteert u **Web App, Automated App of Bot**. U kunt de **URL voor terugbellen** veld leeg is en uw configuratie opslaan.

   ![](assets/tw-app-type.png)

1. Ga terug naar het dashboard voor uw app, selecteer uw app en blader naar de **Toetsen en tokens** tab. Onder **Toegangstoken en geheim**, als de **Berichten lezen, schrijven en direct verzenden** De machtiging wordt niet vermeld. U moet de token en het geheim van uw app opnieuw genereren. Alle toetsen en tokens moeten bij het maken worden opgeslagen. U hebt ze nodig om uw Campagne Twitter-service te configureren.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>U hebt één toepassing per Twitter-account nodig. Als gevolg hiervan moet u een andere testtoepassing maken om proefdrukken naar uw testaccount te verzenden.

## Een Twitter-service maken in Campagne {#create-tw-service}

Als u uw Campagne-instantie wilt koppelen aan uw Twitter-account, maakt u een **Twitter** de dienst en afgevaardigde schrijven toegang tot Campagne.

>[!CAUTION]
>
>Een maken **Twitter** service per Twitter-account. Dientengevolge moet u een andere testdienst tot stand brengen om proeven naar uw te verzenden [testaccount](#tw-test-account).
>
>Elk **Twitter** De dienst moet ook door Adobe op uw instantie worden gecreeerd MID. Neem contact op met uw Adobe-vertegenwoordiger om uw omgeving te configureren.

Als u instellingen wilt invoeren, hebt u toegang tot zowel uw Adobe Campaign-console als uw Twitter-toepassingsmachtigingen.

1. In **Adobe Campaign**, bladert u naar de **[!UICONTROL Profiles and targets]** en selecteert u de **[!UICONTROL Services and Subscriptions]** link
1. Maak een nieuwe service.
1. Selecteer **[!UICONTROL Twitter]** type.
1. Voer het label en de interne naam van de service in.

   >[!CAUTION]
   >
   >De **[!UICONTROL Internal name]** van de service moet precies dezelfde naam hebben als uw Twitter-account.

1. Standaard worden volgers opgeslagen in de **[!UICONTROL Visitors]** map. U kunt een andere locatie selecteren in het menu **[!UICONTROL Visitor folder]** veld. [Meer informatie](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >De **[!UICONTROL Synchronize subscriptions]** Deze optie is standaard ingeschakeld: Met deze optie wordt de lijst met Twitter-volgers automatisch hersteld, zodat u [sturen hen directe berichten](../send/twitter.md#direct-tw-messages). Synchronisatie wordt uitgevoerd door een [specifieke technische workflow](#synchro-tw-accounts).

1. Kopieer de inhoud van de **API-sleutel** en **[API-sleutelgeheim]** velden en plak deze in de **[!UICONTROL Consumer key]** en **[!UICONTROL Consumer secret]** velden van uw campagne **Twitter** service.

1. Kopieer de inhoud van de **Toegangstoken** en **Toegangstoken geheim** velden en plak deze in de **[!UICONTROL Access token]** en **[!UICONTROL Access token secret]** velden van uw campagne **Twitter** service.

1. Klik in de Campagne-clientconsole op **[!UICONTROL Save]**. U hebt nu schrijftoegang gedelegeerd aan Adobe Campaign.

U kunt de instellingen controleren door:

* Bewerk de **Twitter** service die u zojuist hebt gemaakt.
* Bladeren in het dialoogvenster **[!UICONTROL Twitter page]** tab: je Twitter-account moet worden weergegeven.
   ![](assets/tw-page.png)


## Je Twitter-account synchroniseren {#synchro-tw-accounts}

De synchronisatie tussen Campagne en Twitter wordt beheerd door specifieke technische werkschema&#39;s. Deze workflows worden opgeslagen in de **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** map.

Ze worden standaard gestopt: u moet ze handmatig starten wanneer u de **Sociale marketing** module.

De **[!UICONTROL Synchronization of Twitter accounts]** met de technische workflow worden Twitter-accounts in Adobe Campaign gesynchroniseerd. Deze workflow herstelt de lijst met Twitter-volgers, zodat u deze rechtstreeks kunt verzenden. [Meer informatie](../send/twitter.md#direct-tw-messages)

Deze workflow wordt standaard elke donderdag om 7.30 uur geactiveerd. U kunt de **[!UICONTROL Execute pending task(s) now]** als u de workflow op elk gewenst moment wilt starten terwijl u deze integratie implementeert.  U kunt de planner ook uitgeven om het werkschema te veranderen dat frequentie teweegbrengt. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}.

>[!CAUTION]
>
>Als u de lijst met Twitter-abonnees wilt herstellen, **[!UICONTROL Twitter account synchronization]** Deze optie moet worden gecontroleerd op de service die aan de account is gekoppeld. [Meer informatie](#create-tw-service)

De volgende mappen worden opgeslagen in een specifieke tabel: de bezoekerslijst. Blader naar de **[!UICONTROL Profiles and Targets > Visitors]**.

Voor elke volgende gegevens slaat Adobe Campaign de volgende gegevens op:

* **[!UICONTROL Origin]**: Twitter
* **[!UICONTROL External ID]**: gebruikersnaam
* **[!UICONTROL Username]**: accountnaam van de gebruiker
* **[!UICONTROL Full name]**: naam van de gebruiker
* **[!UICONTROL Number of friends]**: aantal volgers
* **[!UICONTROL Checked]**: in dit veld wordt aangegeven of de gebruiker een geverifieerde Twitter-account heeft

Zodra deze configuratie is voltooid, kunt u tweets posten naar uw Twitter-accounts en directe berichten verzenden naar uw volgers. [Meer informatie](../send/twitter.md)

## Een testaccount maken op Twitter {#tw-test-account}

Maak naast Twitter-account een particuliere Twitter-account die u kunt gebruiken voor verzending [proefdrukken van tweet](../send/twitter.md#send-tw-proofs). Volg de onderstaande stappen om dit te doen:

1. Maak een nieuwe Twitter-account.
1. Toegang krijgen tot de account  **Instellingen**.
1. Bladeren naar **Privacy en veiligheid** en **Publiek en Tags toevoegen** en de **Protect your Tweets** optie. Uw tweets en andere accountgegevens zijn alleen zichtbaar voor de personen die u volgen.

![](assets/social_tw_test_page.png)

Configureer uw Twitter-app en -campagneservice om met deze testaccount te werken, zoals hierboven beschreven.
