---
title: Werken met campagne en Twitter
description: Leer hoe u uw Campagne-omgeving kunt integreren met Twitter
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
hide: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 137dba3461a82621af7d2e5f54442bf87422ad47
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Werken met campagne en Twitter{#tw-ac-ovv}

De **Beheer van sociale netwerken (sociale marketing)** kunt u via Twitter met uw klanten communiceren. Gebruik deze mogelijkheid om:

* Berichten verzenden - Gebruik Adobe Campaign Social Marketing om berichten op Twitter te plaatsen. U kunt ook directe berichten verzenden naar al uw volgers.

* Verzamel nieuwe contacten - Adobe Campaign Social Marketing maakt het ook gemakkelijk om nieuwe contacten te verwerven: Neem contact op met gebruikers en vraag hen of zij hun profielgegevens willen delen. Als ze het accepteren, herstelt Adobe Campaign automatisch de gegevens, waarmee u doelgerichte campagnes kunt voeren en waar mogelijk kanaalstrategieën kunt implementeren.

![](../assets/do-not-localize/speech.png)  Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support) om Campagne met Twitter te verbinden. De  **Beheer van sociale netwerken (sociale marketing)** moet op uw milieu, door het specifieke pakket worden geïnstalleerd.


Als u Adobe Campaign wilt configureren om tweets te posten naar uw Twitter-accounts, kunt u voor deze accounts schrijfrechten delegeren aan Adobe Campaign. Dit doet u als volgt:

1. Een Twitter-account maken
1. Een Twitter-testaccount maken voor het verzenden van proefdrukken
1. Een Twitter-toepassing maken (één app per Twitter-account)
1. Nieuwe service maken voor **[!UICONTROL Twitter]** (één service per Twitter-account)

## Een testaccount maken op Twitter {#tw-test-account}

