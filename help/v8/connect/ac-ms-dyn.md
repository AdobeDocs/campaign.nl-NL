---
title: Werken met Campagne en Microsoft Dynamics
description: Leer hoe u kunt werken met Campagne en Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Werken met Campagne en Microsoft Dynamics 365{#crm-ms-dynamics}

Activeer uw CRM-gegevens voor kanaalcommunicatie: leren hoe te om contacten van over te gaan **Microsoft Dynamics 365** naar Adobe Campaign en deel gegevens over de campagneprestaties (verstuurt, opent, klikt en stuit) van Adobe Campaign naar Microsoft Dynamics 365.

Zodra configuratie wordt gedaan, wordt de gegevenssynchronisatie tussen systemen uitgevoerd via een specifieke werkschemaactiviteit. [Meer informatie](crm-data-sync.md).

>[!NOTE]
>
>Ondersteunde versies voor Microsoft Dynamics worden gedetailleerd beschreven in de campagne [Compatibiliteitsmatrix](../start/compatibility-matrix.md).

Voer de onderstaande stappen uit om een speciale externe account te configureren voor het importeren en exporteren van Microsoft Dynamics 365-gegevens naar Adobe Campaign.

Voor elk systeem, moeten deze stappen door een beheerder worden uitgevoerd.

>[!CAUTION]
> De stappen in deze documentatie zullen u door het creëren van integratie/registraties begeleiden die het toewijzen van toestemmingen en/of admin toegang impliceren. Het is uw verantwoordelijkheid om ervoor te zorgen dat deze stappen voldoen aan uw bedrijfsbeleid alvorens uit te voeren, en hen zorgvuldig uit te voeren.

## Microsoft Dynamics 365 configureren {#config-crm-microsoft}

Microsoft Dynamics 365 verbinden om met Adobe Campaign te werken via **Web-API**, aanmelden bij [Microsoft Azure Directory](https://portal.azure.com) met een **Algemene beheerder** referentie en volg de onderstaande stappen:

1. Krijg uw Dynamica 365 toepassings (cliënt) identiteitskaart [Meer informatie](#get-client-id-microsoft)
1. Sleutel-id voor Microsoft Dynamics Certificate en Key ID genereren. [Meer informatie](#config-certificate-key-id)
1. Machtigingen configureren. [Meer informatie](#config-permissions-microsoft)
1. Maak een App-gebruiker. [Meer informatie](#create-app-user-microsoft)
1. Codeer de persoonlijke sleutel. [Meer informatie](#configure-acc-for-microsoftt)


### Dynamics 365 Client ID ophalen {#get-client-id-microsoft}

Om de toepassings (cliënt) identiteitskaart te krijgen, moet u een App in Azure Actieve Folder registreren.

1. Bladeren naar **Azure Active Directory > App-registraties** en selecteert u **Nieuwe registratie**.
1. Voer een unieke naam in die u kunt helpen een instantie te identificeren, zoals **adobecampagne`<instance identifier>`**.

Als u het bestand eenmaal hebt opgeslagen, wijst Microsoft Azure Directory een unieke gebeurtenis toe **Toepassings-id (client)** naar uw app. Deze id hebt u later nodig bij het configureren van Dynamics 365 in Adobe Campaign.

Meer informatie in [Microsoft Dynamics 365 - documentatie](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target=&quot;_blank&quot;}.

### Sleutel-id voor Microsoft Dynamics Certificate en Key ID genereren {#config-certificate-key-id}

Om de **Id van certificaatsleutel (customKeyIdentifier)** en de **Sleutel-id (keyId)**, moet u een certificaat uploaden. Certificaten kunnen als geheimen worden gebruikt om de identiteit van de toepassing aan te tonen wanneer een token wordt aangevraagd. U kunt het ook openbare sleutels noemen.

Volg de onderstaande stappen:

1. Bladeren naar **Azure Active Directory > App-registraties** en selecteer de toepassing die eerder is gemaakt.
1. Selecteren op **Certificaten en geheim**.
1. Van de **Certificaten** tabblad, klikt u op **Certificaat uploaden**
1. Upload uw openbare certificaat.
1. Bladeren naar de **Manifest** koppeling om de **Id van certificaatsleutel (customKeyIdentifier)** en de **Sleutel-id (keyId)**.

De **Id van certificaatsleutel (customKeyIdentifier)** en de **Sleutel-id (keyId)** zijn nodig in Campagne om uw externe rekening van Microsoft Dynamics 365 CRM te vormen gebruikend het Certificaat **[!UICONTROL CRM O-Auth type]**.

+++ Het genereren van het openbare certificaat

U kunt opensl gebruiken om het certificaat te genereren.

Bijvoorbeeld:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>U kunt hier het aantal dagen wijzigen `-days 365`, in de voorbeeldcode voor een langere geldigheidsperiode van het certificaat.

Vervolgens moet u het certificaat coderen in base64. Om dit te doen, kunt u de hulp van een Codeur gebruiken Base64 of de bevellijn gebruiken `base64 -w0 private.key` voor Linux.

+++

### Machtigingen configureren {#config-permissions-microsoft}

**Stap 1**: Configureer de **Vereiste machtigingen** voor de app die is gemaakt.

1. Navigeren naar **Azure Active Directory > App-registraties** en selecteer de toepassing die eerder is gemaakt.
1. Klikken **Instellingen** links boven.
1. Aan **Vereiste machtigingen**, klikt u op **Toevoegen** en **Selecteer een API > Dynamics CRM Online**.
1. Klikken **Selecteren**, enable **De Dynamica 365 van de toegang als organisatiegebruikers** selectievakje en klik op **Selecteren**.
1. Selecteer vervolgens in uw app de optie **Manifest** onder de **Beheren** -menu.
1. Van de **Manifest** editor, stelt de `allowPublicClient` eigenschap van `null` tot `true` en klik op **Opslaan**.

**Stap 2**: Toelating beheerder

1. Navigeren naar **Azure Active Directory > Enterprise-toepassingen**.
1. Selecteer de toepassing waaraan u admin toestemming voor de gehele huurder wilt verlenen.
1. Selecteer in het menu van het linkerdeelvenster de optie **Machtigingen** krachtens **Beveiliging**.
1. Klikken **Toelating beheerder**.

Raadpleeg voor meer informatie hierover [Azure-documentatie](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Een App-gebruiker maken {#create-app-user-microsoft}

>[!NOTE]
>
> Deze stap is optioneel met **[!UICONTROL Password credentials]** verificatie.

De gebruiker van de app is de gebruiker die de hierboven geregistreerde toepassing zal gebruiken. Wijzigingen die met de bovenstaande app zijn aangebracht in Microsoft Dynamics, worden via deze gebruiker doorgevoerd.

**Stap 1**: Een niet-interactieve gebruiker maken in de azure actieve map

1. Klikken **Azure Active Directory > Users** en klik op **Nieuwe gebruiker**.
1. Geef een juiste naam die u wilt gebruiken en de gebruikersnaam moet een e-mailindeling zijn.
1. Kies **Dynamics 365 Administrator** in de **Maprol**.

**Stap 2**: Een juiste licentie toewijzen aan de nieuwe gebruiker

1. Van [Microsoft Azure](https://portal.azure.com), klikt u op **Admin-app**.
1. Ga naar **Gebruikers > Actieve gebruikers** en klik op de nieuwe gebruiker.
1. Klikken op **Productlicenties bewerken** en selecteert u de **Dynamics 365 Customer Engagement Plan**.
1. Klikken **Sluiten**.

**Stap 3**: Creeer een toepassingsgebruiker op Dynamica CRM

1. Van [Microsoft Azure](https://portal.azure.com), navigeer naar **Instellingen > Beveiliging > Gebruikers**.
1. Klik in de vervolgkeuzelijst en selecteer **Toepassingsgebruikers** en klik op **Nieuw**.
1. Gebruik dezelfde gebruikersnaam als de gebruiker die hierboven in de actieve map is gemaakt.
1. Wijs het **Toepassings-id** for [de toepassing die u eerder hebt gemaakt](#get-client-id-microsoft).
1. Klikken op **Rollen beheren** en kiest u **Systeembeheerder** rol voor de gebruiker.

## Campaign configureren {#configure-acc-for-microsoft}

### Verbinding maken{#new-ms-dyn-external-account}

Ten eerste moet u de externe account van Microsoft Dynamics 365 maken.

1. Bladeren in het dialoogvenster **[!UICONTROL Administration > Platform > External accounts]** van de Campagneverkenner en maak een externe account.
1. Selecteren **[!UICONTROL Microsoft Dynamics CRM]** externe rekening in de **Type** sectie.
1. Selecteer de verificatiemethode in het dialoogvenster **[!UICONTROL CRM O-Auth type]** vervolgkeuzelijst.

   ![](assets/ms-dyn-external-account.png)

   1. De externe account van Microsoft Dynamics CRM configureren voor verbinding met Adobe Campaign met **Wachtwoordreferenties** de volgende gegevens verstrekken:

      * **Server**: URL van uw Microsoft CRM-server. Als u de URL van uw Microsoft CRM-server wilt vinden, opent u uw Microsoft Dynamics CRM-account en klikt u op Dynamics 365 en selecteert u uw app. Vervolgens vindt u de URL van de server in de adresbalk van uw browser, bijvoorbeeld https://myserver.crm.dynamics.com/.
      * **Account**: Account gebruikt om u aan te melden bij Microsoft CRM.
      * **Wachtwoord**: Account gebruikt om u aan te melden bij Microsoft CRM.
      * **Client-id**: De toepassings (cliënt) identiteitskaart die van Microsoft Azure beheersportaal in Update uw codecategorie, het gebied van identiteitskaart van de Cliënt kan worden gevonden.
      * **CRM-versie**: Kies de versie van CRM 365 van Dynamica CRM.
   1. Om de externe rekening van CRM van de Dynamica van Microsoft te vormen om met Adobe Campaign te verbinden met **Certificaat** de volgende gegevens verstrekken:

      * **Server**: URL van uw Microsoft CRM-server. Als u de URL van uw Microsoft CRM-server wilt vinden, opent u uw Microsoft Dynamics CRM-account en klikt u op Dynamics 365 en selecteert u uw app. Vervolgens vindt u de URL van de server in de adresbalk van uw browser, bijvoorbeeld https://myserver.crm.dynamics.com/.
      * **Persoonlijke sleutel**: De persoonlijke sleutel met codering base64 kopiëren/plakken, zoals wordt uitgelegd in [deze sectie](#config-certificate-key-id).
      * **Sleutel-id**: Sleutel beschikbaar in het dialoogvenster **Manifest** tabblad van uw toepassing, zoals wordt uitgelegd in [deze sectie](#config-certificate-key-id).
      * **Id van aangepaste sleutel**: Id beschikbaar in het dialoogvenster **Manifest** tabblad van uw toepassing, zoals wordt uitgelegd in [deze sectie](#config-certificate-key-id).
      * **Client-id**: Application (client) ID, te vinden op de Microsoft Azure-beheerportal, zoals uitgelegd in [deze sectie](#get-client-id-microsoft).
      * **CRM-versie**: Kies de versie van CRM 365 van Dynamica CRM.


1. Selecteer **Inschakelen** om het account te activeren in Campagne.

>[!NOTE]
>
>U kunt de installatie goedkeuren door u af en weer aan te melden bij de Adobe Campaign-console.

### Tabellen selecteren om te synchroniseren{#ms-dyn-create-tables}

U kunt nu tabellen configureren om te synchroniseren.

1. Klik op de knop **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. Selecteer de tabellen die u wilt synchroniseren en start het proces.
1. Controleer het schema dat in Adobe Campaign is gegenereerd in het dialoogvenster **[!UICONTROL Administration > Configuration > Data schemas]** knooppunt.

>[!NOTE]
>
>Zorg ervoor om aan de lijst van gewenste personen twee URLs toe te voegen: de server-URL en `login.microsoftonline.com`. Neem hiervoor contact op met uw Adobe-vertegenwoordiger.

## Opsommingen synchroniseren{#sfdc-enum-sync}

Zodra het schema wordt gecreeerd, kunt u opsommingen van Dynamiek 365 aan Adobe Campaign automatisch synchroniseren.

1. Open de assistent vanuit de  **[!UICONTROL Synchronizing enumerations...]** koppeling.
1. Selecteer de opsomming van Adobe Campaign die de Dynamica 365 opsomming aanpast.
U kunt alle waarden van een opsomming van Adobe Campaign door die van CRM vervangen: Selecteer **[!UICONTROL Yes]** in de **[!UICONTROL Replace]** kolom.
1. Klikken **[!UICONTROL Next]** en vervolgens **[!UICONTROL Start]** om de opsommingen te importeren.
1. Bladeren in het dialoogvenster **[!UICONTROL Administration > Platform > Enumerations]** knooppunt om geïmporteerde waarden te controleren.

Adobe Campaign en Microsoft Dynamics 365 zijn nu verbonden. U kunt gegevenssynchronisatie tussen de twee systemen instellen.

Als u gegevens wilt synchroniseren tussen Adobe Campaign-gegevens en Microsoft CRM, maakt u een workflow en gebruikt u de opdracht **[!UICONTROL CRM connector]** activiteit.

Meer informatie over gegevenssynchronisatie [op deze pagina](crm-data-sync.md).

### Ondersteunde veldgegevenstypen {#ms-dyn-supported-types}

Voor Microsoft Dynamics 365 worden de ondersteunde/niet-ondersteunde kenmerktypen hieronder vermeld:


| Type kenmerk | Ondersteund |
| --------------------------------------------------------------------------------- | --------- |
| Basistypen: boolean, datetime, decimal, float, double, integer, bigint , string | Ja |
| Geld (als dubbel) | Ja |
| memo, entiteitsnaam, primarykey, uniqueidentifier (als tekenreeksen) | Ja |
| Status, picklist (we slaan de mogelijke waarden op in opsommingen), state (string) | Ja |
| owner (als string) | Ja |
| Opzoeken (alleen zoeken naar verwijzingen naar één entiteit) | Ja |
| klant | Nee |
| Betreffende | Nee |
| PartyList | Nee |
| ManagedProperty | Nee |
