---
product: campaign
title: Filterregels configureren
description: Leer hoe te om het filtreren regels te vormen
feature: Typology Rules
exl-id: 17507cdf-211f-4fa2-abb9-33d4f6dc47bb
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# Filterregels{#filtering-rules}

Met filterregels kunt u de berichten definiëren die u wilt uitsluiten op basis van criteria die in een query zijn gedefinieerd. Deze regels zijn gekoppeld aan een doelgerichte dimensie.

Filterregels kunnen worden gekoppeld aan andere soorten regels (controle, druk, enz.) in typologieën, of gegroepeerd in een specifiek **Filteren** typologie. [Meer informatie](#create-and-use-a-filtering-typology).

## Een filterregel maken {#create-a-filtering-rule}

Bijvoorbeeld, kunt u uw nieuwsbrief abonnees filtreren om mededelingen te verhinderen worden verzonden naar ontvangers die onderage zijn.

Pas de volgende stappen toe om dit filter te definiëren:

1. Een **[!UICONTROL Filtering]** typologieregel die van toepassing is op alle communicatiekanalen.

   ![](assets/campaign_opt_create_filter_01.png)

1. Wijzig de standaarddimensie voor het opgeven van doelen en selecteer de abonnementen (**nms:abonnement**).

   ![](assets/campaign_opt_create_filter_02.png)

1. Maak het filter met het gereedschap **[!UICONTROL Edit the query from the targeting dimension...]** koppeling.

   ![](assets/campaign_opt_create_filter_03.png)

1. Koppel deze regel aan een campagnetypologie en sla deze op.

   ![](assets/campaign_opt_create_filter_04.png)

Wanneer deze regel in een levering wordt gebruikt, worden minderjarige abonnees automatisch uitgesloten. Een specifiek bericht geeft regeltoepassing aan:

![](assets/campaign_opt_create_filter_05.png)

## Een filterregel conditioneren {#condition-a-filtering-rule}

U kunt het toepassingsgebied van de het filtreren regel beperken die op de verbonden levering of leveringsoverzicht wordt gebaseerd.

Ga om dit te doen naar de **[!UICONTROL General]** selecteert u het type beperking dat u wilt toepassen en maakt u het filter, zoals hieronder wordt weergegeven:

![](assets/campaign_opt_create_filter_06.png)

In dit geval wordt de regel, zelfs als deze aan alle leveringen is gekoppeld, alleen toegepast op leveringen die aan de criteria van het gedefinieerde filter voldoen.

>[!NOTE]
>
>De typologieën en het filtreren regels kunnen in een werkschema, in worden gebruikt **[!UICONTROL Delivery outline]** activiteit. [Meer informatie](../workflow/delivery-outline.md).

## Filtertypologie maken en gebruiken {#create-and-use-a-filtering-typology}

U kunt **[!UICONTROL Filtering]** typologieën: zij bevatten alleen filterregels .

![](assets/campaign_opt_create_typo_filtering.png)

Deze specifieke typologieën kunnen aan een levering worden verbonden wanneer het doel wordt geselecteerd: in de leveringstovenaar, klik **[!UICONTROL To]** klikt u op de koppeling **[!UICONTROL Exclusions]** tab.

![](assets/campaign_opt_apply_typo_filtering.png)

Selecteer vervolgens de filtertypologie die op de levering moet worden toegepast. Om dit te doen, klik **[!UICONTROL Add]** en selecteert u de toe te passen typologieën.

U kunt filterregels ook rechtstreeks via dit tabblad koppelen, zonder ze te groeperen in een typologie. Gebruik hiervoor de onderste sectie van het venster.

![](assets/campaign_opt_select_typo_filtering.png)

>[!NOTE]
>
>Alleen typologieën en filterregels zijn beschikbaar in het selectievenster.
>
>Deze configuraties kunnen in het leveringsmalplaatje worden bepaald dat automatisch op alle nieuwe die leveringen worden toegepast worden gecreeerd gebruikend het malplaatje.

## Uitsluitingsregels voor standaardlevering {#default-deliverability-exclusion-rules}

Twee het filtreren regels zijn beschikbaar door gebrek: **[!UICONTROL Exclude addresses]** ( **[!UICONTROL addressExclusions]** ) en **[!UICONTROL Exclude domains]** ( **[!UICONTROL domainExclusions]** ). Tijdens de e-mailanalyse, vergelijken deze regels de ontvankelijke e-mailadressen met de verboden adressen of domeinnamen in een gecodeerde globale suppressielijst die in de leveringsinstantie wordt beheerd. Als er een gelijke is, wordt het bericht niet verzonden naar die ontvanger.

Hiermee voorkomt u dat de lijst van gewezen personen wordt toegevoegd vanwege kwaadwillige activiteiten, met name het gebruik van een Spamtrap. Als bijvoorbeeld een spamtrap wordt gebruikt om zich te abonneren via een van uw webformulieren, wordt automatisch een bevestigingsbericht verzonden naar die spamtrap. Hierdoor wordt uw adres automatisch toegevoegd aan de lijst van gewezen personen.

>[!NOTE]
>
>De adressen en domeinnamen in de globale suppressielijst worden verborgen. Alleen het aantal uitgesloten ontvangers wordt vermeld in de logboeken van de leveringsanalyse.
