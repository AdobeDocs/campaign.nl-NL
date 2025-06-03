---
title: Aan de slag met berichten
description: Aan de slag met berichten
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a523e76d-776c-47d3-9c15-34241cee1092
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 6%

---

# Aan de slag met berichten {#gs-ac-msg}

Met Adobe Campaign kunt u kanaalcampagnes verzenden, waaronder e-mails, SMS, pushmeldingen en directe mails, en de doeltreffendheid van deze campagnes meten aan de hand van verschillende speciale rapporten. Deze berichten worden ontworpen en verzonden door leveringen, en kunnen voor elke ontvanger worden gepersonaliseerd.

De kernfuncties omvatten het richten, het bepalen en het personaliseren van berichten, de uitvoering van mededelingen, en de bijbehorende operationele rapporten.

## Gebruiksscenario’s {#gs-ac-delivery}

Als u berichten wilt verzenden, moet u een levering maken. De wijze van de leveringsverwezenlijking hangt van uw gebruiksgeval af.

>[!NOTE]
>
>Wanneer u een levering maakt, moet u een sjabloon selecteren. Voor elk kanaal zijn standaardsjablonen beschikbaar. Leer meer over leveringsmalplaatjes in [ deze pagina ](../send/create-templates.md).

1. **One-shot berichten** - u kunt one-shot berichten naar een publiek verzenden. Leer hoe te om uw eerste bericht in [ te verzenden deze sectie ](create-message.md).

   ![](assets/send-email.png)

1. **Berichten in een marketing campagne** - u kunt berichten in de context van a [ marketing campagne ](campaigns.md) verzenden, een goedkeuringsproces bepalen, hen verzenden en volgen in een geconsolideerd dashboard. Leer hoe in [ deze sectie ](../../automation/campaigns/marketing-campaign-deliveries.md).

   ![](assets/deliveries-in-a-campaign.png)

1. **Berichten in een werkschema** - u kunt berichten via a [ werkschema ](../config/workflows.md) verzenden en uw leveringen automatiseren. Leer hoe in [ deze pagina ](../../automation/workflow/delivery.md).

   ![](assets/send-in-a-wf.png)

1. **teweeggebrachte berichten** - u kunt [ Berichten ](../send/transactional.md) van een gebeurtenis teweegbrengen. Transactioneel overseinen (het Centrum van het Bericht) is de module van de Campagne die voor het beheren van trekkerberichten wordt ontworpen. De stappen om transactionele berichten te vormen en te verzenden zijn gedetailleerd in [ deze pagina ](../send/transactional.md)

## Communicatiekanalen {#gs-channel}

Adobe Campaign v8 wordt geleverd met de onderstaande leveringskanalen. Welke kanalen beschikbaar zijn in uw omgeving is afhankelijk van uw contract. Controleer hiervoor uw licentieovereenkomst.

* **E-mailkanaal**: De e-mailleveringen laten u gepersonaliseerde e-mails naar de doelbevolking verzenden. [Meer informatie](../send/email.md)

* **Mobiele kanalen**: de leveringen op mobiele kanalen laten u gepersonaliseerde berichten op mobiele apparaten naar de doelbevolking verzenden. U kunt [ SMS ](../send/sms/sms.md) verzenden en [ LIJN ](../send/line.md) berichten op mobiles.

* **Mobiel toepassingskanaal**: U kunt Adobe Campaign gebruiken om gepersonaliseerde en gesegmenteerde [ dupberichten ](../send/push.md) op iOS en Android mobiele apparaten, door specifieke apps te verzenden. Nadat configuratie- en integratiestappen zijn uitgevoerd, kunnen iOS- en Android-leveringen worden gemaakt en verzonden met Adobe Campaign. U kunt ook uitgebreide berichten met afbeeldingen of video&#39;s ontwerpen en verzenden naar Android-apparaten.

* **Directe postkanaal**: [ Directe post ](../send/direct-mail.md) is een off-line kanaal dat u toestaat om tot stand te brengen, te personaliseren en een extern dossier te produceren om met uw directe postleveranciers te delen. Gebruik dit kanaal om online en offline kanalen in uw klantenreizen te orkesteren.

  Wanneer u een direct-maillevering voorbereidt, genereert Adobe Campaign een bestand met alle doelprofielen en de gekozen contactinformatie (bijvoorbeeld postadres). U kunt dit bestand vervolgens naar uw directe-mailprovider sturen, die voor de verzending zal zorgen.


