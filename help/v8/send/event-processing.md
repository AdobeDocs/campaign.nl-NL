---
title: Gebeurtenissen verzamelen en verwerken
description: Leer hoe het Transactionele overseinen van de Campagne gebeurtenissen verzamelt en verwerkt
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: c1deb0a1-aeba-4813-b674-a6a164b98b02
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---

# Gebeurtenisverwerking {#event-processing}

In de context van transactiemeldingen wordt een gebeurtenis gegenereerd door een extern informatiesysteem en wordt deze via het **[!UICONTROL PushEvent]** en **[!UICONTROL PushEvents]** methoden. Deze methoden worden beschreven in [deze sectie](event-description.md).

Deze gebeurtenis bevat gegevens die zijn gekoppeld aan de gebeurtenis, zoals:

* haar [type](transactional.md#create-event-types): bevestiging bestellen, account maken op een website, enz.;
* het e-mailadres of telefoonnummer;
* om het even welke andere informatie te verrijken en het transactionele bericht vóór levering te personaliseren: contactgegevens van de klant, taal van het bericht, e-mailindeling, enz.

Voorbeeld van gebeurtenisgegevens:

![](assets/mc-event-request.png)

Om transactionele berichtengebeurtenissen te verwerken, worden de volgende stappen toegepast op de uitvoeringsinstantie(s):

1. [Gebeurtenisverzameling](#event-collection)
1. [Gebeurtenisoverdracht naar een berichtsjabloon](#routing-towards-a-template)
1. Gebeurtenisverrijking met personalisatiegegevens
1. [Uitvoering van levering](delivery-execution.md)
1. [Recycling van gebeurtenissen](#event-recycling) waarvan de gekoppelde levering is mislukt (via een Adobe Campaign-workflow)

Zodra alle stappen worden bereikt, ontvangt elke gerichte ontvanger een gepersonaliseerd bericht.

## Gebeurtenissen verzamelen {#event-collection}

Gebeurtenissen die door het informatiesysteem worden gegenereerd, kunnen in twee modi worden verzameld:

* Met aanroepen van SOAP-methoden kunt u gebeurtenissen in Adobe Campaign duwen: Met de methode PushEvent kunt u één gebeurtenis tegelijk verzenden. Met de methode PushEvents kunt u meerdere gebeurtenissen tegelijk verzenden. [Meer informatie](event-description.md).

* Als u een workflow maakt, kunt u gebeurtenissen herstellen door bestanden te importeren of via een SQL-gateway, met de [Federale gegevenstoegang](../connect/fda.md) module.

Nadat de gebeurtenissen zijn verzameld, worden ze uitgesplitst naar technische workflows tussen realtime- en batchwachtrijen van de uitvoeringsinstantie(s), terwijl ze wachten om te worden gekoppeld aan een [berichtsjabloon](transactional-template.md).

![](assets/mc-event-queues.png)

>[!NOTE]
>
>In de uitvoeringsinstanties worden de **[!UICONTROL Real time events]** of **[!UICONTROL Batch events]** mappen mogen niet worden ingesteld als weergaven, omdat dit tot problemen met toegangsrechten kan leiden. Raadpleeg voor meer informatie over het instellen van een map als weergave [deze sectie](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## Een gebeurtenis overbrengen naar een sjabloon {#event-to-template}

Nadat de berichtsjabloon op de uitvoeringsinstantie(s) is gepubliceerd, worden automatisch twee sjablonen gegenereerd: die moet worden gekoppeld aan een realtime-gebeurtenis en een gebeurtenis die moet worden gekoppeld aan een batchgebeurtenis.

De verpletterende stap bestaat uit het verbinden van een gebeurtenis aan het aangewezen berichtmalplaatje, dat op wordt gebaseerd:

* Het gebeurtenistype dat is opgegeven in de eigenschappen van de gebeurtenis zelf:

   ![](assets/event-type-sample.png)

* Het gebeurtenistype dat in de eigenschappen van het berichtmalplaatje wordt gespecificeerd:

   ![](assets/event-type-select.png)

Door gebrek, baseert het verpletteren zich op de volgende informatie:

* Het gebeurtenistype
* Het kanaal dat moet worden gebruikt (standaard: e-mail)
* De meest recente leveringstemplate, gebaseerd op de publicatiedatum

## Gebeurtenisstatus controleren {#event-statuses}

Alle verwerkte gebeurtenissen worden gegroepeerd in één weergave, in het dialoogvenster **Gebeurtenisgeschiedenis** of de Verkenner. Ze kunnen worden gecategoriseerd op gebeurtenistype of op **status**.

Mogelijke statussen zijn:

* **In behandeling**

   * Een gebeurtenis in behandeling kan een gebeurtenis zijn die net is verzameld en die nog niet is verwerkt. De **[!UICONTROL Number of errors]** geeft de waarde 0 aan in de kolom. De e-mailsjabloon is nog niet gekoppeld.
   * Een gebeurtenis in behandeling kan ook een gebeurtenis zijn die wordt verwerkt maar waarvan de bevestiging onjuist is. De **[!UICONTROL Number of errors]** in de kolom wordt een waarde weergegeven die niet 0 is. Als u wilt weten wanneer deze gebeurtenis opnieuw wordt verwerkt, raadpleegt u de **[!UICONTROL Process requested on]** kolom.

* **In behandeling**
De gebeurtenis is verwerkt en de leveringssjabloon is gekoppeld. De e-mail is in afwachting van levering en het klassieke leveringsproces wordt toegepast. Voor meer informatie kunt u de levering openen.
* **Verzonden**, **Genegeerd** en **Afleveringsfout**
Deze leveringsstatussen worden teruggevorderd via de 
**updateEventsStatus** workflow. Voor meer informatie kunt u de relevante levering openen.
* **Gebeurtenis niet gedekt**
Het transactionele overseinen die fase verplettert ontbrak. Adobe Campaign heeft bijvoorbeeld het e-mailbericht dat als sjabloon voor de gebeurtenis fungeert, niet gevonden.
* **Gebeurtenis verlopen**
Het maximumaantal verzendpogingen is bereikt. De gebeurtenis wordt als null beschouwd.

## Gebeurtenissen van Recycle {#event-recycling}

Als de levering van een bericht op een specifiek kanaal mislukt, kan Adobe Campaign het bericht opnieuw verzenden via een ander kanaal. Als een levering op het SMS-kanaal bijvoorbeeld mislukt, wordt het bericht opnieuw verzonden via het e-mailkanaal.

Hiertoe moet u een workflow configureren die alle gebeurtenissen opnieuw maakt met de **Afleveringsfout** en wijst er een ander kanaal aan toe.

>[!CAUTION]
>
>Deze stap kan alleen worden uitgevoerd met behulp van een workflow en is daarom voorbehouden aan professionele gebruikers. Neem voor meer informatie contact op met de manager van uw Adobe-account.
