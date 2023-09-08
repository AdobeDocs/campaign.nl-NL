---
title: bestemmingspagina's en profielkenmerken voor campagne
description: Leer hoe u Adobe Campaign-bestemmingspagina's en Adobe Experience Platform-profielkenmerken synchroniseert
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 79faf36db774239477089c13c98cbf48a66752a3
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 0%

---

# Adobe Experience Platform-profielen bijwerken vanaf Adobe Campaign-bestemmingspagina&#39;s

Dankzij de integratie tussen Adobe Campaign en Adobe Experience Platform kunt u gegevens naadloos synchroniseren tussen uw Adobe Campaign-landingspagina&#39;s en Adobe Experience Platform. Met deze integratie kunt u:

* Haal Adobe Experience Platform-profielkenmerken op om bijgewerkte informatie weer te geven op Adobe Campaign-bestemmingspagina&#39;s,
* Stuur bijgewerkte profielkenmerken terug naar Adobe Experience Platform om de bijbehorende kenmerken bij te werken op basis van wat is ingevuld en verzonden op de bestemmingspagina&#39;s.

De belangrijkste stappen om deze integratie tot stand te brengen zijn:

<table>
<tr>
<td><img src="../assets/do-not-localize/icon-connection.svg" width="60px"><p><a href="#oauth">Een OAuth-verbinding instellen</a></p></td>
<td><img src="../assets/do-not-localize/icon-source.svg" width="60px"><p><a href="#source">Een HTTP API-bronverbinding maken</a></p></td>
<td><img src="../assets/do-not-localize/icon-options.svg" width="60px"><p><a href="#xtk">Verificatieopties toevoegen in campagne</a></p></td>
<td><img src="../assets/do-not-localize/icon-javascript.svg" width="60px"><p><a href="#javascript">JavaScript-codes toevoegen in campagne</a></p></td>
<td><img src="../assets/do-not-localize/icon-workflow.svg" width="60px"><p><a href="#script">De workflow voor de openingspagina configureren</a></p></td>
</table>

## Een Oauth-verbinding instellen {#oauth}

Adobe Cloud Platform API&#39;s gebruiken het OAuth 2.0-protocol voor verificatie en autorisatie. Als u Adobe Experience Platform met behulp van API-aanroepen wilt verbinden met Adobe Campaign, moet u een toegangstoken genereren met de OAuth Integration die in Adobe Developer Console is gemaakt.

Ga als volgt te werk om dit te doen:

