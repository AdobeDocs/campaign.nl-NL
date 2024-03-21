---
title: Campagne-schema's uitbreiden
description: Meer informatie over het uitbreiden van Campagne-schema's
feature: Schema Extension, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Een schema uitbreiden{#extend-schemas}

Als technische gebruiker, kunt u datamodel van de Campagne aanpassen om aan de behoeften van uw implementatie te voldoen: voeg elementen aan een bestaand schema toe, wijzig een element in een schema of schrap elementen.

De belangrijkste stappen om het datamodel van de Campagne aan te passen zijn:

1. Een extensieschema maken
1. Campagne-database bijwerken
1. Het invoerformulier aanpassen

>[!CAUTION]
>Ingebouwd schema mag niet rechtstreeks worden gewijzigd. Als u een ingebouwd schema moet aanpassen, moet u het uitbreiden.

Voor een beter inzicht in ingebouwde lijsten van de Campagne en hun interactie, verwijs naar [deze pagina](datamodel.md). Zie ook aanbevelingen wanneer het creëren van een nieuw schema in [deze pagina](create-schema.md).

Voer de volgende stappen uit om een schema uit te breiden:

1. Ga naar de **[!UICONTROL Administration > Configuration > Data schemas]** in de Explorer.
1. Klik op de knop **Nieuw** en selecteert u **[!UICONTROL Extend the data in a table using an extension schema]**.

   ![](assets/extend-schema-option.png)

1. Identificeer het ingebouwde schema om het uit te breiden en te selecteren.

   ![](assets/extend-schema-select.png)

   Door overeenkomst, noem het uitbreidingsschema het zelfde als het ingebouwde schema, en gebruik een douanenamespace.  Sommige naamruimten zijn alleen intern. [Meer informatie](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. Voeg in de schema-editor de benodigde elementen toe via het contextmenu en sla deze op.

   ![](assets/extend-schema-edit.png)

   In het onderstaande voorbeeld voegen we de **LidmaatschapJaar** -kenmerk, een lengtelimiet voor achternaam instellen (deze limiet overschrijft de standaardwaarde) en de geboortedatum uit het ingebouwde schema verwijderen.

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. Maak en maak opnieuw verbinding met Campagne om de update van de schemastructuur te controleren in het dialoogvenster **[!UICONTROL Structure]** tab.

   ![](assets/extend-schema-structure.png)

1. Werk de databasestructuur bij om de wijzigingen toe te passen. [Meer informatie](update-database-structure.md)

1. Nadat de wijzigingen in de database zijn geïmplementeerd, kunt u het invoerformulier voor de ontvanger aanpassen om de wijzigingen zichtbaar te maken. [Meer informatie](forms.md)
