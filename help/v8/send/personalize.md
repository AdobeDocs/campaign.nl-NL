---
title: Aan de slag met personalisatie
description: Leer hoe u de inhoud van berichten kunt aanpassen
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 5%

---

# Aan de slag met personalisatie {#personalize-content}

Om optimaal te profiteren van elke marketingcampagne, biedt Adobe Campaign u een manier om aangepaste inhoud te leveren die klanten op hun niveau spreekt. Gebaseerd op profielgegevens, verpersoonlijkingsmogelijkheden om een douaneervaring voor verschillende groepen en individuen tot stand te brengen: u kunt uw berichten aan elke specifieke ontvanger aanpassen door de gegevens en de informatie leveraging u over hen hebt. Het kan hun voornaam zijn, belangen, waar ze wonen, wat ze hebben gekocht, en nog veel meer.

Adobe Campaign vereenvoudigt personalisatie: u kunt verschillende soorten inhoud tonen die voor elke ontvanger wordt aangepast gebruikend één enkele [e-mailsjabloon](create-templates.md). In je transactieberichten, zoals het e-mailbericht voor bevestiging van de aankoop of het verlaten van het winkelwagentje, moet je voor elk individu informatie over productaanbiedingen opnemen in één e-mailtemplate.


## Personalisatiestrategieën {#personalization-strategy}

Met Campagne kunt u dynamische inhoud maken en persoonlijke berichten verzenden. U kunt aanpassingsmogelijkheden combineren om uw berichten te verbeteren en een aangepaste gebruikerservaring te creëren.

U kunt de inhoud van het bericht aanpassen door:

* Dynamisch invoegen **personalisatievelden**

   De gebieden van de verpersoonlijking worden gebruikt voor verpersoonlijking op het eerste niveau van uw berichten. U kunt om het even welk gebied selecteren beschikbaar in het gegevensbestand van de verpersoonlijkingsredacteur. Voor een levering, kunt u om het even welk gebied selecteren met betrekking tot de ontvanger, het bericht of de levering. Deze verpersoonlijkingsattributen kunnen in de onderwerpregel of het lichaam van uw berichten worden opgenomen. [Meer informatie](personalization-fields.md).

   De volgende syntaxis voegt de plaats van de ontvanger in uw inhoud in: &lt;%= receiving.location.city %>.

* Vooraf gedefinieerde invoegen **inhoudsblokken**

   De campagne wordt geleverd met een reeks verpersoonlijkingsblokken die een specifieke rendering bevatten die u in uw leveringen kunt invoegen. U kunt bijvoorbeeld een logo, een wensbericht of een koppeling naar de spiegelpagina van het bericht toevoegen. Inhoudsblokken zijn beschikbaar bij een speciale vermelding in de personalisatie-editor. [Meer informatie](personalization-blocks.md).

* Maken **voorwaardelijke inhoud**

   Configureer voorwaardelijke inhoud om bijvoorbeeld dynamische personalisatie toe te voegen op basis van het profiel van de ontvanger. Tekstblokken en/of afbeeldingen worden ingevoegd wanneer een bepaalde voorwaarde waar is. [Meer informatie](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Guardrails en aanbevelingen{#perso-guardrails}

### Personalisatietijd uit{#perso-timeout}

Om leveringsbescherming te verbeteren, kunt u een onderbreking voor de verpersoonlijkingsfase plaatsen.

In de **[!UICONTROL Delivery]** tabblad van het dialoogvenster **[!UICONTROL Delivery properties]** selecteert u een maximumwaarde in seconden voor de **[!UICONTROL Maximum personalization run time]** optie.

Als tijdens de voorvertoning of het verzenden de maximale tijd die u in dit veld instelt, wordt overschreden, wordt het proces afgebroken met een foutbericht en mislukt de levering.

De standaardwaarde is 5 seconden.

Als u deze optie instelt op 0, is er geen tijdslimiet voor de verpersoonlijkingsfase.


### Interne variabelen{#internal-variables}

De volgende variabelen zijn interne variabelen die voor verpersoonlijking kunnen worden gebruikt maar niet moeten worden gewijzigd: **levering**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue**, **voorstel**.


## Video over zelfstudie {#personalization-video}

Begrijp de verschillende soorten dynamische content en leer personalisatieblokken en voorwaardelijke verklaringen maken en toepassen op een levering.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
