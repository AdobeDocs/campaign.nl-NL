---
title: Aan de slag met berichten
description: Aan de slag met berichten
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: fb0b7dbeae1d083935da91bbe50a711ce5f47b7e
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 5%

---

# Aan de slag met berichten{#gs-ac-audiences}

Met Adobe Campaign kunt u kanaalcampagnes verzenden, waaronder e-mails, SMS, pushmeldingen en directe mails, en de doeltreffendheid van deze campagnes meten aan de hand van verschillende speciale rapporten. Deze berichten worden ontworpen en verzonden door leveringen, en kunnen voor elke ontvanger worden gepersonaliseerd.

De kernfuncties omvatten het richten, het bepalen en het personaliseren van berichten, de uitvoering van mededelingen, en de bijbehorende operationele rapporten. Het belangrijkste functionele toegangspunt is de leveringsmedewerker. Dit toegangspunt leidt tot meerdere mogelijkheden die door Adobe Campaign worden gedekt.

Adobe Campaign v8 wordt geleverd met de volgende leveringskanalen:

* **Email channel**: Met e-mailleveringen kunt u persoonlijke e-mails sturen naar de doelgroep. [Meer informatie](#gs-channel-email)

* **Mobiele kanalen**: Met leveringen op mobiele kanalen kunt u persoonlijke berichten op mobiele apparaten naar de doelgroep sturen. [Meer informatie](#gs-channel-sms)

* **Mobiel toepassingskanaal**: met de levering van mobiele apps kunt u meldingen verzenden naar iOS en Android-apparaten. [Meer informatie](#gs-channel-push)

* **Direct mailkanaal**: Met direct mail kunt u een extractiebestand genereren dat gegevens over de doelpopulatie bevat. [Meer informatie](#gs-channel-direct)


  Andere kanalen worden beschreven op [deze sectie](#other-channels).

  >[!NOTE]
  >
  >Het aantal beschikbare kanalen is afhankelijk van uw contract. Controleer hiervoor uw licentieovereenkomst.

## Kies uw kanaal{#gs-channel}

### Email channel {#gs-channel-email}

De [Email channel](../send/direct-mail.md) is een van de kernkanalen in Adobe Campaign, zodat u persoonlijke e-mails kunt plannen en verzenden naar specifieke doelgroepen.

U kunt verschillende typen e-mailberichten verzenden:

* E-mailberichten voor één verzending: e-mails die u één keer naar een bepaald doel kunt verzenden. Deze worden gewoonlijk gebruikt om een specifieke inhoud te promoten die maar één keer wordt voorbereid en verzonden (nieuwsbrief, promotiemail, enz.).
* Herhalende e-mails: in een campagne verzendt u regelmatig dezelfde e-mail en aggregeert u elke verzending en de bijbehorende rapporten op gezette tijden. Dezelfde e-mail wordt verzonden, maar doorgaans naar een ander doel, op basis van het in aanmerking komende doel voor de dag van de verzending. Een veelvoorkomend voorbeeld is een e-mailbericht voor verjaardagen. Raadpleeg voor meer informatie hierover [Terugkerende leveringen](../../automation/workflow/recurring-delivery.md).
* Transactiee-mails: eenheidse e-mails die worden geactiveerd op basis van het gedrag van uw klanten. Zie [Transactieberichten](../send/transactional.md).

Raadpleeg Adobe Campaign Classic voor meer informatie over het gebruik en de aanbevelingen van de levering [Best practices voor levering](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"}

Raadpleeg voor meer informatie over de verschillende typen leveringen [deze sectie](#types-of-deliveries).

### Mobiel kanaal {#gs-channel-sms}

Met Adobe Campaign kunt u leveren [SMS](../send/sms.md) en [REGEL](../send/line.md) berichten op mobiele apparaten.

Voor SMS-berichten kunt u alleen in tekstindeling berichten maken, wijzigen en personaliseren. Je kunt ook een voorbeeld van je SMS-berichten bekijken voordat ze worden verzonden.

Voor lijnberichten kunt u tekst of afbeeldingen en koppelingen verzenden.

Als u SMS- of lijnberichten wilt verzenden naar een mobiele telefoon die u nodig hebt:

* Een externe account geconfigureerd op de **[!UICONTROL Mobile (SMS)]** of op **[!UICONTROL LINE]** kanaal.
* Een SMS- of REGELS-leveringssjabloon die correct is gekoppeld aan deze externe account.


### Push-meldingskanaal {#gs-channel-push}

Met Adobe Campaign kunt u persoonlijke en gesegmenteerde gegevens verzenden [pushmeldingen](../send/push.md) op mobiele iOS- en Android-apparaten, via specifieke apps. Nadat configuratie- en integratiestappen zijn uitgevoerd, kunnen iOS- en Android-leveringen worden gemaakt en verzonden met Adobe Campaign. U kunt ook veelzijdige meldingen met afbeeldingen of video&#39;s ontwerpen en verzenden naar Android-apparaten.

### Direct mailkanaal {#gs-channel-direct}

[Directe post](../send/direct-mail.md) is een offlinekanaal waarmee u een extern bestand kunt maken, personaliseren en genereren dat u met uw direct-mailproviders kunt delen. Gebruik dit kanaal om online en offline kanalen in uw klantenreizen te orkesteren.

Wanneer u een direct-maillevering voorbereidt, genereert Adobe Campaign een bestand met alle doelprofielen en de gekozen contactinformatie (bijvoorbeeld postadres). U kunt dit bestand vervolgens naar uw directe-mailprovider sturen, die voor de verzending zal zorgen.


### Andere kanalen {#other-channels}

Adobe Campaign wordt ook geleverd met een sjabloon voor telefonische levering, die wordt gebruikt om externe leveringen te maken. Als u dit kanaal gebruikt, implementeert u speciale methoden voor het verwerken van uitvoerbestanden. Configuratiestappen zijn hetzelfde als voor [Direct mailkanaal](../send/direct-mail.md).

>[!NOTE]
>
>Het telefoonkanaal is geen ingebouwd kanaal. Voor de implementatie ervan is overleg met de Adobe of betrokkenheid van een Adobe-partner vereist. Neem contact op met uw Adobe voor meer informatie.

Voor de leveringen van het type &#39;Overige&#39; wordt een specifieke technische sjabloon gebruikt die geen proces uitvoert: hiermee kunnen ze marketingacties beheren die buiten het Adobe Campaign-platform worden uitgevoerd.

Dit kanaal heeft geen specifiek mechanisme. Het is een generisch kanaal dat zijn eigen externe rekening heeft die optie, het type van leveringsmalplaatje, en activiteit van het campagnewerkschema verpletteren, enkel zoals een ander communicatiekanaal beschikbaar in Adobe Campaign. Dit kanaal is alleen bedoeld voor beschrijvende doeleinden, bijvoorbeeld om leveringen te definiëren waarvoor u het doel van een campagne die is uitgevoerd in een ander programma dan Adobe Campaign, wilt bijhouden.

## Kies het type levering {#types-of-deliveries}

Er zijn drie typen leveringsobjecten in campagne:

### Eén levering {#single-delivery}

A **bezorging** is een zelfstandig leveringsobject dat één keer wordt uitgevoerd. Het kan worden gedupliceerd, opnieuw worden bereid, maar zolang het in zijn definitieve staat (geannuleerd, gestopt, gebeëindigd) is, kan het niet opnieuw worden gebruikt.

Leveringen kunnen worden gemaakt op basis van de lijst met leveringen of binnen een workflow via een [Aflevering](../../automation/workflow/delivery.md) activiteit.

Workflows bieden ook specifieke leveringsactiviteiten op basis van het type kanaal dat u wilt gebruiken. Raadpleeg voor meer informatie over deze activiteiten [deze sectie](../../automation/workflow/cross-channel-deliveries.md).

### Terugkerende levering {#recurring-delivery}

A **terugkerende levering** is beschikbaar in de context van een werkstroom. Hiermee kunt u telkens een nieuwe levering maken wanneer de activiteit wordt uitgevoerd. Zo voorkomt u dat u een nieuwe levering moet maken voor terugkerende taken. Als u dit soort activiteiten bijvoorbeeld eens per maand uitvoert, krijgt u na een jaar 12 leveringen.

Terugkerende leveringen worden binnen workflows gemaakt via de [Terugkerende leveringsactiviteit](../../automation/workflow/recurring-delivery.md). Een voorbeeld van deze activiteit die wordt gebruikt wordt voorgesteld in deze sectie: [Een terugkerende levering maken in een doelworkflow](../../automation/workflow/send-a-birthday-email.md).

### Doorlopende levering {#continuous-delivery}

A **continue levering** is beschikbaar in de context van een werkstroom. Het laat u nieuwe ontvangers aan een bestaande levering toevoegen, die vermijdt het moeten een nieuwe levering tot stand brengen telkens als het wordt uitgevoerd.

Als een informatie in de levering verandert (inhoud, naam, enz.), wordt een nieuw leveringsvoorwerp gecreeerd bij de leveringsuitvoering. Als er geen informatie is gewijzigd, wordt hetzelfde leveringsobject opnieuw gebruikt en worden de logbestanden voor levering en bijhouden toegevoegd aan hetzelfde object.

Als voorbeeld, als u dit type van activiteit eens per maand in werking stelt, zult u eindigen met één enkele levering na een jaar (vooropgesteld u geen verandering in de levering).

Doorlopende leveringen worden binnen workflows gemaakt via de [Continue leveringsactiviteit](../../automation/workflow/continuous-delivery.md).


## Geef op hoe berichten moeten worden verzonden{#gs-send-msg}

Nadat u het bericht hebt gemaakt en de inhoud ervan hebt ontworpen en getest, kunt u kiezen hoe u het bericht wilt verzenden. De campagne biedt een reeks mogelijkheden aan:

* Handmatig berichten verzenden naar het hoofddoel

  ![](assets/send-email.png)

  Leer hoe berichten worden verzonden in [deze sectie](../send/send.md)

* Berichten verzenden die aan een [marketingcampagne](campaigns.md)

  ![](assets/deliveries-in-a-campaign.png)

  Leer hoe u berichten kunt verzenden in het kader van een campagne in [deze sectie](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html){target="_blank"}

* Verzend berichten via [werkstroom](../config/workflows.md)

  ![](assets/send-in-a-wf.png)

  Leer hoe u e-mailleveringen kunt automatiseren in [deze pagina](../../automation/workflow/delivery.md)

* [Berichten activeren](../send/transactional.md) van een gebeurtenis

  Transactioneel overseinen (het Centrum van het Bericht) is de module van de Campagne die voor het beheren van trekkerberichten wordt ontworpen.

  Meer informatie over de mogelijkheid van transactieberichten vindt u in [deze sectie](../architecture/architecture.md#transac-msg-archi)

  De stappen om transactieberichten te vormen en te verzenden zijn gedetailleerd in [deze pagina](../send/transactional.md)

* Uw berichten plannen

  ![](assets/schedule-send.png)

  Leer hoe u het verzenden van uw leveringen kunt plannen in [deze pagina](../send/configure-and-send.md)

  Zie ook dit [Hoofd-kleine letter gebruiken: leer hoe je een verjaardagsbericht plant en verzend](../../automation/workflow/send-a-birthday-email.md)


## Aanpassing toevoegen{#personalization}

Berichten van Adobe Campaign kunnen op verschillende manieren worden gepersonaliseerd. [Meer informatie over personalisatiemogelijkheden](../send/personalize.md)

U kunt:

* Dynamische personalisatievelden invoegen. [Meer informatie](../send/personalization-fields.md)
* Vooraf gedefinieerde aanpassingsblokken invoegen. [Meer informatie](../send/personalization-blocks.md)
* Voorwaardelijke content maken. [Meer informatie](../send/conditions.md)


## Logbestanden voor aflevering en bijhouden{#gs-tracking-logs}

Het controleren van uw leveringen nadat deze zijn verzonden, is een belangrijke stap om ervoor te zorgen dat uw marketingcampagnes efficiënt zijn en uw klanten bereiken. U kunt controleren na het verzenden van een levering, evenals begrijpen hoe de leveringsmislukkingen en quarantines worden beheerd.

Leer hoe u uw leveringen kunt controleren in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target="_blank"}

