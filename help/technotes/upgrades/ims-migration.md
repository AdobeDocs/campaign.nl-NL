---
title: Migratie van technische gebruikers naar Adobe Developer-console
description: Leer hoe u technische operatoren van campagnes kunt migreren naar een technische account op de Adobe Developer-console
feature: Technote
role: Admin
exl-id: 775c5dbb-ef73-48dd-b163-23cfadc3dab8
source-git-commit: 07c2a7460c407a0afb536d8b64f4105d8bc547f4
workflow-type: tm+mt
source-wordcount: '1547'
ht-degree: 0%

---

# Migratie van technische operatoren van campagnes naar Adobe Developer Console {#migrate-tech-users-to-ims}

Als onderdeel van de inspanningen om het beveiligings- en verificatieproces te versterken, te beginnen met Campagne v8.5, wordt het verificatieproces voor Campagne v8 verbeterd. Technische operatoren kunnen nu de [Adobe Identity Management System (IMS)](https://helpx.adobe.com/nl/enterprise/using/identity.html){target="_blank"} om verbinding te maken met Campagne. Meer informatie over het verificatieproces van de nieuwe server naar de server vindt u in [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Een technische operator is een Campagnegebruikersprofiel dat expliciet is gemaakt voor API-integratie. In dit artikel worden de stappen beschreven die nodig zijn om een technische operator via de Adobe Developer-console naar een technische account te migreren.


## Heb je invloed op?{#ims-impacts}

Als u API-aanroepen maakt van een systeem dat extern is voor Campagne, naar de instantie Campagne Marketing of naar de instantie Real-Time Message Center, moet u de technische operator(s) migreren naar een technische account(s) via de Adobe Developer-console, zoals hieronder beschreven.

Deze wijziging is van toepassing vanaf Campagne v8.5 en wordt **verplicht** startcampagne v8.6.


## Migratieproces {#ims-migration-procedure}

Voer de onderstaande stappen uit om een of meer technische accounts te maken in de Adobe Developer Console en gebruik vervolgens deze nieuwe accounts om de verificatiemethoden te kunnen wijzigen voor al uw externe systemen die API-aanroepen uitvoeren in Adobe Campaign.

Een overzicht van de stappen is:

* Een project maken in de Adobe Developer-console
* De juiste API&#39;s toewijzen aan het nieuwe project
* De vereiste profielen van het Product van de Campagne aan het project verlenen
* De API&#39;s bijwerken en de nieuwe gegevens van de technische account gebruiken
* Verwijder de verouderde technische operatoren uit uw Campagne-instantie

### Voorwaarden voor migratie{#ims-migration-prerequisites}

<!--To be able to create the technical accounts which replace the technical operators, the prerequisite that the proper Campaign Product Profiles exist within the Admin Console for all Campaign instances need to be validated. You can learn more about Product Profiles within the Adobe Console in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.-->

Voor API-aanroepen in de Message Center-instantie(s) had een productprofiel moeten worden gemaakt tijdens de upgrade naar Campagne v8.5 of tijdens de provisioning van de instantie. Dit productprofiel heeft de volgende naam:

`campaign - <your campaign instance> - messagecenter`

Als u reeds op IMS gebaseerde authentificatie voor gebruikerstoegang tot Campagne gebruikt, dan zouden de productprofielen nodig voor de API vraag reeds binnen de Admin Console moeten bestaan. Als u een groep van de douaneexploitant binnen Campagne voor de API vraag aan de instantie van de Marketing gebruikt, moet u dat productprofiel binnen de Admin Console tot stand brengen.

In andere gevallen moet u contact opnemen met de Adobe Transition Manager, zodat technische teams van Adoben uw bestaande groepen met operatoren en benoemde rechten kunnen migreren naar de productprofielen in de Admin Console.


### Stap 1 - Maak uw Campagne-project in de Adobe Developer-console {#ims-migration-step-1}

Integraties worden gemaakt als onderdeel van een **Project** in Adobe Developer Console. Meer informatie over projecten in [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

U kunt elk project gebruiken dat u eerder hebt gemaakt of u kunt een nieuw project maken. De stappen voor het maken van een project worden beschreven in het dialoogvenster [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}. U vindt hieronder de belangrijkste stappen

<!--
For this migration, you must add below APIs in your project: **I/O Management API** and **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)-->

Als u een nieuw project wilt maken, klikt u op **Nieuw project maken** in het hoofdscherm van de Adobe Developer-console.

![](assets/New-Project.png)

U kunt de **Project bewerken** om de naam van dit project te wijzigen.


### Stap 2 - voeg APIs aan uw project toe {#ims-migration-step-2}

Voeg vanuit het nieuwe projectscherm de API&#39;s toe die nodig zijn om dit project als een technische account te kunnen gebruiken voor uw API-aanroepen naar Adobe Campaign.

Ga als volgt te werk om API&#39;s aan uw project toe te voegen:

1. Klikken op **API toevoegen** om APIs te selecteren om aan uw project toe te voegen.
   ![](assets/do-not-localize/ims-updates-01.png)
1. Selecteer de Adobe Campaign API en voeg deze toe aan uw project door het selectievakje rechtsboven in de Adobe Campaign-kaart in te schakelen. Dit selectievakje wordt weergegeven wanneer u de muis boven de kaart houdt
   ![](assets/do-not-localize/ims-updates-02.png)
1. Klikken **Volgende** onder aan het scherm.

### Stap 3 - selecteer het authentificatietype  {#ims-migration-step-3}

In de **API configureren** het vereiste verificatietype. **OAuth Server-to-Server** Verificatie is vereist voor dit project. Zorg ervoor dat deze is geselecteerd en klik op **Volgende** onder aan het scherm.

![](assets/do-not-localize/ims-updates-03.png)

<!--
Once your project is created in the Adobe Developer Console, add an API that uses Server-to-Server authentication. Learn how to set up the OAuth Server-to-Server credential in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

When the API has been successfully connected, you can access the newly generated credentials including Client ID and Client Secret, as well as generate an access token.-->

### Stap 4 - Selecteer de productprofielen {#ims-migration-step-4}

Zoals beschreven in de sectie Voorwaarden moet u de juiste productprofielen toewijzen die door het project worden gebruikt. In deze stap moet u het productprofiel of de profielen selecteren die moeten worden gebruikt door de technische account die wordt gemaakt.

Als dit technische account wordt gebruikt om API-aanroepen uit te voeren naar de Message Center-instantie, moet u de Adobe selecteren om een productprofiel te maken dat eindigt met `messagecenter`.

Voor API-aanroepen naar de marketinginstantie(s) selecteert u het productprofiel dat overeenkomt met de instantie en de Operator Group.

Klik op **geconfigureerde API opslaan** onder aan het scherm.

<!--
You can now add your Campaign product profile to the project, as detailed below:

1. Open the Adobe Campaign API.
1. Click the **Edit product profiles** button

    ![](assets/do-not-localize/ims-edit-api.png)

1. Assign all the relevant Product Profiles to the API, for example 'messagecenter', and save your changes.
1. Browse to the **Credential details** tab of your project, and copy the **Technical Account Email** value.-->

### Stap 5 - voeg toe I/O beheer API aan uw project {#ims-migration-step-5}


Van het projectscherm, klik **[!UICONTROL + Add to Project]** en kiest u **[!UICONTROL API]** linksboven in het scherm om de API voor I/O-beheer aan dit project toe te voegen.

![](assets/do-not-localize/ims-updates-04.png)

In de **Een API toevoegen** scherm, omlaag schuiven om de **API voor I/O-beheer** kaart. Selecteer het door checkbox te klikken die verschijnt wanneer u over de kaart beweegt. Klik vervolgens op **Volgende** onder aan het scherm.

![](assets/do-not-localize/ims-updates-05.png)


In de **API configureren** -scherm, bestaat de OAuth Server-to-Server-verificatie al. Klikken **geconfigureerde API opslaan** onder aan het scherm.


![](assets/do-not-localize/ims-updates-06.png)

Dit neemt u terug naar het scherm van het Project binnen het I/O Beheer API van het pas gecreëerde project. Klik op de projectnaam in de broodkruimels bij de bovenkant van het scherm om terug naar de belangrijkste pagina van de Details van het Project te nemen.


### Stap 6 - verifieer de projectopstelling {#ims-migration-step-6}

Controleer uw project om ervoor te zorgen dat het er net als hieronder uitziet **API voor I/O-beheer** en **ADOBE CAMPAIGN API** zichtbaar in de sectie Producten en de Diensten en **OAuth Server-to-Server** in de sectie Referenties.

![](assets/do-not-localize/ims-updates-07.png)


### Stap 7 - Valideer uw configuratie {#ims-migration-step-7}

Voer de stappen in het dialoogvenster [Handleiding voor Adobe Developer Console-referenties](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} voor het produceren van een toegangstoken en kopieer het verstrekte bevel van de Steekproef cURL. U kunt een soapaanroep maken met deze gegevens om te testen of u de Adobe Campaign-instantie(s) correct kunt verifiëren en er verbinding mee kunt maken. We raden u aan deze validatie uit te voeren voordat u alle wijzigingen aanbrengt in de integratie van de externe API.

### Stap 8 - De integratie van de externe API bijwerken {#ims-migration-step-8}

U moet nu alle API-integraties bijwerken en aanroepen naar Adobe Campaign uitvoeren om het zojuist gemaakte technische account te kunnen gebruiken.

Raadpleeg voor meer informatie over de integratiestappen van de API, waaronder een voorbeeldcode voor een vloeiende integratie [Adobe Developer Console-verificatiedocumentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Hieronder zijn steekproef SOAP vraag die vóór en na migratievraag naar de derdesystemen toont.

Als u Adobe Identity Management System (IMS)-verificatie gebruikt om een WSDL-bestand te genereren, moet u het volgende toevoegen `Authorization: Bearer <IMS_Technical_Token_Token>` in de postbode :

```
curl --location --request POST 'https://<instance_url>/nl/jsp/schemawsdl.jsp?schema=nms:rtEvent' \--header 'Authorization: Bearer <Technical account access token>'
```

Zodra het migratieproces wordt bereikt en bevestigd, worden de Vraag van Soap als volgt bijgewerkt:

* Vóór de migratie: er was geen ondersteuning voor het token voor toegang tot de technische account.

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```

* Na de migratie: er is ondersteuning voor het token voor toegang tot de technische account. Van het toegangstoken wordt verwacht dat het wordt geleverd in `Authorization` koptekst als token voor Drager. Het gebruik van sessietoken moet hier worden genegeerd, zoals in het onderstaande voorbeeld met soapoproepen wordt getoond.

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  Authorization: Bearer <IMS_Technical_Token_Token>
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken></urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```

### Stap 9 - (facultatief) Werk de technische rekeningexploitant binnen de cliënt van de Campagne console bij {#ims-migration-step-9}

Deze stap is optioneel en alleen beschikbaar binnen de marketinginstantie(s), niet binnen een Message Center-instantie. Indien specifieke mapmachtigingen of benoemde rechten zijn gedefinieerd voor de technische exploitant, niet via de toegewezen groep(en) bedieners. U moet de nieuwe gebruiker van de Technische Rekening in de Admin Console nu bijwerken om de omslagtoestemmingen of de genoemde vereiste rechten te verlenen.

De gebruiker van de Technische Rekening zal NIET in Adobe Campaign bestaan tot minstens één API vraag aan de Instantie van de Campagne wordt gemaakt, waarbij IMS de gebruiker binnen Campagne zal creëren. Als u de technische gebruikers niet kunt vinden in Campagne, moet u ervoor zorgen dat u een API-aanroep zoals beschreven hebt kunnen verzenden [in stap 7](#ims-migration-step-7).

1. Als u de wijzigingen die nodig zijn voor de nieuwe gebruiker van de technische account wilt toepassen, zoekt u deze via e-mailadres in de clientconsole van de campagne. Dit e-mailadres is gemaakt tijdens de bovenstaande stappen voor het maken en verifiëren van projecten.

   U kunt dit e-mailadres vinden door op het **OAuth Server-to-Server** in de **Credentials** van het project.

   ![](assets/do-not-localize/ims-updates-07.png)

   Blader in het scherm Credentials omlaag om de **Technical Account Email &#x200B;** te zoeken en klik op de knop **Kopiëren** knop.

   ![](assets/do-not-localize/ims-updates-08.png)

1. U moet nu de nieuwe technische operator bijwerken in de Adobe Campaign-clientconsole. U moet de bestaande technische omslagtoestemmingen van de exploitant op de nieuwe technische exploitant toepassen.

   Ga als volgt te werk om deze operator bij te werken:

   1. Blader vanuit Campagne-clientconsoleverkenner naar de **Beheer > Toegangsbeheer > Operatoren**.
   1. Toegang krijgen tot de bestaande technische operator die wordt gebruikt voor API&#39;s.
   1. Blader naar de machtigingen voor de map en controleer de rechten.
   1. Pas de zelfde toestemmingen op de pas gecreëerde technische exploitant toe. De e-mail van deze operator is de **E-mail technische account** eerder gekopieerde waarde.
   1. Sla uw wijzigingen op.


>[!CAUTION]
>
>De nieuwe technische exploitant moet minstens één API vraag hebben gemaakt om aan de cliëntconsole van de Campagne te worden toegevoegd.
>

### Stap 10 - Verwijder de oude technische operator uit Adobe Campaign {#ims-migration-step-10}

Nadat u alle systemen van derden hebt gemigreerd om de nieuwe technische account met IMS-verificatie te gebruiken, kunt u de oude technische operator verwijderen uit de Campagne-clientconsole.

U doet dit door in de de cliëntconsole van de Campagne te registreren, navigerend aan **Beheer > Toegangsbeheer > Operatoren** en de oude technische gebruikers zoeken en verwijderen.
