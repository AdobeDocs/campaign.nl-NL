---
title: Testprofielen maken in campagne
description: Leer testprofielen maken en beheren in Adobe Campaign
feature: Audiences, Profiles, Seed Address, Proofs
role: User
level: Beginner
exl-id: 878b5963-100c-4dd7-97a0-c59a62c493b1
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 0%

---

# Testprofielen maken en beheren {#create-test-profiles}

## Wat is een zaadadres? {#gs-seeds}

Testprofielen worden gemaakt als beginadressen. Ze worden gebruikt om ontvangers aan te wijzen die niet voldoen aan de gedefinieerde doelcriteria. Met zaadadressen kunt u de personalisatie en rendering voorvertonen en testen voordat u de levering verzendt, door ze proefdrukken te sturen.

De zaadadressen hebben de volgende voordelen:

* Willekeurige vervanging van velden door gegevens uit ontvangende profielen: hiermee kunt u alleen het e-mailadres invoeren, bijvoorbeeld in de sectie met het zaadadres, en Campagne automatisch de andere velden van het profiel laten invullen. Leer meer in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html) {target="_blank"}.
* Wanneer u een workflow met functies voor gegevensbeheer gebruikt, kunnen de aanvullende gegevens die in leveringen worden verwerkt, op het niveau van het zaadadres worden ingevoerd om waarden af te dwingen: dit verlaagt de vervanging van willekeurige waarden.
* Zaadadressen worden automatisch uitgesloten van rapporten over de volgende leveringsstatistieken: **[!UICONTROL Clicks]**, **[!UICONTROL Opens]**, **[!UICONTROL Unsubscriptions]** .

De zaadadressen worden toegevoegd aan het doel van leveringen door worden ingevoerd of door in de levering of de campagne direct worden gecreeerd.

>[!NOTE]
>
>De zaadadressen worden niet gecreeerd in de ontvangers lijst, maar in een afzonderlijke lijst. Als u de lijst van ontvangers met nieuwe gegevens uitbreidt, moet u de lijst van zaadadressen evenals met de zelfde gegevens uitbreiden. Anders, zullen zij uitgebreide gebieden niet in aanmerking worden genomen voor zaadadressen.
>
>Een voorbeeld van hoe te om de zaadadreslijst uit te breiden wordt voorgesteld in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html) {target="_blank"}.

## Seedadressen maken

Zaadadressen worden niet beheerd via standaardprofielen en -doelen, maar in een speciaal knooppunt van de Adobe Campaign Explorer: **[!UICONTROL Resources > Campaign management > Seed addresses]** . U kunt submappen maken om de zaadadressen te ordenen.

