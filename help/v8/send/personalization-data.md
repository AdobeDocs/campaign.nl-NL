---
title: Personalization-gegevensbronnen
description: Ontdek welke bronnen kunnen worden gebruikt voor personalisatie
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 711256e2-ab77-404a-b052-6793a85da193
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Personalization-gegevensbronnen{#personalization-data}

Personalization-gegevens kunnen worden opgehaald uit verschillende typen bronnen: Campagne maken van de gegevensbron van de database, externe bestandsgegevensbron of externe databasegegevensbron.

## Bron van Campagnedatabase

In het meest algemene geval, worden de verpersoonlijkingsgegevens opgeslagen in het gegevensbestand. Velden voor &#39;persoonlijke voorkeur van ontvangers&#39; zijn bijvoorbeeld alle velden die zijn gedefinieerd in de tabel met ontvangers, standaardvelden (doorgaans: achternaam, voornaam, adres, plaats, geboortedatum, enz.) of aangepaste velden.

![ de verpersoonlijkingsgebieden van de Campagne in e-mail ](assets/perso-campaign-datasource.png)


## Externe bestandsgegevensbron

U kunt een extern bestand gebruiken dat alle velden bevat die in kolommen zijn gedefinieerd. Dit bestand wordt gebruikt als invoer tijdens een definitie van berichtlevering. U kunt ervoor kiezen deze profielen al dan niet in de database in te voegen.

Om het dossier te selecteren om als gegevensbron te gebruiken, doorblader aan te verbinden in het venster van de berichtverwezenlijking en selecteer **Gedefinieerd in een extern dossier** optie. Zodra het dossier wordt geladen, heb toegang tot de ontvankelijke gegevens in de verpersoonlijkingsopties, van de **Gebieden van de dossier** ingang.

![ gegevens van Personalization van een dossier ](assets/perso-from-file.png)


## FDA-gegevensbron

De gegevens van Personalization kunnen uit een externe lijst door [ Federated Toegang van Gegevens ](../connect/fda.md) worden getrokken.  Als u personalisatie in uw leveringen wilt uitvoeren gebruikend gegevens van het externe gegevensbestand, verzamel de gegevens in een werkschema te gebruiken om het ter beschikking te stellen in een tijdelijke lijst.

Om dit uit te voeren, voeg de activiteit van de a **Vraag** in het richten werkschema toe en gebruik **gegevens toevoegen...** verbinding om het externe gegevensbestand te selecteren. Het gedetailleerde proces is beschikbaar in [ deze sectie ](../../automation/workflow/query.md#adding-data).

Dan gebruik de gegevens van de tijdelijke lijst om uw levering te personaliseren. Zodra de vraagactiviteit wordt gevormd, heb toegang tot de externe gegevens in de verpersoonlijkingsopties, van de **uitbreiding van het Doel** ingang.

![ gegevens van Personalization van een extern gegevensbestand ](assets/perso-external-db.png)

Wanneer het gebruiken van externe gegevens die in FDA worden betreden, wordt het geadviseerd om berichtverpersoonlijking in een specifiek werkschema vooraf te verwerken gebruikend **de verpersoonlijkingsgegevens met een werkschema** optie zoals hieronder gedetailleerd voor te bereiden.

### Aanpassing optimaliseren {#optimize-personalization}

U kunt personalisatie optimaliseren met behulp van een speciale optie: **[!UICONTROL Prepare the personalization data with a workflow]** , beschikbaar op het tabblad **[!UICONTROL Analysis]** van de leveringseigenschappen.

Tijdens de leveringsanalyse, leidt deze optie automatisch tot en voert een werkschema uit dat alle gegevens met betrekking tot het doel in een tijdelijke lijst, met inbegrip van gegevens van lijsten verbonden in FDA opslaat.

Als u deze optie inschakelt, kunnen de prestaties van de leveringsanalyse aanzienlijk worden verbeterd wanneer een groot aantal gegevens wordt verwerkt, vooral als de personalisatiegegevens afkomstig zijn van een externe tabel via FDA. [Meer informatie](../connect/fda.md).

Volg onderstaande stappen om deze optie te gebruiken:

1. Maak een campagne.
1. In het **[!UICONTROL Targeting and workflows]** lusje van uw campagne, voeg de activiteit van de a **Vraag** aan uw werkschema toe.
1. Voeg een **[!UICONTROL Email delivery]** activiteit aan het werkschema toe en open het.
1. Ga naar de tab **[!UICONTROL Analysis]** van de **[!UICONTROL Delivery properties]** en selecteer de optie **[!UICONTROL Prepare the personalization data with a workflow]** .
1. Configureer de levering en start de workflow om de analyse te starten.

Zodra de analyse wordt gedaan, worden de verpersoonlijkingsgegevens opgeslagen in een tijdelijke lijst door een tijdelijke technische werkschema dat op de vlucht tijdens de analyse wordt gecreeerd.

Deze workflow is niet zichtbaar in de Adobe Campaign-interface. Het is alleen bedoeld als een technisch middel om personalisatiegegevens snel op te slaan en af te handelen.

Wanneer de analyse is voltooid, gaat u naar de workflow **[!UICONTROL Properties]** en selecteert u het tabblad **[!UICONTROL Variables]** . Daar kunt u de naam van de tijdelijke lijst zien die u kunt gebruiken om een SQL vraag te maken om identiteitskaarts te tonen die het bevat.

## Personalization-gegevens in een workflow

Wanneer een levering in de context van een werkschema wordt gecreeerd, kunt u de gegevens van de tijdelijke werkschematabel gebruiken. De gegevens die in de tijdelijke werkstroomlijst worden opgeslagen, zijn beschikbaar voor verpersoonlijkingstaken. Gegevens kunnen worden gebruikt in de verpersoonlijkingsvelden.

Deze gegevens worden gegroepeerd in het menu **[!UICONTROL Target extension]** . Voor meer op dit, verwijs naar [ deze sectie ](../../automation/workflow/use-workflow-data.md#target-data).
