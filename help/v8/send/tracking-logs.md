---
title: Logbestanden voor bijhouden van toegang
description: Leer hoe u trackinglogboeken kunt openen en interpreteren
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Logbestanden voor bijhouden van toegang {#accessing-the-tracking-logs}

Wanneer de levering is verzonden en tracering is geactiveerd, wordt de trackinggegevens opgehaald in de technische workflow van **[!UICONTROL Tracking]** . Deze wordt standaard per uur uitgevoerd.

## Tekstspatiëring weergeven in profielen voor ontvangers {#recipient-tracking}

Deze informatie wordt weergegeven op het tabblad **[!UICONTROL Tracking]** van het profiel van ontvangers voor wie de levering bedoeld is, zoals in het volgende voorbeeld:

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

Op dit tabblad worden alle URL&#39;s weergegeven die door de ontvanger worden bijgehouden en waarop wordt geklikt, inclusief:

* De URL waarop is geklikt
* De datum en tijd van de klik
* De levering waarin de URL is gevonden
* Andere relevante informatie over het bijhouden van gegevens

U kunt deze informatie filteren en sorteren om het gedrag van de ontvanger te analyseren en betrokkenheidspatronen te identificeren.

## Tekstspatiëring weergeven in leveringen {#delivery-tracking}

Trackinggegevens zijn ook toegankelijk via het tabblad **[!UICONTROL Tracking]** van de levering.

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

Op dit tabblad kunt u het volgende weergeven:

* **[!UICONTROL Tracking statistics]**: biedt een overzicht van gebeurtenissen voor openen, klikken en andere tracking
* **[!UICONTROL URLs and click streams]**: geeft aan op welke koppelingen is geklikt en hoeveel keer
* **[!UICONTROL Hot clicks]**: geeft een visuele weergave weer van waar ontvangers in het bericht hebben geklikt
* **[!UICONTROL Tracking logs]**: bevat gedetailleerde, afzonderlijke traceerrecords

## Problemen met bijhouden {#troubleshooting}

>[!NOTE]
>
>Als het tabblad **[!UICONTROL Tracking]** van een levering niet wordt weergegeven, betekent dit dat het bijhouden van gegevens niet is geactiveerd. Verwijs naar [ deze sectie ](tracked-links.md) te leren hoe te om het volgen te vormen.

### De technische workflow voor bijhouden controleren {#check-tracking-workflow}

De technische workflow voor bijhouden moet worden uitgevoerd om trackinggegevens te verzamelen. U vindt de technische workflow voor bijhouden in de map **[!UICONTROL Administration > Production > Technical workflows]** .

Om het werkschema te verifiëren:

1. De **[!UICONTROL Tracking]** -workflow openen
1. Controleer de laatste uitvoeringsdatum
1. Controleren of er geen fouten zijn in de werkstroomlogboeken

Neem contact op met de systeembeheerder als de workflow niet actief is of als er fouten optreden.

## Gegevens bijhouden verifiëren

Na het verzenden van een levering waarvoor tracking is ingeschakeld:

1. Wacht tot de workflow voor bijhouden is uitgevoerd (standaard elk uur)
1. Open de levering en ga naar het tabblad **[!UICONTROL Tracking]**
1. Controleren of gegevens worden bijgehouden
1. Als er geen gegevens worden weergegeven, controleert u of:
   * Tekstspatiëring is geactiveerd in de leveringsinstellingen
   * De technische workflow voor bijhouden wordt uitgevoerd
   * Ontvangers hebben het e-mailbericht geopend en op koppelingen geklikt

## Verwante onderwerpen {#related-topics}

* [Leer hoe u bijgehouden koppelingen kunt configureren](tracked-links.md)
* [Leer hoe u reeksspatiëring kunt testen](testing-tracking.md)
* [Trackingrapporten begrijpen](../reporting/delivery-reports.md#tracking-indicators)