1. Open de Adobe Developer-console.
1. Maak een nieuwe API-verbinding met het Adobe Experience Platform API-product. De gedetailleerde stappen op hoe te om een OAuth 2.0 toegangstoken te verkrijgen zijn beschikbaar in [Adobe Developer Console-documentatie](https://developer.adobe.com/developer-console/docs/guides/authentication/Tools/OAuthPlayground/).
1. Wanneer de verbinding is gemaakt, navigeert u naar de **[!UICONTROL OAuth Server-to-Server]** en kopieert u de onderstaande gegevens, die in Campagne zijn vereist voor verificatie:

   * CLIENT-ID
   * CLIENT SECRET
   * ORGANISATIE-ID

   ![](assets/ac-lp-oauth.png){width="70%"}

Nu uw Oauth verbinding wordt gevormd, creeer en vorm een nieuw **[!UICONTROL HTTP API]** Bronverbinding om Adobe Campaign met Adobe Experience Platform te koppelen.

## Een HTTP API-bronverbinding maken {#source}

Als de OAuth-verbinding is geïnstalleerd, bestaat de volgende stap uit het maken van een **[!UICONTROL HTTP API]** Bronverbinding in Adobe Experience Platform. Met deze verbinding kunt u gegevens streamen naar Adobe Experience Platform via API&#39;s. Voer de volgende stappen uit:

1. Navigeren naar Adobe Experience Platform **[!UICONTROL Sources]**, zoekt u naar **[!UICONTROL HTTP API]** bron en klik vervolgens op **[!UICONTROL Add data]**.

   ![](assets/ac-lp-source.png){width="70%"}

1. Configureer de verbinding afhankelijk van uw behoeften. Gedetailleerde informatie over het configureren van een HTTP API-verbinding is beschikbaar in [Adobe Experience Platform-brondocumentatie](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/streaming/http.html).

   Bij de **[!UICONTROL Authentication]** stap, inschakelen **[!UICONTROL Enable authentication]** optie om voor authentiek te verklaren gebruikend het toegangstoken eerder door de integratie OAuth wordt geproduceerd.

   ![](assets/ac-lp-source-authentication.png){width="70%"}

1. Zodra de bronverbinding wordt gevormd, toont het stromen eindpunt. Dit eindpunt wordt vereist om gegevens in Adobe Experience Platform in te voeren.

   ![](assets/ac-lp-endpoint.png){width="70%"}

   U kunt ook een voorbeeld openen van de gegevensindeling die u in Adobe Experience Platform hebt ingevoerd door de nieuwe gegevensstroom te openen vanuit het dialoogvenster **[!UICONTROL Dataflows]** tab.

   ![](assets/ac-lp-schema.png){width="70%"}

Nu de HTTP API-bronverbinding is ingesteld, moet u specifieke opties toevoegen aan Adobe Campaign om de verbinding met Adobe Experience Platform in te schakelen.

## Verificatieopties toevoegen in Adobe Campaign {#xtk}

Nadat de HTTP API-bronverbinding is geconfigureerd, moet u specifieke opties toevoegen aan Adobe Campaign om de verbinding met Adobe Experience Platform mogelijk te maken. Dit kan of in het menu van het Beleid van de Campagne worden gedaan, of wanneer het uitvoeren van uw het landen paginawerkschema door een specifieke toe te voegen **[!UICONTROL JavaScript code]** activiteit.

Blader op de onderstaande tabbladen naar de twee methoden:

>[!BEGINTABS]

>[!TAB Opties toevoegen via het menu Beheer]

1. Ga naar de **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**  -menu.
1. Voeg de volgende opties toe met de bijbehorende waarden uit Adobe Developer Console:

   * IMS_CLIENT_ID = cryptString(CLIENT ID)
   * IMS_CLIENT_SECRET = cryptString(CLIENT SECRET)
   * IMS_ORG_ID = ORGANIZATION ID
   * IMS_CLIENT_API_KEY = cryptString(CLIENT ID)

   ![](assets/ac-lp-xtk.png){width="70%"}

   >[!NOTE]
   >
   >De functie cryptString() wordt gebruikt om uw verificatiegegevens te coderen.

>[!TAB Opties toevoegen met een JavaScript-codeactiviteit]

Als u deze opties automatisch wilt configureren tijdens de uitvoering van de workflow voor de bestemmingspagina&#39;s, voegt u een **[!UICONTROL JavaScript code]** activiteit aan uw werkschema met de hieronder code. [Leer hoe u een JavaScript-codeactiviteit configureert](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-JavaScript-code.html#JavaScript-code).

Bij de uitvoering van de workflow worden de opties automatisch gemaakt in de Campagneconsole met de opgegeven waarden.

    &quot;
    loadLibrary(&quot;xtk:shared/nl.js&quot;);
    loadLibrary(&quot;xtk:shared/xtk.js&quot;);
    loadLibrary(&quot;xtk:shared/json2.js&quot;);
    loadLibrary(&quot;xtk:common.js&quot;);
    
    function setAuthCredentials()
    {
    setOption(&quot;IMS_CLIENT_ID&quot;, cryptString(&#39;CLIENT ID&#39;);
    setOption(&quot;IMS_CLIENT_SECRET&quot;, cryptString(&#39;CLIENT SECRET&#39;);
    setOption(&quot;IMS_ORG_ID&quot;, cryptString(&#39;ORGANIZATION ID&#39;);
    setOption(&quot;IMS_CLIENT_API_KEY&quot;, cryptString(&#39;CLIENT ID&#39;);
    }
    &quot;

>[!ENDTABS]

Nu verificatieopties zijn geconfigureerd in Campagne, moet u aangepaste JavaScript-codes maken om gegevenssynchronisatie tussen Campagne en Adobe Experience Platform vanaf de landingspagina mogelijk te maken.

## Opties toevoegen bij uitvoering van werkstroom {#javacript}

Als u gegevenssynchronisatie tussen bestemmingspagina&#39;s en Adobe Experience Platform wilt toestaan, moeten aangepaste JavaScript-codes aan Adobe Campaign worden toegevoegd. Voer de volgende stappen uit:

1. Ga naar de **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL JavaScript codes]** -menu.
1. Maak nieuwe JavaScript-codes en kopieer de onderstaande fragmenten.

   >[!NOTE]
   >
   >Toegangstoken- en verificatiegegevens worden automatisch opgehaald uit de eerder ingestelde opties.

   ![](assets/ac-lp-script.png){width="70%"}

+++  Script 1 - Profielkenmerken laden vanuit Experience Platform

   Deze code controleert of het profiel in Adobe Experience Platform bestaat voordat de bestemmingspagina wordt geladen. De profielkenmerken worden opgehaald en weergegeven in de corresponderende velden van de landingspagina.

   ```
   // API implementation to read profile from AEP
   function getProfileInfo(email)
   {
   var accessToken = getAccessToken();
   var request = new HttpClientRequest(('https://platform-stage.adobe.io/data/core/ups/access/entities?schema.name=_xdm.context.profile&entityId=' + email + '&entityIdNS=email&fields=identities,consents.marketing'));
   request.method = 'GET';
   request.header["Content-Type"] = "application/json";
   request.header["sandbox-name"] = "prod";
   request.header["x-gw-ims-org-id"] = getOption('IMS_ORG_ID');
   request.header["x-api-key"] = getOption('IMS_CLIENT_API_KEY');
   request.header["Authorization"] = "Bearer " + accessToken;
   request.execute();
   return request.response;
   }
   ```

+++

+++ Script 2 - Experience Platform-profielkenmerken bijwerken

   Deze code werkt profielkenmerken in Adobe Experience Platform bij met de waarden die op de landingspagina worden verzonden.

   ```
   // API implementation to update profile in AEP
   loadLibrary("xtk:shared/nl.js");
   loadLibrary("xtk:shared/xtk.js");
   loadLibrary("xtk:shared/json2.js");
   loadLibrary("xtk:common.js");
   
   function updateProfileInAEP(profileUpdatePayload)
   {
   var accessToken = getAccessToken();
   var request = new HttpClientRequest('https://dcs-stg.adobedc.net/collection/64a300b84d61c0bcea4f0cd4ecaaa224a19477026d14f7e08b5408ffaf5e6162?syncValidation=false');
   request.method = 'POST';
   request.header["Content-Type"] = "application/json";
   request.header["sandbox-name"] = "prod";
   request.header["Authorization"] = "Bearer " + accessToken;
   var body = '{"header":{"schemaRef":{"id":"https://ns.adobe.com/campdev/schemas/35d8e567772e1a1093ed6cf9e41d2c1fec22eeb3a89583e1","contentType":"application/vnd.adobe.xed-full+json;version=1.0"},"imsOrgId":"A1F66F0D5C47D1950A494133@AdobeOrg","datasetId":"63c7fa2a20cce11b98cccb41","source":{"name":"testHTTPSourcesVinay - 03/06/2023 5:43 PM"}},"body":{"xdmMeta":{"schemaRef":{"id":"https://ns.adobe.com/campdev/schemas/35d8e567772e1a1093ed6cf9e41d2c1fec22eeb3a89583e1","contentType":"application/vnd.adobe.xed-full+json;version=1.0"}},"xdmEntity":' + profileUpdatePayload +'}}';
   request.body = body;
   request.execute();
   return request.response;
   }
   
   
   // Get Access token from OAuth-Server-to-server API call
   function getAccessToken() {
   var clientId = decryptString(getOption('IMS_CLIENT_ID'));
   var clientSecret = decryptString(getOption('IMS_CLIENT_SECRET'));
   var request = new HttpClientRequest(('https://ims-na1-stg1.adobelogin.com/ims/token/v2?grant_type=client_credentials' + '&client_id=' + clientId + '&client_secret=' + clientSecret + '&scope=openid,session,AdobeID,read_organizations,additional_info.projectedProductContext'));
   request.method = 'POST';
   request.execute();
   var response = request.response;
   if(response.code != 200){
   logError('GetAccessToken failed,', response.code, response.body);
   return;
   }
   var body = ''+response.body;
   var parsedResponse = JSON.parse(body);
   var accessToken = parsedResponse.access_token;
   logInfo("Access token generated successfully");
   return accessToken;
   }
   ```

+++

Nu de aangepaste JavaScript-codes in Adobe Campaign zijn gemaakt, kunt u de workflow met de bestemmingspagina zo configureren dat deze JavaScript-codes voor gegevenssynchronisatie worden gebruikt.

## De workflow voor de openingspagina configureren {#script}

Als de JavaScript-codes aan Adobe Campaign zijn toegevoegd, kunt u ze gebruiken voor de workflow van de bestemmingspagina **[!UICONTROL JavaScript code]** activiteiten:

* Als u gegevens uit het Experience Platform wilt laden voordat u de bestemmingspagina laadt, voegt u een **[!UICONTROL JavaScript code]** activiteit vóór de openende paginageactiviteit en kopieer deeg Manuscript 1.

+++ Script 1 - Profielkenmerken laden vanuit Experience Platform

  ```
  // Script code to read profile from AEP.
  
  logInfo("Loading profile from AEP");
  loadLibrary("cus:aepAPI");
  var recipient=ctx.recipient;
  var email = recipient.@email;
  var response = getProfileInfo(email);
  ctx.isAEPProfileExists = 1;
  
  if(response.code == 404){
  ctx.isAEPProfileExists = 0
  logInfo("Profile with email" + email + " not found in AEP, ignoring the update activity");
  }
  else if(response.code == 200){
  var body = ''+response.body;
  var parsedResponse = JSON.parse(body);
  for (var key in parsedResponse) {
      var value =  parsedResponse[key];
      var marketing = value.entity.consents.marketing;
      logInfo("User Consent Details : " + JSON.stringify(marketing));   
      if(marketing.hasOwnProperty('email')&&marketing.email.hasOwnProperty('val')&&marketing.email.val=='n'){
      ctx.recipient.@blackListEmail = 1;
      }
      if(marketing.hasOwnProperty('sms')&&marketing.sms.hasOwnProperty('val')&&marketing.sms.val=='n'){
      ctx.recipient.@blackListMobile = 1;
      }
      if(marketing.hasOwnProperty('push')&&marketing.push.hasOwnProperty('val')&&marketing.push.val=='n'){
      ctx.recipient.@blackListPostalMail = 1;
      }
  } 
  }
  ```

+++

* Als u de profielkenmerken van het Experience Platform wilt bijwerken met de gegevens die op de landingspagina zijn verzonden, voegt u een **[!UICONTROL JavaScript code]** activiteit na de activiteit van de landingspagina en kopieer plakken Script 2.

+++ Script 2 - Experience Platform-profielkenmerken bijwerken

  ```
  // Script code to update profile in AEP and ACC.
  
  logInfo("Executing script to update AEP profile.");
  
  // Loading aepAPI library JS code
  loadLibrary("cus:aepAPI");
  
  var recipient=ctx.recipient
  
  // Update profile only if it exists in AEP
  if(ctx.isAEPProfileExists==1){
  
  var email = recipient.@email
  logInfo(email);
  logInfo(recipient.@blackListEmail);
  logInfo(recipient.@blackListMobile);
  logInfo(recipient.@blackListPostalMail);
  
  var optOutPayload = new Array();
  
  if(recipient.@blackListEmail==1){
      optOutPayload.push('"email":{"val":"n"}');
  }
  else
      optOutPayload.push('"email":{"val":"y"}');
  
  if(recipient.@blackListMobile==1){
      optOutPayload.push('"sms":{"val":"n"}');
  }
  else
      optOutPayload.push('"sms":{"val":"y"}');
  
  if(recipient.@blackListPostalMail==1){
      optOutPayload.push('"push":{"val":"n"}');
  }
  else
      optOutPayload.push('"push":{"val":"y"}');
  
  var profileUpdatePayload = '{'+ '"personalEmail":{"address":' + '\"' + email + '\"' + '},' +'"consents":{"marketing":{' + optOutPayload.toString() + '}}}';
  
  var response = updateProfileInAEP(profileUpdatePayload);
  if(response.code == 200){
  var body = '' + response.body;
  logInfo("AEP Profile Updated successfully, Response " + body);
  // Update ACC profile 
  recipient.@xtkschema = "nms:recipient";
  recipient.@_operation = "update";
  recipient.@_key="@id";
  xtk.session.Write(recipient);
  logInfo("ACC Profile Updated successfully");
  }
  else{
      logError('Server Error: ', response.code, response.body);
  } 
  }
  else {
  logInfo("Ignoring AEP profile update as profile doesn't exists.");
  
  // Update ACC profile   
  recipient.@xtkschema = "nms:recipient";
  recipient.@_operation = "update";
  recipient.@_key="@id";  
  xtk.session.Write(recipient);
  logInfo("ACC Profile Updated successfully");
  }
  ```

+++

>[!CAUTION]
>
>Zorg ervoor dat u de lading in elk manuscript aanpast dat op uw specifieke behoeften wordt gebaseerd.
>
>Als u geen script toevoegt vóór de activiteit van de bestemmingspagina, wordt er geen controle op het bestaan van het profiel uitgevoerd in Adobe Experience Platform. Wanneer de landingspagina wordt verzonden en het profiel niet bestaat, wordt het in Adobe Experience Platform gemaakt met de kenmerken van de bestemmingspagina.

Hier volgt een voorbeeldworkflow met de JavaScript-codeactiviteiten voor en na een landingspagina:

![](assets/ac-lp-wkf.png){width="70%"}

Hier volgt een voorbeeld van een openingspagina en een JavaScript-codeactiviteit die zijn geconfigureerd om profielkenmerken bij te werken in Adobe Experience Platform:

![](assets/ac-lp-example.png){width="70%"}

![](assets/ac-lp-code.png){width="70%" zoomable="yes"}

### Meer informatie

* [Een JavaScript-codeactiviteit configureren](../../automation/workflow/sql-code-and-javascript-code.md#javascript-code)
* [Een introductiepagina maken](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/creating-a-landing-page.html)
* [Abonnementen en abonnementen beheren](../start/subscriptions.md)
