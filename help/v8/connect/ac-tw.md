---
title: Werken met campagne en Twitter
description: Leer hoe u uw Campagne-omgeving kunt integreren met Twitter
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1062'
ht-degree: 3%

---

# Werken met campagne en Twitter {#tw-ac-ovv}

De **Beheer van sociale netwerken (sociale marketing)** kunt u via Twitter met uw klanten communiceren. Gebruik deze mogelijkheid om:

* Post berichten en verzend DMs - Gebruik de Sociale Marketing van Adobe Campaign om berichten op Twitter te posten. U kunt ook directe berichten verzenden naar al uw volgers.

* Verzamel nieuwe contacten - Adobe Campaign Social Marketing maakt het ook gemakkelijk om nieuwe contacten te verwerven: contacteer gebruikers en vraag hen of zij hun profielinformatie willen delen. Als ze het accepteren, herstelt Adobe Campaign automatisch de gegevens, waarmee u doelgerichte campagnes kunt voeren en waar mogelijk kanaalstrategieën kunt implementeren.

![](../assets/do-not-localize/speech.png) Als gebruiker van beheerde Cloud Servicen, [contact Adobe](../start/campaign-faq.md#support) om Campagne met Twitter te verbinden. De  **Beheer van sociale netwerken (sociale marketing)** De invoegtoepassing moet op uw omgeving worden geïnstalleerd via het toegewezen pakket en de externe account van de Twitter moet worden geconfigureerd.


Om Adobe Campaign te vormen om tweets aan uw Twitter rekeningen te posten, afgevaardigde schrijf toegang tot Adobe Campaign voor deze rekeningen. Hiervoor moet u:

1. Maak een Twitter-account en meld u aan voor een ontwikkelaarsaccount. [Meer informatie](#dev-account)
1. (optioneel) Maak een account voor de Twitter van tests om proefdrukken te verzenden. [Meer informatie](#tw-test-account)
1. Maak een Twitter-toepassing (één app per Twitter-account). [Meer informatie](#create-an-app-on-twitter)
1. Nieuwe service maken voor **[!UICONTROL Twitter]** (één service per Twitter-account). [Meer informatie](#create-tw-service)
1. Synchroniseer uw Twitter account met Campagne. [Meer informatie](#synchro-tw-accounts)

## Twitter-ontwikkelingsaccount {#dev-account}

Als u met deze integratie wilt beginnen, moet u zich aanmelden voor een [Twitter-ontwikkelingsaccount](https://developer.twitter.com){target="_blank"}.

De campagne gebruikt versie 1.1 van Twitter API. Om het te gebruiken, moet u voor Verhoogde toegang via het Portaal van de Ontwikkelaar aanvragen. Meer informatie over verhoogde toegang tot Twitter [op deze pagina](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Een toepassing maken bij Twitter {#create-an-app-on-twitter}

Zodra u met Verhoogde toegang bent goedgekeurd, creeer een toepassing van de Twitter om Adobe Campaign toe te laten om tweets aan uw rekening van de Twitter te posten. Volg de onderstaande stappen om dit te doen:

1. Meld u aan bij uw Twitter-account.
1. Verbinden met [Developer Portal voor twitter](https://developer.twitter.com/en/apps).
1. Selecteren **Een app maken**.
1. Laat de medewerker van de Twitter u door het proces begeleiden.
1. Als u wilt toestaan dat Adobe Campaign tweets op uw account plaatst, bewerkt u de **Toepassingsmachtigingen** in het gedeelte Gebruikersverificatie dat is ingesteld in uw app. Selecteren **Berichten lezen, schrijven en direct verzenden**.

   ![](assets/tw-permissions.png)

1. In de **Type app** sectie, selecteert u **Web App, Automated App of Bot**. U kunt de **URL voor terugbellen** veld leeg is en uw configuratie opslaan.

   ![](assets/tw-app-type.png)

1. Ga terug naar het dashboard voor uw app, selecteer uw app en blader naar de **Toetsen en tokens** tab. Onder **Toegangstoken en geheim**, als de **Berichten lezen, schrijven en direct verzenden** De machtiging wordt niet vermeld. U moet de token en het geheim van uw app opnieuw genereren. Alle toetsen en tokens moeten bij het maken worden opgeslagen. U zult hen nodig hebben om uw dienst van de Twitter van de Campagne te vormen.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>U hebt één toepassing per Twitter-account nodig. Als gevolg hiervan moet u een andere testtoepassing maken om proefdrukken naar uw testaccount te verzenden.
>

## Een Twitter maken in Campagne {#create-tw-service}

Als u uw Campagne-instantie wilt koppelen aan uw Twitter-account, maakt u een **Twitter** de dienst en afgevaardigde schrijven toegang tot Campagne.

>[!CAUTION]
>
>Een maken **Twitter** service per Twitter account. Als gevolg hiervan moet u een andere testservice maken om proefdrukken naar uw [testaccount](#tw-test-account).
>
>Elk **Twitter** De dienst moet ook door Adobe op uw instantie worden gecreeerd MID. Neem contact op met uw Adobe om uw omgeving te configureren.
>

Als u instellingen wilt invoeren, hebt u toegang tot zowel uw Adobe Campaign Client Console als uw Twitter-app.

1. In **Adobe Campaign**, bladert u naar de **[!UICONTROL Profiles and targets]** en selecteert u de **[!UICONTROL Services and Subscriptions]** link
1. Maak een nieuwe service.
1. Selecteer de **[!UICONTROL Twitter]** type.
1. Voer het label en de interne naam van de service in.

   >[!CAUTION]
   >
   >De **[!UICONTROL Internal name]** van de service moet precies dezelfde naam hebben voor uw Twitter account.
   >

1. Standaard worden volgers opgeslagen in de **[!UICONTROL Visitors]** map. U kunt een andere locatie selecteren in het menu **[!UICONTROL Visitor folder]** veld. [Meer informatie](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >De **[!UICONTROL Synchronize subscriptions]** Deze optie is standaard ingeschakeld: met deze optie wordt automatisch de lijst met Twitter-volgers hersteld, zodat u [sturen hen directe berichten](../send/twitter.md#direct-tw-messages). Synchronisatie wordt uitgevoerd door een [specifieke technische workflow](#synchro-tw-accounts).

1. Kopieer de inhoud van de Twitter-app **API-sleutel** en **[API-sleutelgeheim]** velden en plak deze in de **[!UICONTROL Consumer key]** en **[!UICONTROL Consumer secret]** velden van uw campagne **Twitter** service.

1. Kopieer de inhoud van de Twitter-app **Toegangstoken** en **Toegangstoken geheim** velden en plak deze in de **[!UICONTROL Access token]** en **[!UICONTROL Access token secret]** velden van uw campagne **Twitter** service.

1. Klik in de Campagne Client Console op **[!UICONTROL Save]**. U hebt nu schrijftoegang gedelegeerd aan Adobe Campaign.

U kunt de instellingen controleren door:

* Bewerk de **Twitter** service die u zojuist hebt gemaakt.
* Bladeren in het dialoogvenster **[!UICONTROL Twitter page]** tab: uw Twitter account moet worden weergegeven.
  ![](assets/tw-page.png)


## Uw Twitter-account synchroniseren {#synchro-tw-accounts}

De synchronisatie tussen Campagne en Twitter wordt beheerd door specifieke technische werkschema&#39;s. Deze workflows worden opgeslagen in de **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** map.

Deze worden standaard gestopt: u moet ze handmatig starten wanneer u de functie **Sociale marketing** -module.

De **[!UICONTROL Synchronization of Twitter accounts]** de technische werkstroom synchroniseert de rekeningen van de Twitter in Adobe Campaign. Deze workflow herstelt de lijst met Twitter mappen, zodat u deze rechtstreeks kunt verzenden. [Meer informatie](../send/twitter.md#direct-tw-messages)

Deze workflow wordt standaard elke donderdag om 7.30 uur geactiveerd. U kunt de **[!UICONTROL Execute pending task(s) now]** als u de workflow op elk gewenst moment wilt starten terwijl u deze integratie implementeert.  U kunt de planner ook uitgeven om het werkschema te veranderen dat frequentie teweegbrengt. Meer informatie in [deze pagina](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Om de lijst van Twitter abonnees terug te krijgen, **[!UICONTROL Twitter account synchronization]** Deze optie moet worden gecontroleerd op de service die aan de account is gekoppeld. [Meer informatie](#create-tw-service)

De volgende mappen worden opgeslagen in een specifieke tabel: de tabel met bezoekers. Blader naar de Twitter om de lijst met mappen weer te geven **[!UICONTROL Profiles and Targets > Visitors]**.

Voor elke volgende gegevens slaat Adobe Campaign de volgende gegevens op:

* **[!UICONTROL Origin]**: TWITTER
* **[!UICONTROL External ID]**: gebruikers-id
* **[!UICONTROL Username]**: accountnaam van de gebruiker
* **[!UICONTROL Full name]**: naam van de gebruiker
* **[!UICONTROL Number of friends]**: aantal volgers
* **[!UICONTROL Checked]**: in dit veld wordt aangegeven of de gebruiker een geverifieerde Twitter-account heeft

Zodra deze configuratie wordt gedaan, kunt u tweets aan uw rekeningen van de Twitter posten en directe berichten naar uw volgers verzenden. [Meer informatie](../send/twitter.md)

## Een testaccount maken bij Twitter {#tw-test-account}

Naast een account voor Twitters maakt u een account voor een particuliere Twitter die u kunt gebruiken voor verzending [proefdrukken van tweet](../send/twitter.md#send-tw-proofs). Volg de onderstaande stappen om dit te doen:

1. Maak een nieuwe Twitter-account.
1. Toegang krijgen tot de account  **Instellingen**.
1. Bladeren naar **Privacy en veiligheid** en **Publiek en tags toepassen** en de **Protect your Tweets** -optie. Uw tweets en andere accountgegevens zijn alleen zichtbaar voor de personen die u volgen.

![](assets/social_tw_test_page.png)

Configureer uw Twitter-app en campagneservice om met deze testaccount te werken, zoals hierboven beschreven.