Met Adobe Campaign kunt u ook zaadadressjablonen maken die worden geïmporteerd in leveringen of campagnes en die worden aangepast aan de specifieke behoeften van de desbetreffende leveringen en campagnes. Verwijs naar [ zaadadresmalplaatjes ](#creating-seed-address-templates) creëren.

### Adressen definiëren {#defining-addresses}

Voer de volgende stappen uit om zaadadressen te maken:

1. Klik op de knop **[!UICONTROL New]** boven de lijst met adressen.
1. Voer in de overeenkomende velden op het tabblad **[!UICONTROL Recipient]** de gegevens in die zijn gekoppeld aan het adres. De beschikbare velden komen overeen met de standaardvelden in de profielen van de ontvangers (nms:tabel van de ontvanger): naam, voornaam, e-mail, enz.

   >[!NOTE]
   >
   >Het label van het adres wordt automatisch ingevuld met de achternaam en voornaam die u hebt gedefinieerd.
   >
   >U hoeft niet alle velden van elk tabblad in te voeren wanneer u een zaadadres maakt. Ontbrekende personalisatie-elementen worden willekeurig ingevoerd tijdens de leveringsanalyse.

1. Voer op het tabblad **[!UICONTROL Address fields]** de waarden in die u tijdens de analysefase in de **[!UICONTROL nms:broadLog]** -tabel wilt invoegen in de leveringslogboeken.

1. Voer op het tabblad **[!UICONTROL Additional data]** de aanpassingsgegevens in die worden gebruikt voor de leveringen die in de workflows voor gegevensbeheer zijn gemaakt en waaraan u een specifieke waarde wilt toewijzen.

   Controleer of er aanvullende doelgegevens zijn gedefinieerd met een alias, beginnend met &#39;@&#39; in de **[!UICONTROL Enrichment]** -werkstroomactiviteit. Anders, zult u hen niet behoorlijk met uw zaadadressen in uw leveringsactiviteit kunnen gebruiken.

### Sjablonen voor zaadadressen maken {#creating-seed-address-templates}

U kunt adressjablonen maken die voor elke levering kunnen worden geïmporteerd en gewijzigd. Het proces is het zelfde als wanneer het bepalen van een nieuw zaadadres. Het enige verschil is dat de adressen van zaadadresmalplaatjes in een &quot;Malplaatje&quot;typemap moeten worden opgeslagen.

### Adressen voor directe postzendingen {#direct-mail-seed-addresses}

Voor [ directe postleveringen ](../send/direct-mail.md), worden de zaadadressen toegevoegd tijdens extractie en in het outputdocument gemengd.

Voor direct-mailleveringen moet de indeling van het extractiebestand voldoen aan de volgende beperkingen:

* De optie **[!UICONTROL Handle groupings (GROUP BY+HAVING)]** mag niet worden gebruikt.

* Als elementverzamelingen worden geëxtraheerd, hebben deze velden een lege waarde voor de zaadadressen, tenzij de optie **[!UICONTROL Single row (expert user)]** is geselecteerd.

## Voeg zaadadressen in een levering toe{#seed-addresses-in-a-delivery}

Als u specifieke zaadadressen voor een levering wilt toevoegen, klikt u op de koppeling **[!UICONTROL To]** en selecteert u vervolgens de tab **[!UICONTROL Seed addresses]** .

Er zijn drie mogelijke invoegmodi:

1. Voer enkele zaadadressen in.  Klik hiertoe op de knop **[!UICONTROL Add]** en definieer de inhoud van de adresvelden. Herhaal dit voor elk adres.

1. De invoer [ malplaatjes van het zaadadres ](#creating-seed-address-template) en past hen aan uw behoeften aan. Klik hiertoe op de koppeling **[!UICONTROL Import seed templates...]** en selecteer de map die de adressjablonen bevat.

   Indien nodig kunt u dubbelklikken op de knoppen **[!UICONTROL Detail...]** nadat u deze hebt toegevoegd om de inhoud van elk adres aan te passen.

1. Creeer een voorwaarde om dynamisch de controleadressen te selecteren die moeten worden opgenomen. Klik hiertoe op de koppeling **[!UICONTROL Edit the dynamic condition...]** en voer vervolgens de selectieparameters voor het zaadadres in. Bijvoorbeeld, kon u alle zaadadressen omvatten in een specifieke omslag, of zaadadressen die tot een specifieke afdeling van uw organisatie behoren.

   Een voorbeeld van dit wordt voorgesteld in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html) {target="_blank"}.

Voor leveringen kunt u ook de manier aanpassen waarop adressen worden ingevoegd in het extractiebestand. Deze worden standaard ingevoegd in de sorteervolgorde van het uitvoerbestand, maar u kunt ervoor kiezen ze aan het einde of het begin van het bestand in te voegen, of willekeurig onder de ontvangers van het hoofddoel.

## zaadadressen toevoegen in een campagne {#seed-addresses-in-a-campaign}

Als u zaadadressen wilt toevoegen aan een doel voor een campagne, selecteert u de bewerking en klikt u op het tabblad **[!UICONTROL Edit]** .

Klik op de koppeling **[!UICONTROL Advanced campaign settings...]** en vervolgens op de tab **[!UICONTROL Seed addresses]** . De zaadadressen die van de campagne worden opgenomen worden toegevoegd aan het doel van elke levering in de campagne.

## Zaadadressen en aangepaste tabel {#using-an-external-recipient-table}

Als de leveringstabel een externe lijst is, zult u extra configuraties moeten maken. Het schema **[!UICONTROL nms:seedmember]** moet worden uitgebreid. Er wordt een tabblad toegevoegd aan het zaadadres om de juiste velden te definiëren

In dit geval, om zaadadressen aan de levering toe te voegen, ga de aangewezen gebieden direct in het passende lusje in, of voer de adresmalplaatjes in.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->
