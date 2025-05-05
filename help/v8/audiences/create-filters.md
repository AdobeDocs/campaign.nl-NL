---
title: Filters maken in Adobe Campaign
description: Leer hoe u uw gegevens filtert en filters opslaat in Campagne
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---

# Filters maken en beheren{#create-filters}

Het filtreren van gegevens is het proces om een kleiner deel van uw gegevensreeks, slechts die verslagen te selecteren die bepaalde criteria aanpassen, en die ondergroep voor specifieke acties (updates, publieksverwezenlijking) of analyse te gebruiken.

Wanneer u een campagne bladert vanuit de **[!UICONTROL Explorer]**, worden de gegevens weergegeven in lijsten. U kunt bestaande ingebouwde filters gebruiken om tot een specifieke ondergroep van deze gegevens toegang te hebben: quarantined adressen, niet-gerichte ontvangers, een specifieke leeftijdswaaier of aanmaakdatum bijvoorbeeld.

U kunt ook uw eigen filters maken, deze opslaan voor toekomstig gebruik of deze delen met andere campagnegebruikers.

Met de filterconfiguratie kunt u gegevens uit een lijst selecteren **[!UICONTROL dynamically]**: Wanneer de gegevens worden gewijzigd, worden de gefilterde gegevens bijgewerkt.

>[!NOTE]
>
>De de configuratiemontages van de gebruikersinterface worden plaatselijk bepaald op het apparatenniveau. Soms kan het nodig zijn deze gegevens op te schonen, vooral als zich problemen voordoen bij het vernieuwen van gegevens. Om dit te doen, gebruik **[!UICONTROL File > Clear the local cache]** -menu.

De volgende filtertypen zijn beschikbaar in Adobe Campaign:

## Vooraf gedefinieerde filters{#predefined-filters}

Vooraf gedefinieerde filters zijn beschikbaar in het menu **Filters** boven elke lijst.

Voor de profielen zijn bijvoorbeeld de volgende ingebouwde filters beschikbaar:

![](assets/built-in-filters.png)

U hebt toegang tot de filterdetails in het dialoogvenster **[!UICONTROL Profiles and Targets > Pre-defined filters]** knoop van de Ontdekkingsreiziger.

>[!NOTE]
>
>Voor alle andere gegevenslijsten worden vooraf gedefinieerde filters opgeslagen in de  **[!UICONTROL Administration > Configuration > Predefined filters]** knooppunt.

Selecteer een filter om de definitie ervan weer te geven.

![](assets/predefined-filter-list.png)

Gebruik het laatste tabblad om een voorvertoning van de gefilterde gegevens weer te geven.

![](assets/built-in-filter-preview.png)


