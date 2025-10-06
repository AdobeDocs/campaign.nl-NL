---
title: Het Transactionele overseinen van de campagne
description: Aan de slag met Transactionele berichten
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---

# Aan de slag met Transactioneel overseinen{#send-transactional-messages}

Transactioneel overseinen (het Centrum van het Bericht) is een module van de Campagne die voor het beheren van trekkerberichten wordt ontworpen. Deze meldingen worden gegenereerd op basis van gebeurtenissen die in werking zijn gesteld via informatiesystemen, en kunnen zijn: factuur, orderbevestiging, bevestiging van verzending, wijziging van het wachtwoord, kennisgeving van onbeschikbaarheid van het product, rekeningoverzicht, aanmaak van websiteaccount, enz.

>[!NOTE]
>
>Als Beheerde gebruiker van de Diensten van de Wolk, [&#x200B; contacteer Adobe &#x200B;](../start/campaign-faq.md#support){target="_blank"} om het Transactionele overseinen van de Campagne in uw milieu te vormen.

Transactieberichten worden gebruikt voor het verzenden van:

* meldingen, zoals bevestiging van bestellingen of opnieuw instellen van wachtwoorden, bijvoorbeeld
* een individuele reactie in real time op een klantenactie
* niet-promotionele inhoud

De montages van het Transactionele overseinen zijn gedetailleerd in [&#x200B; deze sectie &#x200B;](../config/transactional-msg-settings.md).

Begrijp transactie overseinenarchitectuur op [&#x200B; deze pagina &#x200B;](../architecture/architecture.md#transac-msg-archi).

## Operationeel beginsel van het transactieverkeer {#transactional-messaging-operating-principle}

De module van het Overseinen van Adobe Campaign Transactional integreert in een informatiesysteem dat gebeurtenissen terugkeert die in gepersonaliseerde transactionele berichten moeten worden veranderd. Deze berichten kunnen individueel of in partijen via e-mail, SMS of push-berichten worden verzonden.

Stel dat u een bedrijf bent met een website waar uw klanten producten kunnen kopen.

Met Adobe Campaign kunt u een meldingsbericht verzenden naar klanten die producten aan hun winkelwagentje hebben toegevoegd. Wanneer een van hen uw website verlaat zonder door te gaan met hun aankopen (externe gebeurtenis die een Campagne-gebeurtenis activeert), wordt er automatisch een e-mailbericht over het verlaten van de winkelwagen naar hen verzonden (levering van transactiemeldingen).

De belangrijkste stappen om dit in werking te stellen zijn hieronder beschreven:

1. [&#x200B; creeer een gebeurtenistype &#x200B;](#create-event-types).
1. [&#x200B; creeer en ontwerp het berichtmalplaatje &#x200B;](transactional-template.md#create-message-template). Tijdens deze stap moet u een gebeurtenis koppelen aan uw bericht.
1. [&#x200B; Test het bericht &#x200B;](transactional-template.md#test-message-template).
1. [&#x200B; publiceer het berichtmalplaatje &#x200B;](transactional-template.md#publish-message-template).

Zodra u het transactionele berichtmalplaatje ontwierp en publiceerde, als een overeenkomstige gebeurtenis wordt teweeggebracht, worden de relevante gegevens verzonden naar Campagne via de methodes PushEvent en PushEvents [&#x200B; SOAP &#x200B;](../send/event-description.md), en de levering wordt verzonden naar de gerichte ontvangers.

## Gebeurtenistypen maken {#create-event-types}

Om ervoor te zorgen elke gebeurtenis in een gepersonaliseerd bericht kan worden veranderd, moet u eerst **gebeurtenistypen** creëren.

Wanneer [&#x200B; creërend een berichtmalplaatje &#x200B;](#create-message-template), zult u het type van gebeurtenis selecteren die het bericht aanpast u wilt verzenden.

>[!CAUTION]
>
>U moet gebeurtenistypen creëren alvorens hen in berichtmalplaatjes te kunnen gebruiken.

Voer de volgende stappen uit om gebeurtenistypen te maken die door Adobe Campaign worden verwerkt:

1. Blader naar de map **[!UICONTROL Administration > Platform > Enumerations]** van de Campagneverkenner.
1. Selecteer de opsomming **[!UICONTROL Event type]** in de lijst.
1. Klik op **[!UICONTROL Add]** om een opsommingswaarde te maken. Dit kan een bevestiging zijn van de bestelling, een wijziging van het wachtwoord, een wijziging in de levering van de bestelling, enzovoort.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Elk gebeurtenistype moet overeenkomen met een waarde in de opsomming **[!UICONTROL Event type]** .

1. Nadat de gespecificeerde lijstwaarden zijn gecreeerd, logoff en terug op uw geval voor de verwezenlijking om efficiënt te zijn.

>[!NOTE]
>
>Leer meer over [&#x200B; opsommingen &#x200B;](../config/enumerations.md).

Voor volgende stap, leer hoe te [&#x200B; uw malplaatje voor Transactioneel overseinen &#x200B;](transactional-template.md) creëren en publiceren.
