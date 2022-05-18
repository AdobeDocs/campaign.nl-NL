---
title: Het Transactionele overseinen van de campagne
description: Aan de slag met Transactionele berichten
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1527'
ht-degree: 1%

---

# Aan de slag met Transactioneel overseinen{#send-transactional-messages}

Transactioneel overseinen (het Centrum van het Bericht) is een module van de Campagne die voor het beheren van trekkerberichten wordt ontworpen. Deze meldingen worden gegenereerd op basis van gebeurtenissen die worden geactiveerd via informatiesystemen en kunnen: factuur, bevestiging van bestelling, bevestiging van verzending, wijziging van wachtwoord, kennisgeving van onbeschikbaarheid van product, rekeningoverzicht, aanmaken van websiteaccount, enz.

![](../assets/do-not-localize/speech.png)  Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support){target=&quot;_blank&quot;} om het Transactionele overseinen van de Campagne in uw milieu te vormen.

Transactieberichten worden gebruikt voor het verzenden van:

* meldingen, zoals orderbevestigingen of opnieuw instellen van wachtwoorden, bijvoorbeeld
* een individuele reactie in real time op een klantenactie
* niet-promotionele inhoud

![](../assets/do-not-localize/glass.png) De instellingen voor Transactieberichten worden gedetailleerd in [deze sectie](../config/transactional-msg-settings.md).

