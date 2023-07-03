---
title: E-mailparameters in Adobe Campaign
description: Meer informatie over opties en instellingen die specifiek zijn voor e-maillevering in Adobe Campaign.
feature: Email
role: User
level: Beginner, Intermediate, Experienced
source-git-commit: 44f30f753e3ed75b7e56caf7bd8cdfa7cbee5c35
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 8%

---

# E-mailparameters {#email-parameters}

In deze sectie worden de opties en parameters weergegeven die beschikbaar zijn in de leveringseigenschappen die specifiek zijn voor e-maillevering.

## E-mail BCC gebruiken {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

U kunt Adobe Campaign zo configureren dat een kopie van de e-mails die u van uw platform hebt ontvangen, bewaard blijft.

Adobe Campaign zelf beheert gearchiveerde bestanden niet. Hiermee kunt u de berichten van uw keuze naar een specifiek BCC-e-mailadres (blinde koolstofkopie) sturen, vanwaar ze via een extern systeem kunnen worden verwerkt en gearchiveerd. De .eml-bestanden die overeenkomen met de verzonden e-mails kunnen vervolgens worden overgebracht naar een externe server, zoals een SMTP-e-mailserver.

>[!CAUTION]
>
>Om privacyredenen moeten BCC-e-mails worden verwerkt door een archiveringssysteem dat veilig identificeerbare informatie (PII) kan opslaan.

De archiveringsbestemming is het BCC-e-mailadres van uw keuze, dat onzichtbaar blijft voor de ontvangers van de levering.

