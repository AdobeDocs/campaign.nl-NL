---
title: PI-weergave beperken
description: Leer hoe u de weergave PI beperkt
feature: PI, Privacy, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
source-git-commit: 2d13ba585b55f0e149d1bca53240b05fe5a8a9eb
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# PI-weergave beperken{#restricting-pii-view}

## Overzicht {#overview}

Als u marketinggebruikers toegang wilt geven tot gegevensrecords, maar ze geen persoonlijke gegevens van ontvangers (zoals voornaam, achternaam of e-mailadres) wilt laten zien, past u de onderstaande richtlijnen toe om de privacy te beschermen en te voorkomen dat gegevens worden misbruikt door reguliere campagneoperatoren.

## Implementatie {#implementation}

Een specifiek attribuut dat op om het even welk element of attribuut kan worden toegepast is toegevoegd aan de schema&#39;s, vult het bestaande attribuut **[!UICONTROL visibleIf]** aan. Dit kenmerk is: **[!UICONTROL accessibleIf]** . Als een XTK-expressie wordt opgenomen die gerelateerd is aan de huidige gebruikerscontext, kan deze bijvoorbeeld gebruikmaken van **[!UICONTROL HasNamedRight]** of **[!UICONTROL $(login)]** .

U kunt een voorbeeld van een ontvankelijke schemauitbreiding vinden die dit gebruik hieronder toont:

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

De belangrijkste eigenschappen zijn:

* **[!UICONTROL visibleIf]**: verbergt de gebieden van de meta-gegevens, vandaar zij niet binnen een schemamening, of kolomselectie, of een [&#x200B; Bouwer van de Uitdrukking &#x200B;](../../v8/start/filter-conditions.md#list-of-functions) kunnen worden betreden. Maar dit verbergt geen gegevens, als de veldnaam handmatig wordt ingevoerd in een expressie, wordt de waarde weergegeven.
* **[!UICONTROL accessibleIf]**: verbergt de gegevens (vervangt deze door lege waarden) uit de resulterende query. Als visibleIf leeg is, krijgt het dezelfde expressie als **[!UICONTROL accessibleIf]** .

Hier volgen de gevolgen van het gebruik van dit kenmerk in Campagne:

* De gegevens zullen niet worden getoond gebruikend generische vraagredacteur in de console,
* Gegevens zijn niet zichtbaar in overzichtslijsten en recordlijst (console).
* Gegevens worden alleen-lezen in gedetailleerde weergave.
* Gegevens kunnen alleen worden gebruikt in filters (u kunt waarden toch raden met behulp van bepaalde dichotomiestrategieën).
* Expressies die zijn gemaakt met een beperkt veld, worden beperkt tot: lower(@email) wordt even toegankelijk als @email.
* In een werkstroom kunt u de beperkte kolom aan de doelpopulatie toevoegen als een extra kolom van de overgang, maar deze is nog steeds niet toegankelijk voor Adobe Campaign-gebruikers.
* Wanneer de doelpopulatie in een groep (lijst) wordt opgeslagen, zijn de kenmerken van de opgeslagen velden gelijk aan de gegevensbron.
* Gegevens zijn standaard niet toegankelijk voor JS-code.

>[!IMPORTANT]
>
>Het gebruiken van **accessibleIf** attributen op kritieke parameters (zoals die in samengestelde sleutels) kan in fouten voor gebruikers resulteren die niet worden toegestaan om de gegevens te lezen toe te schrijven aan verborgen gegevens. Dit kan tot vraagmislukkingen of onverwacht gedrag leiden. Ervoor zorgen dat essentiële parameters toegankelijk zijn om verstoringen te voorkomen.

## Aanbevelingen {#recommendations}

Bij elke levering worden e-mailadressen naar de tabellen **[!UICONTROL broadLog]** en **[!UICONTROL forecastLog]** gekopieerd. Daarom moeten deze velden ook worden beveiligd.

Hieronder ziet u een voorbeeld van de extensie van een logtabel voor het implementeren van deze extensie:

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>Deze beperking is alleen van toepassing op niet-technische gebruikers en isoleert geen gegevens: een technische gebruiker met gerelateerde machtigingen kan gegevens ophalen.
