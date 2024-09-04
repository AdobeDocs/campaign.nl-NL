---
title: Met SMS wordt de inhoud gedefinieerd
description: Leer hoe u de inhoud van een SMS-levering instelt
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="Beperkte beschikbaarheid" type="Informative"
source-git-commit: a184a29301f2bd739bc3fd1373fc8cfad58f0393
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---


# SMS-inhoud {#sms-content}

Om de inhoud van uw levering van SMS te vormen:

1. Voer de inhoud van het bericht in de wizard **[!UICONTROL Text content]** in

   ![](assets/sms_content.png){zoomable="yes"}

1. U kunt uw bericht personaliseren door verpersoonlijkingsgebieden op te nemen (bijvoorbeeld toevoegend de voornaam), of het opnemen van vooraf bepaald verpersoonlijkingsblok (bijvoorbeeld toevoegend de groeten). U kunt op de verpersoonlijkingsknoop klikken om deze toe te voegen:

   ![](assets/sms_perso.png){zoomable="yes"}

   Nadat u op **[!UICONTROL Recipient]** > **[!UICONTROL First name]** hebt geklikt, ziet u de personalisatie als volgt:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. U kunt een voorvertoning van de levering weergeven door op het tabblad **[!UICONTROL Preview]** te klikken en op de vervolgkeuzelijst **[!UICONTROL Test personalization]** te klikken en door een ontvanger in de tabel **[!UICONTROL Recipient]** te kiezen.

   ![](assets/sms_preview.png){zoomable="yes"}

   Je krijgt een voorbeeld van je SMS met de personalisatie:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* SMS-berichten mogen niet langer zijn dan 160 tekens als de codepagina Latin-1 (ISO-8859-1) wordt gebruikt. Als het bericht in Unicode wordt geschreven, moet het niet 70 karakters overschrijden. Bepaalde speciale tekens kunnen de lengte van het bericht beïnvloeden. Voor meer informatie over berichtlengte, verwijs naar [ het karaktervertaling van SMS ](smpp-external-account.md#smpp-channel-settings) sectie.
>
>* Wanneer verpersoonlijkingsgebieden of voorwaardelijke inhoudsgebieden aanwezig zijn, varieert de grootte van het bericht van één ontvanger aan andere. De lengte van het bericht moet worden geëvalueerd wanneer de personalisatie is uitgevoerd.
>
>*Wanneer u de analyse lanceert, wordt de lengte van berichten gecontroleerd en een waarschuwing getoond in het geval van overstroming.

Na het creëren van de inhoud van uw levering, kunt u [ uw publiek ](sms-audience.md) selecteren.