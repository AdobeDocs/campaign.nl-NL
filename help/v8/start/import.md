---
title: Aan de slag met profielen
description: Aan de slag met profielen
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
version: Campaign v8, Campaign Classic v7
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '3832'
ht-degree: 0%

---

# Gegevens importeren in campagne {#ootb-profiles}

De campagne helpt u contacten aan het gegevensbestand toevoegen. U kunt een dossier laden, veelvoudige contactupdates plannen en automatiseren, gegevens op het Web verzamelen, of profielinformatie direct in de ontvankelijke lijst ingaan.

De invoer van het profiel wordt gevormd in specifieke malplaatjes die door werkschema&#39;s via de **invoer** activiteit worden uitgevoerd. Ze kunnen automatisch volgens een schema worden herhaald, bijvoorbeeld om de gegevensuitwisseling tussen verschillende informatiesystemen te automatiseren. Lees meer in [deze sectie](../../automation/workflow/recurring-import-workflow.md).

![](assets/import-wf.png)

## Importeren uitvoeren

Met Adobe Campaign kunt u gegevens uit een of meer bestanden in tekst-, CSV-, TAB- of XML-indeling importeren in de database. Deze bestanden zijn gekoppeld aan een tabel (hoofd of gekoppeld) en elk veld van het bronbestand of de bronbestanden is gekoppeld aan een veld van de database.

>[!NOTE]
>
>U kunt gegevens importeren zonder deze toe te wijzen aan de databasegegevens met behulp van de functie **[!UICONTROL Import a list]** . De gegevens kunnen vervolgens uitsluitend in workflows via het **[!UICONTROL Read list]** -object worden gebruikt. Raadpleeg [deze pagina](../../automation/workflow/read-list.md) voor meer informatie.


## De importassistent gebruiken

Met de importassistent kunt u een importbewerking configureren, opties ervan definiëren (zoals gegevenstransformatie) en uitvoering starten. Het is een reeks schermen waarvan de inhoud afhankelijk is van het type import (enkelvoudig of meervoudig) en de rechten van de operator.

De importassistent wordt weergegeven nadat een nieuwe importtaak is gemaakt.

![](assets/new-import.png)

In het bronbestand valt elke regel samen met een record. De gegevens in records worden gescheiden door scheidingstekens (spatie, tab, teken, enz.). Dit betekent dat de gegevens in de vorm van kolommen worden teruggewonnen, en elke kolom wordt geassocieerd met een gebied van het gegevensbestand.

### Stap 1 - Kies de importsjabloon {#step-1---choosing-the-import-template}

Wanneer u de importassistent start, moet u eerst een sjabloon selecteren. Als voorbeeld, om de invoer van ontvangers te vormen die een nieuwsbrief ontvingen, volg de stappen hieronder:

1. Selecteer de map **[!UICONTROL Profiles and Targets > Job > Generic imports and exports]** .
1. Klik **Nieuw** en klik dan **Invoer** om het de invoermalplaatje tot stand te brengen.

   ![](assets/s_ncs_user_import_wizard01_1.png)

1. Klik op de pijl rechts van het veld **[!UICONTROL Import template]** om de sjabloon te selecteren of klik op **[!UICONTROL Select link]** om door de structuur te bladeren.

   De native sjabloon is **[!UICONTROL New text import]** . Deze sjabloon moet niet worden gewijzigd, maar u kunt het dupliceren om een nieuwe sjabloon te configureren, afhankelijk van uw vereisten. Importeersjablonen worden standaard opgeslagen in het knooppunt **[!UICONTROL Profiles and targets > Templates > Job templates]** .

1. Voer in het veld **[!UICONTROL Label]** een naam in voor deze importbewerking. U kunt een beschrijving toevoegen.
1. Selecteer het type import in het desbetreffende veld. Er zijn twee mogelijke typen importeren: **[!UICONTROL Simple import]** als u slechts één bestand wilt importeren, en **[!UICONTROL Multiple import]** als u meerdere bestanden tegelijk wilt importeren.

   Selecteer voor een meervoudige importbewerking **[!UICONTROL Multiple import]** in de vervolgkeuzelijst **[!UICONTROL Import type]** in het eerste scherm van de importassistent.

   ![](assets/s_ncs_user_import_wizard01_2.png)

