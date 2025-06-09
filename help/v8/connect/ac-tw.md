---
title: Werken met campagne en X (Twitter)
description: Leer hoe u uw campagneomgeving kunt integreren met X (voorheen bekend als Twitter)
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 2%

---

# Werken met campagne en X (Twitter) {#tw-ac-ovv}

**het Leiden sociale netwerken (Sociale Marketing)** module laat u met uw klanten via X (vroeger gekend als Twitter) in wisselwerking staan. Gebruik deze mogelijkheid om:

* Post berichten en verzend DMs - Gebruik de Sociale Marketing van Adobe Campaign om berichten op X te posten. U kunt ook directe berichten verzenden naar al uw volgers.

* Verzamel nieuwe contacten - Adobe Campaign Social Marketing maakt het ook gemakkelijk om nieuwe contacten te verwerven: contacteer gebruikers en vraag hen of zij hun profielinformatie willen delen. Als ze het accepteren, herstelt Adobe Campaign automatisch de gegevens, waarmee u doelgerichte campagnes kunt voeren en waar mogelijk kanaalstrategieën kunt implementeren.


>[!NOTE]
>
>Als Beheerde gebruiker van de Diensten van de Wolk, [ contacteer Adobe ](../start/campaign-faq.md#support) om Campagne met X te verbinden. **het Leiden sociale netwerken (Sociale Marketing)** toe:voegen-op moet op uw milieu, door het specifieke pakket worden geïnstalleerd, en de Externe Rekening Twitter moet worden gevormd.


Als u Adobe Campaign wilt configureren om tweets te posten naar uw X-accounts, kunt u voor deze accounts schrijfrechten delegeren aan Adobe Campaign. Hiervoor moet u:

1. Maak een X-account en meld u aan voor een ontwikkelingsaccount. [Meer informatie](#dev-account)
1. (optioneel) Maak een test-X-account voor het verzenden van proefdrukken. [Meer informatie](#tw-test-account)
1. Maak een X-toepassing (één app per X-account). [Meer informatie](#create-an-app-on-twitter)
1. Maak een nieuwe service voor **[!UICONTROL Twitter]** (één service per X-account). [Meer informatie](#create-tw-service)
1. Synchroniseer uw X-account met campagne. [Meer informatie](#synchro-tw-accounts)

## X-ontwikkelingsaccount {#dev-account}

Om met deze integratie te beginnen, moet u omhoog voor a [ X ontwikkelaarsrekening ](https://developer.twitter.com){target="_blank"} ondertekenen.

De campagne gebruikt versie 1.1 van X API. Om het te gebruiken, moet u voor Verhoogde toegang via het Portaal van de Ontwikkelaar aanvragen. Leer meer over X Verhoogde Toegang [ in deze pagina ](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Een toepassing maken op X {#create-an-app-on-twitter}

Zodra u met Verhoogde toegang bent goedgekeurd, creeer een X toepassing om Adobe Campaign toe te laten om posten op uw rekening van X tot stand te brengen. Hiervoor voert u de volgende stappen uit:

1. Meld u aan bij uw X-account.
1. Verbind met [ X ontwikkelaarsportaal ](https://developer.twitter.com/en/apps){target="_blank"}.
1. Selecteer **creeer een app**.
1. Laat X de medewerker u door het proces begeleiden.
1. Om Adobe Campaign toe te staan om posten op uw rekening tot stand te brengen, geef aan de **toestemmingen van de Toepassing** van de de authentificatieset van de Gebruiker van uw app uit. Selecteer **Gelezen, schrijven, en Directe Berichten**.

   ![](assets/tw-permissions.png)

1. In het **Type van app** sectie, uitgezocht **Web App, Geautomatiseerde App of Bot**. U kunt het **CallbackURL** gebied leeg verlaten, en uw configuratie bewaren.

   ![](assets/tw-app-type.png)

1. Terug naar uw app dashboard, selecteer uw app en doorblader aan **Sleutels en tokens** tabel. Onder **Symbolisch en Geheim van de Toegang**, als **leest, schrijft, en de Directe toestemming van Berichten** niet wordt vermeld, moet u het teken en geheim van uw app opnieuw produceren. Alle toetsen en tokens moeten bij het maken worden opgeslagen. U hebt ze nodig om uw service Campagne Twitter te configureren.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>U hebt één toepassing per X-account nodig. Als gevolg hiervan moet u een andere testtoepassing maken om proefdrukken naar uw testaccount te verzenden.
>

## Een Twitter-service maken in Campagne {#create-tw-service}

Om uw instantie van de Campagne met uw rekening van X te verbinden, creeer de dienst van a **Twitter** en afgevaardigde schrijven toegang tot Campagne.

>[!CAUTION]
>
>Creeer één **Twitter** dienst per rekening van X. Dientengevolge, moet u een andere testdienst tot stand brengen om proeven naar uw [ testrekening ](#tw-test-account) te verzenden.
>
>Elke **Twitter** dienst moet ook door Adobe op uw mid-sourcing (MID) instantie worden gecreeerd. Neem contact op met uw Adobe-vertegenwoordiger om uw omgeving te configureren.
>

Als u instellingen wilt invoeren, hebt u zowel toegang tot uw Adobe Campaign Client Console als tot uw X-toepassingsmachtigingen.

1. In **Adobe Campaign**, doorblader aan het **[!UICONTROL Profiles and targets]** lusje, en selecteer de **[!UICONTROL Services and Subscriptions]** verbinding
1. Maak een nieuwe service.
1. Selecteer het type **[!UICONTROL Twitter]** .
1. Voer het label en de interne naam van de service in.

   >[!CAUTION]
   >
   >De **[!UICONTROL Internal name]** van de service moet precies dezelfde naam hebben als uw X-account.
   >

1. Standaard worden volgers opgeslagen in de map **[!UICONTROL Visitors]** . U kunt een andere locatie selecteren in het veld **[!UICONTROL Visitor folder]** . [Meer informatie](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >De **[!UICONTROL Synchronize subscriptions]** optie wordt toegelaten door gebrek: deze optie herstelt automatisch de lijst van uw volgers van X zodat u hen directe berichten [&#128279;](../send/twitter.md#direct-tw-messages) kunt  verzenden. De synchronisatie wordt uitgevoerd door a [ specifiek technisch werkschema ](#synchro-tw-accounts).

1. Van uw app van X, kopieer de inhoud van de **Sleutel API** en **[API Zeer belangrijk Geheime]** gebieden en kleef hen in **[!UICONTROL Consumer key]** en **[!UICONTROL Consumer secret]** gebieden van uw 2&rbrace; Twitter **dienst van de Campagne**.

1. Van uw app van X, kopieer de inhoud van de **Token van de Toegang** en **Symbolische Geheime van de Toegang** gebieden en kleef hen in **[!UICONTROL Access token]** en **[!UICONTROL Access token secret]** gebieden van uw Campagne **Twitter** dienst.

1. Klik in Campagne Client Console op **[!UICONTROL Save]** . U hebt nu schrijftoegang gedelegeerd aan Adobe Campaign.

U kunt de instellingen controleren door:

* Bewerk de **Twitter** dienst die u net hebt gecreeerd.
* Blader door het tabblad **[!UICONTROL Twitter page]** : uw Twitter-account moet worden weergegeven.
  ![](assets/tw-page.png)

## Uw X-account synchroniseren {#synchro-tw-accounts}

De synchronisatie tussen Campagne en X wordt beheerd door specifieke technische werkschema&#39;s. Deze workflows worden opgeslagen in de map **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** .

Zij worden tegengehouden door gebrek: u moet hen manueel beginnen wanneer u begint de **Sociale Marketing** module te gebruiken.

De technische workflow van **[!UICONTROL Synchronization of Twitter accounts]** synchroniseert X-accounts in Adobe Campaign. Deze workflow herstelt de lijst met X-volgers, zodat u deze rechtstreeks kunt verzenden. [Meer informatie](../send/twitter.md#direct-tw-messages)

Deze workflow wordt standaard elke donderdag om 7.30 uur geactiveerd. U kunt de optie **[!UICONTROL Execute pending task(s) now]** gebruiken om de workflow op elk gewenst moment tijdens de implementatie van deze integratie te starten.  U kunt de planner ook uitgeven om het werkschema te veranderen dat frequentie teweegbrengt. Meer informatie vindt u [op deze pagina](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Als u de lijst met X-abonnees wilt herstellen, moet de optie **[!UICONTROL Twitter account synchronization]** worden gecontroleerd op de service die aan de account is gekoppeld. [Meer informatie](#create-tw-service)

De volgende mappen worden opgeslagen in een specifieke tabel: de tabel met bezoekers. Blader naar **[!UICONTROL Profiles and Targets > Visitors]** om de lijst met X-volgers weer te geven.

Voor elke volgende gegevens slaat Adobe Campaign de volgende gegevens op:

* **[!UICONTROL Origin]**: Twitter
* **[!UICONTROL External ID]**: gebruikers-id
* **[!UICONTROL Username]**: accountnaam van de gebruiker
* **[!UICONTROL Full name]**: naam van de gebruiker
* **[!UICONTROL Number of friends]**: aantal volgers
* **[!UICONTROL Checked]**: in dit veld wordt aangegeven of de gebruiker een geverifieerde Twitter-account heeft

Zodra deze configuratie wordt gedaan, kunt u berichten op uw rekeningen van X tot stand brengen en directe berichten verzenden naar uw volgers. [Meer informatie](../send/twitter.md)

## Een testaccount maken op X {#tw-test-account}

Naast de rekening van X, creeer een privé rekening van X die voor het verzenden van [ tweet proef ](../send/twitter.md#send-tw-proofs) kan worden gebruikt. Hiervoor voert u de volgende stappen uit:

1. Maak een nieuw X-account.
1. Heb toegang tot de rekening **Montages**.
1. Blader naar **Privacy &amp; Veiligheid** en **Publiek en het Tags toevoegen** en controleer **uw plaatsen** optie beschermen. Je berichten en andere accountgegevens zijn alleen zichtbaar voor mensen die je volgen.

![](assets/do-not-localize/social_tw_test_page.png)

Configureer uw X-app en Campagne-service om met deze testaccount te werken, zoals hierboven beschreven.
