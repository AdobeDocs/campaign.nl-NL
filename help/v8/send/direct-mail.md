---
title: Directe e-mails verzenden met Adobe Campaign
description: Ga aan de slag met direct mail in Campagne
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 2%

---

# Direct-mailleveringen maken

Met Direct mail kunt u een extractiebestand genereren dat gegevens over de doelpopulatie bevat. U kunt dit dossier met de leverancier dan delen die berichten aan de doelpopulaties zal leveren.

De volgende stappen voor het genereren van het bestand zijn:

1. De levering maken

   Creeer direct postlevering die op het malplaatje wordt gebaseerd. U kunt de **[!UICONTROL Deliver by direct mail (paper)]** ingebouwde sjabloon.

   Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html?lang=nl-NL){target="_blank"}

1. De doelgroep definiëren

   De profielen van ontvangers moeten ten minste hun naam en postadres bevatten.

   Postadressen zijn berekende velden. Een adres kan standaard maximaal zes regels bevatten: de eerste regel bevat de voornaam en achternaam, de volgende regels bevatten het postadres (weg enz.) en de laatste regel bevat de postcode en de stad of stad. De definitie van het standaard berekende postadresgebied kan in nms worden herzien:ontvangend schema.

   Een adres wordt als volledig beschouwd als de naam, het gebied van de code van ZIP/Postal, en stad/stad gebieden niet leeg zijn. Ontvangers met onvolledige adressen worden uitgesloten van directe mailleveringen.

   Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=nl-NL){target="_blank"}

1. De inhoud van het bestand definiëren

   Gebruik de extractietovenaar om de informatie (kolommen) te bepalen die in het outputdossier moet worden uitgevoerd.

   Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html?lang=nl-NL){target="_blank"}

1. De levering valideren

   Controleer het resultaat van de analyse en de inhoud van het uitvoerbestand.

   Meer informatie in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html?lang=nl-NL){target="_blank"}

   In het kader van een marketingcampagne wordt op de extractiedatum het extractiebestand gemaakt. U kunt de inhoud van het geëxtraheerde bestand weergeven, goedkeuren of de indeling wijzigen en de extractie indien nodig opnieuw starten. Zodra het dossier is goedgekeurd, kunt u het bericht e-mail naar de router verzenden. Meer informatie in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=nl-NL)

1. De levering starten

   Nadat u het extractiebestand hebt gevalideerd, klikt u op **Levering bevestigen** Met een bevestigingsbericht kunt u de levering starten.

   De bevestiging start de gegevensextractie in het opgegeven bestand.

   In het kader van een marketingcampagne, wanneer alle goedkeuringen zijn verleend, worden de extractiebestanden gemaakt via een speciale workflow die, in de standaardconfiguratie, automatisch wordt gestart wanneer een direct mailbericht in behandeling is voor extractie. Meer informatie in [deze sectie](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=nl-NL){target="_blank"}.
