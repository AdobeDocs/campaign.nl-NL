---
product: campaign
title: Technote - Asymetrische Encryptie en Decryptie in Adobe Campaign
description: Technische opmerking - Asymetrische versleuteling en ontsleuteling in Adobe Campaign
hide: true
hidefromtoc: true
source-git-commit: 1d9d4111cde1e230220a04c8fd10a126116339ad
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# TechNote: Asymmetrische encryptie en Decryptie in Adobe Campaign {#asymetric-encryption}

Cryptografie met openbare sleutels, of asymmetrische cryptografie, is het gebied van cryptografische systemen die paren van verwante sleutels gebruiken. Elk zeer belangrijk paar bestaat uit a **openbare sleutel** en een overeenkomstige **privé sleutel**.

* De **openbare sleutel** wordt openlijk gedeeld en gebruikt om gegevens te coderen.

* De **privé sleutel** wordt bewaard geheim en gebruikt om gegevens te decrypteren.

Deze benadering zorgt ervoor dat zelfs als iemand de openbare sleutel heeft, zij niet het bericht zonder de privé sleutel kunnen decrypteren. Het verstrekt zeer belangrijke veiligheidseigenschappen zoals vertrouwelijkheid, authentificatie, en integriteit.

Vanaf Adobe Campaign v8.8.3 worden twee nieuwe Javascript-functies toegevoegd voor versleuteling en ontsleuteling:

* Codering met gebruik van openbare sleutel: `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* Decodering met behulp van persoonlijke sleutel: `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


Voorbeeld:

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

**Extra middelen**

* [ krijgen Begonnen met  [!DNL Campaign]  APIs ](https://experienceleague.adobe.com/nl/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [ de documentatie van JSAPI van de Campagne ](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=nl-NL){target="_blank"}
