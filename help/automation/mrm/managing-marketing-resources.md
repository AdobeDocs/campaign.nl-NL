---
product: campaign
title: Marketingbronnen beheren
description: Leer hoe u marketingbronnen beheert
feature: Campaigns, Resource Management
role: User
exl-id: 4d91fb7d-f846-4644-b83d-5a6a988ae297
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 1%

---

# Marketingbronnen beheren{#managing-marketing-resources}

Gebruik Adobe Campaign om de marketingbronnen die betrokken zijn bij de levenscyclus van de campagne te beheren en bij te houden. Deze marketingbronnen kunnen een whitepaper, een gegevensbestand, een logo of een ander middel zijn dat verband houdt met een campagne.

Voor elke marketingbron die via Adobe Campaign wordt beheerd, kunt u op elk gewenst moment de status en geschiedenis van de resource bijhouden en de huidige versie bekijken.

Door gebrek, worden de marketing middelen opgeslagen in **[!UICONTROL MRM > Marketing resources]** map van Campaign Explorer.

## Een marketingbron toevoegen {#adding-a-marketing-resource}

Volg onderstaande stappen om een marketingbron toe te voegen:

1. Bladeren naar de **[!UICONTROL Campaigns]** en selecteert u **[!UICONTROL Marketing resouces]**.

1. Klik op de knop **[!UICONTROL Create]**.
   ![](assets/add-a-mkt-resource.png)
1. Sleep het bestand naar de Campagneserver en zet het neer in het resourcevenster Marketing om het te uploaden. U kunt ook de opdracht **[!UICONTROL Upload file to server...]** koppeling.
   ![](assets/mkt-resource-creation.png)

Wanneer het uploaden is voltooid, wordt de bron toegevoegd aan de lijst met beschikbare bronnen.

## Marketingbronnen beheren {#manage-marketing-resources}

Nadat de marketingbron is geüpload, is deze beschikbaar voor alle Adobe Campaign-operatoren. Zij kunnen het bekijken, een exemplaar maken om het te wijzigen, of het dossier op de server bijwerken.

![](assets/open-a-marketing-resource.png)

Gebruik de **[!UICONTROL Assigned to]** vervolgkeuzelijst in de **[!UICONTROL Edit]** om de operator te selecteren die verantwoordelijk is voor de resource.

![](assets/assign-a-mkt-resource.png)

U kunt ook de operatoren of groepen operatoren selecteren die verantwoordelijk zijn voor de validatie van bronnen en de publicatie van bronnen. Klik op de knop  **[!UICONTROL Advanced parameters]** koppeling.

Deze operatoren worden via e-mail op de hoogte gesteld wanneer het validatieproces van de bron wordt gestart.

Als er geen controleur is geselecteerd, wordt de bron **[!UICONTROL cannot be]** onder voorbehoud van goedkeuring.

Gebruik de **[!UICONTROL Audit]** om een proeflezer toe te voegen en een beschikbaarheidsdatum voor het middel te bepalen. Na deze datum wordt het weergegeven met **[!UICONTROL Late]** status.

>[!NOTE]
>
>De **[!UICONTROL History]** bevat het download- en updatelogboek voor de bron. De **[!UICONTROL Details]** Hiermee kunt u de geselecteerde versie weergeven.
>
>De **[!UICONTROL Audit]** kunt u alle acties controleren die op de bron worden uitgevoerd: goedkeuringen, weigeringen van goedkeuring, verwante opmerkingen of publicaties.

### Een bron vergrendelen/ontgrendelen {#locking-unlocking-a-resource}

Zodra gecreeerd, zijn de middelen beschikbaar in het marketing middeldashboard, en de exploitanten kunnen hen uitgeven en wijzigen.

