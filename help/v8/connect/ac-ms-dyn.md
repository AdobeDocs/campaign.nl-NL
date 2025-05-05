---
title: Werken met Campagne en Microsoft Dynamics
description: Leer hoe te met Campagne en de Dynamica van Microsoft werken
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 1%

---

# Werken met Campagne en Microsoft Dynamics 365{#crm-ms-dynamics}

Activeer uw gegevens van CRM op dwars-kanaalmededeling: leer hoe te om contacten van **Dynamica 365 van Microsoft** aan Adobe Campaign over te gaan, en de gegevens van de campagneprestaties (verzendt, opent, klikt, en stuitert) terug van Adobe Campaign aan de Dynamica 365 van Microsoft.

Zodra configuratie wordt gedaan, wordt de gegevenssynchronisatie tussen systemen uitgevoerd via een specifieke werkschemaactiviteit. [Meer informatie](crm-data-sync.md).

>[!NOTE]
>
>De gesteunde versies van de Dynamiek van Microsoft zijn gedetailleerd in de matrijs van de Verenigbaarheid van de Campagne [&#128279;](../start/compatibility-matrix.md).

Voer de onderstaande stappen uit om een speciale externe account te configureren voor het importeren en exporteren van Microsoft Dynamics 365-gegevens naar Adobe Campaign.

Voor elk systeem, moeten deze stappen door een beheerder worden uitgevoerd.

>[!CAUTION]
> De stappen in deze documentatie zullen u door het creëren van integratie/registraties begeleiden die het toewijzen van toestemmingen en/of admin toegang impliceren. Het is uw verantwoordelijkheid om ervoor te zorgen dat deze stappen voldoen aan uw bedrijfsbeleid alvorens uit te voeren, en hen zorgvuldig uit te voeren.

## Microsoft Dynamics 365 configureren {#config-crm-microsoft}

Om de Dynamiek van Microsoft 365 aan het werk met Adobe Campaign via **Web API** te verbinden, login aan [ de Azure Folder van Microsoft ](https://portal.azure.com) gebruikend a **Globale beheerder** credential, en de stappen hieronder te volgen:

1. Krijg uw Dynamica 365 toepassings (cliënt) identiteitskaart [Meer informatie](#get-client-id-microsoft)
1. Sleutel-id voor certificaat en sleutel-id voor Microsoft Dynamics genereren. [Meer informatie](#config-certificate-key-id)
1. Machtigingen configureren. [Meer informatie](#config-permissions-microsoft)
1. Maak een App-gebruiker. [Meer informatie](#create-app-user-microsoft)
1. Codeer de persoonlijke sleutel. [Meer informatie](#configure-acc-for-microsoftt)


### Dynamics 365 Client ID ophalen {#get-client-id-microsoft}

Om de toepassings (cliënt) identiteitskaart te krijgen, moet u een App in Azure Actieve Folder registreren.

1. Blader naar **Azure Actieve Folder > de Registraties van de App**, en selecteer **Nieuwe Registratie**.
1. Ga een unieke naam in die een geval, zoals **kan helpen identificeren adobecampagne`<instance identifier>`**.

Zodra u sparen, wijst de Folder van Microsoft Azure een unieke **identiteitskaart van de Toepassing (cliënt)** aan uw app toe. Deze id hebt u later nodig bij het configureren van Dynamics 365 in Adobe Campaign.

Leer meer in [ Dynamica 365 van Microsoft documentatie ](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"} .

### Sleutel-id voor certificaat en sleutel-id voor Microsoft Dynamics genereren {#config-certificate-key-id}

Om het **belangrijkste herkenningsteken van het Certificaat (customKeyIdentifier)** en **Zeer belangrijke identiteitskaart (keyId)** te krijgen, moet u een certificaat uploaden. Certificaten kunnen als geheimen worden gebruikt om de identiteit van de toepassing te bewijzen wanneer een token wordt aangevraagd. U kunt het ook openbare sleutels noemen.

Volg de onderstaande stappen:

1. Blader naar **Azure Actieve Folder > de Registraties van de App** en selecteer de Toepassing die vroeger werd gecreeerd.
1. Selecteer op **Certificaten &amp; Geheim**.
1. Van het **Certificaten** lusje, klik op **uploadt certificaat**
1. Upload uw openbare certificaat.
1. Blader aan de **Duidelijke** verbinding om het **belangrijkste herkenningsteken van het Certificaat (customKeyIdentifier)** en **Zeer belangrijke identiteitskaart (keyId)** te krijgen.

Het **belangrijkste herkenningsteken van het Certificaat (customKeyIdentifier)** en **Zeer belangrijke identiteitskaart (keyId)** zijn nodig in Campagne om uw van de Dynamiek van Microsoft te vormen 365 CRM externe rekening gebruikend het Certificaat **[!UICONTROL CRM O-Auth type]**.

+++ Het genereren van het openbare certificaat

U kunt opensl gebruiken om het certificaat te genereren.

Bijvoorbeeld:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>U kunt het aantal dagen hier `-days 365` in het codevoorbeeld wijzigen voor een langere geldigheidsperiode van het certificaat.

Vervolgens moet u het certificaat coderen in base64. Hiertoe kunt u de hulp van een Base64-encoder gebruiken of de opdrachtregel `base64 -w0 private.key` voor Linux.

+++

### Machtigingen configureren {#config-permissions-microsoft}

**Stap 1**: Vorm **Vereiste Toestemmingen** voor app die werd gecreeerd.

1. Navigeer aan **Azure Actieve Folder > de Registraties van de App** en selecteer de Toepassing die vroeger werd gecreeerd.
1. Klik **Montages** op de hoogste linkerzijde.
1. Op **Vereiste Toestemmingen**, klik **&#x200B;**&#x200B;toevoegen en **selecteer online API > Dynamische CRM**.
1. Klik **Uitgezochte**, laat **Dynamica 365 van de Toegang als organisatiegebruikers** checkbox toe en klik **Uitgezochte**.
1. Dan, van uw app, selecteer **Manifest** onder **leidt** menu.
1. Van de **Manifest** redacteur, plaats het `allowPublicClient` bezit van `null` aan `true` en klik **sparen**.

**Stap 2**: De toestemming van het beheerder van de subsidie

1. Navigeer aan **Azure Actieve Folder > de toepassingen van de Onderneming**.
1. Selecteer de toepassing waaraan u admin toestemming voor de gehele huurder wilt verlenen.
1. Van het linkerpaneelmenu, uitgezochte **Toestemmingen** onder **Veiligheid**.
1. Klik **verlenen admin toestemming**.

Voor meer informatie over dit, verwijs naar [ Azure documentatie ](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Een App-gebruiker maken {#create-app-user-microsoft}

>[!NOTE]
>
> Deze stap is optioneel met **[!UICONTROL Password credentials]** -verificatie.

De gebruiker van de app is de gebruiker die de hierboven geregistreerde toepassing zal gebruiken. Alle wijzigingen die met de hierboven geregistreerde toepassing zijn aangebracht in Microsoft Dynamics worden doorgevoerd via deze gebruiker.

**Stap 1**: Creeer een niet-interactieve gebruiker op azure actieve folder

1. Klik **Azure Actieve Folder > Gebruikers** en klik **Nieuwe Gebruiker**.
1. Geef een juiste naam die u wilt gebruiken en de gebruikersnaam moet een e-mailindeling zijn.
1. Kies **Beheerder 365 van de Dynamiek 365** in de **Rol van de Folder**.

**Stap 2**: Wijs een juiste vergunning aan de gecreeerde gebruiker toe

1. Van [ Microsoft Azure ](https://portal.azure.com), klik op **Admin app**.
1. Ga naar **Gebruikers > Actieve Gebruikers** en klik op de pas gecreëerde gebruiker.
1. Klik op **geef productvergunningen** uit en selecteer de **Dynamiek 365 Plan van de Betrokkenheid van de Klant**.
1. Klik **dicht**.

**Stap 3**: Creeer een toepassingsgebruiker op Dynamica CRM

1. Van [ Microsoft Azure ](https://portal.azure.com), navigeer aan **Montages > Veiligheid > Gebruikers**.
1. Klik op drop-down, uitgezochte **gebruikers van de Toepassing**, en klik **Nieuw**.
1. Gebruik dezelfde gebruikersnaam als de gebruiker die hierboven in de actieve map is gemaakt.
1. Wijs **identiteitskaart van de Toepassing** voor [ toe de toepassing u vroeger ](#get-client-id-microsoft) creeerde.
1. Klik op **leiden Rollen** en kies de **beheerder van het Systeem** rol aan de gebruiker.

## Campagne configureren {#configure-acc-for-microsoft}

### Verbinding maken{#new-ms-dyn-external-account}

Ten eerste moet u de externe account van Microsoft Dynamics 365 maken.

1. Blader door het knooppunt **[!UICONTROL Administration > Platform > External accounts]** van de Campagneverkenner en maak een extern account.
1. Selecteer **[!UICONTROL Microsoft Dynamics CRM]** externe rekening in de **sectie van het Type**.
1. Selecteer de verificatiemethode in de vervolgkeuzelijst **[!UICONTROL CRM O-Auth type]** .

   ![](assets/ms-dyn-external-account.png)

   1. Om de externe rekening van CRM van de Dynamica van Microsoft te vormen om met Adobe Campaign met **Credentials van het Wachtwoord te verbinden**, verstrek de volgende details:

      * **Server**: URL van uw server van Microsoft CRM. Als u de URL van uw Microsoft CRM-server wilt vinden, opent u uw Microsoft Dynamics CRM-account en klikt u op Dynamics 365 en selecteert u uw app. Vervolgens vindt u de URL van de server in de adresbalk van uw browser, bijvoorbeeld https://myserver.crm.dynamics.com/.
      * **Rekening**: Rekening die wordt gebruikt om binnen aan Microsoft CRM te ondertekenen.
      * **Wachtwoord**: Rekening die wordt gebruikt om binnen aan Microsoft CRM te ondertekenen.
      * **identiteitskaart van de Cliënt**: Identiteitskaart van de toepassing (cliënt) die van Microsoft kan worden gevonden Azure beheersportaal in Update uw codecategorie, het gebied van identiteitskaart van de Cliënt.
      * **versie van CRM**: Kies de versie van CRM 365 van Dynamica CRM.

   1. Om de externe rekening van CRM van de Dynamica van Microsoft te vormen om met Adobe Campaign met a **Certificaat** te verbinden, verstrek de volgende details:

      * **Server**: URL van uw server van Microsoft CRM. Als u de URL van uw Microsoft CRM-server wilt vinden, opent u uw Microsoft Dynamics CRM-account en klikt u op Dynamics 365 en selecteert u uw app. Vervolgens vindt u de URL van de server in de adresbalk van uw browser, bijvoorbeeld https://myserver.crm.dynamics.com/.
      * **Persoonlijke sleutel**: Exemplaar/plak de privé sleutel, gecodeerde base64 zoals die in [ wordt verklaard deze sectie ](#config-certificate-key-id).
      * **Zeer belangrijke identiteitskaart**: Sleutel beschikbaar in het **Manifest** lusje van uw toepassing, zoals verklaard in [ deze sectie ](#config-certificate-key-id).
      * **Zeer belangrijke herkenningsteken van de Douane**: Herkenningsteken beschikbaar in het **Manifest** lusje van uw toepassing, zoals verklaard in [ deze sectie ](#config-certificate-key-id).
      * **herkenningsteken van de Cliënt**: identiteitskaart van de toepassing (cliënt) die van Microsoft kan worden gevonden Azure beheersportaal zoals die in [ wordt verklaard deze sectie ](#get-client-id-microsoft).
      * **versie van CRM**: Kies de versie van CRM 365 van Dynamica CRM.

1. Selecteer **toelaten** optie om de rekening in Campagne te activeren.

>[!NOTE]
>
>Om de opstelling goed te keuren, logoff en terug aan de cliëntconsole van Adobe Campaign.

### Tabellen selecteren voor synchronisatie{#ms-dyn-create-tables}

U kunt nu tabellen configureren voor synchronisatie.

1. Klik op **[!UICONTROL Microsoft CRM configuration wizard...]** .
1. Selecteer de tabellen die u wilt synchroniseren en start het proces.
1. Controleer het schema dat in Adobe Campaign is gegenereerd in het knooppunt **[!UICONTROL Administration > Configuration > Data schemas]** .

>[!NOTE]
>
>Voeg twee URL&#39;s toe aan de lijst van gewenste personen: de URL van de server en `login.microsoftonline.com` . Neem hiervoor contact op met uw Adobe.

## Opsommingen synchroniseren{#sfdc-enum-sync}

Zodra het schema wordt gecreeerd, kunt u opsommingen van Dynamiek 365 aan Adobe Campaign automatisch synchroniseren.

1. Open de assistent via de koppeling **[!UICONTROL Synchronizing enumerations...]** .
1. Selecteer de opsomming van Adobe Campaign die de Dynamica 365 opsomming aanpast.
U kunt alle waarden van een Adobe Campaign-opsomming vervangen door die van de CRM: hiervoor selecteert u **[!UICONTROL Yes]** in de kolom **[!UICONTROL Replace]** .
1. Klik op **[!UICONTROL Next]** en vervolgens op **[!UICONTROL Start]** om de opsommingen te importeren.
1. Blader door het knooppunt **[!UICONTROL Administration > Platform > Enumerations]** om de geïmporteerde waarden te controleren.

Adobe Campaign en Microsoft Dynamics 365 zijn nu verbonden. U kunt gegevenssynchronisatie tussen de twee systemen instellen.

Als u gegevens wilt synchroniseren tussen Adobe Campaign-gegevens en Microsoft CRM, maakt u een workflow en gebruikt u de **[!UICONTROL CRM connector]** -activiteit.

Leer meer over gegevenssynchronisatie [ in deze pagina ](crm-data-sync.md).

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
