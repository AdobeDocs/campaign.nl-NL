---
product: campaign
title: Inbox rendering in campagne
description: Leer hoe u e-mailweergaven vastlegt en beschikbaar maakt in een speciaal rapport
feature: Inbox Rendering, Monitoring, Email Rendering
role: User
version: Campaign v8, Campaign Classic v7
exl-id: a3294e70-ac96-4e51-865f-b969624528ce
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 8%

---

# Inboxrendering{#inbox-rendering}

## Inbox-rendering {#about-inbox-rendering}

Alvorens **te raken verzend** knoop, zorg ervoor dat uw bericht aan de ontvangers op een optimale manier op een verscheidenheid van Webcliënten, Webpost en apparaten zal worden getoond.

Om dit toe te staan, gebruikt Adobe Campaign de [ web-based e-mailtestende oplossing 0} Litmus {om de teruggaven te vangen en hen beschikbaar te maken in een specifiek rapport. ](https://litmus.com/email-testing){target="_blank"} Hierdoor kunt u een voorvertoning van het verzonden bericht weergeven in de verschillende contexten waarin het kan worden ontvangen en de compatibiliteit van grote desktops en toepassingen controleren.

>[!CAUTION]
>Inbox het teruggeven is niet compatibel met [ terugkomende leveringen ](../../automation/workflow/recurring-delivery.md).

Litmus is een functie-rijke e-mailbevestiging en previewing toepassing. Hiermee kunnen makers van e-mailinhoud hun berichtinhoud voorvertonen in meer dan 70 e-mailrenderers, zoals de Gmail inbox of de Apple Mail client.

De mobiele, overseinen en webmail cliënten beschikbaar voor **Inbox teruggevend** in Adobe Campaign zijn vermeld op de [ website van de Samenvatting ](https://litmus.com/email-testing){target="_blank"} (klik **Mening alle e-mailcliënten**).

>[!NOTE]
>
>Rendering in doos is niet nodig om personalisatie in leveringen te testen. Personalization kan met de hulpmiddelen van Adobe Campaign zoals **[!UICONTROL Preview]** en [ Proofs ](preview-and-proof.md#send-proofs) worden gecontroleerd.

## Informatie over Litmus tokens {#about-litmus-tokens}

Aangezien Litmus een derdedienst is, werkt het op een krediet-per-gebruiksmodel. Telkens wanneer een gebruiker op de functionaliteit van de Leiding roept, wordt het krediet afgetrokken.

In Adobe Campaign komt het krediet overeen met het aantal beschikbare renderingen (tokens genoemd).

>[!NOTE]
>
>Het aantal beschikbare Litmus tokens hangt af van de campagnelicentie die u hebt aangeschaft. Controleer uw licentieovereenkomst.

Telkens wanneer u de functie **[!UICONTROL Inbox rendering]** in een levering gebruikt, vermindert elke gegenereerde rendering de beschikbare tokens met één.

>[!IMPORTANT]
>
>Tokens zijn voor elke afzonderlijke rendering en niet voor het hele Inbox-renderrapport, wat betekent dat:
>
>* Telkens als Inbox teruggevend rapport wordt geproduceerd, wordt één teken per overseinencliënt afgetrokken: één teken voor het teruggeven van Vooruitzichten 2000, voor het teruggeven van Vooruitzichten 2010, voor Apple Mail 9, etc.
>* Als u voor dezelfde levering de rendering Inbox opnieuw genereert, wordt het aantal beschikbare tokens opnieuw verminderd met het aantal gegenereerde renderingen.
>

Het aantal resterende beschikbare tokens wordt getoond in het [ Inbox teruggevend rapport ](#inbox-rendering-report).

![](assets/s_tn_inbox_rendering_tokens.png)

Doorgaans wordt de renderfunctie Inbox gebruikt om het HTML-framework van een nieuw ontworpen e-mail te testen. Voor elke rendering zijn ongeveer 70 tokens nodig (afhankelijk van het aantal omgevingen dat doorgaans wordt getest). In sommige gevallen hebt u echter meerdere renderingrapporten in postvak nodig om de levering volledig te testen. Het zou dus meer tokens kunnen vergen om meerdere controles te voltooien.

## Toegang tot het renderrapport in Postvak IN {#accessing-the-inbox-rendering-report}

Voer onderstaande stappen uit als u de e-maillevering hebt gemaakt en de content en de doelpopulatie ervan hebt bepaald.

Voor meer bij het creëren van, het ontwerpen van en het richten van een levering, verwijs naar deze [ pagina ](defining-the-email-content.md).


1. Klik op de knop **[!UICONTROL Inbox rendering]** op de bovenste balk van de levering.

1. Selecteer **[!UICONTROL Analyze]** om het vastlegproces te starten.

   ![](assets/s_tn_inbox_rendering_button.png)

   Er wordt een bewijs verzonden. De renderingminiaturen zijn enkele minuten na het verzenden van de e-mails toegankelijk in die proefdruk. Voor meer bij het verzenden van proeven, verwijs naar [ deze sectie ](preview-and-proof.md#send-proofs).

1. Na verzending wordt de proefdruk weergegeven in de leveringslijst. Dubbelklik erop.

   ![](assets/s_tn_inbox_rendering_delivery_list.png)

1. Ga naar **Inbox die** tabel teruggeeft van de proef.

   ![](assets/s_tn_inbox_rendering_tab.png)

   Het renderrapport Inbox wordt weergegeven.

## Inbox rendering report {#inbox-rendering-report}

In dit rapport worden de inbox-weergaven weergegeven zoals deze aan de ontvanger worden weergegeven. De renderingen kunnen afwijken, afhankelijk van de manier waarop de ontvanger de e-maillevering opent: in een browser, op een mobiel apparaat of via een e-mailtoepassing.

In de bovenste sectie wordt de verdeling weergegeven van het aantal ontvangen berichten, ongewenste berichten (spam), niet-ontvangen berichten of in afwachting van ontvangst via een grafische kleurcodering.

![](assets/s_tn_inbox_rendering_summary.png){width="40%" align="left"}

Houd de cursor boven het diagram om de details van elke kleur weer te geven. Klik op een item in de lijst om de bijbehorende categorie in het diagram te verbergen of weer te geven.

De hoofdtekst van het rapport bestaat uit drie delen: **[!UICONTROL Mobile]** , **[!UICONTROL Desktop]** en **[!UICONTROL Webmails]** . Blader omlaag door het rapport om alle weergaven gegroepeerd in deze drie categorieën te bekijken.

![](assets/s_tn_inbox_rendering_report.png)

Klik op de bijbehorende kaart om de informatie voor elk rapport op te halen. De weergave wordt getoond voor de geselecteerde ontvangstmethode.

![](assets/s_tn_inbox_rendering_example.png)