* **Andere kanalen**: Adobe Campaign komt ook met een malplaatje van de levering van de Telefoon, dat wordt gebruikt om externe leveringen tot stand te brengen. Als u dit kanaal gebruikt, implementeert u speciale methoden voor het verwerken van uitvoerbestanden. De stappen van de configuratie zijn het zelfde als voor [ Directe postkanaal ](../send/direct-mail.md).

  >[!NOTE]
  >
  >Het telefoonkanaal is geen ingebouwd kanaal. Voor de implementatie ervan moet Adobe Consulting of een Adobe-partner betrokken zijn. Neem contact op met je Adobe-vertegenwoordiger voor meer informatie.

  Voor de leveringen van het type &#39;Overige&#39; wordt een specifieke technische sjabloon gebruikt die geen proces uitvoert: hiermee kunnen ze marketingacties beheren die buiten het Adobe Campaign-platform worden uitgevoerd.

  Dit kanaal heeft geen specifiek mechanisme. Het is een generisch kanaal dat zijn eigen externe rekening heeft die optie, het type van leveringsmalplaatje, en activiteit van het campagnewerkschema verpletteren, enkel zoals een ander communicatiekanaal beschikbaar in Adobe Campaign. Dit kanaal is alleen bedoeld voor beschrijvende doeleinden, bijvoorbeeld om leveringen te definiëren waarvoor u het doel van een campagne die is uitgevoerd in een ander programma dan Adobe Campaign, wilt bijhouden.

## Soorten levering {#types-of-deliveries}

Er zijn drie typen leveringsobjecten in campagne:

### Eén levering {#single-delivery}

A **levering** is een standalone leveringsvoorwerp dat eens wordt uitgevoerd. Het kan worden gedupliceerd, opnieuw worden bereid, maar zolang het in zijn definitieve staat (geannuleerd, gestopt, gebeëindigd) is, kan het niet opnieuw worden gebruikt.

De leveringen kunnen of van de lijst van leveringen, of binnen een werkschema via de activiteit van de a [ Levering ](../../automation/workflow/delivery.md) worden gecreeerd.

Workflows bieden ook specifieke leveringsactiviteiten op basis van het type kanaal dat u wilt gebruiken. Voor meer op deze activiteiten, verwijs naar [ deze sectie ](../../automation/workflow/cross-channel-deliveries.md).

### Terugkerende levering {#recurring-delivery}

A **terugkomende levering** is beschikbaar in de context van een werkschema. Hiermee kunt u telkens een nieuwe levering maken wanneer de activiteit wordt uitgevoerd. Zo voorkomt u dat u een nieuwe levering moet maken voor terugkerende taken. Als u dit soort activiteiten bijvoorbeeld eens per maand uitvoert, krijgt u na een jaar 12 leveringen.

De terugkomende leveringen worden gecreeerd binnen werkschema&#39;s via de [ Terugkomende leveringsactiviteit ](../../automation/workflow/recurring-delivery.md). Een voorbeeld van deze activiteit die wordt gebruikt wordt voorgesteld in deze sectie: [ Creërend een terugkomende levering in een het richten werkschema ](../../automation/workflow/send-a-birthday-email.md).

### Doorlopende levering {#continuous-delivery}

A **ononderbroken levering** is beschikbaar in de context van een werkschema. Het laat u nieuwe ontvangers aan een bestaande levering toevoegen, die vermijdt het moeten een nieuwe levering tot stand brengen telkens als het wordt uitgevoerd.

Als een informatie in de levering verandert (inhoud, naam, enz.), wordt een nieuw leveringsvoorwerp gecreeerd bij de leveringsuitvoering. Als er geen informatie is gewijzigd, wordt hetzelfde leveringsobject opnieuw gebruikt en worden de logbestanden voor levering en bijhouden toegevoegd aan hetzelfde object.

Als voorbeeld, als u dit type van activiteit eens per maand in werking stelt, zult u eindigen met één enkele levering na een jaar (vooropgesteld u geen verandering in de levering).

De ononderbroken leveringen worden gecreeerd binnen werkschema&#39;s via de [ Ononderbroken leveringsactiviteit ](../../automation/workflow/continuous-delivery.md).

## Personalization-mogelijkheden {#personalization}

Berichten van Adobe Campaign kunnen op verschillende manieren worden gepersonaliseerd. [ leer meer over verpersoonlijkingsmogelijkheden ](../send/personalize.md)

U kunt:

* Dynamische personalisatievelden invoegen. [Meer informatie](../send/personalization-fields.md)
* Vooraf gedefinieerde aanpassingsblokken invoegen. [Meer informatie](../send/personalization-blocks.md)
* Voorwaardelijke content maken. [Meer informatie](../send/conditions.md)


## Tracering en monitoring {#gs-tracking-logs}

Het controleren van uw leveringen nadat deze zijn verzonden, is een belangrijke stap om ervoor te zorgen dat uw marketingcampagnes efficiënt zijn en uw klanten bereiken. U kunt controleren na het verzenden van een levering, evenals begrijpen hoe de leveringsmislukkingen en quarantines worden beheerd.

Leer hoe te om uw leveringen in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target="_blank"} te controleren
