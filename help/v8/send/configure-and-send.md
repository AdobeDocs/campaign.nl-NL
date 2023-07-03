---
title: E-mails configureren met Adobe Campaign
description: Leer hoe u e-mailberichten configureert in Adobe Campaign.
feature: Email
role: User
level: Beginner
source-git-commit: 44f30f753e3ed75b7e56caf7bd8cdfa7cbee5c35
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 0%

---

# De levering configureren en verzenden {#configure-delivery}

## Aanvullende parameters instellen {#delivery-additional-parameters}

Voordat u de levering verzendt, kunt u de verzendende parameters in de leveringseigenschappen definiëren via de **[!UICONTROL Delivery]** tab.

![](assets/delivery-properties-delivery.png)

* **[!UICONTROL Delivery priority]**: gebruik deze optie om de verzendvolgorde voor uw leveringen te wijzigen door hun prioriteitsniveau in te stellen, van **[!UICONTROL Very low]** tot **[!UICONTROL Very high]** (de standaardwaarde is **[!UICONTROL Normal]**).

* **[!UICONTROL Message batch quantity]**: Gebruik deze optie om het aantal berichten te bepalen die binnen het zelfde leveringspakket van XML worden gegroepeerd. Als de parameter op 0 wordt geplaatst, worden de berichten automatisch gegroepeerd. De pakketgrootte wordt gedefinieerd door de berekening `<delivery size>/1024`, met minimaal 8 en maximaal 256 berichten per pakket.

  >[!IMPORTANT]
  >
  >Wanneer de levering door bestaande wordt gecreeerd te dupliceren, wordt deze parameter teruggesteld.

