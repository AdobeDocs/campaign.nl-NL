---
title: Migratie van technische gebruikers naar Adobe Developer-console
description: Leer hoe u technische operatoren van campagnes kunt migreren naar een technische account op de Adobe Developer-console
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 0%

---

# Migratie van technische operatoren van campagnes naar Adobe Developer Console {#migrate-tech-users-to-ims}

Vanaf Campagne v8.5 wordt het verificatieproces naar Campagne v8 verbeterd. De technische exploitanten moeten [Adobe Identity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} om verbinding te maken met Campagne. Een technische operator is een Campagnegebruikersprofiel dat expliciet is gemaakt voor API-integratie. In dit artikel worden de stappen beschreven die nodig zijn om een technische operator naar een technische account op de Adobe Developer-console te migreren.

## Wat is er veranderd?{#ims-changes}

Campagne voor gewone gebruikers maakt al verbinding met de Adobe Campaign-console via hun Adobe ID, via Adobe Identity Management System (IMS). Als onderdeel van de inspanning om veiligheid en authentificatieproces te versterken, roept de toepassing van de Cliënt van Adobe Campaign nu Campagne APIs direct gebruikend het technische IMS accountteken.

Meer informatie over het verificatieproces van de nieuwe server naar de server vindt u in [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Deze wijziging is van toepassing vanaf Campagne v8.5 en wordt **verplicht** startcampagne v8.6.


## Heeft dit gevolgen voor u?{#ims-impacts}

Als u campagne-API&#39;s gebruikt, moet u de technische operator(s) migreren naar Adobe Developer Console, zoals hieronder wordt beschreven.

## Hoe migreren?{#ims-migration-procedure}

### Vereisten{#ims-migration-prerequisites}

Voordat u met het migratieproces begint, moet u contact opnemen met uw Adobe-medewerker, zodat technische teams van Adobe uw bestaande groepen met operatoren en benoemde rechten kunnen migreren naar het Adobe Identity Management System (IMS).

### Stap 1 - Uw Campagne-project maken/bijwerken in Adobe Developer Console{#ims-migration-step-1}

Integraties worden gemaakt als onderdeel van een **Project** in Adobe Developer Console. Meer informatie over projecten in [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

Als gebruiker van Campagne v8 zou u reeds een project in de Console van Adobe Developer moeten hebben. Als niet, moet u een project tot stand brengen. De stappen om een project te creëren zijn gedetailleerd [in Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Zodra u toegang tot uw Campagne project hebt, kunt u de diensten met inbegrip van APIs, Adobe Campaign, en I/O Beheer API toevoegen. Voor deze migratie moet u de volgende API&#39;s toevoegen aan uw project: **API voor I/O-beheer** en **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Stap 2 - voeg API aan uw project toe gebruikend Server aan de authentificatie van de Server{#ims-migration-step-2}

Nadat uw project in de Adobe Developer-console is gemaakt, voegt u een API toe die Server-naar-server verificatie gebruikt. Leer hoe u de referentie OAuth Server-to-Server instelt in [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Wanneer de API met succes is verbonden, kunt u tot de onlangs geproduceerde geloofsbrieven met inbegrip van identiteitskaart van de Cliënt en Geheim van de Cliënt toegang hebben, evenals een toegangstoken produceren.

### Stap 3 - voeg het productprofiel aan het project toe{#ims-migration-step-3}

U kunt nu uw productprofiel voor Campagne toevoegen aan het project, zoals hieronder beschreven:

1. Open de Adobe Campaign API.
1. Klik op de knop **Productprofielen bewerken** knop

   ![](assets/do-not-localize/ims-edit-api.png)

1. Wijs alle relevante productprofielen toe aan de API, bijvoorbeeld &#39;messageCenter&#39;, en sla uw wijzigingen op.
1. Bladeren naar de **Referentiegegevens** en kopieer het **E-mail technische account** waarde.

### Stap 4 - Werk de technische exploitant in de Console van de Cliënt bij {#ims-migration-step-4}


Deze stap is alleen vereist als specifieke mapmachtigingen of benoemde rechten zijn gedefinieerd voor deze operator (niet via de groep van de operator).

U moet nu de nieuwe technische operator bijwerken in Adobe Campaign Client Console. U moet de bestaande technische omslagtoestemmingen van de exploitant op de nieuwe technische exploitant toepassen.
Ga als volgt te werk om deze operator bij te werken:

1. Blader vanuit de Campagne Client Console-verkenner naar de **Beheer > Toegangsbeheer > Operatoren**.
1. Toegang tot de bestaande technische operator die wordt gebruikt voor API&#39;s.
1. Blader naar de machtigingen voor de map en controleer de rechten.
1. Pas de zelfde toestemmingen op de pas gecreëerde technische exploitant toe. De e-mail van deze operator is de **E-mail technische account** eerder gekopieerde waarde.
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

Voer de stappen in het dialoogvenster [Handleiding voor Adobe Developer Console-referenties](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} voor het produceren van een toegangstoken en kopieer het verstrekte bevel van de Steekproef cURL.


### Stap 6 - Werk de integratie van de derdeAPI bij {#ims-migration-step-6}

U moet de API-integratie bijwerken met systemen van derden.

Raadpleeg voor meer informatie over de integratiestappen van de API, waaronder een voorbeeldcode voor een vloeiende integratie [Adobe Developer Console-verificatiedocumentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Stap 7 - Verwijder de oude technische operator {#ims-migration-step-7}


Na de migratie van alle API/aangepaste code-integratie met de gebruiker van de technische account. U kunt de oude technische exploitant van de de cliëntconsole van de Campagne schrappen.

### Soap call samples{#ims-migration-samples}

Zodra het migratieproces wordt bereikt en bevestigd, worden de Vraag van Soap als volgt bijgewerkt:

* Voor de migratie

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

* Na de migratie

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