Wanneer een exploitant aan een middel begint te werken, is de beste praktijken het te sluiten, om andere exploitanten te verhinderen het tezelfdertijd te wijzigen. De bron is vervolgens gereserveerd: deze blijft toegankelijk, maar kan niet op de server worden gepubliceerd of bijgewerkt door een andere operator.

Een marketingbron kan alleen worden vergrendeld als deze niet is goedgekeurd.

Als u een bron wilt vergrendelen, klikt u op de knop **[!UICONTROL Lock]** in het dashboard voor de bron.

![](assets/lock-a-resource.png)


Wanneer de bron is bijgewerkt, klikt u op de knop **[!UICONTROL Lock]** in het resourcedashboard om deze opnieuw beschikbaar te maken voor alle operatoren.

Een speciaal bericht geeft een melding aan alle operatoren die toegang proberen te krijgen tot het bericht:

![](assets/mkt-resource-locked.png)

De **[!UICONTROL Tracking]** tab geeft de naam aan van de operator die de resource heeft vergrendeld.

![](assets/mkt-resource-audit-tab.png)


>[!NOTE]
>
>Alleen de operator die de resource heeft vergrendeld en de operators met beheerdersrechten zijn gemachtigd om een resource te ontgrendelen.

### Discussieforums {#discussion-forums}

Voor elke bron wordt de **[!UICONTROL Forum]** op dit tabblad kunnen deelnemers informatie delen.

![](assets/mkt-resource-forum.png)

Meer informatie in het dialoogvenster [Discussieforums](discussion-forums.md) sectie.

### Goedkeuringsproces {#approval-process}

De verwachte beschikbaarheidsdatum wordt getoond in de middeldetails, als het in **[!UICONTROL Tracking]** tab. Als deze datum is bereikt, kunt u het goedkeuringsproces uitvoeren met de opdracht **[!UICONTROL Submit for approval]** in het dashboard voor de bron. De middelstatus verandert dan in **[!UICONTROL Approval in progress]**.

Als u een bron wilt goedkeuren, klikt u op de knop **[!UICONTROL Approve the resource]** op het dashboard.

![](assets/mkt-resouce-approve.png)

Geautoriseerde marktdeelnemers kunnen vervolgens de goedkeuring accepteren of afwijzen. Deze actie is mogelijk: via het verzonden e-mailbericht (door op de koppeling in het meldingsbericht te klikken) of via de clientconsole (door op de knop **[!UICONTROL Approve]** ).

In het goedkeuringsvenster kunt u een opmerking invoeren.

![](assets/mkt-resource-approval-confirmation.png)

Bladeren naar de **[!UICONTROL Tracking]** om goedkeuringen te controleren.

>[!NOTE]
>
>Naast de recensent die voor elke marketing middel wordt gespecificeerd, zijn de exploitanten met beheerderrechten en middelmanager gemachtigd om een marketing middel goed te keuren.

### Een bron publiceren {#publishing-a-resource}

Wanneer deze is goedgekeurd, moet de marketingbron worden gepubliceerd. Het publicatieproces moet afhankelijk worden gesteld van een specifieke tenuitvoerlegging overeenkomstig de eisen van de onderneming. Dit betekent dat de middelen op een Extranet of een andere server kunnen worden gepubliceerd, kan de specifieke informatie naar een externe dienstverlener, enz. worden verzonden.

Als u een bron wilt publiceren, klikt u op de knop **[!UICONTROL Publish]** in de bewerkingszone van het dashboard voor marketingbronnen.

![](assets/mkt-resource-publish.png)

U kunt het publiceren van een bron ook automatiseren via een workflow.

Het publiceren van een middel betekent het ter beschikking stellen voor gebruik (door een andere taak, bijvoorbeeld). Publicatie als zodanig varieert afhankelijk van de aard van uw bron: voor een flyer kan publiceren betekenen dat het bestand naar een printer wordt gestuurd, voor een webagentschap kan het betekenen dat het naar een website wordt gepubliceerd, enzovoort.

