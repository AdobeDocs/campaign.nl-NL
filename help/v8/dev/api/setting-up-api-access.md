---
title: API-toegang instellen
description: Leer hoe u toegang tot Campaign Standard API's instelt.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 6%

---

# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt gedetailleerd in de [ documentatie van Adobe Developer ](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Om certificaten in [ Adobe Developer ](https://developer.adobe.com/) te beheren, zorg ervoor u **de beheerderrechten van het Systeem** op de organisatie of a [ ontwikkelaarrekening ](https://helpx.adobe.com/enterprise/using/manage-developers.html) in Admin Console hebt.

1. **Controle u een digitaal certificaat** hebt, of creeer indien nodig. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **creeer een nieuwe integratie aan de Dienst van Adobe Campaign** in [ Adobe Developer ](https://developer.adobe.com/) en vorm het. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **creeer een OAuth Server-aan-Server** credential door deze [ implementatiestappen te volgen ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)

   >[!IMPORTANT]
   >
   >JWT (JSON Web Tokens) wordt momenteel uitgefaseerd en wordt vervangen door OAuth. De overgang wordt geleidelijk uitgevoerd in de komende releases van Campagne. De referenties van de serviceaccount (JWT) zijn gemarkeerd als afgekeurd. Ze blijven werken tot 27 januari 2025. Daarom moet u uw toepassing of integratie migreren om de nieuwe server-aan-server referentie OAuth vóór 27 jan. 2025 te gebruiken. OAuth-verificatie verdient de voorkeur. U zult alle elementen vinden om van authentificatie JWT aan authentificatie OAuth op deze pagina&#39;s te migreren:
   >* [ Migratie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [ Implementatie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [ Veelgestelde Veelgestelde vragen van de Verdringing JWT ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

Om een veilige service-to-service Adobe I/O API-sessie tot stand te brengen, moet elke aanvraag naar een Adobe-service de onderstaande informatie bevatten in de machtigingheader.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZATION>**: Dit is uw persoonlijke ORGANIZATION identiteitskaart, één ORGANIZATION identiteitskaart wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;ORGANIZATION>: uw productieexemplaar
   * &lt;ORGANIZATION-market-stage>: de instantie van het werkgebied.

  Als u de waarde van uw ORGANISATIE-id wilt opvragen, raadpleegt u uw beheerder of uw technische contactpersoon voor Adobe. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie de <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/"> documentatie van Adobe Developer </a>).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw Tken van het Web JSON door een POST verzoek.

* **&lt;API_KEY>**: uw persoonlijke API Sleutel. Het wordt geleverd in Adobe I/O na het creëren van een nieuwe integratie aan de Dienst van Adobe Campaign.

  ![ alt tekst ](assets/tenant.png)

## Problemen oplossen

Als de volgende fout optreedt tijdens de integratie met AdobeIO:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Raadpleeg uw beheerder of uw technische contactpersoon voor Adobe om te controleren of de CNAME-parameter correct is gemaakt.