Maak naast Twitter-account een particuliere Twitter-account die u kunt gebruiken voor verzending [proefdrukken van tweet](../send/twitter.md#send-tw-proofs). Volg de onderstaande stappen om dit te doen:

1. Maak een nieuwe Twitter-account.
1. Toegang krijgen tot de account  **Instellingen**.
1. Bladeren naar **Privacy en veiligheid** en **Publiek en Tags toevoegen** en de **Protect your Tweets** optie. Uw tweets en andere accountgegevens zijn alleen zichtbaar voor de personen die u volgen.

![](assets/social_tw_test_page.png)

## Een toepassing maken op Twitter {#create-an-app-on-twitter}

Maak een Twitter-toepassing waarmee Adobe Campaign tweets kan plaatsen op uw Twitter-account.  Volg de onderstaande stappen om dit te doen:

1. Meld u aan bij uw Twitter-account.
1. Verbinden met [Twitter Developer Portal](https://developer.twitter.com/en/apps).
1. Selecteren **Een app maken**.
1. Laat de Twitter-assistent u door het proces begeleiden.

   Als u wilt toestaan dat Adobe Campaign tweets op uw account plaatst, bewerkt u de **Machtigingen** tabblad van de toepassing en selecteert u **Lezen en schrijven** voor de **Toegang** sectie. In de **Instellingen** , moet u ook de **URL voor terugbellen** veld leeg.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>U hebt één toepassing per Twitter-account nodig. Als gevolg hiervan moet u een andere testtoepassing maken om proefdrukken naar uw testaccount te verzenden.

## Een Twitter-service maken in Campagne {#create-tw-service}

Als u uw Campagne-instantie wilt koppelen aan uw Twitter-account, maakt u een **Twitter** de dienst en afgevaardigde schrijven toegang tot Campagne.

Als u instellingen wilt invoeren, hebt u zowel toegang tot uw Adobe Campaign-console als tot uw Twitter-account:

1. Openen **Twitter** en van [de pagina Project en Apps](https://developer.twitter.com/en/portal/projects-and-apps)selecteert u de eerder gemaakte app. Toegang krijgen tot **Toepassingsmachtigingen**.

   ![](assets/social_tw_service.png)

   Bewerk de **Toetsen en tokens** voor toegang tot uw toepassingsgegevens.

1. In **Adobe Campaign**, bladert u naar de **[!UICONTROL Profiles and targets]** en selecteert u de **[!UICONTROL Services and Subscriptions]** link
1. Maak een nieuwe service.
1. Selecteer **[!UICONTROL Twitter]** type.

   >[!NOTE]
   >
   >De **[!UICONTROL Synchronize subscriptions]** Deze optie is standaard ingeschakeld: Met deze optie wordt de lijst met Twitter-volgers automatisch hersteld, zodat u [sturen hen directe berichten](../send/twitter.md#direct-tw-messages). Synchronisatie wordt uitgevoerd door een [specifieke technische workflow](#synchro-tw-accounts).

1. Voer het label en de interne naam van de service in.

   >[!CAUTION]
   >
   >De **[!UICONTROL Internal name]** van de service moet precies dezelfde naam hebben als uw Twitter-account. U kunt de instellingen controleren door:

   * Klik op de knop **[!UICONTROL Save]**.
   * Selecteer in het overzicht van de services de optie **Twitter** service die u zojuist hebt gemaakt.
   * Bladeren in het dialoogvenster **[!UICONTROL Twitter page]** tab: je Twitter-account moet worden weergegeven.

1. Standaard worden volgers opgeslagen in de **[!UICONTROL Visitors]** map. U kunt een andere locatie selecteren in het menu **[!UICONTROL Visitor folder]** veld. [Meer informatie](../send/twitter.md#direct-tw-messages)

1. Kopieer de inhoud van de **[!UICONTROL Consumer Key (API Key)]** en **[!UICONTROL Consumer Secret (API Secret)]** velden en plak deze in de **[!UICONTROL Consumer key]** en **[!UICONTROL Consumer secret]** velden van uw campagne **Twitter** service.

1. Kopieer de inhoud van de **[!UICONTROL Access Token]** en **[!UICONTROL Access Token Secret]** velden en plak deze in de **[!UICONTROL Access token]** en **[!UICONTROL Access token secret]** velden van uw campagne **Twitter** service.

1. Klik in de Campagne-clientconsole op **[!UICONTROL Save]**. U hebt nu schrijftoegang gedelegeerd aan Adobe Campaign.


>[!NOTE]
>
>Een maken **Twitter** service per Twitter-account. Als gevolg hiervan moet u nog een testservice maken om proefdrukken naar uw testaccount te verzenden.

## Je Twitter-account synchroniseren {#synchro-tw-accounts}

De synchronisatie tussen Campagne en Twitter wordt beheerd door specifieke technische werkschema&#39;s. Deze workflows worden opgeslagen in de **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** map.

Ze worden standaard gestopt: u moet ze handmatig starten wanneer u de **Sociale marketing** module.

De **[!UICONTROL Twitter account synchronization]** met de technische workflow worden Twitter-accounts in Adobe Campaign gesynchroniseerd. Deze workflow herstelt de lijst met Twitter-volgers, zodat u deze rechtstreeks kunt verzenden. [Meer informatie](../send/twitter.md#direct-tw-messages)

Deze workflow wordt standaard elke donderdag om 7.30 uur geactiveerd. U kunt de **[!UICONTROL Execute pending task(s) now]** als u de workflow op elk gewenst moment wilt starten terwijl u deze integratie implementeert.  U kunt de planner ook uitgeven om het werkschema te veranderen dat frequentie teweegbrengt. Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}.

>[!CAUTION]
>
>Als u de lijst met Twitter-abonnees wilt herstellen, **[!UICONTROL Twitter account synchronization]** Deze optie moet worden gecontroleerd op de service die aan de account is gekoppeld. [Meer informatie](#create-tw-service)

De volgende mappen worden opgeslagen in een specifieke tabel: de bezoekerslijst. Blader naar de **[!UICONTROL Profiles and Targets > Visitors]**.

Voor elke volgende gegevens slaat Adobe Campaign de volgende gegevens op:

* **[!UICONTROL Origin]**: naam van het sociale netwerk (Twitter)
* **[!UICONTROL External ID]**: gebruikersnaam
* **[!UICONTROL User name]**: accountnaam van de gebruiker
* **[!UICONTROL Full name]**: naam van de gebruiker
* **[!UICONTROL Language]**: gebruikerstaal
* **[!UICONTROL Number of friends]**: aantal volgers
* **[!UICONTROL Time zone]**: tijdzone van gebruiker
* **[!UICONTROL Verified]**: in dit veld wordt aangegeven of de gebruiker een geverifieerde Twitter-account heeft

Zodra deze configuratie is voltooid, kunt u tweets posten naar uw Twitter-accounts en directe berichten verzenden naar uw volgers. [Meer informatie](../send/twitter.md)
