---
product: campaign
title: Laden (SOAP)
description: Laden (SOAP)
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 21c42a36-9a50-49b8-8a07-b041ba8b2026
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 4%

---

# Laden (SOAP){#loading-soap}



>[!CAUTION]
>
>De **Lading (SOAP)** activiteit is slechts beschikbaar als u **FDA (Federated Data Access)** geïnstalleerde module hebt. Controleer hiervoor uw licentieovereenkomst.

De **Lading (SOAP)** activiteit wordt gebruikt naast de **gegevens ladende (RDBMS)** activiteit wanneer het niet mogelijk is om gegevens direct via FDA in een extern gegevensbestand te verzamelen.

De bewerking is als volgt:

1. Selecteer tussen het gebruiken van een voorbeeld van XML of een WSDL.

   Het volgende voorbeeld komt uit een technisch werkschema van de module van het Centrum van het Bericht.

   ![](assets/load_soap_002.png)

1. Selecteer een voorbeeldbestand voor een XML-voorbeeld. Het bestand wordt geanalyseerd om een voorbeeld van een resultaat te maken.

   Voer voor een WSDL de overeenkomende toegangs-URL in en genereren vervolgens de skeletcode. De dienst en de geselecteerde vraag worden automatisch bijgewerkt en getoond.

   ![](assets/soap_load_003.png)

1. Selecteer **[!UICONTROL Click here to view and edit analysis results]** om elke geïdentificeerde kolom op te geven.

   ![](assets/soap_load_001.png)

   Selecteer **[!UICONTROL Re-analyze the example]** als u het voorbeeld wilt bijwerken.

1. U kunt het regelnummer als een identifier gebruiken en/of opgeven dat de SOAP-aanroep meerdere elementen retourneert.
1. Voer de volgende tabscripts in op basis van hun functie:

   * **[!UICONTROL Initialization]** : maakt een SOAP-verbinding.
   * **[!UICONTROL Iteration]**: voert de aanroep naar de SOAP-service uit. De return voor deze functie moet een XML-object zijn dat compatibel is met de beschrijving van het voorbeeld of de WSDL.

     De code van dit tabblad wordt aangeroepen in een lus door Adobe Campaign totdat een null XML-object wordt geretourneerd.

   * **[!UICONTROL Finalization]**: hiermee wordt de verbinding gesloten en/of worden andere bronnen vrijgemaakt die tijdens de verwerking zijn gemaakt.
