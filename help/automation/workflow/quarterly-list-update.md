---
product: campaign
title: Driemaandelijkse lijstupdate met een incrementele query
description: In dit geval wordt een incrementele query gebruikt om een lijst met ontvangers automatisch bij te werken.
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: eedc796a-865f-47a8-8807-5980546b8adf
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 5%

---

# Driemaandelijkse lijstupdate met een incrementele query {#quarterly-list-update}



In het volgende voorbeeld, wordt een [&#x200B; stijgende vraag &#x200B;](incremental-query.md) gebruikt om een ontvankelijke lijst automatisch bij te werken. Deze ontvangers zijn gericht op seizoensgebonden marketingcampagnes.

Aangezien deze campagnes aan het begin van elk seizoen worden gestart om relevante sportactiviteiten aan te bieden, worden deze lijsten elk kwartaal bijgewerkt. Een ontvanger mag echter slechts om de negen maanden voor deze campagne worden ingezet. Op deze manier kunt u de subsidiabiliteitsfrequentie van de ontvanger uitsplitsen en activiteiten aanbieden voor verschillende seizoenen in de loop van de jaren.

![](assets/incremental_query_example.png)

1. Voeg een stijgende vraag evenals een activiteit van de lijstupdate in een nieuw werkschema toe.
1. Vorm het **[!UICONTROL Incremental query]** lusje van de activiteit zoals die in [&#x200B; wordt gespecificeerd creeer een vraag &#x200B;](query.md#creating-a-query).
1. Selecteer het tabblad **[!UICONTROL Scheduling & History]** en geef vervolgens een historie van 270 dagen op. Een ontvanger die reeds als doelwit is aangemerkt, zal niet langer voor een periode van 270 dagen, of ruwweg 9 maanden, worden aangewezen.

   Klik vervolgens op de knop **[!UICONTROL Change...]** .

1. Selecteer **[!UICONTROL Monthly]** om ervoor te zorgen dat de lijst voor het begin van elk seizoen wordt bijgewerkt.
1. Selecteer in het volgende scherm de opties maart, juni, september en december. Kies de 20e van de maand en geef op wanneer u de workflow wilt starten.
1. Selecteer vervolgens de geldigheidsperiode voor de query. Selecteer bijvoorbeeld **[!UICONTROL Permanent validity]** als u deze activiteit permanent actief wilt maken.

1. Na het goedkeuren van de stijgende vraag, vorm de activiteit van de lijstupdate zoals die in [&#x200B; wordt verklaard update van de Lijst &#x200B;](list-update.md).

De workflow wordt daarom automatisch gestart vlak voor het begin van elk seizoen. De lijst wordt bijgewerkt met nieuwe, in aanmerking komende ontvangers die de aanbiedingen ontvangen.
