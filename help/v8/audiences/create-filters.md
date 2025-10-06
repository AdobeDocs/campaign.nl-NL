---
title: Filters maken in Adobe Campaign
description: Leer hoe u uw gegevens filtert en filters opslaat in Campagne
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
version: Campaign v8, Campaign Classic v7
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---

# Filters maken en beheren{#create-filters}

Het filtreren van gegevens is het proces om een kleiner deel van uw gegevensreeks, slechts die verslagen te selecteren die bepaalde criteria aanpassen, en die ondergroep voor specifieke acties (updates, publieksverwezenlijking) of analyse te gebruiken.

Wanneer u in de **[!UICONTROL Explorer]** -campagne bladert, worden de gegevens weergegeven in lijsten. U kunt bestaande ingebouwde filters gebruiken om tot een specifieke ondergroep van deze gegevens toegang te hebben: quarantined adressen, niet-gerichte ontvangers, een specifieke leeftijdswaaier of aanmaakdatum bijvoorbeeld.

U kunt ook uw eigen filters maken, deze opslaan voor toekomstig gebruik of deze delen met andere campagnegebruikers.

Met de filterconfiguratie kunt u gegevens in een lijst selecteren **[!UICONTROL dynamically]** : wanneer de gegevens worden gewijzigd, worden de gefilterde gegevens bijgewerkt.

>[!NOTE]
>
>De de configuratiemontages van de gebruikersinterface worden plaatselijk bepaald op het apparatenniveau. Soms kan het nodig zijn deze gegevens op te schonen, vooral als zich problemen voordoen bij het vernieuwen van gegevens. Gebruik hiervoor het menu **[!UICONTROL File > Clear the local cache]** .

De volgende filtertypen zijn beschikbaar in Adobe Campaign:

## Vooraf gedefinieerde filters{#predefined-filters}

De vooraf bepaalde filters zijn beschikbaar bij de **knoop van Filters** boven elke lijst.

Voor de profielen zijn bijvoorbeeld de volgende ingebouwde filters beschikbaar:

![](assets/built-in-filters.png)

U hebt toegang tot de details van de filters in het knooppunt **[!UICONTROL Profiles and Targets > Pre-defined filters]** van de Explorer.

>[!NOTE]
>
>Voor alle andere gegevenslijsten worden vooraf gedefinieerde filters opgeslagen in het knooppunt **[!UICONTROL Administration > Configuration > Predefined filters]** .

Selecteer een filter om de definitie ervan weer te geven.

![](assets/predefined-filter-list.png)

Gebruik het laatste tabblad om een voorvertoning van de gefilterde gegevens weer te geven.

![](assets/built-in-filter-preview.png)


