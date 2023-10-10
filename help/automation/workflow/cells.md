---
product: campaign
title: Cellen
description: Cellen
feature: Workflows, Targeting Activity
role: User
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 2%

---

# Cellen{#cells}

De **[!UICONTROL Cells]** Deze activiteit biedt een weergave van de verschillende subsets als gegevenskolommen. Het vergemakkelijkt manipulatie van subsets en is ook ontworpen om personalisatiemogelijkheden te benutten.

![](assets/wf_split_cells.png)

Deze activiteit kan worden gevormd om specifieke parameters in te gaan die op gebruikersbehoeften worden gebaseerd. Standaard worden de details van elke subset in een speciaal venster beschreven via de **[!UICONTROL Cells]** en **[!UICONTROL Advanced]** tabs.

![](assets/wf_split_cells_with_customization.png)

In het onderstaande voorbeeld is het invoerformulier gewijzigd: **[!UICONTROL Data]** tab is toegevoegd om het koppelen van een aanbieding en een prioriteitsniveau voor elke subset mogelijk te maken.

![](assets/cells-activity-sample.png)

Voor deze configuratie is de volgende informatie toegevoegd aan het werkstroomformulier, in het gedeelte **[!UICONTROL Administration > Configurations > Input forms]** knooppunt van Adobe Campaign Explorer:

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

Personalisatie van invoerformulieren in Adobe Campaign is gereserveerd voor deskundige gebruikers.