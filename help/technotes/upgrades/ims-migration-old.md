---
title: Migratie van technische gebruikers naar Adobe Developer-console
description: Leer hoe u technische operatoren van campagnes kunt migreren naar een technische account op de Adobe Developer-console
exl-id: 63008b58-4384-4d2b-864a-57f11d701c01
hide: true
hidefromtoc: true
source-git-commit: 41e39e046ec77de8b5e657ba76645898ff1cd2d7
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 0%

---

# Migratie van de technische actoren van de campagne naar Adobe Developer Console {#migrate-tech-users-to-ims}

Vanaf Campagne v8.5 wordt het verificatieproces naar Campagne v8 verbeterd. De technische exploitanten moeten [ het Systeem van Adobe Identity Management (IMS) ](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} gebruiken om met Campagne te verbinden. Een technische operator is een Campagnegebruikersprofiel dat expliciet is gemaakt voor API-integratie. In dit artikel worden de stappen beschreven die nodig zijn om een technische operator naar een technische account op de Adobe Developer-console te migreren.

## Wat is er veranderd?{#ims-changes}

Campagne voor gewone gebruikers maakt al verbinding met de Adobe Campaign-console via hun Adobe ID, via Adobe Identity Management System (IMS). Als onderdeel van de inspanning om veiligheid en authentificatieproces te versterken, roept de toepassing van de Cliënt van Adobe Campaign nu Campagne APIs direct gebruikend het technische IMS accountteken.