![](../assets/do-not-localize/glass.png) Begrijp transactie overseinenarchitectuur op [deze pagina](../architecture/architecture.md#transac-msg-archi).

## Werkingsprincipe voor transactieberichten {#transactional-messaging-operating-principle}

De module van het Overseinen van Adobe Campaign Transactional integreert in een informatiesysteem dat gebeurtenissen terugkeert die in gepersonaliseerde transactionele berichten moeten worden veranderd. Deze berichten kunnen individueel of in partijen via e-mail, SMS of push-berichten worden verzonden.

Stel dat u een bedrijf bent met een website waar uw klanten producten kunnen kopen.

Met Adobe Campaign kunt u een meldingsbericht verzenden naar klanten die producten aan hun winkelwagentje hebben toegevoegd. Wanneer een van hen uw website verlaat zonder door te gaan met hun aankopen (externe gebeurtenis die een Campagne-gebeurtenis activeert), wordt er automatisch een e-mailbericht over het verlaten van de winkelwagen naar hen verzonden (levering van transactiemeldingen).

De belangrijkste stappen om dit in werking te stellen zijn hieronder beschreven:

1. [Een gebeurtenistype maken](#create-event-types).
1. [De berichtsjabloon maken en ontwerpen](#create-message-template). Tijdens deze stap moet u een gebeurtenis koppelen aan uw bericht.
1. [Het bericht testen](#test-message-template).
1. [Publiceer de berichtsjabloon](#publish-message-template).

Zodra u het transactionele berichtmalplaatje ontwierp en publiceerde, als een overeenkomstige gebeurtenis wordt teweeggebracht, worden de relevante gegevens verzonden naar Campagne via PushEvent en PushEvents [SOAP-methoden](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html){target=&quot;_blank&quot;} en de levering wordt naar de beoogde ontvangers verzonden.

## Gebeurtenistypen maken {#create-event-types}

Om ervoor te zorgen dat elke gebeurtenis in een gepersonaliseerd bericht kan worden veranderd, moet u eerst creëren **gebeurtenistypen**.

Wanneer [een berichtsjabloon maken](#create-message-template), selecteert u het type gebeurtenis dat overeenkomt met het bericht dat u wilt verzenden.

>[!CAUTION]
>
>U moet gebeurtenistypen creëren alvorens hen in berichtmalplaatjes te kunnen gebruiken.

Voer de volgende stappen uit om gebeurtenistypen te maken die door Adobe Campaign worden verwerkt:

1. Ga naar de **[!UICONTROL Administration > Platform > Enumerations]** map van de structuur.

1. Selecteren **[!UICONTROL Event type]** in de lijst.

1. Klikken **[!UICONTROL Add]** om een opsommingswaarde te maken. Dit kan een bevestiging zijn van de bestelling, een wijziging van het wachtwoord, een wijziging in de levering van de bestelling, enzovoort.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Elk gebeurtenistype moet overeenkomen met een waarde in het dialoogvenster **[!UICONTROL Event type]** opsomming.

1. Nadat de gespecificeerde lijstwaarden zijn gecreeerd, logoff en terug op uw geval voor de verwezenlijking om efficiënt te zijn.

>[!NOTE]
>
>Meer informatie over gespecificeerde lijsten in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/managing-enumerations.html){target=&quot;_blank&quot;}.

## Een transactiemalplaatje definiëren {#create-message-template}

Elke gebeurtenis kan een gepersonaliseerd bericht teweegbrengen. Hiervoor moet u een berichtsjabloon maken die overeenkomt met elk gebeurtenistype. De malplaatjes bevatten de noodzakelijke informatie voor het personaliseren van het transactiebericht. U kunt malplaatjes ook gebruiken om de berichtvoorproef te testen en proeven te verzenden gebruikend zaadadressen alvorens aan het definitieve doel te leveren.

### De sjabloon maken

Volg onderstaande stappen om een berichtsjabloon te maken:

1. Ga naar de **[!UICONTROL Message Center >Transactional message templates]** in de Adobe Campaign-structuur.
1. Klik in de lijst met transactiemalesjablonen met de rechtermuisknop en selecteer **[!UICONTROL New]** in het vervolgkeuzemenu of klik op de knop **[!UICONTROL New]** boven de lijst met transactiemalusjablonen voor berichten.

   ![](assets/messagecenter_create_model_001.png)

1. Selecteer in het leveringsvenster de leveringssjabloon die geschikt is voor het kanaal dat u wilt gebruiken.

   ![](assets/messagecenter_create_model_002.png)

1. Wijzig indien nodig het label.
1. Selecteer het type gebeurtenis dat overeenkomt met het bericht dat u wilt verzenden. Gebeurtenistypen die bestemd zijn om door Adobe Campaign te worden verwerkt, moeten vooraf worden gemaakt. [Meer informatie](#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >Een gebeurtenistype mag nooit aan meerdere sjablonen worden gekoppeld.

1. Voer een aard en beschrijving in en klik vervolgens op **[!UICONTROL Continue]** om de berichttekst te maken.

### De inhoud maken{#create-message-content}

De definitie van de inhoud van het transactiebericht is hetzelfde als voor alle leveringen in Adobe Campaign. Voor een e-maillevering kunt u bijvoorbeeld inhoud in HTML- of tekstindeling maken, bijlagen toevoegen of het bezorgingsobject aanpassen. [Meer informatie](../start/create-message.md).

>[!CAUTION]
>
>Afbeeldingen in het bericht moeten openbaar toegankelijk zijn. Adobe Campaign biedt geen mechanisme voor het uploaden van afbeeldingen voor transactieberichten.\
>In tegenstelling tot JSSP of webApp, `<%=` heeft geen standaardescape.
>
>U moet alle gegevens die uit de gebeurtenis komen, op de juiste wijze verwijderen. Deze escape is afhankelijk van de manier waarop dit veld wordt gebruikt. Gebruik in een URL bijvoorbeeld encodeURIComponent. U kunt escapeXMLString gebruiken om in de HTML te worden weergegeven.

Zodra u uw berichtinhoud hebt bepaald, kunt u gebeurtenisinformatie in het berichtlichaam integreren en het personaliseren. Gebeurtenisgegevens worden via personalisatietags in de tekst ingevoegd.

![](assets/messagecenter_create_content.png)

* Alle verpersoonlijkingsgebieden komen van de lading.
* Het is mogelijk om één of verscheidene verpersoonlijkingsblokken in een transactiebericht van verwijzingen te voorzien. <!--The block content will be added to the delivery content during the publication to the execution instance.-->

Voer de volgende stappen uit om personalisatietags in te voegen in de tekst van een e-mailbericht:

1. Klik in de berichtsjabloon op het tabblad dat overeenkomt met de e-mailindeling (HTML of tekst).
1. Voer de tekst van het bericht in.
1. Voeg in de tekst de tag in met behulp van de **[!UICONTROL Real time events>Event XML]** menu&#39;s.

   ![](assets/messagecenter_create_custo_1.png)

1. Vul de tag in met de volgende syntaxis: **elementnaam**.@**kenmerknaam** zoals hieronder weergegeven.

   ![](assets/messagecenter_create_custo_2.png)

## Test het transactiemalplaatje van het berichtbericht {#test-message-template}

### Seedadressen toevoegen{#add-seeds}

Een zaadadres laat u een voorproef van uw bericht tonen, een proef, en de personalisatie van het testbericht verzenden alvorens het bericht te verzenden. De zaadadressen zijn verbonden met de levering en kunnen niet voor andere leveringen worden gebruikt.

1. Klik in de sjabloon Transactiebericht op de knop **[!UICONTROL Seed addresses]** en klikt u op de knop **[!UICONTROL Add]** knop.

   ![](assets/messagecenter_create_seed_1.png)

1. Wijs er later een label aan toe voor een eenvoudige selectie en voer vervolgens het beginadres in (afhankelijk van het communicatiekanaal via e-mail of mobiele telefoon).

1. Voer de externe id in: in dit optionele veld kunt u een zakelijke sleutel invoeren (unieke id, naam + e-mail, enz.) Deze instelling geldt voor alle toepassingen op uw website die worden gebruikt om uw profielen te identificeren. Als dit veld ook aanwezig is in de Adobe Campaign-marketingdatabase, kunt u een gebeurtenis vervolgens afstemmen op een profiel in de database.

   ![](assets/messagecenter_create_seed_2.png)

1. Voeg testgegevens in. Zie [deze sectie](#personalization-data).

   ![](assets/messagecenter_create_custo_3.png)

1. Klikken **[!UICONTROL Ok]** ter bevestiging van de oprichting van het zaadadres.

1. Herhaal dit proces om zoveel adressen te maken als u nodig hebt.

   ![](assets/messagecenter_create_seed_6.png)

Zodra de adressen worden gecreeerd, kunt u tot hun voorproef en verpersoonlijking toegang hebben.

<!--

### Add personalization data{#personalization-data}

You can add data in the message template to test transactional message personalization. This will allow you to generate a preview or send a proof. If you install the **Deliverability** module, this data allows you to display a rendering of the messages for various desktop, web or mobile clients.

The purpose of this data is to test your messages before their final delivery. These messages do not coincide with actual data to be processed by Message Center.

However, the XML structure must be identical to that of the event stored in the execution instance, as shown below. 

![](assets/messagecenter_create_custo_4.png)

This information enables you to personalize message content using personalization tags.

1. In the message template, click the **[!UICONTROL Seed addresses]** tab.
1. In the event content, enter the test information in XML format.

   ![](assets/messagecenter_create_custo_3.png)
-->

### Je transactiebericht bekijken{#transactional-message-preview}

Zodra u één of meerdere zaadadressen en het berichtlichaam hebt gecreeerd, kunt u voorproef het bericht en zijn verpersoonlijking controleren.

1. Klik in de berichtsjabloon op de knop **[!UICONTROL Preview]** tab, dan selecteren **[!UICONTROL A seed address]** in de vervolgkeuzelijst.

   ![](assets/messagecenter_preview_1.png)

1. Selecteer het zaadadres eerder wordt gecreeerd om het gepersonaliseerde bericht te tonen dat.

   ![](assets/messagecenter_create_seed_7.png)

### Een proef verzenden

U kunt berichtlevering testen door een bewijs naar een eerder gecreeerd zaadadres te verzenden.

Bij het verzenden van een bewijs wordt hetzelfde proces gebruikt als bij elke levering.

![](../assets/do-not-localize/book.png) Meer informatie over proefdrukken in [Campaign Classic v7-documentatie](https://experienceleague-review.corp.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html#sending-a-proof){target=&quot;_blank&quot;}

Als u echter een bewijs van een transactiebericht wilt verzenden, moet u de volgende bewerkingen uitvoeren:

* Een of meer maken [zaadadressen](#add-seeds) met gegevens van een personalisatietest
* Berichtinhoud maken

Het bewijs verzenden:

1. Klik op de knop **[!UICONTROL Send a proof]** in het leveringsvenster.
1. Analyseer de levering.
1. Corrigeer eventuele fouten en bevestig de levering.

   ![](assets/messagecenter_send_proof_001.png)

1. Controleer of het bericht aan het zaadadres is bezorgd en of de inhoud ervan aan uw configuratie voldoet.

   ![](assets/messagecenter_send_proof_002.png)

In elke sjabloon zijn proefdrukken toegankelijk via de **[!UICONTROL Audit]** tab.

![](assets/messagecenter_send_proof_003.png)

## De sjabloon publiceren {#publish-message-template}

Als de berichtsjabloon is gemaakt<!-- on the control instance--> is voltooid, kunt u het publiceren, waardoor u berichten kunt verzenden die zijn gekoppeld aan realtime- en batchgebeurtenissen.

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>Wanneer u om het even welke veranderingen in een malplaatje aanbrengt, zorg ervoor u het voor deze veranderingen opnieuw publiceert om tijdens de levering van het transactiemelding van berichten effectief te zijn.

1. Ga naar de **[!UICONTROL Message Center > Transactional message templates]** map van de structuur.
1. Selecteer de sjabloon die u wilt publiceren<!--on your execution instances-->.
1. Klik op **[!UICONTROL Publish]**.

   ![](assets/messagecenter_publish_template.png)

Wanneer de publicatie is voltooid, worden zowel berichtsjablonen die moeten worden toegepast op batch- als real-time-type-gebeurtenissen gemaakt in het dialoogvenster **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** map.

![](assets/messagecenter_deployed_model.png)

Als een sjabloon eenmaal is gepubliceerd en de bijbehorende gebeurtenis wordt geactiveerd, Adobe Campaign<!--execution instance--> ontvangt de gebeurtenis, koppelt deze aan de transactiesjabloon en stuurt het bijbehorende transactiemelding naar elke ontvanger.

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## Publicatie van een sjabloon ongedaan maken

Zodra een berichtmalplaatje wordt gepubliceerd <!--on the execution instances-->, kan het niet gepubliceerd zijn.

* Een gepubliceerde sjabloon kan zelfs nog steeds worden opgeroepen als de overeenkomstige gebeurtenis wordt geactiveerd: Als u geen berichtmalplaatje meer gebruikt, wordt het geadviseerd om het unpublish. Dit om te voorkomen dat er per ongeluk een ongewenste transactiemelding wordt verzonden.

   U hebt bijvoorbeeld een berichtsjabloon gepubliceerd die u alleen gebruikt voor kerstcampagnes. Misschien wilt u de publicatie ongedaan maken nadat de kerstperiode is afgelopen en deze volgend jaar opnieuw publiceren.

* U kunt ook geen transactiemalplaatje verwijderen dat de **[!UICONTROL Published]** status. U moet eerst de publicatie ongedaan maken.

Volg onderstaande stappen om de publicatie van een transactiemalplaatje ongedaan te maken.

1. Bladeren naar de **[!UICONTROL Message Center > Transactional message templates]** map.
1. Selecteer de sjabloon die u wilt verwijderen.
1. Klik op **[!UICONTROL Unpublish]**.
1. Klik op **[!UICONTROL Start]**.

![](assets/message-center-unpublish.png)

De status van de transactiemalplaatje verandert terug van **[!UICONTROL Published]** tot **[!UICONTROL Being edited]**.

Zodra de publicatie is voltooid:

* Beide berichtmalplaatjes (die op partij en in real time typegebeurtenissen worden toegepast) worden geschrapt<!-- from each execution instance-->.

   Ze verschijnen niet meer in het dialoogvenster **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]** map.

* Nadat een sjabloon niet is gepubliceerd, kunt u deze verwijderen<!-- from the control instance-->.

   Selecteer dit in de lijst en klik op de knop **[!UICONTROL Delete]** op de rechterbovenhoek van het scherm.
