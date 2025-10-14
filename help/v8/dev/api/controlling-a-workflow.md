---
title: Een workflow beheren
description: Leer hoe u een workflow kunt besturen met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 10%

---

# Een workflow beheren {#controlling-a-workflow}

U kunt een workflow rechtstreeks vanuit de REST API beheren via een POST-aanvraag met de workflow-id en de vereiste uitvoeringsopdracht:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Als de workflow-id in Adobe Campaign wordt gewijzigd, werkt de API-aanvraag niet meer.

Er zijn vier uitvoeringsopdrachten beschikbaar om een workflow te besturen:

* Starten
* Pauzeren
* Hervatten
* Stoppen

Voor meer informatie over de uitvoeringsbevelen, verwijs naar de [&#x200B; documentatie van de Campagne &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html?lang=nl-NL).

<br/>

***verzoeken van de Steekproef***

* Start een workflow.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"start"}'
  ```

  <!-- + réponse -->

* Stop een workflow.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"stop"}'
  ```

  <!-- + réponse -->