Leer meer over de nieuwe server aan het proces van de serverauthentificatie in [ documentatie van Adobe Developer Console ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Deze verandering is van toepassing beginnend Campagne v8.5, en zal **verplicht** aanvang Campagne v8.6 zijn.


## Heb je invloed op?{#ims-impacts}

Als u campagne-API&#39;s gebruikt, moet u de technische operator(s) migreren naar Adobe Developer Console, zoals hieronder wordt beschreven.

## Hoe migreren?{#ims-migration-procedure}

Elke technische exploitant moet ten minste één technische rekening hebben.

De belangrijkste stappen zijn:

1. Maak eerst de technische rekening die overeenkomt met de technische exploitant. Bijvoorbeeld, veronderstel de pas gecreëerde technische rekening (TA1) voor technische exploitant (TO1).
1. Voer de hieronder beschreven stappen uit op technische rekening TA1
   [ Stap 4 ](#ims-migration-step-4) is facultatief en slechts vereist als de technische exploitant specifieke omslagtoestemmingen heeft.
1. Migreer alle de integratieimplementatie van de Campagne API aan de pas gecreëerde technische rekening TA1.
1. Zodra alle klant die met API/Integratie te maken heeft volledig functioneel begint op TA1, vervang de technische exploitant TO1 door technische rekening TA1.

### Vereisten{#ims-migration-prerequisites}

Voordat u het migratieproces start, moet u contact opnemen met uw Adobe Transition Manager, zodat technische Adobe-teams uw bestaande Operator groups en Named Rights kunnen migreren naar Adobe Identity Management System (IMS).

### Stap 1 - Uw Campagne-project maken/bijwerken in Adobe Developer Console{#ims-migration-step-1}

De integratie wordt gecreeerd als deel van a **Project** binnen Adobe Developer Console. Leer meer over Projecten in [ documentatie van Adobe Developer Console ](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

U kunt elk project gebruiken dat u eerder hebt gemaakt of u kunt een nieuw project maken. De stappen om een project tot stand te brengen zijn gedetailleerd in de [ documentatie van Adobe Developer Console ](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Voor deze migratie, moet u onder APIs in uw project toevoegen: **I/O Beheer API** en **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Stap 2 - voeg API aan uw project toe gebruikend Server aan de authentificatie van de Server{#ims-migration-step-2}

Zodra uw project in Adobe Developer Console wordt gecreeerd, voeg API toe die server-aan-Server authentificatie gebruikt. Leer hoe te opstelling de Server-aan-Server referentie OAuth in [ documentatie van Adobe Developer Console ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Wanneer de API met succes is verbonden, kunt u tot de onlangs geproduceerde geloofsbrieven met inbegrip van identiteitskaart van de Cliënt en Geheim van de Cliënt toegang hebben, evenals een toegangstoken produceren.

### Stap 3 - voeg het productprofiel aan het project toe{#ims-migration-step-3}

U kunt nu uw productprofiel voor Campagne toevoegen aan het project, zoals hieronder beschreven:

1. Open de Adobe Campaign API.
1. Klik **uitgeven productprofielen** knoop

   ![](assets/do-not-localize/ims-edit-api.png)

1. Wijs alle relevante productprofielen toe aan de API, bijvoorbeeld &#39;messageCenter&#39;, en sla uw wijzigingen op.
1. Blader aan het **Credentiële details** lusje van uw project, en kopieer de **Technische waarde E-mail van de Rekening**.

### Stap 4 - Werk de technische operator bij in de clientconsole {#ims-migration-step-4}

Deze stap is alleen vereist als specifieke mapmachtigingen of benoemde rechten zijn gedefinieerd voor deze operator (niet via de groep van de operator).

U moet nu de nieuwe technische operator bijwerken in Adobe Campaign Client Console. U moet de bestaande technische omslagtoestemmingen van de exploitant op de nieuwe technische exploitant toepassen.
Ga als volgt te werk om deze operator bij te werken:

1. Van de ontdekkingsreiziger van de Console van de Cliënt van de Campagne, doorblader aan het **Beleid > Beheer van de Toegang > Operatoren**.
1. Toegang krijgen tot de bestaande technische operator die wordt gebruikt voor API&#39;s.
1. Blader naar de machtigingen voor de map en controleer de rechten.
1. Pas de zelfde toestemmingen op de pas gecreëerde technische exploitant toe. E-mail van deze exploitant is de **Technische die waarde E-mail van de Rekening** vroeger wordt gekopieerd.
1. Sla uw wijzigingen op.


>[!CAUTION]
>
>De nieuwe technische exploitant moet minstens één API vraag hebben gemaakt om aan de Console van de Cliënt van de Campagne te worden toegevoegd.
>

<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Edit the existing technical operator used for APIs.
1. Replace the **Name (login)** of this technical operator by the technical account email retrieved earlier.
1. Browse to the **Edit** button on the top left beside **File**, and select **Edit the XML source**.
1. Update the authentication mode to `ims`, as follows:

    ```javascript
    <operator 
    ...
        <access authenticationType="ims" ...
        ...
        </access>
    ...
    </operator>
    ```

1. Save your changes.

You can also update the technical operator programmatically, using SQL scripts or Campaign APIs. These modes help you automate the steps which update operator's name with associated Technical account email address and/or authentication type. 

* Use the following **SQL Script** to replace operator's name with associated email:

    ```sql
    UPDATE xtkoperator
    SET sauthenticationtype = 'ims',
            sname = '{email}'
    WHERE sname = '{name}' AND itype = 0;
    ```

* Use the following `queryDef.ExecuteQuery` **Campaign API** to fetch id of an operator for given technical operator:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <ExecuteQuery xmlns="urn:xtk:queryDef">
                <sessiontoken>{session_token}</sessiontoken>
                <entity>
                    <queryDef schema="xtk:operator" operation="select">
                        <select>
                            <node expr="@id"/>
                        </select>
                        <where>
                            <condition expr="@name='{name}'"/>
                            <condition expr="@type=0"/>
                        </where>
                    </queryDef>
                </entity>
            </ExecuteQuery>
        </soap:Body>
    </soap:Envelope>
    ```

* Use the following `session.Write` **Campaign API** to update name with given technical account email address:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <Write xmlns="urn:xtk:session">
                <sessiontoken>{session_token}</sessiontoken>
                <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                    <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                        <access authenticationType="ims" />
                    </operator>
                </domDoc>
            </Write>
        </soap:Body>
    </soap:Envelope>
    ```
-->

### Stap 5 - bevestig uw configuratie {#ims-migration-step-5}

Om de verbinding uit te proberen, volg de stappen in de [ de geloofsbrieven van Adobe Developer Console gids ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} voor het produceren van een toegangstoken worden gedetailleerd en kopieer het bevel van de Steekproef cURL verstrekte.


### Stap 6 - Werk de externe API-integratie bij {#ims-migration-step-6}

U moet de API-integratie bijwerken met systemen van derden.

Voor verdere details over API integratiestappen, met inbegrip van een steekproefcode voor vlotte integratie, verwijs naar [ de authentificatiedocumentatie van Adobe Developer Console ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Stap 7 - Verwijder de oude technische operator {#ims-migration-step-7}


Na de migratie van alle API/aangepaste code-integratie met de gebruiker van de technische account. U kunt de oude technische exploitant van de de cliëntconsole van de Campagne schrappen.

### Soap call samples{#ims-migration-samples}

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

* Na de migratie: er is ondersteuning voor het token voor toegang tot de technische account. Van het toegangstoken wordt verwacht dat het in `Authorization` kopbal als Token van de Drager wordt geleverd. Het gebruik van sessietoken moet hier worden genegeerd, zoals in het onderstaande voorbeeld met soapoproepen wordt getoond.

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
