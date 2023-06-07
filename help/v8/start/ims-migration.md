---
title: Migratie van technische gebruikers naar Technical Account op Developer Console
description: Migratie van technische gebruikers naar Technical Account op Developer Console
hide: true
hidefromtoc: true
source-git-commit: 8842404511bd6166d920ebdeee942007b33a1bab
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 0%

---

# Migratie van technische operatoren van campagnes naar Adobe Developer Console {#migrate-tech-users-to-ims}

Vanaf Campagne v8.5 wordt het verificatieproces naar Campagne v8 verbeterd. De technische exploitanten moeten [Adobe Identity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} om verbinding te maken met Campagne. Een technische operator is een Campagnegebruikersprofiel dat expliciet is gemaakt voor API-integratie. In dit artikel worden de stappen beschreven die nodig zijn om een technische operator naar een technische account op de Adobe Developer-console te migreren.

## Wat is er veranderd?{#ims-changes}

Campagne voor gewone gebruikers maakt al verbinding met de Adobe Campaign-console via hun Adobe ID, via Adobe Identity Management System (IMS). Als onderdeel van de inspanning om veiligheid en authentificatieproces te versterken, roept de toepassing van de Cliënt van Adobe Campaign nu Campagne APIs direct gebruikend het technische IMS accountteken.

Meer informatie over het verificatieproces van de nieuwe server naar de server [in Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

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

Nadat uw project in de Adobe Developer-console is gemaakt, voegt u een API toe die Server gebruikt voor serververificatie. Leer hoe u de referentie OAuth Server-to-Server instelt in [in Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Wanneer de API met succes is verbonden, kunt u tot de onlangs geproduceerde geloofsbrieven met inbegrip van identiteitskaart van de Cliënt en Geheim van de Cliënt toegang hebben, evenals een toegangstoken produceren.

### Stap 3 - voeg het productprofiel aan het project toe{#ims-migration-step-3}

U kunt nu uw productprofiel voor Campagne toevoegen aan het project, zoals hieronder beschreven:

1. Open de Adobe Campaign API.
1. Klik op de knop **Productprofielen bewerken** knop

   ![](assets/do-not-localize/ims-edit-api.png)

1. Wijs alle relevante productprofielen toe aan de API, bijvoorbeeld &#39;messageCenter&#39;, en sla uw wijzigingen op.
1. Bladeren naar de **Referentiegegevens** en kopieer het **E-mail technische account** waarde.

### Stap 4 - Werk de technische exploitant in de console van de Cliënt bij {#ims-migration-step-4}

De laatste stap bestaat uit het bijwerken van de technische operator in de Adobe Campaign Client Console.

>[!CAUTION]
>
>Nadat het verificatietype voor de technische operator is bijgewerkt, werken alle API-integraties met deze technische operator niet meer. U moet [de API-integratie bijwerken](#ims-migration-step-6).

Ga als volgt te werk om de technische authenticatiemodus van de operator bij te werken naar IMS:

1. Blader vanuit de Campagne Client Console-verkenner naar de **Beheer > Toegangsbeheer > Operatoren**.
1. Bewerk de bestaande technische operator die voor API&#39;s wordt gebruikt.
1. Vervang de **Naam (aanmelding)** van deze technische exploitant door de e-mail van de technische rekening die eerder is opgehaald.
1. Bladeren naar de **Bewerken** knop linksboven naast **Bestand** en selecteert u **De XML-bron bewerken**.
1. De verificatiemodus bijwerken naar `ims`, als volgt:

   ```javascript
   <operator 
   ...
       <access authenticationType="ims" ...
       ...
       </access>
   ...
   </operator>
   ```

1. Sla uw wijzigingen op.

U kunt de technische exploitant programmatically ook bijwerken, gebruikend SQL manuscripten of Campagne APIs. Met deze modi kunt u de stappen automatiseren waarmee de naam van de operator wordt bijgewerkt met het bijbehorende e-mailadres en/of verificatietype van de technische account.

* Gebruik het volgende **SQL-script** om de naam van de operator te vervangen door de bijbehorende e-mail:

   ```sql
   UPDATE xtkoperator
   SET sauthenticationtype = 'ims',
           sname = '{email}'
   WHERE sname = '{name}' AND itype = 0;
   ```

* Gebruik het volgende `queryDef.ExecuteQuery` **Campagne-API** om de id van een exploitant voor een bepaalde technische exploitant op te halen:

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

* Gebruik het volgende `session.Write` **Campagne-API** om de naam bij te werken met opgegeven e-mailadres voor een technische account:

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

### Stap 5 - bevestig uw configuratie {#ims-migration-step-5}

Voer de stappen in het dialoogvenster [Handleiding voor Adobe Developer Console-referenties](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} voor het produceren van een toegangstoken en kopieer het verstrekte bevel van de Steekproef cURL.


### Stap 6 - Werk de integratie van de derdeAPI bij {#ims-migration-step-6}

U moet de API-integratie bijwerken met systemen van derden.

Raadpleeg voor meer informatie over de integratiestappen van de API, waaronder een voorbeeldcode voor een vloeiende integratie [Adobe Developer Console-verificatiedocumentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


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