+++  Geïntegreerde voorgedefinieerde filters

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Query</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Geopend <br /> </td> 
   <td> Selecteert ontvangers die een levering hebben geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geopend maar niet geklikt <br /> </td> 
   <td> Selecteert ontvangers die een levering hebben geopend maar niet op een verbinding geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inactieve ontvangers <br /> </td> 
   <td> Selecteert ontvangers die geen levering in X maanden hebben geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Laatste activiteit door apparatentype <br /> </td> 
   <td> Selecteert ontvangers die of levering Y gebruikend apparaat X in de laatste dagen van Z hebben geklikt geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Laatste activiteit door apparatentype (het Volgen) <br /> </td> 
   <td> Selecteert ontvangers die of levering Y gebruikend apparaat X in de laatste dagen van Z hebben geklikt geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Niet-doelontvangers <br /> </td> 
   <td> Selecteert ontvangers die nooit via kanaal Y in X maanden zijn gericht.<br /> </td> 
  </tr> 
  <tr> 
   <td> Zeer actieve ontvangers <br /> </td> 
   <td> Selecteert ontvangers die in een levering minstens x keer in de laatste maanden van Y hebben geklikt.<br /> </td> 
  </tr> 
  <tr> 
 <td> Op de lijst met ongewenste personen staan e-mailadres <br /> </td> 
    <td> Selecteert ontvangers de waarvan e-mailadres op de lijst van gewezen personen is.<br/> </td>
  </tr> 
  <tr> 
   <td> Gegarandeerd e-mailadres <br /> </td> 
   <td> Hiermee selecteert u ontvangers waarvan het e-mailadres in quarantaine is geplaatst.<br /> </td> 
  </tr> 
  <tr> 
   <td> E-mailadressen gedupliceerd in de map <br /> </td> 
   <td> Hiermee selecteert u ontvangers waarvan het e-mailadres in de map wordt gedupliceerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Niet geopend en niet geklikt <br /> </td> 
   <td> Selecteert ontvangers die geen levering hebben geopend, of in een levering geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nieuwe ontvangers (dagen) <br /> </td> 
   <td> Selecteert ontvangers die in de laatste dagen van X werden gecreeerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nieuwe ontvangers (minuten) <br /> </td> 
   <td> Selecteert ontvangers die in de laatste notulen van X werden gecreeerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nieuwe ontvangers (maanden) <br /> </td> 
   <td> Selecteert ontvangers die in de laatste maanden van X werden gecreeerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op abonnement <br /> </td> 
   <td> Selecteert ontvangers door abonnement.<br /> </td> 
  </tr> 
  <tr> 
   <td> Door op een specifieke verbinding <br /> te klikken </td> 
   <td> Selecteert ontvangers die op bepaalde URL in een levering klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per postbezorgingsgedrag <br /> </td> 
   <td> Selecteert ontvangers volgens hun gedrag na het ontvangen van een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op aanmaakdatum <br /> </td> 
   <td> Hiermee selecteert u ontvangers op aanmaakdatum, over een periode van X maanden (huidige datum min n maanden) tot Y maanden (huidige datum min n maanden).<br /> </td> 
  </tr> 
  <tr> 
   <td> Op lijst <br /> </td> 
   <td> Hiermee selecteert u ontvangers op lijst.<br /> </td> 
  </tr> 
  <tr> 
   <td> Door aantal kliks <br /> </td> 
   <td> Selecteert ontvangers die in een levering in de laatste maanden van X klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Door aantal ontvangen berichten <br /> </td> 
   <td> Selecteert ontvangers op het aantal berichten dat zij ontvingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Door aantal van opent <br /> </td> 
   <td> Selecteert ontvangers die tussen de levering van X en van Y over de hoeveelheid tijd van Z opende.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op naam of e-mail <br /> </td> 
   <td> Hiermee selecteert u ontvangers op basis van hun naam of e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Op leeftijdsbereik <br /> </td> 
   <td> Hiermee selecteert u ontvangers op basis van hun leeftijd.<br /> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Standaardfilters{#default-filters}

De gebieden boven elke lijst laten u de **vooraf bepaalde standaardfilter** voor deze lijst gebruiken. In de lijst met ontvangers kunt u standaard op de naam en het e-mailadres filteren.

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>Het teken **%** vervangt om het even welke karakterkoord. Typ bijvoorbeeld `%@gmail.com` in het veld E-mail om alle profielen met een Gmail-adres weer te geven. Typ `%@L` in het veld Achternaam om alle profielen met een L in hun achternaam weer te geven.

Blader naar het knooppunt **[!UICONTROL Profiles and Targets > Predefined filters]** om het standaardfilter voor een lijst met ontvangers te wijzigen.

Voor alle andere gegevenstypen configureert u het standaardfilter via het knooppunt **[!UICONTROL Administration > Configuration > Predefined filters]** .

Voer de volgende stappen uit:

1. Selecteer het filter dat u standaard wilt gebruiken.
1. Klik op de tab **[!UICONTROL Parameters]** en selecteer **[!UICONTROL Default filter for the associated document type]** .

   ![](assets/change-default-filter.png)

1. Schakel die optie uit voor het huidige standaard vooraf gedefinieerde filter.
1. Klik op **[!UICONTROL Save]** om het filter toe te passen.
1. Blader naar de map Ontvanger en klik op het pictogram **[!UICONTROL Remove this filter]** rechts van het huidige filter: het nieuwe standaardfilter is beschikbaar.
   ![](assets/updated-default-filter.png)


## Snelle filters{#quick-filters}

Gebruik en combineer **Snelle filters** om filters op specifieke gebieden te bepalen.

Zodra u een snelfilterveld hebt toegevoegd, worden dit boven de gegevenslijst weergegeven, een na een. Ze kunnen onafhankelijk van elkaar worden verwijderd.

Snelle filters zijn specifiek voor elke operator en worden telkens opnieuw geïnitialiseerd wanneer de operator de cache van de bijbehorende clientconsole wist.

Als u een filter opnieuw moet gebruiken, creeer een **geavanceerde filter** en bewaar het. [Meer informatie](#advanced-filters).

Om a **snelle filter** tot stand te brengen, volg de stappen:

1. Klik met de rechtermuisknop op het veld waarop u wilt filteren en selecteer **[!UICONTROL Filter on this field]** .

   ![](assets/quick-filter-on-this-field.png)

   De standaardfiltervelden worden boven de lijst weergegeven.

   ![](assets/quick-filter-above-list.png)

1. Selecteer de filteropties.
1. Gebruik indien nodig het grijze pictogram aan de rechterkant van een filter om het te verwijderen.
1. U kunt filters combineren om het filter te verfijnen.

   ![](assets/add-filter-above-the-list.png)


Als u wilt filteren op een veld dat niet beschikbaar is in het formulier, ziet u dit in de kolommen en filtert u op die kolom. Om dit te doen,

1. Klik op het pictogram **[!UICONTROL Configure list]** .

   ![](assets/configure-list.png)

1. Selecteer de kolom aan vertoning, bijvoorbeeld de leeftijd van de ontvangers, en klik **O.K.**.

   ![](assets/add-age-column.png)

1. Klik met de rechtermuisknop op de **pagina** -kolom in de lijst met ontvangers en selecteer **[!UICONTROL Filter on this column]** .

   ![](assets/age-filter-on-this-column.png)

   Vervolgens kunt u de filteropties voor leeftijd selecteren. Voeg nog een filter op de pagina toe om een bereik te definiëren.

   ![](assets/filter-on-age.png)

## Geavanceerde filters{#advanced-filters}

Combineer complexe criteria in **Geavanceerde filters**. Gebruik deze filters om een complexe vraag of een combinatie vragen over uw gegevens tot stand te brengen. Deze filters kunnen worden opgeslagen en gedeeld met andere Campagnegebruikers.

### Een geavanceerd filter maken{#create-adv-filters}

Om een **geavanceerde filter** tot stand te brengen, klik de **[!UICONTROL Filters]** knoop en selecteer **[!UICONTROL Advanced filter...]**.

![](assets/adv-filter.png)

U kunt ook met de rechtermuisknop op de lijst met gegevens klikken en **[!UICONTROL Advanced filter...]** selecteren.

Definieer de filtervoorwaarden. In het onderstaande voorbeeld filtert u op ontvangers waarvan het accountnummer niet begint met NL en die in Parijs of Los Angeles wonen.

1. Klik op het pictogram **[!UICONTROL Edit expression]** van de kolom **[!UICONTROL Expression]** .

   ![](assets/edit-exp.png)

1. Selecteer het veld waarop u wilt filteren.
1. Selecteer in de vervolgkeuzelijst de operator die u wilt toepassen.

   ![](assets/select-operator.png)

1. Selecteer een verwachte waarde in de kolom **[!UICONTROL Value]** . U kunt verschillende filters combineren om de query te verfijnen. Klik op **[!UICONTROL Add]** om een filtervoorwaarde toe te voegen.

   ![](assets/add-an-exp.png)

   >[!NOTE]
   >
   >U kunt een hiërarchie aan de uitdrukkingen toewijzen of de orde van de vraaguitdrukkingen veranderen gebruikend de toolbarpijlen.

1. Drie exploitanten zijn beschikbaar om uitdrukkingen te combineren: **en**, **of**, **behalve**. Klik de pijl om aan **of** over te schakelen.

   ![](assets/select-or-operator.png)

1. Klik op **[!UICONTROL Ok]** om het filter te maken en toe te passen op de huidige lijst.

Het toegepaste filter wordt boven de lijst weergegeven.

![](assets/adv-filter-link.png)

Als u dit filter wilt bewerken of wijzigen, klikt u op de beschrijvingskoppeling in blauw, boven de lijst.


### Een geavanceerd filter opslaan{#save-adv-filters}

U kunt een geavanceerd filter als a [ bewaren vooraf bepaalde filter ](#predefined-filters), zodat u het kunt hergebruiken en het met de andere gebruikers van de Campagne delen.

Volg onderstaande stappen om een geavanceerd filter op te slaan:

1. Klik op de beschrijving van het filter om het te bewerken.
1. Klik op het pictogram **[!UICONTROL Save as filter]** rechtsboven in het venster.

   ![](assets/save-as-filter.png)

1. Voer een naam voor dit filter in en sla het op.

   ![](assets/application-filter-save.png)

Het filter wordt toegevoegd aan de [ vooraf bepaalde filters ](#predefined-filters). Het kan vanaf dit knooppunt worden bijgewerkt.

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>U kunt een sneltoets voor het filter toevoegen om het te activeren vanaf het toetsenbord.



Dit filter is ook beschikbaar bij de vooraf gedefinieerde filters in de lijst met ontvangers.

![](assets/access-to-new-predefined-filter.png)



### Een filter gebruiken om een segment te definiëren {#filter-as-segment}

U kunt filters gebruiken en combineren om een doelpopulatiesegment tot stand te brengen.

Nadat de bestanden zijn opgeslagen, zijn er geavanceerde filters beschikbaar wanneer u de doelpopulatie van een bericht selecteert in de sectie **[!UICONTROL User filters]** .

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>Gebruik **[!UICONTROL Exclude recipients from this segment]** om slechts contacten te richten die niet de filtercriteria aanpassen.


### Functies gebruiken om geavanceerde filters te maken{#use-functions-adv-filters}

Voor geavanceerde filtermogelijkheden gebruikt u functies om de inhoud van het filter te definiëren. De geavanceerde filterredacteur gebruikt alle mogelijkheden van de vraagredacteur van de Campagne.

Leer hoe te om geavanceerde vragen in deze steekproeven van begin tot eind te bouwen:

* Leer hoe te om op eenvoudige ontvankelijke attributen in [ te richten deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.
* Leer hoe te om op ontvangers te filtreren die niet tijdens de laatste 7 dagen in [ worden gecontacteerd deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html){target="_blank"}.
* Leer hoe te om de lijst van exploitanten terug te krijgen door Actieve rekeningen in [ kan worden gefiltreerd deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/create-a-filter.html){target="_blank"}.
* Leer hoe te om een e-mailpubliek van de verjaardag in [ te bouwen deze pagina ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"}.


### Geavanceerde parameters voor vooraf gedefinieerde filters {#param-for-data-filters}

Geavanceerde parameters zijn beschikbaar voor vooraf gedefinieerde filters. Blader naar de tab **[!UICONTROL Parameters]** van het filter om deze te openen.

* Als u het filter standaard wilt weergeven voor alle lijsten die op dit documenttype zijn gebaseerd, selecteert u de optie **[!UICONTROL Default filter for the associated document type]** .

  Het filter **[!UICONTROL By name or login]** wordt bijvoorbeeld toegepast op operatoren. Deze optie is geselecteerd en het filter wordt dus altijd weergegeven in alle operatorlijsten.

* Als u een filter beschikbaar wilt maken voor alle campagneoperatoren, selecteert u de optie **[!UICONTROL Filter shared with other operators]** .

* Als u een formulier wilt definiëren om de filtercriteria te selecteren, selecteert u de optie **[!UICONTROL Use parameter entry form]** . Dit formulier moet worden ingevoerd in XML-indeling op het tabblad **[!UICONTROL Form]** . Met het ingebouwde vooraf gedefinieerde filter **[!UICONTROL Recipients who have opened]** dat beschikbaar is in de lijst met ontvangers, wordt bijvoorbeeld een filterveld weergegeven waarin u de levering kunt selecteren waarop het filter van toepassing is.

![](assets/predefined-filters-parameters.png)


* Met de koppeling **[!UICONTROL Advanced parameters]** kunt u aanvullende instellingen definiëren.

   * U kunt een SQL-tabel aan het filter koppelen om deze te gebruiken voor alle editors die de tabel delen.
   * Als u wilt voorkomen dat een gebruiker het filter overschrijft, selecteert u de optie **[!UICONTROL Do not restrict the filter]** . Deze optie is bijvoorbeeld actief voor de filters &quot;Ontvangers van een levering&quot; en &quot;Ontvangers van leveringen die tot een map behoren&quot; die beschikbaar zijn in de wizard voor levering. Deze filters kunnen niet worden overbelast.


### Operatoren
