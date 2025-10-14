---
title: Gebeurtenissen verzamelen en verwerken
description: Leer hoe het Transactionele overseinen van de Campagne gebeurtenissen verzamelt en verwerkt
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: c1deb0a1-aeba-4813-b674-a6a164b98b02
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 1%

---

# Gebeurtenisverwerking {#event-processing}

In de context van transactiemeldingen wordt een gebeurtenis gegenereerd door een extern informatiesysteem en wordt deze via de methoden **[!UICONTROL PushEvent]** en **[!UICONTROL PushEvents]** naar Adobe Campaign verzonden. Deze methodes worden beschreven in [&#x200B; deze sectie &#x200B;](event-description.md).

Deze gebeurtenis bevat gegevens die zijn gekoppeld aan de gebeurtenis, zoals:

* zijn [&#x200B; type &#x200B;](transactional.md#create-event-types): ordesbevestiging, rekeningsverwezenlijking op een website, enz.,
* het e-mailadres of telefoonnummer;
* alle andere informatie die het transactiemelding vóór levering moet verrijken en personaliseren: contactgegevens van de klant, taal van het bericht, e-mailformaat, enz.

Voorbeeld van gebeurtenisgegevens:

![](assets/mc-event-request.png)

Om transactionele berichtengebeurtenissen te verwerken, worden de volgende stappen toegepast op de uitvoeringsinstantie(s):

1. [Gebeurtenisverzameling](#event-collection)
1. [Gebeurtenisoverdracht naar een berichtsjabloon](#routing-towards-a-template)
1. Gebeurtenisverrijking met personalisatiegegevens
1. [Uitvoering van levering](delivery-execution.md)
1. [&#x200B; Recycling van gebeurtenissen &#x200B;](#event-recycling) de waarvan verbonden levering ontbrak (via een werkschema van Adobe Campaign)

Zodra alle stappen worden bereikt, ontvangt elke gerichte ontvanger een gepersonaliseerd bericht.

## Gebeurtenissen verzamelen {#event-collection}

Gebeurtenissen die door het informatiesysteem worden gegenereerd, kunnen in twee modi worden verzameld:

* Met aanroepen van SOAP-methoden kunt u gebeurtenissen in Adobe Campaign duwen: met de methode PushEvent kunt u één gebeurtenis tegelijk verzenden. Met de methode PushEvents kunt u verschillende gebeurtenissen tegelijk verzenden. [Meer informatie](event-description.md).

* Het creëren van een werkschema laat u gebeurtenissen terugkrijgen door dossiers of via een SQL gateway, met de [&#x200B; Verdeelde module van de Toegang van Gegevens &#x200B;](../connect/fda.md) in te voeren.

Zodra zij worden verzameld, worden de gebeurtenissen verdeeld door technische werkschema&#39;s tussen real time en partijrijen van de uitvoeringsinstantie(s), terwijl het wachten om aan a [&#x200B; berichtmalplaatje &#x200B;](transactional-template.md) worden verbonden.

![](assets/mc-event-queues.png)

>[!NOTE]
>
>Op uitvoeringsinstanties moeten de mappen **[!UICONTROL Real time events]** of **[!UICONTROL Batch events]** niet worden ingesteld als weergaven, omdat dit tot problemen met toegangsrechten kan leiden. Voor meer bij het plaatsen van een omslag als mening, verwijs naar [&#x200B; deze sectie &#x200B;](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## Een gebeurtenis overbrengen naar een sjabloon {#event-to-template}

Nadat de berichtsjabloon op de uitvoeringsinstantie(s) is gepubliceerd, worden automatisch twee sjablonen gegenereerd: een sjabloon die moet worden gekoppeld aan een realtime-gebeurtenis en een sjabloon dat moet worden gekoppeld aan een batchgebeurtenis.

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

Alle verwerkte gebeurtenissen worden gegroepeerd in één enkele mening, in de **de geschiedenisomslag van de Gebeurtenis** of Ontdekkingsreiziger. Zij kunnen door gebeurtenistype of door **status** worden gecategoriseerd.

Mogelijke statussen zijn:

* **In afwachting van**

   * Een gebeurtenis in behandeling kan een gebeurtenis zijn die net is verzameld en die nog niet is verwerkt. In de kolom **[!UICONTROL Number of errors]** wordt de waarde 0 weergegeven. De e-mailsjabloon is nog niet gekoppeld.
   * Een gebeurtenis in behandeling kan ook een gebeurtenis zijn die wordt verwerkt maar waarvan de bevestiging onjuist is. De kolom **[!UICONTROL Number of errors]** toont een waarde die niet 0 is. Raadpleeg de kolom **[!UICONTROL Process requested on]** als u wilt weten wanneer deze gebeurtenis opnieuw wordt verwerkt.

* **Hangende levering**
De gebeurtenis is verwerkt en de leveringssjabloon is gekoppeld. De e-mail is in afwachting van levering en het klassieke leveringsproces wordt toegepast. Voor meer informatie kunt u de levering openen.
* **Verzonden**, **genegeerde** en **fout van de Levering**
Deze leveringsstatussen worden teruggekregen via het **updateEventsStatus** werkschema. Voor meer informatie kunt u de relevante levering openen.
* **niet behandelde Gebeurtenis**
Het transactionele overseinen die fase verplettert ontbrak. Adobe Campaign heeft bijvoorbeeld het e-mailbericht dat als sjabloon voor de gebeurtenis fungeert, niet gevonden.
* **Gebeurtenis verlopen**
Het maximumaantal verzendpogingen is bereikt. De gebeurtenis wordt als null beschouwd.

## Gebeurtenissen van Recycle {#event-recycling}

Als de levering van een bericht op een specifiek kanaal mislukt, kan Adobe Campaign het bericht opnieuw verzenden via een ander kanaal. Als een levering op het SMS-kanaal bijvoorbeeld mislukt, wordt het bericht opnieuw verzonden via het e-mailkanaal.

Om dit te doen, moet u een werkschema vormen dat alle gebeurtenissen met de **fout van de Levering** status ontspant, en een verschillend kanaal aan hen toewijst.

>[!CAUTION]
>
>Deze stap kan alleen worden uitgevoerd met behulp van een workflow en is daarom voorbehouden aan professionele gebruikers. Neem voor meer informatie contact op met de Adobe-accountmanager.