1. Geef de velden op die u wilt importeren door op **[!UICONTROL Add]** te klikken.

   ![](assets/s_ncs_user_import_wizard01_3.png)

   Telkens wanneer een bestand wordt toegevoegd, wordt het scherm van de **[!UICONTROL File to import]** assistent weergegeven. Zie sectie [&#x200B; Stap 2 - het dossierselectie van Source &#x200B;](#step-2---source-file-selection) en volg de stappen in de medewerker om de invoeropties zoals voor een eenvoudige invoer te bepalen.

   >[!NOTE]
   >
   >Meerdere importen moeten alleen aan specifieke behoeften voldoen en worden niet aanbevolen.

#### Stap 2 - Source-bestandsselectie {#step-2---source-file-selection}

Het bronbestand kan de tekstindeling (txt, csv, tab, vaste kolommen) of xml hebben.

Standaard is **[!UICONTROL Upload file on the server]** geselecteerd. Klik op de map rechts van het veld **[!UICONTROL Local file]** om naar de lokale schijf te bladeren en selecteer het bestand dat u wilt importeren. U kunt deze optie deselecteren om het toegangspad en de naam in te voeren van het bestand als dit zich op de server bevindt.

![](assets/s_ncs_user_import_wizard02_1.png)

Wanneer het bestand is opgegeven, kunt u de gegevens ervan weergeven in de onderste sectie van het venster door op **[!UICONTROL Auto-detect format]** te klikken. In deze voorvertoning worden de eerste 200 regels van het bronbestand weergegeven.

![](assets/s_ncs_user_import_wizard02_2.png)

Gebruik de opties boven deze weergave om het importeren te configureren. De parameters die via deze opties worden gedefinieerd, worden overgebracht naar de voorvertoning. De volgende opties zijn beschikbaar:

* Met **[!UICONTROL Click here to change the file format...]** kunt u de bestandsindeling controleren en de configuratie perfectioneren.
* Met **[!UICONTROL Update on server...]** kunt u het lokale bestand overbrengen naar de server. Deze optie is alleen beschikbaar als **[!UICONTROL Upload file on the server]** is geselecteerd.
* **[!UICONTROL Download]** is alleen beschikbaar als het bestand op de server is geüpload.
* **[!UICONTROL Auto-detect format]** wordt gebruikt om de indeling van de gegevensbron opnieuw te initialiseren. Met deze optie kunt u de oorspronkelijke indelingen opnieuw toepassen op gegevens die zijn opgemaakt via de optie **[!UICONTROL Click here to change the file format...]** .
* Met de koppeling **[!UICONTROL Advanced parameters]** kunt u de brongegevens filteren en geavanceerde opties gebruiken. Vanuit dit scherm kunt u ervoor kiezen om slechts een deel van het bestand te importeren. U kunt ook een filter definiëren, bijvoorbeeld om alleen gebruikers van het type Prospect of Klant te importeren, op basis van de waarde van de corresponderende regel. Deze opties mogen alleen worden gebruikt door deskundige JavaScript-gebruikers.

### De bestandsindeling wijzigen {#changing-the-file-format}

Met de optie **[!UICONTROL Click here to change the file format...]** kunt u de gegevens van het bronbestand opmaken, en met name het kolomscheidingsteken en het type gegevens voor elk veld opgeven. Deze configuratie wordt uitgevoerd via het volgende venster:

![](assets/s_ncs_user_import_wizard02_3.png)

In deze stap kunt u beschrijven hoe de waarden van de bestandsvelden moeten worden gelezen. In het geval van een datum kunnen de datum- of datum- en tijdgegevens bijvoorbeeld worden gekoppeld aan een notatie (dd/mm/jjjj, mm/dd/jj, enz.). Als de invoergegevens niet overeenkomen met de verwachte indeling, worden deze tijdens het importeren geweigerd.

U kunt het resultaat van de configuratie weergeven in de voorvertoningszone in het onderste gedeelte van het venster.

Klik op **[!UICONTROL OK]** om de opmaak op te slaan en klik vervolgens op **[!UICONTROL Next]** om de volgende stap weer te geven.

### Stap 3 - Toewijzing van velden {#step-3---field-mapping}

U moet dan het bestemmingsschema selecteren en de gegevens van elke kolom op gebieden in het gegevensbestand in kaart brengen.

![](assets/s_ncs_user_import_wizard03_1.png)

* In het veld **[!UICONTROL Destination schema]** kunt u het schema selecteren waarin de gegevens worden geïmporteerd. Deze informatie is verplicht. Klik op het pictogram **[!UICONTROL Select link]** om een van de bestaande schema&#39;s te selecteren. Klik op **[!UICONTROL Edit link]** om de inhoud van de geselecteerde tabel weer te geven.
* In de centrale tabel staan alle velden die in het bronbestand zijn gedefinieerd. Selecteer de velden die u wilt importeren om er een doelbestand aan te koppelen. Deze velden kunnen handmatig of automatisch worden toegewezen.

  Als u een veld handmatig wilt toewijzen, klikt u op het selectievakje om het bronveld te selecteren en klikt u op de tweede kolom om de cel te activeren die overeenkomt met het geselecteerde veld. Klik vervolgens op het pictogram **[!UICONTROL Edit expression]** om alle velden van de huidige tabel weer te geven. Selecteer het doelveld en klik op **[!UICONTROL OK]** om de toewijzing te valideren.

  Als u de bronvelden en doelvelden automatisch wilt koppelen, klikt u op het pictogram **[!UICONTROL Guess the destination fields]** rechts van de lijst met velden. De voorgestelde velden kunnen indien nodig worden gewijzigd.

  >[!IMPORTANT]
  >
  >Het resultaat van deze bewerking moet altijd worden gevalideerd voordat u verdergaat met de volgende stap.

* U kunt een transformatie toepassen op de geïmporteerde velden. Klik hiertoe in de cel van de kolom **[!UICONTROL Transformation]** die betrekking heeft op het desbetreffende veld en selecteer de transformatie die u wilt toepassen.

  ![](assets/s_ncs_user_import_wizard03_2.png)

  >[!IMPORTANT]
  >
  >De transformatie wordt toegepast op het moment van importeren. Als beperkingen op het bestemmingsgebied, echter (in het bovenstaande voorbeeld, op het @lastname gebied) zijn bepaald, nemen deze beperkingen prioriteit.

* U kunt berekende velden toevoegen met het juiste pictogram rechts van de centrale tabel. Met berekende velden kunt u complexe transformaties uitvoeren, virtuele kolommen toevoegen of de gegevens van meerdere kolommen samenvoegen. Raadpleeg de volgende secties voor meer informatie over de verschillende mogelijkheden.

#### Berekende velden {#calculated-fields}

Berekende velden zijn nieuwe kolommen die aan het bronbestand worden toegevoegd en uit andere kolommen worden berekend. Berekende velden kunnen vervolgens worden gekoppeld aan velden in de Adobe Campaign-database. Afstemmingen zijn echter niet mogelijk op berekende velden.

Er zijn vier typen berekende velden:

* **[!UICONTROL Fixed string]** : de waarde van het berekende veld is gelijk voor alle regels van het bronbestand. Hiermee kunt u de waarde instellen van een veld met records die zijn ingevoegd of bijgewerkt. U kunt bijvoorbeeld voor alle geïmporteerde records een markering instellen op &quot;ja&quot;.
* **[!UICONTROL String with JavaScript tags]**: de waarde van het berekende veld is een tekenreeks met JavaScript-opdrachten.
* **[!UICONTROL JavaScript expression]**: de waarde van het berekende veld is het resultaat van de evaluatie van een JavaScript-functie. De geretourneerde waarde kan een getal, een datum enzovoort zijn.
* **[!UICONTROL Enumeration]** : de waarde van het veld wordt toegewezen op basis van een waarde in het bronbestand. De redacteur laat u de bronkolom specificeren en de lijst van opsommingswaarden ingaan, zoals in het volgende voorbeeld:

  ![](assets/s_ncs_user_import_wizard03_3.png)

  Op het tabblad **[!UICONTROL Preview]** kunt u het resultaat van de gedefinieerde configuratie weergeven. Hier is de kolom **[!UICONTROL Subscription]** toegevoegd. De waarde wordt berekend van het **gebied van de Status**.

  ![](assets/s_ncs_user_import_wizard03_4.png)

### Stap 4 - Verzoening {#step-4---reconciliation}

Met de afstemmingsstap van de importassistent kunt u de modus definiëren waarmee de gegevens uit het bestand worden afgestemd op de bestaande gegevens in de database en kunt u de prioriteitsregels instellen tussen de bestandsgegevens en de databasegegevens. Het configuratievenster ziet er als volgt uit:

![](assets/s_ncs_user_import_wizard04_1.png)

Het centrale gedeelte van het scherm bevat een structuur met de velden en tabellen van de Adobe Campaign-database waarnaar de gegevens worden geïmporteerd.

Er zijn speciale opties beschikbaar voor elk knooppunt (tabel of veld). Wanneer u op het betrokken knooppunt klikt in de lijst, worden de parameters en een korte beschrijving ervan hieronder weergegeven. Het gedrag dat voor elk element wordt gedefinieerd, wordt weergegeven in de corresponderende **[!UICONTROL Behavior]** -kolom.

![](assets/s_ncs_user_import_wizard04_2.png)

#### Soorten bewerkingen {#types-of-operation}

Voor elke tabel waarop de invoer betrekking heeft, moet u het type bewerking definiëren. De volgende bewerkingen zijn beschikbaar voor het hoofdelement van de database:

* **[!UICONTROL Update or insertion]** : werkt de record bij als deze in de database bestaat en maakt deze zo niet.
* **[!UICONTROL Insertion]**: voegt records in de database in.
* **[!UICONTROL Update]**: werkt alleen bestaande records bij (negeert andere records).
* **[!UICONTROL Reconciliation only]**: zoekt naar de record in de database, maar voert geen update uit. Hiermee kunt u bijvoorbeeld de map met ontvangers koppelen om te importeren volgens een kolom van het bestand zonder de gegevens in de mappen bij te werken.
* **[!UICONTROL Deletion]**: hiermee kunt u records in de database vernietigen.

De volgende opties zijn beschikbaar voor elk veld in de tabel waarop de invoer betrekking heeft:

* **[!UICONTROL Update (empty) if source value is empty]**: in het geval van een update verwijdert de waarde in het veld de databasewaarde als het veld leeg is in het bronbestand. Anders wordt het databaseveld bewaard.
* **[!UICONTROL Update only if destination is empty]**: de waarde van het bronbestand overschrijft de waarde in het databaseveld alleen als het databaseveld leeg is. In dat geval wordt de waarde van het bronbestand gebruikt.
* **[!UICONTROL Update the field only when the record is inserted]**: tijdens een update- of invoegbewerking worden alleen nieuwe bronbestandsrecords geïmporteerd.

>[!NOTE]
>
>De definitie van een verzoeningssleutel is altijd **verplicht**, behalve in het geval van toevoeging zonder deduplicatie.

#### Afstemmingssleutels {#reconciliation-keys}

Er moet ten minste één afstemmingssleutel worden ingevuld om deduplicatie te beheren.

Een afstemmingssleutel is een set velden die wordt gebruikt om een record te identificeren. Als u bijvoorbeeld ontvangers wilt importeren, kan de afstemmingssleutel het rekeningnummer, het veld E-mail of de velden Achternaam, Voornaam, Bedrijf zijn, enzovoort.

In dit geval vergelijkt de importengine de waarden van het bestand met die van de database voor alle velden van de sleutel om te zien of een regel van een bestand overeenkomt met een bestaande ontvanger in de database. Wanneer velden specifiek zijn voor een record, kan een nauwkeurige vergelijking tussen de bron- en de doelgegevens worden uitgevoerd, zodat de integriteit van de gegevens na het importeren wordt gegarandeerd. Een tweede afstemmingssleutel kan worden ingevuld voor dezelfde tabel; deze wordt gebruikt voor de regels waarvan de eerste sleutel leeg is.

Kies geen veld dat tijdens het importeren kan worden gewijzigd. Als dit gebeurt, kan de engine aanvullende records maken.

![](assets/s_ncs_user_import_wizard04_3.png)

>[!NOTE]
>
>Voor het importeren van ontvangers wordt de id van de geselecteerde map impliciet aan de sleutel toegevoegd.
>
>Afstemming wordt daarom alleen op deze map uitgevoerd (tenzij er geen map is geselecteerd).

#### Deduplicatie {#deduplication}

>[!NOTE]
>
>Een &#39;dubbel&#39; is een item dat twee of meer keren voorkomt in het bestand dat moet worden geïmporteerd.
>
>Een &#39;duplicaat&#39; is een item dat aanwezig is in het bestand dat moet worden geïmporteerd en in de database.

In het veld **[!UICONTROL Management of doubles]** kunt u de deduplicatie van gegevens configureren. De deduplicatie heeft betrekking op verslagen die verscheidene tijden **in het brondossier** (of brondossiers in het geval van een veelvoudig-dossierinvoer) verschijnen, d.w.z. lijnen waarvoor de gebieden van de verzoeningssleutel identiek zijn.

* Duplicaatbeheer in de modus **[!UICONTROL Update]** (de standaardmodus) voert geen deduplicatie uit. De laatste record heeft daarom prioriteit (omdat deze de gegevens van de voorgaande records bijwerkt). Het tellen van duplicaten wordt niet uitgevoerd in deze modus.
* Bij gedupliceerd beheer in de modus **[!UICONTROL Ignore]** of **[!UICONTROL Reject entity]** worden duplicaten van het importeren uitgesloten. In dit geval wordt geen record geïmporteerd.
* In de modus **[!UICONTROL Reject entity]** wordt het element niet geïmporteerd en wordt een fout gegenereerd in de importlogboeken.
* In de modus **[!UICONTROL Ignore]** wordt het element niet geïmporteerd, maar wordt geen spoor van de fout behouden. In deze modus kunt u de prestaties optimaliseren.

>[!IMPORTANT]
>
>Deduplicatie wordt alleen in het geheugen uitgevoerd. De omvang van een invoer met deduplicatie is daarom beperkt. De limiet is afhankelijk van verschillende parameters (capaciteit van de toepassingsserver, activiteit, aantal velden in de sleutel, enz.). De maximale grootte voor een deduplicatie is ongeveer 1.000.000 regels.

Deduplicatie heeft betrekking op een record die zowel in het bronbestand als in de database aanwezig is. Het betreft bewerkingen met alleen update (d.w.z. **[!UICONTROL Update and insertion]** of **[!UICONTROL Update]** ). Met de optie **[!UICONTROL Duplicate management]** kunt u de record bijwerken of negeren als deze zich in zowel het bronbestand als de database bevindt. De optie **[!UICONTROL Update or insert based on origin]** behoort tot de optionele module en kan niet worden gebruikt in een standaardcontext.

De opties **[!UICONTROL Reject]** en **[!UICONTROL Ignore]** werken zoals hierboven beschreven.

### In geval van fout {#behavior-in-the-event-of-an-error}

De meeste gegevensoverdrachtsbewerkingen genereren verschillende soorten fouten (incoherente regelindeling, ongeldig e-mailadres, enz.). Alle fouten en waarschuwingen die door de importengine worden gegenereerd, worden opgeslagen en gekoppeld aan het importexemplaar.

![](assets/s_ncs_user_import_general_tab.png)

De details van deze afwijzing&#39;s kunnen worden weergegeven via het tabblad **[!UICONTROL Rejects]** .

![](assets/s_ncs_user_import_rejets_tab.png)

Er zijn twee typen afwijzing (het type wordt weergegeven in de kolom **[!UICONTROL Connector]** ):

* Afwijzingen van de tekstconnector hebben betrekking op fouten die optreden tijdens het verwerken van de bestandsregel (berekend veld, gegevensanalyse, enz.). In dit geval wordt bij een fout de hele regel altijd geweigerd.
* Afkeuringen van databaseverbindingen hebben betrekking op fouten die optreden tijdens het afstemmen van gegevens of het schrijven naar de database. In het geval van een import naar meerdere tabellen kan de afwijzing alleen betrekking hebben op een deel van de record (bijvoorbeeld bij het importeren van ontvangers en bijbehorende gebeurtenissen kan een fout het bijwerken van een gebeurtenis voorkomen zonder de ontvanger te negeren).

Op de pagina voor het afstemmen van gegevens kunt u het gewenste veld voor het type foutbeheer per veld en tabel per tabel definiëren.

* **[!UICONTROL Ignore and log a warning]**: alle velden worden geïmporteerd in de database, behalve de velden die een fout hebben gegenereerd.
* **[!UICONTROL Reject parent element]** : de volledige regel van de record wordt geweigerd, niet alleen het veld dat een fout heeft veroorzaakt.
* **[!UICONTROL Reject all elements]** : het importeren wordt gestopt en alle elementen van de record worden geweigerd.

  ![](assets/s_ncs_user_import_wizard04_4.png)

De structuur in het afstotingsscherm van een importinstantie geeft aan welke velden zijn geweigerd en waar de fouten zijn opgetreden.

U kunt een bestand met deze records genereren via het pictogram **[!UICONTROL Export rejects]** :

![](assets/s_ncs_user_import_errors_export.png)

### Stap 5 - Extra stap bij het importeren van ontvangers {#step-5---additional-step-when-importing-recipients}

In de volgende stap van de importassistent kunt u de map selecteren of maken waarin gegevens worden geïmporteerd, kunt u geïmporteerde ontvangers automatisch toewijzen aan een (nieuwe of bestaande) lijst en kunt u ontvangers aan een service toewijzen.

![](assets/s_ncs_user_import_wizard05_1.png)

>[!NOTE]
>
>Deze stap verschijnt wanneer het invoeren slechts ontvangers en wanneer het gebruiken van de standaardAdobe Campaign ontvangerslijst (**nms:recipient**).

* Klik op de koppelingen in **[!UICONTROL Edit]** om de map, de lijst of de service te selecteren waaraan u de ontvangers wilt koppelen of zich erop wilt abonneren.

   1. Importeren in een map

      Met de koppeling **[!UICONTROL Edit...]** in de sectie **[!UICONTROL Import into a folder]** kunt u de map selecteren of maken waarin de ontvangers worden geïmporteerd. Als standaard geen partitie is gedefinieerd, worden de gegevens geïmporteerd in de standaardmap van de operator.

      >[!NOTE]
      >
      >De standaardmap voor een operator is de eerste map waarvoor de operator schrijftoegang heeft. Leer meer in [&#x200B; leidt omslagen en meningen &#x200B;](../audiences/folders-and-views.md).

      Als u de importmap wilt selecteren, klikt u op de pijl rechts van het veld **[!UICONTROL Folder]** en selecteert u de desbetreffende map. U kunt het pictogram **[!UICONTROL Select link]** ook gebruiken om de structuur in een nieuw venster weer te geven of een nieuwe map te maken.

      ![](assets/s_ncs_user_import_wizard05_2.png)

      Als u een nieuwe map wilt maken, selecteert u het knooppunt waaruit u een map wilt toevoegen en klikt u met de rechtermuisknop. Selecteer **[!UICONTROL Create a new 'Recipients' folder]**.

      ![](assets/s_ncs_user_import_wizard05_3.png)

      De map wordt toegevoegd onder het huidige knooppunt. Voer de naam van de nieuwe map in, klik op Enter om te bevestigen en klik op **[!UICONTROL OK]** .

      ![](assets/s_ncs_user_import_wizard05_4.png)

   1. Koppelen aan een lijst

      Met de koppeling **[!UICONTROL Edit...]** in de sectie **[!UICONTROL Add recipients to a list]** kunt u een lijst selecteren of maken waarin de ontvangers worden geïmporteerd.

      ![](assets/s_ncs_user_import_wizard05_5.png)

      U kunt een nieuwe lijst voor deze ontvangers maken door op **[!UICONTROL Select link]** en vervolgens op **[!UICONTROL Create]** te klikken.

      ![](assets/s_ncs_user_import_wizard05_6.png)

      U kunt besluiten om de ontvangers aan degenen toe te voegen die reeds in een lijst aanwezig zijn, of de lijst met de nieuwe ontvangers opnieuw te maken. In dit geval worden ontvangers verwijderd en vervangen door de geïmporteerde ontvangers als de lijst al ontvangers bevatte.

   1. Abonneren op een service

      Als u alle geïmporteerde ontvangers wilt abonneren op een informatieservice, klikt u op de koppeling **[!UICONTROL Edit...]** in de sectie **[!UICONTROL Subscribe recipients to a service]** om de informatieservice te selecteren of te maken waarop de ontvangers zich moeten abonneren. U kunt de optie **[!UICONTROL Send a confirmation message]** selecteren: de inhoud van dit bericht wordt gedefinieerd in de leveringssjabloon die is gekoppeld aan de abonnementenservice.

      ![](assets/s_ncs_user_import_wizard05_7.png)

      U kunt een nieuwe service voor deze ontvangers maken door op **[!UICONTROL Select link]** en vervolgens op het pictogram **[!UICONTROL Create]** te klikken. Het beheer van de informatiediensten wordt voorgesteld in [&#x200B; deze sectie &#x200B;](../start/subscriptions.md).

* Gebruik het veld **[!UICONTROL Origin]** om informatie over de oorsprong van ontvangers toe te voegen aan hun profielen. Deze informatie is met name nuttig in het kader van een meervoudige import.

Klik op **[!UICONTROL Next]** om deze stap te valideren en de volgende stap weer te geven.

### Stap 6 - Het importeren starten {#step-6---launching-the-import}

In de laatste stap van de assistent kunt u gegevensimport starten. Klik hiertoe op de knop **[!UICONTROL Start]** .

![](assets/s_ncs_user_import_wizard06_1.png)

U kunt de uitvoering van de de invoerbaan dan controleren (zie [&#x200B; de werkschemauitvoering van de Monitor &#x200B;](../../automation/workflow/monitor-workflow-execution.md)).

## Gegevens exporteren

Met de exporttaken hebt u toegang tot gegevens in de database en kunt u deze ophalen: contactpersonen, clients, lijsten, segmenten enzovoort.

Het kan bijvoorbeeld handig zijn om gegevens over het bijhouden van campagnes (geschiedenis bijhouden, enz.) in een spreadsheet te gebruiken. De uitvoergegevens kunnen de indeling TXT, CSV, TAB of XML hebben.

Met de exportassistent kunt u een exportbewerking configureren, opties definiëren en uitvoering starten. Het is een reeks schermen waarvan de inhoud afhankelijk is van het type export (eenvoudig of meervoudig) en de rechten van de operator.

De exportassistent wordt weergegeven nadat een nieuwe exporttaak is gemaakt.

### Stap 1 - Kies de exportsjabloon {#step-1---choosing-the-export-template}

Wanneer u de exportassistent start, moet u eerst een sjabloon selecteren. Als voorbeeld, om de uitvoer van ontvangers te vormen die onlangs registreerden, volg de stappen hieronder:

1. Selecteer de map **[!UICONTROL Profiles and Targets > Job > Generic imports and exports]** .
1. Klik **Nieuw** en klik dan **Uitvoer** om het uitvoermalplaatje tot stand te brengen.

   ![](assets/s_ncs_user_export_wizard01.png)

1. Klik op de pijl rechts van het veld **[!UICONTROL Export template]** om de sjabloon te selecteren of klik op **[!UICONTROL Select link]** om door de structuur te bladeren.

   De native sjabloon is **[!UICONTROL New text export]** . Deze sjabloon moet niet worden gewijzigd, maar u kunt het dupliceren om een nieuwe sjabloon te configureren. Exportsjablonen worden standaard opgeslagen in het knooppunt **[!UICONTROL Resources > Templates > Job templates]** .

1. Voer in het veld **[!UICONTROL Label]** een naam in voor het exporteren. U kunt een beschrijving toevoegen.
1. Selecteer het exporttype. Er zijn twee mogelijke exporttypen: **[!UICONTROL Simple export]** om slechts één bestand te exporteren en **[!UICONTROL Multiple export]** om meerdere bestanden in één uitvoering uit een of meer typen brondocument te exporteren.

### Stap 2 - Type bestand dat moet worden geëxporteerd {#step-2---type-of-file-to-export}

Selecteer het type document dat u wilt exporteren, dat wil zeggen het schema van de gegevens die u wilt exporteren.

Wanneer het exporteren wordt gestart vanuit het knooppunt **[!UICONTROL Jobs]** , komen de gegevens standaard uit de tabel met ontvangers. Wanneer het exporteren wordt gestart vanuit een lijst met gegevens (vanuit het menu **[!UICONTROL right click > Export]** ), wordt de tabel waartoe de gegevens behoren automatisch ingevuld in het veld **[!UICONTROL Document type]** .

![](assets/s_ncs_user_export_wizard02.png)

* Standaard is de optie **[!UICONTROL Download the file generated on the server after the export]** geselecteerd. Vul in het veld **[!UICONTROL Local file]** de naam en het pad in van het bestand dat u wilt maken, of blader door de lokale schijf door op de map rechts van het veld te klikken. U kunt deze optie deselecteren om het toegangspad en de naam van het uitvoerbestand van de server in te voeren.

  >[!NOTE]
  >
  >Taken voor automatisch importeren en exporteren worden altijd op de server uitgevoerd.
  >
  >Als u slechts enkele gegevens wilt exporteren, klikt u op **[!UICONTROL Advanced parameters]** en voert u in het desbetreffende veld het aantal regels in dat u wilt exporteren.

* U kunt een differentiële exportbewerking maken om alleen records te exporteren die sinds de laatste uitvoering zijn gewijzigd. Klik hiertoe op de koppeling **[!UICONTROL Advanced parameters]** , klik vervolgens op de tab **[!UICONTROL Differential export]** en selecteer **[!UICONTROL Activate differential export]** .

  ![](assets/s_ncs_user_export_wizard02_b.png)

  U moet de datum van de laatste wijziging invoeren. Deze kan worden opgehaald uit een veld of berekend.

### Stap 3 - Bepaal de outputformaat {#step-3---defining-the-output-format}

Selecteer een uitvoerindeling voor het exportbestand. De volgende indelingen kunnen worden gebruikt: tekst, tekst met een vaste kolom, CSV en XML.

![](assets/s_ncs_user_export_wizard03.png)

* Selecteer bij de notatie **[!UICONTROL Text]** de scheidingstekens tussen de kolommen (tabs, komma&#39;s, puntkomma&#39;s of aangepast) en de tekenreeksen (enkele of dubbele aanhalingstekens of geen).
* Voor **[!UICONTROL text]** en **[!UICONTROL CSV]** kunt u de optie **[!UICONTROL Use first lines as column titles]** selecteren.
* Geef de datumnotatie en getalnotatie op. Klik hiertoe op de knop **[!UICONTROL Edit]** voor het desbetreffende veld en gebruik de editor.
* Voor velden met opsommingswaarden kunt u **[!UICONTROL Export labels instead of internal values of enumerations]** selecteren. Bijvoorbeeld, kan de titel in de vorm **worden opgeslagen 1=Mr.**, **2=Onjuffrouw**, **3=Mevrouw.**. Als deze optie wordt geselecteerd, **Mr.**, **juf** en **mevrouw** zal worden uitgevoerd.

### Stap 4 - Selectie van gegevens {#step-4---data-selection}

Selecteer de te exporteren velden. Dit doet u als volgt:

1. Dubbelklik op de gewenste velden in de lijst **[!UICONTROL Available fields]** om deze toe te voegen aan de sectie **[!UICONTROL Output columns]** .
1. Gebruik de pijlen rechts van de lijst om de volgorde van de velden in het uitvoerbestand te definiëren.

   ![](assets/s_ncs_user_export_wizard04.png)

1. Klik op de knop **[!UICONTROL Add]** om functies aan te roepen.

### Stap 5 - Kolommen sorteren {#step-5---sorting-columns}

Selecteer de sorteervolgorde van de kolommen.

![](assets/s_ncs_user_export_wizard05.png)

### Stap 6 - Filtervoorwaarden {#step-6---filter-conditions-}

U kunt filtervoorwaarden toevoegen om het exporteren van alle gegevens te voorkomen. De configuratie van dit het filtreren is het zelfde als ontvankelijke het richten in de leveringsmedewerker.

![](assets/s_ncs_user_export_wizard05_b.png)

### Stap 7 - Gegevensopmaak {#step-7---data-formatting}

U kunt de volgorde en het label van de velden voor het uitvoerbestand wijzigen en transformaties op de brongegevens toepassen.

* Als u de volgorde van de kolommen die u wilt exporteren wilt wijzigen, selecteert u de desbetreffende kolom en gebruikt u de blauwe pijlen rechts van de tabel.
* Als u het label van een veld wilt wijzigen, klikt u in de cel van de kolom **[!UICONTROL Label]** die overeenkomt met het veld dat u wilt wijzigen, en voert u het nieuwe label in. Druk op Enter op het toetsenbord om te bevestigen.
* Als u een hoofdlettertransformatie wilt toepassen op de inhoud van een veld, selecteert u deze in de kolom **[!UICONTROL Transformation]** . U kunt selecteren:

   * Overschakelen naar kleine letters
   * Overschakelen naar hoofdletters
   * Eerste letter in hoofdletters

  ![](assets/s_ncs_user_export_wizard06.png)

* Klik op **[!UICONTROL Add a calculated field]** als u een nieuw berekend veld wilt maken (bijvoorbeeld een kolom met de achternaam en de voornaam). Raadpleeg de sectie Gegevens importeren voor meer informatie.

Als u een verzameling elementen exporteert (bijvoorbeeld abonnementen van ontvangers, lijsten waartoe ze behoren, enz.), moet u het aantal elementen in de verzameling opgeven dat u wilt exporteren.

![](assets/s_ncs_user_export_wizard06_c.png)

### Stap 8 - Voorvertoning gegevens {#step-8---data-preview}

Klik op **[!UICONTROL Start the preview of the data]** voor een voorvertoning van het exportresultaat. Standaard worden de eerste 200 regels weergegeven. Als u deze waarde wilt wijzigen, klikt u op de pijlen rechts van het veld **[!UICONTROL Lines to display]** .

![](assets/s_ncs_user_export_wizard07.png)

Klik de lusjes bij de bodem van de medewerker om van de voorproef van resultaten in kolommen aan de resultaten in XML over te schakelen. U kunt de gegenereerde SQL-query&#39;s ook weergeven.

### Stap 9 - Het exporteren starten {#step-9---launching-the-export}

Klik op **[!UICONTROL Start]** om het exporteren van gegevens te starten.

![](assets/s_ncs_user_export_wizard08.png)

Vervolgens kunt u de uitvoering van de importtaak controleren.


## Profielen verzamelen via webtoepassingen

Met Campagne kunt u webformulieren maken en profielgegevens eenvoudig en efficiënt verzamelen en beheren. U kunt deze formulieren delen op uw website, zodat uw contactpersonen gemakkelijk hun gegevens kunnen verstrekken. Hun informatie wordt verzonden naar Campagne om hun profiel tot stand te brengen of hun informatie bij te werken als zij reeds in het gegevensbestand aanwezig zijn.

![](assets/web-form-page.png)

Leer hoe te om Webvormen in [&#x200B; Campaign Classic v7 documentatie &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html){target="_blank"} tot stand te brengen.

**Verwante onderwerpen**

* [Soorten publiek maken](audiences.md)
* [Gedupliceerde profielen](../../automation/workflow/deduplication-merge.md)
* [Profielgegevens vergroten](../../automation/workflow/enrich-data.md)
* Begrijp Campagne [&#x200B; gegevensmodel &#x200B;](../dev/datamodel.md)