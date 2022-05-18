---
title: Campaign Classic v7 - Capaciteitsmatrix voor campagne v8
description: De verschillen tussen Campaign Classic v7 en Campagne v8 begrijpen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 4%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8-mogelijkheden{#gs-matrix}

Als voormalig [!DNL Campaign Classic] v7 gebruiker, zou u geen grote verstoring in de manier moeten verwachten u gewoonlijk met [!DNL Adobe Campaign]. De meeste wijzigingen in v8 zijn niet zichtbaar, behalve kleine wijzigingen die in de gebruikersinterface en configuratiestappen worden doorgevoerd.

Adobe Campaign v8 is beschikbaar als een **Beheerde Cloud Service**. Het nieuwe aanbod combineert services van topklasse met proactief toezicht en tijdige waarschuwingen, waarbij de nadruk ligt op drie gebieden:

* **Wolkenbehendigheid** — automatisering door Adobe, met geoptimaliseerde, gestandaardiseerde cloudimplementaties voor meer voorspelbare prestaties, grotere flexibiliteit en verbeterde zelfbedieningsproductiviteit.
* **Serviceervaring** — proactieve beschikbaarheid, capaciteit, en prestatiescontrole en reactie om verstoringen te voorkomen, incidenten sneller op te lossen, en de dienst regelmatig voor voortdurende verbetering te herzien.
* **Expertise in diepe campagne** — service met hoge affiniteit van deskundige Customer Engineering-teams om te voldoen aan de behoeften op het gebied van functionaliteit, techniek of leverbaarheid, het implementatierisico te beperken en wijzigingsbeheer te verbeteren.

Als voormalig [!DNL Campaign Classic] gebruiker, merk op dat het grootste deel van [!DNL Campaign Classic] v7-functies zijn beschikbaar via [!DNL Campaign] v8, met uitzondering van een kleine set, die worden vermeld in [deze sectie](#gs-removed). Andere zullen in toekomstige versies worden vrijgegeven. [Meer informatie in deze sectie](#gs-unavailable-features)

>[!NOTE]
>
> Campagne v8 is gebaseerd op een hybride architectuur. Als u van Campaign Classic v7 overgaat, merk op dat alle leveringen door de midsourcingserver gaan. [Meer informatie](../architecture/architecture.md)
>
> Als gevolg hiervan is interne routering **niet mogelijk** in Campagne v8 en de externe account is dienovereenkomstig uitgeschakeld.


## [!DNL Campaign] en [!DNL Snowflake] {#ac-gs-snowflake}

Campagne v8 werkt met [!DNL Snowflake]. Er zijn twee implementatiemodellen beschikbaar.

![](../assets/do-not-localize/glass.png) Meer informatie over [!DNL Campaign] v8-architectuur in [deze pagina](../architecture/architecture.md).


## Adobe ID gebruiken om verbinding te maken met campagne{#adobe-id}

Campagnegebruikers maken verbinding via hun Adobe ID. Dezelfde Adobe ID wordt gebruikt om al uw Adobe-plannen en -producten voor één account te bewaren, voor alle Adobe Experience Cloud-oplossingen.

![](../assets/do-not-localize/glass.png) Leer hoe u verbinding kunt maken met [!DNL Campaign] in [deze pagina](connect.md).

## Gegevens met kubussen analyseren{#adobe-reporting}

Met de module Marketing Analytics kunt u gegevens analyseren en meten, statistieken berekenen, het maken en berekenen van rapporten vereenvoudigen en optimaliseren. Daarnaast kunt u rapporten maken en doelgroepen opbouwen: zodra ze zijn geïdentificeerd, worden ze opgeslagen in lijsten die in Adobe Campaign kunnen worden gebruikt (gericht, segmentatie, enz.).

Adobe Campaign-kubusrapporten zijn geoptimaliseerd en bieden betere schaalmogelijkheden dan Campaign Classic v7. Voormalige beperkingen op kubussen zijn niet van toepassing in Campaign v8.

## Databron wijzigen {#change-data-source}

Campagne v8 biedt een extra activiteit voor een doelgerichte workflow: **[!UICONTROL Change data source]**.

De **[!UICONTROL Change data source]** activiteit staat u toe om de gegevensbron van een werkschema te veranderen **[!UICONTROL Working table]** gegevens over verschillende gegevensbronnen te beheren, zoals FDA, FFDA en de lokale gegevensbank.

![](../assets/do-not-localize/glass.png) Meer informatie over de **[!UICONTROL Change data source]** activiteit in [deze pagina](../config/workflows.md#change-data-source-activity).

## Niet-beschikbare functies{#gs-unavailable-features}

Houd er rekening mee dat bepaalde mogelijkheden niet beschikbaar zijn in deze versie van Campagne, zoals:

* Marketing Resource Management
* Gedistribueerde marketing
* Responsbeheer
* Hybride/on-premise plaatsingsmodellen

>[!CAUTION]
>
>* Momenteel is Campagne v8 **alleen** beschikbaar als Beheerde Cloud Service, en kan niet op een ongebouw of hybride milieu&#39;s worden opgesteld.
>
>* Migratie vanuit een bestaande Campaign Classic v7-omgeving is nog niet beschikbaar.
>
>* Als u niet zeker bent van uw implementatiemodel of een vraag hebt, neemt u contact op met uw Adobe-accountmanager.


## Niet-ondersteunde functies{#gs-removed}

Om zich aan het nieuwe architectuur en plaatsingsmodel van Campagne v8 aan te sluiten, worden sommige historische Campaign Classic v7 mogelijkheden niet meer gesteund met Campagne v8, zoals:

* Coupons
* Webtracking
* Enquêtes
* Sociale marketing met Facebook
* ACS Connector (primaire aanbieding)
* Integratie met LDAP
* Gebruiker/wachtwoord aanmelden

>[!NOTE]
>
>Sommige niet-beschikbare of niet-ondersteunde functies zijn mogelijk nog wel zichtbaar in de gebruikersinterface.