![](../assets/do-not-localize/speech.png)  Als gebruiker van Beheerde Cloud Services, [contact Adobe](../start/campaign-faq.md#support){target="_blank"} om het BCC e-mailadres mee te delen dat voor archivering moet worden gebruikt.

Zodra het BCC e-mailadres wordt bepaald, moet u de specifieke optie op het leveringsniveau toelaten.

>[!CAUTION]
>
>**[!UICONTROL Email BCC]** is niet standaard ingeschakeld. U moet het manueel in het e-maillevering of leveringsmalplaatje toelaten.

Volg de onderstaande stappen om dit te doen:

1. Ga naar **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**, of **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Selecteer de levering van uw keuze of dupliceer de uit-van-de-doos **[!UICONTROL Email delivery]** selecteert u vervolgens de gedupliceerde sjabloon.
1. Klik op de knop **[!UICONTROL Properties]**.
1. Selecteer het tabblad **[!UICONTROL Delivery]**. 
1. Schakel de optie **[!UICONTROL Email BCC]** in.

   ![](assets/email-bcc.png)

1. Selecteer **[!UICONTROL Ok]**.

Een kopie van alle verzonden berichten voor elke levering op basis van deze sjabloon wordt verzonden naar het e-mailadres BCC dat is geconfigureerd.

Houd rekening met de volgende specifieke kenmerken en aanbevelingen:

* U kunt slechts één BCC-e-mailadres gebruiken.

* Controleer of het BCC-adres voldoende ontvangstcapaciteit heeft om alle verzonden e-mails te archiveren.

* BCC e-mailen <!--with Enhanced MTA--> levert aan het BCC e-mailadres alvorens aan de ontvangers te leveren, wat in BCC berichten kan resulteren die worden verzonden alhoewel de originele leveringen kunnen hebben teruggestuurd. Voor meer informatie over grenzen raadpleegt u [Uitvoeren van fouten begrijpen](delivery-failures.md).

* Als de e-mails die naar het BCC-adres worden verzonden worden geopend en als hierop wordt geklikt, wordt hiermee rekening gehouden in het dialoogvenster **[!UICONTROL Total opens]** en **[!UICONTROL Clicks]** van de send analyse, die sommige misberekeningen zou kunnen veroorzaken.

<!--Only successfully sent emails are taken in account, bounces are not.-->

## Berichtindelingen selecteren {#selecting-message-formats}

U kunt de indeling van verzonden e-mailberichten wijzigen. Hiervoor bewerkt u de leveringseigenschappen en klikt u op de knop **[!UICONTROL Delivery]** tab.

![](assets/email-message-format.png)

Selecteer de indeling van de e-mail in de onderste sectie van het venster:

* **[!UICONTROL Use recipient preferences]** (standaardmodus)

  De berichtindeling wordt gedefinieerd op basis van de gegevens die zijn opgeslagen in het ontvangende profiel en wordt standaard opgeslagen in het dialoogvenster **[!UICONTROL email format]** veld (@emailFormat). Als een ontvanger berichten in een bepaalde indeling wenst te ontvangen, wordt deze indeling gebruikt. Als het veld niet is ingevuld, wordt een meerdelig alternatief bericht verzonden (zie hieronder).

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  Het bericht bevat beide indelingen: tekst en HTML. Het formaat dat op ontvangst wordt getoond hangt van de configuratie van de postsoftware van de ontvanger (multipart-alternatief) af.

  >[!IMPORTANT]
  >
  >Deze optie omvat beide versies van het document. Het vermindert daarom de leveringsproductie, omdat de berichtgrootte groter is.

* **[!UICONTROL Send all messages in text format]**

  Het bericht wordt verzonden in tekstformaat. De indeling HTML wordt niet verzonden, maar wordt alleen voor de spiegelpagina gebruikt wanneer de ontvanger op het bericht klikt.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## Tekencodering instellen {#character-encoding}

In de **[!UICONTROL SMTP]** tabblad van de leveringsparameters, **[!UICONTROL Character encoding]** kunt u een specifieke codering instellen.

De standaardcodering is UTF-8. Als sommige e-mailproviders van uw ontvangers de standaardcodering UTF-8 niet ondersteunen, kunt u een specifieke codering instellen om de speciale tekens correct weer te geven aan de ontvangers van uw e-mail.

U wilt bijvoorbeeld een e-mail verzenden met Japanse tekens. Om ervoor te zorgen dat alle tekens correct worden weergegeven aan ontvangers in Japan, kunt u een codering gebruiken die de Japanse tekens ondersteunt in plaats van de standaard UTF-8.

Selecteer hiervoor de optie **[!UICONTROL Force the encoding used for messages]** in de **[!UICONTROL Character encoding]** en kiest u een codering in de vervolgkeuzelijst die wordt weergegeven.

![](assets/email-smtp-encoding.png)

## Bounce-e-mails beheren {#managing-bounce-emails}

De **[!UICONTROL SMTP]** tabblad van de leveringseigenschappen kunt u ook het beheer van stuiterende berichten configureren.

* **[!UICONTROL Errors-to-address]**: Standaard worden teruggestuurde e-mailberichten ontvangen in het standaardfoutvak van het platform, maar u kunt een specifiek foutadres voor een levering definiëren.

* **[!UICONTROL Bounce address]**: U kunt ook een ander adres definiëren waarnaar de onverwerkte teruggestuurde e-mails worden doorgestuurd. Met dit adres kunt u de redenen voor het stuiteren onderzoeken wanneer e-mails niet automatisch kunnen worden gekwalificeerd door de toepassing.

Elk van deze velden kan worden gepersonaliseerd met behulp van het toegewezen pictogram. Meer informatie over personalisatievelden in [deze sectie](personalization-fields.md).

![](assets/email-smtp-bounce.png)

Zie voor meer informatie over stuiterend mailbeheer [deze sectie](delivery-failures.md#bounce-mail-management).

## SMTP-koppen toevoegen {#adding-smtp-headers}

Het is mogelijk om kopballen SMTP aan uw leveringen toe te voegen. Hiervoor gebruikt u de desbetreffende sectie van de **[!UICONTROL SMTP]** in de levering.

Het script dat in dit venster wordt ingevoerd, moet in het volgende formulier verwijzen naar één koptekst per regel: **name:value**.

Waarden worden indien nodig automatisch gecodeerd.

>[!IMPORTANT]
>
>Het toevoegen van een script voor het opnemen van extra SMTP-kopteksten is gereserveerd voor gevorderde gebruikers.
>
>De syntaxis van dit script moet voldoen aan de vereisten van dit type content: geen ongebruikte ruimte, geen lege regel, enz.

![](assets/email-smtp-headers.png)

<!--
## Generate mirror page {#generating-mirror-page}

The mirror page is an HTML page accessible online via a web browser. Its content is identical to the email. It can be useful if your recipients are experiencing rendering issues or broken images when trying to view your email in their inbox.

Learn how to insert a link to the mirror page in [this section](mirror-page.md).-->