Adobe Campaign kan alleen publiceren als u een geschikte workflow maakt en deze aan de bron koppelt. Open hiertoe de **[!UICONTROL Advanced settings...]** van de bron en selecteer vervolgens de gewenste workflow in het dialoogvenster **[!UICONTROL Post-processing]** veld.

![](assets/mkt-resource-post-processing-wf.png)

De workflow wordt uitgevoerd:

* Wanneer de controleur op de knop **[!UICONTROL Publish resource]** koppeling (of, als er geen controleur is gedefinieerd, de persoon die verantwoordelijk is voor de bron).
* Als het middel via een marketing middelaanmaaktaak wordt beheerd, zal het worden uitgevoerd wanneer de taak wordt geplaatst aan **[!UICONTROL Finished]**, zolang de **[!UICONTROL Publish the marketing resource]** is ingeschakeld in de taak. [Meer informatie](creating-and-managing-tasks.md#marketing-resource-creation-task))

Als een werkstroom niet onmiddellijk wordt gestart (als de werkstroom bijvoorbeeld wordt gestopt), verandert de status van de bron in **[!UICONTROL Pending publication]**. Zodra de werkstroom is gestart, verandert de status van de bron in **[!UICONTROL Published]**. Deze status houdt geen rekening met mogelijke fouten in het publicatieproces. Controleer de status van uw workflow om er zeker van te zijn dat deze correct is uitgevoerd.

## Een bron koppelen aan een campagne {#linking-a-resource-to-a-campaign}

### Verwijzing naar een marketingbron {#referencing-a-marketing-resource}

Marketingbronnen kunnen aan campagnes worden gekoppeld, op voorwaarde dat deze functie is geselecteerd in het dialoogvenster [campagnemalsjabloon](../campaigns/marketing-campaign-templates.md).

Bladeren naar de **[!UICONTROL Edit > Documents > Resources]** tabblad in het campagnecdashboard en klik vervolgens op **[!UICONTROL Add]** om de betrokken bron te selecteren.

![](assets/link-a-mkt-resource-to-a-campaign.png)

U kunt bronnen filteren op status, aard of type of een gepersonaliseerd filter toepassen.

Gebruik de **[!UICONTROL Details]** om de bron te bewerken en voor te vertonen.

### Een marketingbron toevoegen aan een leveringsoverzicht {#adding-a-marketing-resource-to-a-delivery-outline}

Marketingbronnen kunnen worden gekoppeld aan leveringen via leveringscontouren.

Meer informatie over leveringscontouren vindt u in [deze sectie](../campaigns/marketing-campaign-deliveries.md).

Klik hiertoe met de rechtermuisknop op een leveringsoverzicht en selecteer **Nieuw > Bron**.

![](assets/mkt-resource-add-in-del-outline.png)

Voer de naam van het element in en selecteer het in het menu **Marketing resource** vervolgkeuzelijst.

![](assets/mkt-resource-select-in-del-outline.png)


## Voorraadbeheer {#stock-management}

U kunt een marketingbron koppelen aan een of meer voorraden om uw voorraad te beheren en een waarschuwing op het dashboard weer te geven als er onvoldoende voorraad is.


Volg onderstaande stappen om een marketingbron te koppelen aan een bestand:

1. Een bestand bewerken of een nieuw bestand maken. Meer informatie over voorraden in [deze sectie](../campaigns/providers--stocks-and-budgets.md#stock-management).

1. Voeg een voorraadlijn toe, en selecteer de overeenkomstige marketing middel.

   ![](assets/mkt-resource-in-a-stock-line.png)

   U kunt de geselecteerde bron bewerken via het dialoogvenster **[!UICONTROL Edit the link]** pictogram rechts van de bron als deze is geselecteerd.

1. Geef de eerste voorraad en het waarschuwingsbestand op en sla deze op.

De voorraad wordt vermeld in de marketingbron **Voorraden** tab.
