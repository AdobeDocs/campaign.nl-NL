---
title: Directe e-mails verzenden met Adobe Campaign
description: Ga aan de slag met direct mail in Campagne
feature: Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 4%

---

# Direct-mailleveringen maken

Met Direct mail kunt u een extractiebestand genereren dat gegevens over de doelpopulatie bevat. U kunt dit dossier met de leverancier dan delen die berichten aan de doelpopulaties zal leveren.

De volgende stappen voor het genereren van het bestand zijn:

1. [De levering maken](#creating-a-direct-mail-delivery)
1. [De doelgroep definiëren](#defining-the-direct-mail-audience)
1. [De inhoud van het bestand definiëren](#defining-the-direct-mail-content)
1. [De levering valideren](#validating)
1. [De levering starten](#start-delivery)

## De levering maken{#creating-a-direct-mail-delivery}

Creeer direct postlevering die op het malplaatje wordt gebaseerd. U kunt de **[!UICONTROL Deliver by direct mail (paper)]** ingebouwde sjabloon dupliceren en configureren.

Voer de volgende stappen uit om een nieuwe levering via e-mail te maken:

>[!NOTE]
>
>De globale concepten op leveringsverwezenlijking worden voorgesteld in [ deze sectie ](../start/create-message.md).

1. Maak een nieuwe levering, bijvoorbeeld via het dashboard Levering.
1. Selecteer het leveringsmalplaatje **leveren door directe post (document)**.

   ![](assets/direct_mail.png)

1. Identificeer uw levering met een etiket, code, en beschrijving. Raadpleeg [deze sectie](../start/create-message.md#create-the-delivery) voor meer informatie.
1. Klik **verdergaan** om deze informatie te bevestigen en het venster van de berichtconfiguratie te tonen.

## De doelgroep definiëren{#defining-the-direct-mail-audience}

De profielen van ontvangers moeten ten minste hun naam en postadres bevatten.

Postadressen zijn berekende velden. Een adres kan standaard maximaal zes regels bevatten: de eerste regel bevat de voornaam en achternaam, de volgende regels bevatten het postadres (weg enz.) en de laatste regel bevat de postcode en de stad of stad. De definitie van het standaard berekende postadresgebied kan in het nms :recipient schema worden herzien.

Een adres wordt als volledig beschouwd als de naam, het gebied van de code van ZIP/Postal, en stad/stad gebieden niet leeg zijn. Ontvangers met onvolledige adressen worden uitgesloten van directe mailleveringen.

Lees meer in [deze sectie](../start/create-message.md#target-population).

## De inhoud van het bestand definiëren{#defining-the-direct-mail-content}

Gebruik de extractietovenaar om de informatie (kolommen) te bepalen die in het outputdossier moet worden uitgevoerd.

De naam van het bestand met de geëxtraheerde gegevens wordt gedefinieerd in het veld **[!UICONTROL File]** . Met de knop rechts van het veld kunt u aanpassingsvelden gebruiken om de bestandsnaam te maken.

Standaard wordt het extractiebestand gemaakt en opgeslagen op de server. U kunt het opslaan op uw computer. Controleer **[!UICONTROL Download the generated file after the analysis of the delivery]** om dit te doen. In dit geval moet u het toegangspad naar de lokale opslagmap en de bestandsnaam aangeven.

![](assets/s_ncs_user_mail_delivery_local_file.png)

Voor direct mail levering, wordt de inhoud van de extractie bepaald in **[!UICONTROL Edit the extraction file format...]** verbinding.

![](assets/s_ncs_user_mail_delivery_format_link.png)

Met deze koppeling hebt u toegang tot de extractieassistent en definieert u de informatie (kolommen) die u wilt exporteren naar het uitvoerbestand.

![](assets/s_ncs_user_mail_delivery_format_wz.png)

U kunt een gepersonaliseerde URL in het extractiedossier opnemen. Voor meer op dit, verwijs naar de Adobe Campaign Classic [ documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/publishing-a-web-form.html){target="_blank"}.

>[!NOTE]
>
>Deze assistent omvat de stappen van de uitvoerassistent gedetailleerd de Adobe Campaign Classic [ documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-export-jobs.html){target="_blank"}.

## De levering valideren{#validating}

Controleer het resultaat van de analyse en de inhoud van het uitvoerbestand.

In het kader van een marketingcampagne wordt op de extractiedatum het extractiebestand gemaakt. U kunt de inhoud van het geëxtraheerde bestand weergeven, goedkeuren of de indeling wijzigen en de extractie indien nodig opnieuw starten. Zodra het dossier is goedgekeurd, kunt u het bericht e-mail naar de router verzenden. Meer informatie vindt u [op deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html){target="_blank"}.

De globale concepten wanneer het bevestigen van een levering worden voorgesteld in [ deze sectie ](../start/create-message.md#validate-the-delivery).

Het outputdossier van een directe postlevering wordt geproduceerd tijdens de leveringsanalyse. De inhoud van het dossier hangt van de geselecteerde outputkolommen (verwijs naar dit [ sectiedossier ](#defining-the-direct-mail-content)) af.

>[!NOTE]
>
>De analysefase wordt gedetailleerd in deze [ sectie ](delivery-analysis.md).

Tijdens de analysefase wordt het bestand gegenereerd, maar wordt informatie over ontvangers (d.w.z. leveringslogboeken) niet bijgewerkt. U kunt deze taak dus annuleren zonder risico&#39;s te lopen.

Controleer het resultaat van de analyse en de inhoud van het uitvoerbestand voordat u op **[!UICONTROL Confirm delivery]** klikt. Met een bevestigingsbericht kunt u de levering starten.

Met de verzendbevestiging wordt de gegevensextractie in het opgegeven bestand gestart.

![](assets/s_ncs_user_postal_del_send_confirm_postal.png)

U kunt de assistent vervolgens sluiten en de leveringslogboeken bekijken via het tabblad **[!UICONTROL Delivery]** , dat toegankelijk is via de leveringsdetails.

U kunt de terugwinningswijze van de leveringslogboeken van het **[!UICONTROL Analysis]** lusje van de leveringseigenschappen vormen.

Er zijn twee modi:

* **[!UICONTROL Messages are considered sent after validation]** (standaardmodus): in deze functiemodus worden alle uitzendingen bijgewerkt wanneer de operator de send bevestigt (de status gaat van &#39;In behandeling&#39; naar &#39;Verzonden&#39;) en wordt de levering automatisch ingesteld op **[!UICONTROL Finished]** .
* **[!UICONTROL A file of results determines the messages that are sent and those that have failed]** : in deze modus kunt u de uitzendingen bijwerken via een extern bestand dat door het servicebureau is verzonden. In dit geval moet een workflow voor het verwerken van deze informatie worden gebruikt om de status van de broadlog bij te werken.

  >[!NOTE]
  >
  >In dit geval moet de gebruiker ook de status van de levering wijzigen in **[!UICONTROL Finished]** zodra de weblogs zijn bijgewerkt.

## De levering starten{#start-delivery}

Zodra u het extractiedossier bevestigde, klik **bevestig levering** een bevestigingsbericht laat u de levering lanceren.

De bevestiging start de gegevensextractie in het opgegeven bestand.

In het kader van een marketingcampagne, wanneer alle goedkeuringen zijn verleend, worden de extractiebestanden gemaakt via een speciale workflow die, in de standaardconfiguratie, automatisch wordt gestart wanneer een direct mailbericht in behandeling is voor extractie. Lees meer in [deze sectie](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html){target="_blank"}.
