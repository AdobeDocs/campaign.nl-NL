---
product: campaign
title: Laden (SOAP)
description: Laden (SOAP)
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 4%

---

# Laden (SOAP){#loading-soap}



>[!CAUTION]
>
>De **Laden (SOAP)** activiteit is alleen beschikbaar als u beschikt over **FDA (Federated Data Access)** geïnstalleerde module. Controleer hiervoor uw licentieovereenkomst.

De **Laden (SOAP)** naast de **gegevens laden (RDBMS)** activiteit wanneer het niet mogelijk is om gegevens rechtstreeks via de FDA in een externe databank te verzamelen.

De bewerking is als volgt:

1. Selecteer tussen het gebruiken van een voorbeeld van XML of een WSDL.

   Het volgende voorbeeld komt uit een technisch werkschema van de module van het Centrum van het Bericht.

   ![](assets/load_soap_002.png)

1. Selecteer een voorbeeldbestand voor een XML-voorbeeld. Het bestand wordt geanalyseerd om een voorbeeld van een resultaat te maken.

   Voer voor een WSDL de overeenkomende toegangs-URL in en genereren vervolgens de skeletcode. De dienst en de geselecteerde vraag worden automatisch bijgewerkt en getoond.

   ![](assets/soap_load_003.png)

1. Selecteren **[!UICONTROL Click here to view and edit analysis results]** om elke geïdentificeerde kolom te specificeren.

   ![](assets/soap_load_001.png)

   Als u het voorbeeld wilt bijwerken, selecteert u **[!UICONTROL Re-analyze the example]**.

   U kunt de notatie van kolomgegevens ook aanpassen via de **.

1. U kunt het lijnaantal als herkenningsteken gebruiken en/of specificeren dat de vraag van de ZEEP verscheidene elementen terugkeert.
1. Voer de volgende tabscripts in op basis van hun functie:

   * **[!UICONTROL Initialization]**: stelt een verbinding van de ZEEP in.
   * **[!UICONTROL Iteration]**: voert de vraag aan de dienst van de ZEEP uit. De return voor deze functie moet een XML-object zijn dat compatibel is met de beschrijving van het voorbeeld of de WSDL.

      De code van dit tabblad wordt aangeroepen in een lus door Adobe Campaign totdat een null XML-object wordt geretourneerd.

   * **[!UICONTROL Finalization]**: sluit verbinding en/of bevrijdt andere middelen die tijdens verwerking worden gecreeerd.
