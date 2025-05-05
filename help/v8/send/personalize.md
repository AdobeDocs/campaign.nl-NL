---
title: Aan de slag met personalisatie
description: Leer hoe u de inhoud van berichten kunt aanpassen
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: 3ac2976839f084761ba56647b282062d8d457ff2
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 5%

---

# Aan de slag met personalisatie {#personalize-content}

Om optimaal te profiteren van elke marketingcampagne, biedt Adobe Campaign u een manier om aangepaste inhoud te leveren die klanten op hun niveau spreekt. Gebaseerd op profielgegevens, verpersoonlijkingsmogelijkheden om een douaneervaring voor verschillende groepen en individuen tot stand te brengen: u kunt uw berichten aan elke specifieke ontvanger aanpassen door de gegevens en de informatie te gebruiken u over hen hebt. Het kan hun voornaam zijn, belangen, waar ze wonen, wat ze hebben gekocht, en nog veel meer.

Adobe Campaign vereenvoudigt verpersoonlijking: u kunt verschillende soorten inhoud tonen die voor elke ontvanger wordt aangepast gebruikend één enkel [ berichtmalplaatje ](create-templates.md). In je transactieberichten, zoals het e-mailbericht voor bevestiging van de aankoop of het verlaten van het winkelwagentje, moet je voor elk individu informatie over productaanbiedingen opnemen in één e-mailtemplate.


## Personalization-strategieën {#personalization-strategy}

Met Campagne kunt u dynamische inhoud maken en persoonlijke berichten verzenden. Personalization-mogelijkheden kunnen worden gecombineerd om uw berichten te verbeteren en een aangepaste gebruikerservaring te creëren.

U kunt de inhoud van het bericht aanpassen door:

* Het opnemen van dynamische **verpersoonlijkingsgebieden**

  De gebieden van de verpersoonlijking worden gebruikt voor verpersoonlijking op het eerste niveau van uw berichten. U kunt om het even welk gebied selecteren beschikbaar in het gegevensbestand van de verpersoonlijkingsredacteur. Voor een levering kunt u elk veld selecteren dat betrekking heeft op de ontvanger, het bericht of de levering. Deze verpersoonlijkingsattributen kunnen in de onderwerpregel of het lichaam van uw berichten worden opgenomen. [Meer informatie](personalization-fields.md).

  Met de volgende syntaxis wordt de plaats van de ontvanger in de inhoud ingevoegd: &lt;%= receiving.location.city %>.

* Het opnemen van vooraf bepaalde **inhoudsblokken**

  De campagne wordt geleverd met een reeks verpersoonlijkingsblokken die een specifieke rendering bevatten die u in uw leveringen kunt invoegen. U kunt bijvoorbeeld een logo, een wensbericht of een koppeling naar de spiegelpagina van het bericht toevoegen. Inhoudsblokken zijn beschikbaar bij een speciale vermelding in de personalisatie-editor. [Meer informatie](personalization-blocks.md).

* Creeer **voorwaardelijke inhoud**

  Vorm voorwaardelijke inhoud om dynamische verpersoonlijking toe te voegen die op het profiel van de ontvanger bijvoorbeeld wordt gebaseerd. Tekstblokken en/of afbeeldingen worden ingevoegd wanneer een bepaalde voorwaarde waar is. [Meer informatie](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Guardrails en aanbevelingen{#perso-guardrails}

### Personalization time-out {#perso-timeout}

Om leveringsbescherming te verbeteren, kunt u een onderbreking voor de verpersoonlijkingsfase plaatsen.

Selecteer op het tabblad **[!UICONTROL Delivery]** van **[!UICONTROL Delivery properties]** een maximumwaarde in seconden voor de optie **[!UICONTROL Maximum personalization run time]** .

Als tijdens de voorvertoning of het verzenden de maximale tijd die u in dit veld instelt, wordt overschreden, wordt het proces afgebroken met een foutbericht en mislukt de levering.

De standaardwaarde is 5 seconden.

Als u deze optie instelt op 0, is er geen tijdslimiet voor de verpersoonlijkingsfase.


### Interne variabelen{#internal-variables}

De volgende variabelen zijn interne variabelen die voor verpersoonlijking kunnen worden gebruikt maar moeten niet worden gewijzigd: **levering**, **bericht**, **dataSource**, **targetData**, **leverancier**, **coupon**, **couponValue**, **5&rbrace;.**


## Video over zelfstudie {#personalization-video}

Begrijp de verschillende soorten dynamische content en leer personalisatieblokken en voorwaardelijke verklaringen maken en toepassen op een levering.


>[!VIDEO](https://video.tv.adobe.com/v/3452874?quality=12&captions=dut)
