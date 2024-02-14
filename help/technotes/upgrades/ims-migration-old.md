---
title: Migratie van technische gebruikers naar Adobe Developer-console
description: Leer hoe u technische operatoren van campagnes kunt migreren naar een technische account op de Adobe Developer-console
exl-id: 63008b58-4384-4d2b-864a-57f11d701c01
hide: true
hidefromtoc: true
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 0%

---

# Migratie van technische operatoren van campagnes naar Adobe Developer Console {#migrate-tech-users-to-ims}

Vanaf Campagne v8.5 wordt het verificatieproces naar Campagne v8 verbeterd. De technische exploitanten moeten [Adobe Identity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} om verbinding te maken met Campagne. Een technische operator is een Campagnegebruikersprofiel dat expliciet is gemaakt voor API-integratie. In dit artikel worden de stappen beschreven die nodig zijn om een technische operator naar een technische account op de Adobe Developer-console te migreren.

## Wat is er veranderd?{#ims-changes}

Campagne voor gewone gebruikers maakt al verbinding met de Adobe Campaign-console via hun Adobe ID, via Adobe Identity Management System (IMS). Als onderdeel van de inspanning om veiligheid en authentificatieproces te versterken, roept de toepassing van de Cliënt van Adobe Campaign nu Campagne APIs direct gebruikend het technische IMS accountteken.

Meer informatie over het verificatieproces van de nieuwe server naar de server vindt u in [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Deze wijziging is van toepassing vanaf Campagne v8.5 en wordt **verplicht** startcampagne v8.6.


## Heb je invloed op?{#ims-impacts}

Als u campagne-API&#39;s gebruikt, moet u de technische operator(s) migreren naar Adobe Developer Console, zoals hieronder wordt beschreven.

## Hoe migreren?{#ims-migration-procedure}

Elke technische exploitant moet ten minste één technische rekening hebben.

De belangrijkste stappen zijn:

1. Maak eerst de technische rekening die overeenkomt met de technische exploitant. Bijvoorbeeld, veronderstel de pas gecreëerde technische rekening (TA1) voor technische exploitant (TO1).
1. Voer de hieronder beschreven stappen uit op technische rekening TA1
   [Stap 4](#ims-migration-step-4) is optioneel en is alleen vereist als de technische exploitant specifieke mapmachtigingen heeft.
1. Migreer alle de integratieimplementatie van de Campagne API aan de pas gecreëerde technische rekening TA1.
1. Zodra alle klant die met API/Integratie te maken heeft volledig functioneel begint op TA1, vervang de technische exploitant TO1 door technische rekening TA1.

### Vereisten{#ims-migration-prerequisites}

Alvorens het migratieproces te beginnen, moet u uw Manager van de Overgang van de Adobe bereiken zodat de Adobe technische teams uw bestaande groepen van de Exploitant en Genoemde rechten op het Systeem van Identity Management van de Adobe (IMS) kunnen migreren.

### Stap 1 - Uw Campagne-project maken/bijwerken in Adobe Developer Console{#ims-migration-step-1}

Integraties worden gemaakt als onderdeel van een **Project** in Adobe Developer Console. Meer informatie over projecten in [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

U kunt elk project gebruiken dat u eerder hebt gemaakt of u kunt een nieuw project maken. De stappen voor het maken van een project worden beschreven in het dialoogvenster [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Voor deze migratie moet u de volgende API&#39;s toevoegen aan uw project: **API voor I/O-beheer** en **Adobe Campaign**.

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
1. Bladeren naar de **Referentiegegevens** tabblad van uw project en kopieer het **E-mail technische account** waarde.

### Stap 4 - Werk de technische exploitant in de cliëntconsole bij {#ims-migration-step-4}

Deze stap is alleen vereist als specifieke mapmachtigingen of benoemde rechten zijn gedefinieerd voor deze operator (niet via de groep van de operator).

U moet nu de nieuwe technische operator bijwerken in de Adobe Campaign-clientconsole. U moet de bestaande technische omslagtoestemmingen van de exploitant op de nieuwe technische exploitant toepassen.
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

<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign client console explorer, browse to the **Administration > Access Management > Operators**.
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


### Stap 6 - Werk de externe API-integratie bij {#ims-migration-step-6}

U moet de API-integratie bijwerken met systemen van derden.

Raadpleeg voor meer informatie over de integratiestappen van de API, waaronder een voorbeeldcode voor een vloeiende integratie [Adobe Developer Console-verificatiedocumentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


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
