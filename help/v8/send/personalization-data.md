---
title: Gegevensbronnen aanpassen
description: Ontdek welke bronnen kunnen worden gebruikt voor personalisatie
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---


# Gegevensbronnen aanpassen{#personalization-data}

De gegevens van de Personalisatie kunnen uit diverse soorten bronnen worden teruggewonnen: De gegevensbron van het gegevensbestandgegevensbestand van de campagne, Externe dossiergegevensbron, of Externe gegevensbestandgegevensbron.

## Bron van Campagne-databasegegevens

In het meest algemene geval, worden de verpersoonlijkingsgegevens opgeslagen in het gegevensbestand. &#39;Persoonlijkingsvelden voor ontvangers&#39; zijn bijvoorbeeld alle velden die zijn gedefinieerd in de tabel met ontvangers, standaardvelden (normaal gesproken: achternaam, voornaam, adres, plaats, geboortedatum, enz.) of aangepaste velden.

![De gebieden van de verpersoonlijking van de campagne in een e-mail](assets/perso-campaign-datasource.png)


## Externe bestandsgegevensbron

U kunt een extern bestand gebruiken dat alle velden bevat die in kolommen zijn gedefinieerd. Dit bestand wordt gebruikt als invoer tijdens een definitie van berichtlevering. U kunt ervoor kiezen deze profielen al dan niet in de database in te voegen.

Als u het bestand wilt selecteren dat u als gegevensbron wilt gebruiken, bladert u naar de koppeling Aan in het venster voor het maken van berichten en selecteert u de optie **Gedefinieerd in een extern bestand** optie. Zodra het dossier wordt geladen, heb toegang tot de ontvankelijke gegevens in de verpersoonlijkingsopties, van **Velden uit het bestand** vermelding.

![Persoonlijke gegevens uit een bestand](assets/perso-from-file.png)


## FDA-gegevensbron

Personalisatiegegevens kunnen uit een externe tabel worden gehaald via [Federale gegevenstoegang](../connect/fda.md).  Als u personalisatie in uw leveringen wilt uitvoeren gebruikend gegevens van het externe gegevensbestand, verzamel de gegevens in een werkschema te gebruiken om het ter beschikking te stellen in een tijdelijke lijst.

Voeg een **Query** activiteit in het richten werkschema en gebruik **Gegevens toevoegen...** koppeling om de externe database te selecteren. Het gedetailleerde proces is beschikbaar in [deze sectie](../../automation/workflow/query.md#adding-data).

Dan gebruik de gegevens van de tijdelijke lijst om uw levering te personaliseren. Zodra de vraagactiviteit wordt gevormd, heb toegang tot de externe gegevens in de verpersoonlijkingsopties, van **Doelextensie** vermelding.

![Persoonlijke gegevens uit een externe database](assets/perso-external-db.png)

Als u externe gegevens gebruikt die in FDA worden benaderd, wordt aanbevolen om berichtpersonalisatie vooraf te verwerken in een specifieke workflow met behulp van de **De aanpassingsgegevens voorbereiden met een workflow** zoals hieronder beschreven.

### Aanpassing optimaliseren {#optimize-personalization}

U kunt personalisatie optimaliseren met behulp van een speciale optie: **[!UICONTROL Prepare the personalization data with a workflow]**, beschikbaar in de **[!UICONTROL Analysis]** tabblad van de leveringseigenschappen.

Tijdens de leveringsanalyse, leidt deze optie automatisch tot en voert een werkschema uit dat alle gegevens met betrekking tot het doel in een tijdelijke lijst, met inbegrip van gegevens van lijsten verbonden in FDA opslaat.

Als u deze optie inschakelt, kunnen de prestaties van de leveringsanalyse aanzienlijk worden verbeterd wanneer een groot aantal gegevens wordt verwerkt, vooral als de personalisatiegegevens afkomstig zijn van een externe tabel via FDA. [Meer informatie](../connect/fda.md).

Volg onderstaande stappen om deze optie te gebruiken:

1. Een campagne maken.
1. In de **[!UICONTROL Targeting and workflows]** tabblad van uw campagne, voegt u een **Query** activiteit aan uw werkschema.
1. Een **[!UICONTROL Email delivery]** aan de werkstroom en open het.
1. Ga naar de **[!UICONTROL Analysis]** tabblad van het dialoogvenster **[!UICONTROL Delivery properties]** en selecteert u de **[!UICONTROL Prepare the personalization data with a workflow]** optie.
1. Configureer de levering en start de workflow om de analyse te starten.

Zodra de analyse wordt gedaan, worden de verpersoonlijkingsgegevens opgeslagen in een tijdelijke lijst door een tijdelijke technische werkschema dat op de vlucht tijdens de analyse wordt gecreeerd.

Deze workflow is niet zichtbaar in de Adobe Campaign-interface. Het is alleen bedoeld als een technisch middel om personalisatiegegevens snel op te slaan en af te handelen.

Als de analyse is voltooid, gaat u naar de workflow **[!UICONTROL Properties]** en selecteert u de **[!UICONTROL Variables]** tab. Daar kunt u de naam van de tijdelijke lijst zien die u kunt gebruiken om een SQL vraag te maken om identiteitskaarts te tonen die het bevat.

## Gegevens aanpassen aan een workflow

Wanneer een levering in de context van een werkschema wordt gecreeerd, kunt u de gegevens van de tijdelijke werkschematabel gebruiken. De gegevens die in de tijdelijke werkstroomlijst worden opgeslagen, zijn beschikbaar voor verpersoonlijkingstaken. Gegevens kunnen worden gebruikt in de verpersoonlijkingsvelden.

Deze gegevens worden gegroepeerd in het dialoogvenster **[!UICONTROL Target extension]** -menu. Raadpleeg [deze sectie](../../automation/workflow/use-workflow-data.md#target-data) voor meer informatie.




