---
product: Adobe Campaign
title: Het Transactionele overseinen van de campagne
description: Aan de slag met Transactionele berichten
feature: Overzicht
role: Data Engineer
level: Beginner
source-git-commit: 41ea85bc3c616ed7cdd0718ff3368aab971a5352
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%

---

# Aan de slag met Transactioneel overseinen{#send-transactional-messages}

Transactioneel overseinen (het Centrum van het Bericht) is een module van de Campagne die voor het beheren van trekkerberichten wordt ontworpen. Deze berichten worden geproduceerd van gebeurtenissen die van informatiesystemen teweeggebracht worden, en kunnen zijn: factuur, bevestiging van bestelling, bevestiging van verzending, wijziging van wachtwoord, kennisgeving van onbeschikbaarheid van product, rekeningoverzicht of het maken van websiteaccount, bijvoorbeeld.

[!DNL :speech_balloon:] Als Beheerde gebruiker van Cloud Services,  [contacteer ](../start/campaign-faq.md#support) Adobe om het Transactionele overseinen van de Campagne in uw milieu te installeren en te vormen.

Transactieberichten worden gebruikt voor het verzenden van:

* meldingen, zoals orderbevestigingen of opnieuw instellen van wachtwoorden, bijvoorbeeld
* een individuele reactie in real time op een klantenactie
* niet-promotionele inhoud

[!DNL :bulb:] De instellingen voor het transactiebericht worden in  [deze sectie](../config/transactional-msg-settings.md) beschreven.

[!DNL :bulb:] Begrijp transactie overseinenarchitectuur in  [deze pagina](../dev/architecture.md).

>[!CAUTION]
>
>Voor Transactioneel overseinen is een specifieke licentie vereist. Controleer uw licentieovereenkomst.

## Transactieberichtsjablonen definiëren

Elke gebeurtenis kan een gepersonaliseerd bericht teweegbrengen. Hiervoor moet u een berichtsjabloon maken die overeenkomt met elk gebeurtenistype. De malplaatjes bevatten de noodzakelijke informatie voor het personaliseren van het transactiebericht. U kunt malplaatjes ook gebruiken om de berichtvoorproef te testen en proeven te verzenden gebruikend zaadadressen alvorens aan het definitieve doel te leveren.

## De sjabloon maken

Volg onderstaande stappen om een berichtsjabloon te maken:

1. Ga naar de **[!UICONTROL Message Center >Transactional message templates]** omslag in de boom van Adobe Campaign.
1. Klik in de lijst met transactiemalplaatjes met de rechtermuisknop en selecteer **[!UICONTROL New]** in het vervolgkeuzemenu of klik op de knop **[!UICONTROL New]** boven de lijst met transactionele berichtsjablonen.

   ![](assets/messagecenter_create_model_001.png)

1. Selecteer in het leveringsvenster de leveringssjabloon die geschikt is voor het kanaal dat u wilt gebruiken.

   ![](assets/messagecenter_create_model_002.png)

1. Wijzig indien nodig het label.
1. Selecteer het type gebeurtenis dat overeenkomt met het bericht dat u wilt verzenden.

   ![](assets/messagecenter_create_model_003.png)

   Gebeurtenistypen die bestemd zijn om door Adobe Campaign te worden verwerkt, moeten in de besturingsinstantie door Adobe worden gemaakt.

   >[!NOTE]
   >
   >Een gebeurtenistype mag nooit aan meerdere sjablonen worden gekoppeld.

1. Ga een aard en een beschrijving in, dan klik **[!UICONTROL Continue]** om het berichtlichaam tot stand te brengen. Zie [Berichtinhoud maken](#create-message-content).

## De inhoud maken{#create-message-content}

De definitie van de inhoud van het transactiebericht is hetzelfde als voor alle leveringen in Adobe Campaign. U kunt bijvoorbeeld voor een e-maillevering inhoud in HTML- of tekstindeling maken, bijlagen toevoegen of het bezorgingsobject aanpassen. Raadpleeg [deze sectie](../start/create-message.md) voor meer informatie.

>[!CAUTION]
>
>Afbeeldingen in het bericht moeten openbaar toegankelijk zijn. Adobe Campaign biedt geen mechanisme voor het uploaden van afbeeldingen voor transactieberichten.\
>In tegenstelling tot JSSP of webApp heeft `<%=` geen standaardescaping.
>
>U moet alle gegevens die uit de gebeurtenis komen, op de juiste wijze verwijderen. Deze escape is afhankelijk van de manier waarop dit veld wordt gebruikt. Gebruik in een URL bijvoorbeeld encodeURIComponent. U kunt escapeXMLString gebruiken om in de HTML te worden weergegeven.

Zodra u uw berichtinhoud hebt bepaald, kunt u gebeurtenisinformatie in het berichtlichaam integreren en het personaliseren. Gebeurtenisgegevens worden via personalisatietags in de tekst ingevoegd.

![](assets/messagecenter_create_content.png)

* Alle verpersoonlijkingsgebieden komen van de lading.
* Het is mogelijk om één of verscheidene verpersoonlijkingsblokken in een transactiebericht van verwijzingen te voorzien. De blokinhoud wordt tijdens de publicatie aan de uitvoeringsinstantie toegevoegd aan de leveringsinhoud.

Voer de volgende stappen uit om personalisatietags in te voegen in de tekst van een e-mailbericht:

1. Klik in de berichtsjabloon op het tabblad dat overeenkomt met de e-mailindeling (HTML of tekst).
1. Voer de tekst van het bericht in.
1. Voeg de tag in de tekst in met de menu&#39;s **[!UICONTROL Real time events>Event XML]**.

   ![](assets/messagecenter_create_custo_1.png)

1. Vul de tag in met de volgende syntaxis: **elementnaam**.@**kenmerknaam** zoals hieronder getoond.

   ![](assets/messagecenter_create_custo_2.png)

## Seedadressen toevoegen{#add-seeds}

Een zaadadres laat u een voorproef van uw bericht tonen, een proef, en de personalisatie van het testbericht verzenden alvorens het bericht te verzenden. De zaadadressen zijn verbonden met de levering en kunnen niet voor andere leveringen worden gebruikt.

1. Klik in de transactiemalplaatje van het bericht, op **[!UICONTROL Seed addresses]** tabel, dan klik **[!UICONTROL Add]** knoop.

   ![](assets/messagecenter_create_seed_1.png)

1. Wijs er later een label aan toe voor een eenvoudige selectie en voer vervolgens het beginadres in (afhankelijk van het communicatiekanaal via e-mail of mobiele telefoon).

1. Voer de externe id in: in dit optionele veld kunt u een zakelijke sleutel invoeren (unieke id, naam + e-mail, enz.) Deze instelling geldt voor alle toepassingen op uw website die worden gebruikt om uw profielen te identificeren. Als dit veld ook aanwezig is in de Adobe Campaign-marketingdatabase, kunt u een gebeurtenis vervolgens afstemmen op een profiel in de database.

   ![](assets/messagecenter_create_seed_2.png)

1. Voeg testgegevens in. Zie [deze sectie](#personalization-data).

   ![](assets/messagecenter_create_custo_3.png)

1. Klik **[!UICONTROL Ok]** om de verwezenlijking van het zaadadres te bevestigen.

1. Herhaal dit proces om zoveel adressen te maken als u nodig hebt.

   ![](assets/messagecenter_create_seed_6.png)

Zodra de adressen worden gecreeerd, kunt u tot hun voorproef en verpersoonlijking toegang hebben.

## Aanpassingsgegevens toevoegen{#personalization-data}

U kunt gegevens in het berichtmalplaatje toevoegen om transactionele berichtverpersoonlijking te testen. Op deze manier kunt u een voorbeeld genereren of een proefdruk verzenden. Als u de **Deliverability** module installeert, staat dit gegeven u toe om een teruggave van de berichten voor diverse Desktop, Web of mobiele cliënten te tonen.

Het doel van deze gegevens is om uw berichten vóór hun definitieve levering te testen. Deze berichten vallen niet samen met werkelijke gegevens die door Message Center moeten worden verwerkt. De XML-structuur moet echter gelijk zijn aan die van de gebeurtenis die in de uitvoeringsinstantie is opgeslagen, zoals hieronder wordt weergegeven.

![](assets/messagecenter_create_custo_4.png)

Met deze informatie kunt u de inhoud van berichten personaliseren met personalisatietags.

1. Klik in de berichtsjabloon op het tabblad **[!UICONTROL Seed addresses]**.
1. Voer in de inhoud van de gebeurtenis de testinformatie in XML-indeling in.

   ![](assets/messagecenter_create_custo_3.png)

## Bekijk uw transactiebericht{#transactional-message-preview}

Zodra u één of meerdere zaadadressen en het berichtlichaam hebt gecreeerd, kunt u voorproef het bericht en zijn verpersoonlijking controleren.

1. Klik in de berichtsjabloon op de tab **[!UICONTROL Preview]** en selecteer **[!UICONTROL A seed address]** in de vervolgkeuzelijst.

   ![](assets/messagecenter_preview_1.png)

1. Selecteer het zaadadres eerder wordt gecreeerd om het gepersonaliseerde bericht te tonen dat.

   ![](assets/messagecenter_create_seed_7.png)

## Een proef verzenden

U kunt berichtlevering testen door een bewijs naar een eerder gecreeerd zaadadres te verzenden.

Bij het verzenden van een bewijs wordt hetzelfde proces gebruikt als bij elke levering.

[!DNL :arrow_upper_right:] Meer informatie over proefdrukken vindt u in  [Campaign Classic v7-documentatie]((https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html))

Als u echter een bewijs van een transactiebericht wilt verzenden, moet u de volgende bewerkingen uitvoeren:

* Creeer één of meerdere [zaadadressen](#add-seeds) met de gegevens van de verpersoonlijkingstest
* Berichtinhoud maken

Het bewijs verzenden:

1. Klik op de knop **[!UICONTROL Send a proof]** in het leveringsvenster.
1. Analyseer de levering.
1. Corrigeer eventuele fouten en bevestig de levering.

   ![](assets/messagecenter_send_proof_001.png)

1. Controleer of het bericht aan het zaadadres is bezorgd en of de inhoud ervan aan uw configuratie voldoet.

   ![](assets/messagecenter_send_proof_002.png)

In elke sjabloon kunt u proefdrukken openen via het tabblad **[!UICONTROL Audit]**.

![](assets/messagecenter_send_proof_003.png)

### De sjabloon publiceren

Wanneer het berichtmalplaatje op de controleinstantie wordt gecreeerd volledig is, kunt u het publiceren. Dit proces zal het op alle uitvoeringsinstanties ook publiceren.

>[!NOTE]
>
>Wanneer het publiceren van transactiemalplaatjes van het berichtbericht, worden de typologische regels ook automatisch gepubliceerd op de uitvoeringsinstanties.

Met Publicatie kunt u automatisch twee berichtsjablonen maken op de uitvoeringsinstanties. Hiermee kunt u berichten verzenden die zijn gekoppeld aan realtime- en batchgebeurtenissen.

>[!CAUTION]
>
>Wanneer u om het even welke veranderingen in een malplaatje aanbrengt, zorg ervoor u het voor deze veranderingen opnieuw publiceert om tijdens de levering van het transactiemelding van berichten effectief te zijn.

1. Ga voor de besturingsinstantie naar de map **[!UICONTROL Message Center > Transactional message templates]** van de boomstructuur.
1. Selecteer de sjabloon die u op de uitvoeringsinstanties wilt publiceren.
1. Klik op **[!UICONTROL Publish]**.

   ![](assets/messagecenter_publish_template.png)

Wanneer de publicatie is voltooid, worden zowel berichtsjablonen die moeten worden toegepast op batchgebeurtenissen als realtime-typegebeurtenissen gemaakt in de structuur van de productieinstantie in de map **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]**.

![](assets/messagecenter_deployed_model.png)

Zodra een malplaatje wordt gepubliceerd, als de overeenkomstige gebeurtenis wordt teweeggebracht, zal de uitvoeringsinstantie de gebeurtenis ontvangen, zal het verbinden met het transactiesjabloon en het overeenkomstige transactiemelding naar elke ontvanger verzenden.

>[!NOTE]
>
>Als u een bestaand veld van de transactiemplate voor berichten, zoals het adres van de afzender, vervangt door een lege waarde, wordt het corresponderende veld op de uitvoeringsinstantie(s) niet bijgewerkt wanneer het transactiemelding opnieuw wordt gepubliceerd. De vorige waarde blijft in de selectie staan.
>
>Als u echter een niet-lege waarde toevoegt, wordt het desbetreffende veld op de gebruikelijke wijze na de volgende publicatie bijgewerkt.


### Publicatie van een sjabloon ongedaan maken

Zodra een berichtmalplaatje op de uitvoeringsinstanties wordt gepubliceerd, kan het unpublished.

* Een gepubliceerde sjabloon kan zelfs nog steeds worden opgeroepen als de overeenkomstige gebeurtenis wordt geactiveerd: Als u geen berichtmalplaatje meer gebruikt, wordt het geadviseerd om het unpublish. Dit om te voorkomen dat er per ongeluk een ongewenste transactiemelding wordt verzonden.

   U hebt bijvoorbeeld een berichtsjabloon gepubliceerd die u alleen gebruikt voor kerstcampagnes. Misschien wilt u de publicatie ongedaan maken nadat de kerstperiode is afgelopen en deze volgend jaar opnieuw publiceren.

* U kunt ook geen transactiemalplaatje verwijderen dat de status **[!UICONTROL Published]** heeft. U moet eerst de publicatie ongedaan maken.

Volg onderstaande stappen om de publicatie van een transactiemalplaatje ongedaan te maken.

1. Ga voor de besturingsinstantie naar de map **[!UICONTROL Message Center > Transactional message templates]** van de boomstructuur.
1. Selecteer de sjabloon die u wilt verwijderen.
1. Klik op **[!UICONTROL Unpublish]**.
1. Klik op **[!UICONTROL Start]**.

![](assets/message-center-unpublish.png)

De status van de transactioneleberichtsjabloon verandert weer van **[!UICONTROL Published]** in **[!UICONTROL Being edited]**.

Zodra de publicatie is voltooid:

* Beide berichtmalplaatjes (die op partij en real-time typegebeurtenissen worden toegepast) worden geschrapt van elke uitvoeringsinstantie.

   Zij verschijnen niet meer in **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]** omslag.

* Zodra een malplaatje unpublished is, kunt u het van de controleinstantie schrappen.

   Selecteer dit in de lijst en klik op de knop **[!UICONTROL Delete]** rechtsboven in het scherm.