Ingebouwde vooraf gedefinieerde filters zijn:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Query</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Geopend<br /> </td> 
   <td> Selecteert ontvangers die een levering hebben geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geopend maar niet geklikt<br /> </td> 
   <td> Hiermee selecteert u ontvangers die een levering hebben geopend maar nog niet op een koppeling hebben geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inactieve ontvangers<br /> </td> 
   <td> Selecteert ontvangers die geen levering hebben geopend in X maanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Laatste activiteit per apparaattype<br /> </td> 
   <td> Hiermee selecteert u ontvangers die de laatste Z-dagen op levering Y hebben geklikt of deze hebben geopend met apparaat X.<br /> </td> 
  </tr> 
  <tr> 
   <td> Laatste activiteit per apparaattype (reeksspatiëring)<br /> </td> 
   <td> Hiermee selecteert u ontvangers die de laatste Z-dagen op levering Y hebben geklikt of deze hebben geopend met apparaat X.<br /> </td> 
  </tr> 
  <tr> 
   <td> Niet-doelontvangers<br /> </td> 
   <td> Hiermee selecteert u ontvangers die nog nooit via kanaal Y zijn aangewezen in X maanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Zeer actieve ontvangers<br /> </td> 
   <td> Hiermee selecteert u ontvangers die in de afgelopen maanden ten minste x maal op een levering hebben geklikt.<br /> </td> 
  </tr> 
  <tr> 
 <td> Op de lijst met ongewenste personen staan e-mailadres<br /> </td> 
    <td> Hiermee selecteert u ontvangers waarvan het e-mailadres zich op de lijst van gewezen personen bevindt.<br/> </td>
  </tr> 
  <tr> 
   <td> Gegarandeerd e-mailadres<br /> </td> 
   <td> Hiermee selecteert u ontvangers waarvan het e-mailadres in quarantaine is geplaatst.<br /> </td> 
  </tr> 
  <tr> 
   <td> E-mailadressen gedupliceerd in de map<br /> </td> 
   <td> Hiermee selecteert u ontvangers waarvan het e-mailadres in de map wordt gedupliceerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Niet geopend en niet geklikt<br /> </td> 
   <td> Hiermee selecteert u ontvangers die geen levering hebben geopend of op een levering hebben geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nieuwe ontvangers (dagen)<br /> </td> 
   <td> Hiermee selecteert u ontvangers die in de laatste X dagen zijn gemaakt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nieuwe ontvangers (minuten)<br /> </td> 
   <td> Hiermee selecteert u ontvangers die in de laatste X minuten zijn gemaakt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nieuwe ontvangers (maanden)<br /> </td> 
   <td> Hiermee selecteert u ontvangers die in de laatste X maanden zijn gemaakt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op abonnement<br /> </td> 
   <td> Hiermee selecteert u ontvangers op abonnement.<br /> </td> 
  </tr> 
  <tr> 
   <td> Door op een specifieke koppeling te klikken<br /> </td> 
   <td> Hiermee selecteert u ontvangers die op een bepaalde URL in een levering hebben geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per postbezorging<br /> </td> 
   <td> Hiermee worden ontvangers geselecteerd op basis van hun gedrag na ontvangst van een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op aanmaakdatum<br /> </td> 
   <td> Hiermee selecteert u ontvangers op aanmaakdatum, over een periode van X maanden (huidige datum min n maanden) tot Y maanden (huidige datum min n maanden).<br /> </td> 
  </tr> 
  <tr> 
   <td> Op lijst<br /> </td> 
   <td> Hiermee selecteert u ontvangers op lijst.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op aantal klikken<br /> </td> 
   <td> Selecteert ontvangers die in een levering in de laatste maanden van X klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op aantal ontvangen berichten<br /> </td> 
   <td> Hiermee selecteert u ontvangers op basis van het aantal berichten dat ze hebben ontvangen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op aantal wordt geopend<br /> </td> 
   <td> Selecteert ontvangers die tussen de leveringen van X en van Y over de hoeveelheid tijd van Z opende.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op naam of e-mail<br /> </td> 
   <td> Hiermee selecteert u ontvangers op basis van hun naam of e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op leeftijdbereik<br /> </td> 
   <td> Hiermee worden ontvangers geselecteerd op basis van hun leeftijd.<br /> </td> 
  </tr> 
 </tbody> 
</table>


### Standaardfilters{#default-filters}

Met de velden boven elke lijst kunt u de **vooraf gedefinieerd standaardfilter** voor deze lijst. In de lijst met ontvangers kunt u standaard op de naam en het e-mailadres filteren.

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>De **%** vervangen van tekenreeksen. Voer bijvoorbeeld `%@gmail.com` in het veld E-mail om alle profielen met een Gmail-adres weer te geven. Enter `%@L` in het veld Achternaam om alle profielen met een L in hun achternaam weer te geven.

Blader naar de **[!UICONTROL Profiles and Targets > Predefined filters]** knooppunt.

Voor alle andere soorten gegevens, vorm de standaardfilter via **[!UICONTROL Administration > Configuration > Predefined filters]** knooppunt.

Voer de volgende stappen uit:

1. Selecteer het filter dat u standaard wilt gebruiken.
1. Klik op de knop **[!UICONTROL Parameters]** en selecteert u **[!UICONTROL Default filter for the associated document type]**.

   ![](assets/change-default-filter.png)

1. Schakel die optie uit voor het huidige standaard vooraf gedefinieerde filter.
1. Klikken **[!UICONTROL Save]** om het filter toe te passen.
1. Blader naar de map Ontvanger en klik op de knop **[!UICONTROL Remove this filter]** rechts van het huidige filter: het nieuwe standaardfilter is beschikbaar.
   ![](assets/updated-default-filter.png)


## Snelle filters{#quick-filters}

Gebruiken en combineren **Snelle filters** om filters op specifieke gebieden te bepalen.

Zodra u een snelfilterveld hebt toegevoegd, worden dit boven de gegevenslijst weergegeven, een na een. Ze kunnen onafhankelijk van elkaar worden verwijderd.