* **[!UICONTROL Send using multiple waves]**: Gebruik deze optie als u uw berichten batchgewijs wilt verzenden in plaats van naar het gehele publiek tegelijk. [Meer informatie](#sending-using-multiple-waves).

* **[!UICONTROL Test SMTP delivery]**: gebruik deze optie om het verzenden via SMTP te testen. De levering wordt verwerkt tot verbinding aan de server SMTP maar niet verzonden: voor elke ontvanger van de levering, verbindt de Campagne met de SMTP leverancierserver, voert SMTP RCPT aan bevel uit, en sluit de verbinding vóór het bevel van SMTP DATA.

  >[!NOTE]
  >
  >* Deze optie mag niet worden ingesteld in mid-sourcing.
  >
  >* Meer informatie over de SMTP-serverconfiguratie vindt u in [Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/configure-delivery-settings.html#smtp-relay){target="_blank"}.

* **[!UICONTROL Email BCC]**: Gebruik deze optie om e-mails op te slaan op een extern systeem via BCC door eenvoudig een BCC-e-mailadres toe te voegen aan uw berichtdoel. [Meer informatie](email-parameters.md).

## Verzenden met meerdere golven {#sending-using-multiple-waves}

Als u de lading in evenwicht wilt brengen, kunt u leveringen in verscheidene partijen verdelen. Configureer het aantal partijen en hun verhouding ten opzichte van de volledige levering.

>[!NOTE]
>
>U kunt alleen de grootte en de vertraging tussen twee opeenvolgende golven definiëren. De ontvankelijke selectiecriteria voor elke golf kunnen niet worden gevormd.

1. Open het venster met de leveringseigenschappen en klik op de knop **[!UICONTROL Delivery]** tab.
1. Selecteer **[!UICONTROL Send using multiple waves]** en klik op de knop **[!UICONTROL Define waves...]** koppeling.

   ![](assets/delivery-define-waves.png)

1. Om golven te vormen, kunt u of:

   * Bepaal de grootte voor elke golf. Als u bijvoorbeeld **[!UICONTROL 30%]** op het overeenkomstige gebied, zal elke golf 30% van de berichten vertegenwoordigen inbegrepen in de levering, behalve laatste, die 10% van de berichten zal vertegenwoordigen.

     In de **[!UICONTROL Period]** geeft u de vertraging op tussen het begin van twee opeenvolgende golven. Als u bijvoorbeeld **[!UICONTROL 2d]** De eerste golf begint onmiddellijk, de tweede golf begint over twee dagen, de derde golf over vier dagen, enzovoort.

     ![](assets/delivery-waves-size.png)

   * Definieer een kalender voor het verzenden van elke golf.

     In de **[!UICONTROL Start]** geeft u de vertraging op tussen het begin van twee opeenvolgende golven. In de **[!UICONTROL Size]** Voer een vast getal of een percentage in.

     In het volgende voorbeeld vertegenwoordigt de eerste golf 25% van het totale aantal berichten inbegrepen in de levering en zal onmiddellijk beginnen. De volgende twee golven voltooien de levering en zijn geplaatst om met intervallen van zes uur te beginnen.

     ![](assets/delivery-waves-calendar.png)

   een specifieke typologieregel; **[!UICONTROL Wave scheduling check]**, zorgt ervoor dat de laatste golf vóór de grens van de leveringsgeldigheid wordt gepland. De typologieën van de campagne en hun regels, die in worden gevormd **[!UICONTROL Typology]** tabblad van de leveringseigenschappen, worden weergegeven in [deze sectie](../../automation/campaign-opt/campaign-typologies.md#typology-rules)<!--ref TBC-->.

   >[!IMPORTANT]
   >
   >Zorg ervoor dat de laatste golven de leveringstermijn niet overschrijden, die in het dialoogvenster **[!UICONTROL Validity]** tab. Anders kunnen sommige berichten niet worden verzonden.
   >
   >U moet ook genoeg tijd voor pogingen toestaan wanneer het vormen van de laatste golven. <!--See [this section]().-->

1. Ga naar de leveringslogboeken om uw verzendingen te controleren. Zie [deze pagina](send.md)<!--ref TBC-->.

   De leveringen die al zijn verzonden in de verwerkte golven (**[!UICONTROL Sent]** status) en de in de resterende golven te verzenden leveringen (**[!UICONTROL Pending]** status).

De twee onderstaande voorbeelden zijn de meest gebruikte voorbeelden voor het gebruik van meerdere golven.

* **Tijdens het opvoerproces**

  Wanneer e-mails met een nieuw platform worden verzonden, zijn internetproviders (ISP&#39;s) verdacht van IP-adressen die niet worden herkend. Als er plotseling grote hoeveelheden e-mails worden verzonden, markeren de ISP&#39;s deze vaak als spam.

  Als u wilt voorkomen dat spam wordt gemarkeerd, kunt u het verzonden volume progressief verhogen met golven. Dit zou een vlotte ontwikkeling van de startfase moeten verzekeren en u toelaten om het algemene tarief van ongeldige adressen te verminderen.

  Om dit te doen, gebruik **[!UICONTROL Schedule waves according to a calendar]** optie. Stel bijvoorbeeld de eerste golf in op 10%, de tweede op 15% enzovoort.

  ![](assets/delivery-waves-ex-ramp-up.png)

* **Campagnes die een callcenter impliceren**

  Wanneer het leiden van een campagne van de telefoonloyaliteit, heeft uw organisatie een beperkte capaciteit om het aantal vraag te verwerken om abonnees te contacteren.

  Gebruikend golven, kunt u het aantal berichten tot 20 per dag beperken, die de dagelijkse verwerkingscapaciteit van een vraagcentrum is.

  Selecteer hiervoor de optie **[!UICONTROL Schedule multiple waves of the same size]** optie. Enter **[!UICONTROL 20]** als de grootte van de golf en **[!UICONTROL 1d]** in de **[!UICONTROL Period]** veld.

  ![](assets/delivery-waves-ex-call-center.png)

<!--
## Adjust delivery failure management {#delivery-failure-management}

### Configure retries {#configure-retries}

Temporarily undelivered messages due to a **Soft** or **Ignored** error are subject to an automatic retry. The delivery failure types and reasons are presented in this [section](../../delivery/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

>[!IMPORTANT]
>
>For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the retry settings in the delivery are no longer used by Campaign. Soft bounce retries and the length of time between them are determined by the Enhanced MTA based on the type and severity of the bounce responses coming back from the message's email domain.

For on-premise installations and hosted/hybrid installations using the legacy Campaign MTA, the central section of the **[!UICONTROL Delivery]** tab for delivery parameters indicates how many retries should be performed the day after the delivery and the minimum delay between retries.

![](assets/s_ncs_user_wizard_retry_param.png)

By default, five retries are scheduled for the first day of the delivery with a minimum interval of one hour spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Validity]** tab (see [Defining validity period](#defining-validity-period)).

### Define the validity period {#define-validity-period}

When the delivery has been launched, the messages (and any retries) can be sent until the delivery deadline. This is indicated in the delivery properties, via the **[!UICONTROL Validity]** tab.

![](assets/s_ncs_user_email_del_valid_period.png)

* The **[!UICONTROL Delivery duration]** field lets you enter the limit for global delivery retries. This means that Adobe Campaign sends the messages beginning on the start date, and then, for messages returning an error only, regular, configurable retries are performed until the validity limit is reached.

  You can also choose to specify dates. To do this, select **[!UICONTROL Explicitly set validity dates]**. In this case, the delivery and validity limit dates also let you specify the time. The current time is used by default, but you can modify this directly in the input field.

  >[!IMPORTANT]
  >
  >For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the **[!UICONTROL Delivery duration]** setting in your Campaign email deliveries will be used only if set to **3.5 days or less**. If you define a value higher than 3.5 days, it will not be taken into account.

* **Validity limit of resources**: The **[!UICONTROL Validity limit]** field is used for uploaded resources, mainly for the mirror page and images. The resources on this page are valid for a limited time (to save disk space).

  The values in this field can be expressed in the units listed in [this section](../../platform/using/adobe-campaign-workspace.md#default-units).

## Confirm the delivery {#confirm-delivery}

When the delivery is configured and ready to be sent, make sure you have run the delivery analysis.

To do this, click **[!UICONTROL Send]**, select the desired action and click **[!UICONTROL Analyze]**. For more on this, see [Launching the analysis](../../delivery/using/steps-validating-the-delivery.md#analyzing-the-delivery).

![](assets/s_ncs_user_email_del_send.png)

Once done, click **[!UICONTROL Confirm delivery]** to launch the delivery of messages.

You can then close the delivery wizard and track the execution of the delivery from the **[!UICONTROL Delivery]** tab, accessible via the detail of this delivery or via the list of deliveries.

After sending messages, you can monitor and track your deliveries. For more on this, refer to these sections:

* [Monitoring a delivery](send.md)
* [Understanding delivery failures](delivery-failures.md)
* [About message tracking]

## Schedule the delivery sending {#schedule-delivery-sending}

You can defer the delivery of messages in order to schedule the delivery or to manage sales pressure and avoid over-soliciting a population.

1. Click the **[!UICONTROL Send]** button and select the **[!UICONTROL Postpone delivery]** option.

1. Specify a start date in the **[!UICONTROL Contact date]** field.

  ![](assets/)

1. You can then start the delivery analysis, then confirm the delivery sending. However, the delivery sending will not start until the date given in the **[!UICONTROL Contact date]** field.

  >[!IMPORTANT]
  >
  >Once you have started the analysis, the contact date that you defined is fixed. If you modify this date, you will have to restart the analysis so that your modifications are taken into account.

  ![](assets/)

In the delivery list, the delivery will appear with **[!UICONTROL Pending]** status.

![](assets/send-schedule-pending-status.png)

Scheduling can also be configured upstream via the **[!UICONTROL Scheduling]** button of the delivery.

![](assets/send-scheduling-button.png)

It lets you defer the delivery to a later date or save the delivery in the provisional calendar.

* The **[!UICONTROL Schedule delivery (no automatic execution)]** option lets you schedule a provisional analysis of the delivery.

  When this configuration is saved, the delivery changes to **[!UICONTROL Targeting pending]** status. The analysis will be launched on the specified date.

* The **[!UICONTROL Schedule delivery (automatic execution on planned date)]** option lets you specify the delivery date.

  Click **[!UICONTROL Send]** and select **[!UICONTROL Postpone delivery]** then launch the analysis and confirm delivery. When the analysis is complete, the delivery target is ready and messages will automatically be sent on the specified date.

Dates and times are expressed in the time zone of the current operator. The **[!UICONTROL Time zone]** drop-down list located below the contact date input field lets you automatically convert the entered date and time into the selected time zone.

For instance, if you schedule a delivery to be executed automatically at 8 o'clock London time, the time is automatically converted into the selected time zone:

![](assets/send-schedule-time-zone.png)

-->