---
title: Aan de slag met REST-API's voor campagnes
description: Maak integraties en bouw uw eigen ecosysteem door een interface tussen Campaign en een reeks technologieën tot stand te brengen.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: 115b7b6824f3736e03f9fb87898f1264f9bab636
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 40%

---

# Aan de slag met REST-API&#39;s voor campagnes {#get-started-apis}

De REST APIs van de campagne wordt gericht op het laten van u **integraties** voor Adobe Campaign creëren en **uw eigen ecosysteem** bouwen door Adobe Campaign met het paneel van technologieën te verbinden die u gebruikt.

>[!AVAILABILITY]
>
>* Dit vermogen is slechts beschikbaar op bestelling, voor alle [&#x200B; milieu&#39;s FDA van de Campagne &#x200B;](../../architecture/fda-deployment.md). Het is **niet** beschikbaar voor [&#x200B; de plaatsingen van de Onderneming (FFDA) &#x200B;](../../architecture/enterprise-deployment.md). Neem contact op met uw Adobe-vertegenwoordiger voor toegang.
>
>* Controleer voordat u API-aanroepen uitvoert, de schaalbeperkingen bij uw licentieovereenkomst. Voor meer op dit, verwijs naar de [&#x200B; Adobe Campaign v8 Beschrijving van het Product &#x200B;](https://helpx.adobe.com/nl/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.


Met de Adobe Campaign REST API&#39;s hebt u toegang tot de volgende functies:

<table><tr>
 <td valign="top"><a href="retrieving-profiles.md"><img width="60px" alt="voorwaarden" src="assets/icon_profile.svg"/></a><p><a href="retrieving-profiles.md">Profielen</a></p></td>
<td valign="top"><a href="creating-a-service.md"><img width="60px" alt="voorwaarden" src="assets/icon_services.svg"/></a><p><a href="creating-a-service.md">Services en abonnementen</a></p></td>
<td valign="top"><a href="interacting-with-custom-resources.md"><img width="60px" alt="voorwaarden" src="assets/icon_customresources.svg"/></a><p><a href="interacting-with-custom-resources.md">Aangepaste bronnen</a></p></td>
<td valign="top"><a href="controlling-a-workflow.md"><img width="60px" alt="voorwaarden" src="assets/icon_workflows.svg"/></a><p><a href="controlling-a-workflow.md">Workflows</a></p></td>
<td valign="top"><a href="managing-transactional-messages.md"><img width="60px" alt="voorwaarden" src="assets/icon_transactionalmessage.svg"/></a><p><a href="managing-transactional-messages.md">Transactionele berichten</a></p></td>
</tr></table>

U hebt een Adobe I/O-account nodig om de API&#39;s voor het maken van de campagne REST te gebruiken. Dit is een verplichte eerste stap om verder te kunnen en de API-functies te ontdekken.
Raadpleeg [deze sectie](setting-up-api-access.md) voor meer informatie.

De API’s die we bieden, gebruiken **standaardconcepten** met een REST-interface en JSON-payloads.

Alle eindpunten worden uitgebreid beschreven in deze documentatie met de algemene begrippen die u moet kennen voor het manipuleren van de API, de volledige API-referentie, codevoorbeelden en snelstarthandleidingen. Alle voorbeelden werken met Postman, maar u kunt gerust uw favoriete REST-client gebruiken.