Snelle filters zijn specifiek voor elke operator en worden telkens opnieuw geïnitialiseerd wanneer de operator de cache van de clientconsole wist.

Als u een filter opnieuw moet gebruiken, maakt u een **geavanceerd filter** en sla deze op. [Meer informatie](#advanced-filters).

Een **snelfilter** Voer de volgende stappen uit:

1. Klik met de rechtermuisknop op het veld dat u wilt filteren en selecteer **[!UICONTROL Filter on this field]**.

   ![](assets/quick-filter-on-this-field.png)

   De standaardfiltervelden worden boven de lijst weergegeven.

   ![](assets/quick-filter-above-list.png)

1. Selecteer de filteropties.
1. Gebruik indien nodig het grijze pictogram aan de rechterkant van een filter om het te verwijderen.
1. U kunt filters combineren om het filter te verfijnen.

   ![](assets/add-filter-above-the-list.png)


Als u wilt filteren op een veld dat niet beschikbaar is in het formulier, ziet u dit in de kolommen en filtert u op die kolom. Om dit te doen,

1. Klik op de knop **[!UICONTROL Configure list]** pictogram.

   ![](assets/configure-list.png)

1. Selecteer de kolom die u wilt weergeven, bijvoorbeeld de leeftijd van de ontvangers, en klik op **OK**.

   ![](assets/add-age-column.png)

1. Klik met de rechtermuisknop op de knop **Leeftijd** kolom in de lijst met ontvangers en selecteer **[!UICONTROL Filter on this column]**.

   ![](assets/age-filter-on-this-column.png)

   Vervolgens kunt u de filteropties voor leeftijd selecteren. Voeg nog een filter op de pagina toe om een bereik te definiëren.

   ![](assets/filter-on-age.png)

## Geavanceerde filters{#advanced-filters}

Combineren van complexe criteria in **Geavanceerde filters**. Gebruik deze filters om een complexe vraag of een combinatie vragen over uw gegevens tot stand te brengen. Deze filters kunnen worden opgeslagen en gedeeld met andere Campagnegebruikers.

### Een geavanceerd filter maken{#create-adv-filters}

Om een **geavanceerd filter** klikt u op de knop **[!UICONTROL Filters]** en selecteert u **[!UICONTROL Advanced filter...]**.

![](assets/adv-filter.png)

U kunt ook met de rechtermuisknop op de lijst met gegevens klikken en **[!UICONTROL Advanced filter...]**.

Definieer de filtervoorwaarden. In het onderstaande voorbeeld filtert u op ontvangers waarvan het accountnummer niet begint met NL en die in Parijs of Los Angeles wonen.

1. Klik op de knop **[!UICONTROL Edit expression]** pictogram van de **[!UICONTROL Expression]** kolom.

   ![](assets/edit-exp.png)

1. Selecteer het veld waarop u wilt filteren.
1. Selecteer in de vervolgkeuzelijst de operator die u wilt toepassen.

   ![](assets/select-operator.png)

1. Selecteer een verwachte waarde in het menu **[!UICONTROL Value]** kolom. U kunt verschillende filters combineren om de query te verfijnen. Als u een filtervoorwaarde wilt toevoegen, klikt u **[!UICONTROL Add]**.

   ![](assets/add-an-exp.png)

   >[!NOTE]
   >
   >U kunt een hiërarchie aan de uitdrukkingen toewijzen of de orde van de vraaguitdrukkingen veranderen gebruikend de toolbarpijlen.

1. Er zijn drie operatoren beschikbaar om expressies te combineren:  **en**, **of**, **Behalve**. Klik op de pijl om over te schakelen naar **of**.

   ![](assets/select-or-operator.png)

1. Klikken **[!UICONTROL Ok]** om het filter te maken en toe te passen op de huidige lijst.

Het toegepaste filter wordt boven de lijst weergegeven.

![](assets/adv-filter-link.png)

Als u dit filter wilt bewerken of wijzigen, klikt u op de beschrijvingskoppeling in blauw, boven de lijst.


### Een geavanceerd filter opslaan{#save-adv-filters}

U kunt een geavanceerd filter opslaan als een  [vooraf gedefinieerd filter](#predefined-filters), zodat u deze opnieuw kunt gebruiken en kunt delen met de andere campagnegebruikers.

Volg onderstaande stappen om een geavanceerd filter op te slaan:

1. Klik op de beschrijving van het filter om het te bewerken.
1. Klik op de knop **[!UICONTROL Save as filter]** in de rechterbovensectie van het venster.

   ![](assets/save-as-filter.png)

1. Voer een naam voor dit filter in en sla het op.

   ![](assets/application-filter-save.png)

Het filter wordt toegevoegd aan de [vooraf gedefinieerde filters](#predefined-filters). Het kan vanaf dit knooppunt worden bijgewerkt.

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>U kunt een sneltoets voor het filter toevoegen om het te activeren vanaf het toetsenbord.



Dit filter is ook beschikbaar bij de vooraf gedefinieerde filters in de lijst met ontvangers.

![](assets/access-to-new-predefined-filter.png)



### Een filter gebruiken om een segment te definiëren {#filter-as-segment}

U kunt filters gebruiken en combineren om een doelpopulatiesegment tot stand te brengen.

Als de bestanden eenmaal zijn opgeslagen, zijn er geavanceerde filters beschikbaar wanneer u de doelpopulatie van een bericht selecteert in het dialoogvenster **[!UICONTROL User filters]** sectie.

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>Gebruik de **[!UICONTROL Exclude recipients from this segment]** om slechts contacten te richten die niet de filtercriteria aanpassen.


### Functies gebruiken om geavanceerde filters te maken{#use-functions-adv-filters}

Voor geavanceerde filtermogelijkheden gebruikt u functies om de inhoud van het filter te definiëren. De geavanceerde filterredacteur gebruikt alle mogelijkheden van de vraagredacteur van de Campagne.

Leer hoe te om geavanceerde vragen in deze steekproeven van begin tot eind te bouwen:

* Leer hoe u zich kunt richten op eenvoudige kenmerken voor ontvangers in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=nl-NL){target="_blank"}.
* Leer hoe u kunt filteren op ontvangers die de afgelopen 7 dagen geen contact hebben gehad in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html?lang=nl-NL){target="_blank"}.
* Leer hoe u de lijst met operatoren kunt herstellen door Active-accounts in [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/create-a-filter.html?lang=nl-NL){target="_blank"}.
* Leer hoe u een e-mailpubliek voor uw verjaardag maakt in  [deze pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=nl-NL){target="_blank"}.


### Geavanceerde parameters voor vooraf gedefinieerde filters {#param-for-data-filters}

Geavanceerde parameters zijn beschikbaar voor vooraf gedefinieerde filters. Blader naar de **[!UICONTROL Parameters]** van het filter.

* Als u het filter standaard wilt weergeven voor alle lijsten die op dit documenttype zijn gebaseerd, selecteert u de optie **[!UICONTROL Default filter for the associated document type]** -optie.

  Bijvoorbeeld de **[!UICONTROL By name or login]** filter wordt toegepast op operatoren Deze optie is geselecteerd, zodat het filter altijd op alle operatorlijsten wordt weergegeven.

* Als u een filter beschikbaar wilt maken voor alle campagneoperatoren, selecteert u de optie  **[!UICONTROL Filter shared with other operators]** -optie.

* Als u een formulier wilt definiëren om de filtercriteria te selecteren, selecteert u de optie  **[!UICONTROL Use parameter entry form]** -optie. Dit formulier moet in XML-indeling worden ingevoerd in het dialoogvenster **[!UICONTROL Form]** tab. Het ingebouwde vooraf gedefinieerde filter **[!UICONTROL Recipients who have opened]** Deze optie is beschikbaar in de lijst met ontvangers. Hiermee wordt een filterveld weergegeven waarin u de levering kunt selecteren waarop het filter van toepassing is.

![](assets/predefined-filters-parameters.png)


* De **[!UICONTROL Advanced parameters]** Met de koppeling kunt u aanvullende instellingen definiëren.

   * U kunt een SQL-tabel aan het filter koppelen om deze te gebruiken voor alle editors die de tabel delen.
   * Als u wilt voorkomen dat een gebruiker het filter overschrijft, selecteert u de optie **[!UICONTROL Do not restrict the filter]** -optie. Deze optie is bijvoorbeeld actief voor de filters &quot;Ontvangers van een levering&quot; en &quot;Ontvangers van leveringen die tot een map behoren&quot; die beschikbaar zijn in de wizard voor levering. Deze filters kunnen niet worden overbelast.
