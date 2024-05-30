---
title: Werken met gegevenspakketten
description: Werken met gegevenspakketten
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
source-git-commit: 202a0553f0c736086eca993b9647737732f57d07
workflow-type: tm+mt
source-wordcount: '1941'
ht-degree: 0%

---

# Werken met gegevenspakketten{#data-packages}

## Aan de slag met pakketten {#gs-data-packages}

Met gegevenspakketten kunt u aangepaste instellingen en gegevens van uw platform exporteren en importeren. Een pakket kan verschillende typen configuraties en componenten bevatten, al dan niet gefilterd.

In de gegevenspakketten van de Campagne, worden de entiteiten van het gegevensbestand van Adobe Campaign getoond in de dossiers van XML. In een pakket wordt elke entiteit vertegenwoordigd met al haar gegevens.

Het beginsel van **gegevenspakketten** moet een gegevensconfiguratie exporteren en integreren in een andere Adobe Campaign-omgeving. Leer hoe u een consistente set gegevenspakketten in deze [sectie](#data-package-best-practices).

### Typen pakketten {#types-of-packages}

U kunt in Adobe Campaign met drie typen pakketten werken: gebruikerspakketten, platformpakketten en beheerpakketten.

* A **gebruikerspakket** Hiermee selecteert u de lijst met entiteiten die u wilt exporteren. Dit type pakket beheert afhankelijkheden en controleert fouten.
* A **platformpakket** bevat alle toegevoegde technische bronnen (niet-standaard): schema&#39;s, JavaScript-code, enz.
* An **beheerpakket** bevat alle toegevoegde sjablonen en bedrijfsobjecten (niet-standaard): sjablonen, bibliotheken, enz.

>[!CAUTION]
>
>De **platform** en **admin** pakketten bevatten een vooraf gedefinieerde lijst met te exporteren entiteiten. Elke entiteit is verbonden met het filtreren voorwaarden die u toelaten om de uit-van-de-doosmiddelen van het gecreeerde pakket te verwijderen.

## Gegevensstructuur {#data-structure}

De beschrijving van een gegevenspakket is een gestructureerd XML-document dat voldoet aan de grammatica van de **xrk:navtree** gegevensschema, zoals in het onderstaande voorbeeld:

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

Het XML-document moet beginnen en eindigen met het `<package>` element. Alle `<entities>` elementen die volgen, verdelen de gegevens per documenttype. An `<entities>` element bevat de gegevens van het pakket in de indeling van het gegevensschema dat is ingevoerd in het dialoogvenster **schema** kenmerk. De gegevens in een pakket mogen geen interne sleutels bevatten die niet compatibel zijn tussen databases, zoals automatisch gegenereerde toetsen (**automatische** ).

In ons voorbeeld worden de `folder` en `company` koppelingen zijn vervangen door zogenaamde &quot;toetsen op hoog niveau&quot; in de doeltabellen:

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

De `operation` kenmerk met de waarde `none` definieert een afstemmingskoppeling.

Een gegevenspakket kan manueel van om het even welke tekstredacteur worden gebouwd. U moet ervoor zorgen dat de structuur van het XML-document voldoet aan de `xtk:navtree` gegevensschema. De clientconsole heeft een export- en importmodule voor gegevenspakketten.

## Pakketten exporteren {#export-packages}

U kunt pakketten op drie verschillende manieren exporteren:

* Gebruik de **[!UICONTROL Package Export]** De assistent voor het exporteren van een set objecten in één pakket. [Meer informatie](#export-a-set-of-objects-in-a-package)
* Als u een **één object**, klikt u er met de rechtermuisknop op en selecteert u **[!UICONTROL Actions > Export in a package]**.
* Gebruik de **Pakketdefinities** om een pakketstructuur te maken waarin u objecten toevoegt die u later in een pakket wilt exporteren. [Meer informatie](#manage-package-definitions)

Nadat een pakket is geëxporteerd, kunt u het pakket en alle toegevoegde entiteiten importeren in een andere Campagne-instantie.

### Een set objecten in een pakket exporteren {#export-a-set-of-objects-in-a-package}

Ga als volgt te werk om een set objecten in een gegevenspakket te exporteren:

1. Blader naar de exportassistent voor het pakket via de **[!UICONTROL Tools > Advanced > Export package...]** menu van de verkenner.
1. Selecteer de [typen pakketten](#types-of-packages).

   ![](assets/package_type.png)

1. Klik op de knop **Toevoegen** om de entiteiten te selecteren die u als een pakket wilt exporteren.

   >[!CAUTION]
   >
   >Als u een **[!UICONTROL Offer category]**, **[!UICONTROL Offer environment]**, **[!UICONTROL Program]** of **[!UICONTROL Plan]** typemap, nooit selecteren **xtk:map** omdat u mogelijk gegevens kwijtraakt. Selecteer de entiteit die overeenkomt met de map: **nms:aanbiedingenCategorie** voor aanbiedingrubrieken, **nms:aanbiedingEnv** voor aanbiedingsomgevingen, **nms:programma** voor programma&#39;s, en **nms:plan** voor plannen.

   Het afhankelijkheidsmechanisme bestuurt de uitvoersequentie van de entiteit. Raadpleeg voor meer informatie hierover [Afhankelijkheden beheren](#manage-dependencies).

1. Klikken **[!UICONTROL Next]** en definieert u de filterquery voor het type document dat u wilt extraheren. U moet de het filtreren clausule voor gegevensextractie vormen.

   >[!NOTE]
   >
   >De query-editor wordt weergegeven in [deze sectie](../../automation/workflow/query.md).

1. Klikken **[!UICONTROL Next]** en selecteert u de sorteervolgorde van de geëxporteerde gegevens.

1. Bekijk een voorvertoning van de gegevens die u wilt extraheren om uw configuratie te controleren.

1. Op de laatste pagina van de exportassistent voor pakketten kunt u het exporteren starten. De gegevens worden opgeslagen in het bestand dat in het dialoogvenster **[!UICONTROL File]** veld.

### Afhankelijkheden beheren {#manage-dependencies}

Tijdens het exportproces worden de koppelingen tussen de verschillende geëxporteerde elementen bijgehouden. Dit mechanisme wordt gedefinieerd door twee regels:

* objecten die zijn gekoppeld aan een koppeling met een `own` of `owncopy` Tekstintegriteit wordt geëxporteerd in hetzelfde pakket als het geëxporteerde object.
* objecten die gekoppeld zijn aan een koppeling met een `neutral` of `define` de tekstintegriteit (gedefinieerde koppeling) moet afzonderlijk worden geëxporteerd.

>[!NOTE]
>
>Integriteitstypen die zijn gekoppeld aan schema-elementen worden gedefinieerd in [deze pagina](database-links.md).

#### Een campagne exporteren {#export-a-campaign}

Hieronder ziet u hoe u een campagne kunt exporteren. De uit te voeren marketingcampagne bevat:
* a `MyTask`taak
* a `campaignWorkflow` workflow in de volgende map: **[!UICONTROL Administration > Production > Technical workflows > Campaign processes > MyWorkflow]**.

De taak en de workflow worden in hetzelfde pakket als de campagne geëxporteerd, aangezien de overeenkomende schema&#39;s via koppelingen met een `own` typedonaliteit.

De inhoud van het pakket is:

```xml
<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

De verbinding met een type pakket wordt bepaald in een schema met het `@pkgAdmin and @pkgPlatform` kenmerk. Beide eigenschappen ontvangen een XTK-expressie die de voorwaarden voor aansluiting bij het pakket definieert.

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

Tot slot de `@pkgStatus` kunt u de exportregels voor deze elementen of kenmerken definiëren. Afhankelijk van de waarde van het kenmerk, wordt het element of kenmerk gevonden in het geëxporteerde pakket. De drie mogelijke waarden voor dit kenmerk zijn:

* `never`: exporteert het veld / de koppeling niet
* `always`: forceert export voor dit veld
* `preCreate`: staat oprichting van de gekoppelde entiteit toe

>[!NOTE]
>
>De `preCreate` waarde wordt alleen geaccepteerd voor gebeurtenissen met het koppelingstype. Hiermee kunt u een entiteit maken of ernaar verwijzen die nog niet in het geëxporteerde pakket is geladen.

## Pakketdefinities beheren {#manage-package-definitions}

Met pakketdefinities kunt u een pakketstructuur maken waarin u entiteiten toevoegt die later in één pakket worden geëxporteerd. Vervolgens kunt u dit pakket en alle toegevoegde entiteiten importeren in een andere Campagne-instantie.

### Een pakketdefinitie maken {#create-a-package-definition}

Pakketdefinities zijn toegankelijk via de **[!UICONTROL Administration > Configuration > Package management > Package definitions]** -menu.

Als u een pakketdefinitie wilt maken, klikt u op de knop **[!UICONTROL New]** en vul vervolgens de algemene informatie over de pakketdefinitie in.

![](assets/packagedefinition_create.png)

Vervolgens kunt u entiteiten toevoegen aan de pakketdefinitie en deze exporteren naar een XML-bestandspakket.

**Verwante onderwerpen:**

* [Entiteiten toevoegen aan een pakketdefinitie](#add-entities-to-a-package-definition)
* [Genereren van pakketdefinities configureren](#configure-package-definitions-generation)
* [Pakketten uit een pakketdefinitie exporteren](#export-packages-from-a-package-definition)

### Entiteiten toevoegen aan een pakketdefinitie {#add-entities-to-a-package-definition}

In de **[!UICONTROL Content]** klikt u op de knop **[!UICONTROL Add]** om de entiteiten te selecteren die u met het pakket wilt exporteren. Aanbevolen werkwijzen bij het selecteren van entiteiten in het dialoogvenster [deze sectie](#export-a-set-of-objects-in-a-package).

![](assets/packagedefinition_addentities.png)

Entiteiten kunnen rechtstreeks vanaf hun locatie in de instantie aan een pakketdefinitie worden toegevoegd. Hiervoor voert u de volgende stappen uit:

1. Klik met de rechtermuisknop op de gewenste entiteit en selecteer vervolgens **[!UICONTROL Actions > Export in a package]**.

1. Selecteren **[!UICONTROL Add to a package definition]** Selecteer vervolgens de pakketdefinitie waaraan u de entiteit wilt toevoegen.

1. De entiteit wordt toegevoegd aan de pakketdefinitie en wordt geëxporteerd met het pakket (zie [deze sectie](#export-packages-from-a-package-definition)).

### Genereren van pakketdefinities configureren {#configure-package-definitions-generation}

Pakketgeneratie kan worden geconfigureerd via de pakketdefinitie **[!UICONTROL Content]** tab. Om dit te doen, klik **[!UICONTROL Generation parameters]** koppeling.

![](assets/packagedefinition_generationparameters.png)

* Gebruik de **[!UICONTROL Include the definition]** -optie om de definitie op te nemen die momenteel wordt gebruikt in de pakketdefinitie.
* Gebruik de **[!UICONTROL Include an installation script]** om een JavaScript-script toe te voegen dat moet worden uitgevoerd bij het importeren van het pakket. Als deze optie is geselecteerd, wordt een **[!UICONTROL Script]** wordt toegevoegd in het scherm met pakketdefinities.
* Gebruik de **[!UICONTROL Include default values]** om de waarden van alle kenmerken van de entiteiten toe te voegen aan het pakket.

  Deze optie is niet standaard geselecteerd om lange exportbewerkingen te voorkomen. Dit betekent dat kenmerken van entiteiten met standaardwaarden (&#39;lege tekenreeks&#39;, &#39;0&#39; en &#39;onwaar&#39; als deze niet anders in het schema zijn gedefinieerd) standaard niet aan het pakket worden toegevoegd en daarom niet worden geëxporteerd.

  >[!CAUTION]
  >
  >Als de instantie waarin het pakket wordt geïmporteerd, entiteiten bevat die identiek zijn aan die van het pakket (bijvoorbeeld met dezelfde externe id), worden de kenmerken ervan niet bijgewerkt. Dit kan gebeuren als de kenmerken van de eerste instantie standaardwaarden hebben, omdat ze niet in het pakket zijn opgenomen. In dat geval selecteert u de **[!UICONTROL Include default values]** deze optie voorkomt dat versies worden samengevoegd , aangezien alle kenmerken van de eerste instantie samen met het pakket worden geëxporteerd .

### Pakketten uit een pakketdefinitie exporteren {#export-packages-from-a-package-definition}

Voer de volgende stappen uit om een pakket uit een pakketdefinitie te exporteren:

1. Selecteer de pakketdefinitie die u wilt exporteren, klik op de knop **[!UICONTROL Actions]** en selecteert u **[!UICONTROL Export the package]**.
1. Controleer de naam en locatie van het geëxporteerde bestand.
1. Klik op de knop **[!UICONTROL Start]** om het exporteren te starten.

## Pakketten importeren {#import-packages}

De importassistent voor het pakket is toegankelijk via het hoofdmenu **[!UICONTROL Tools > Advanced > Import package]** van de clientconsole.

### Een pakket uit een bestand installeren {#install-a-package-from-a-file}

Voer de volgende stappen uit om een bestaand gegevenspakket te importeren:

1. De importassistent openen via het hoofdmenu **[!UICONTROL Tools > Advanced > Import package]** van de clientconsole.
1. Selecteer het XML-bestand en klik op **[!UICONTROL Open]**.

De inhoud van het te importeren pakket wordt vervolgens in het middelste gedeelte van de editor weergegeven.

Klikken **[!UICONTROL Next]** en **[!UICONTROL Start]** om het importeren te starten.

### Een ingebouwd pakket installeren {#install-a-standard-package}

Ingebouwde pakketten (ook bekend als (standaardpakketten) worden geïnstalleerd wanneer de Adobe Campaign wordt geconfigureerd. Afhankelijk van uw machtigingen, uw implementatiemodel en uw productaanbod kunt u nieuwe standaardpakketten importeren.

Raadpleeg de licentieovereenkomst om te controleren welke pakketten u kunt installeren.

## Aanbevolen werkwijzen voor gegevenspakketten {#data-package-best-practices}

In deze sectie wordt beschreven hoe u gegevenspakketten op consistente wijze kunt ordenen gedurende de levensduur van het project.


### Versies

U moet altijd importeren binnen dezelfde versie van het platform. U moet controleren dat u uw pakketten tussen twee instanties opstelt die de zelfde bouwstijl hebben. Dwing nooit de import en werk altijd eerst het platform bij (als de build anders is).

>[!IMPORTANT]
>
>Importeren tussen verschillende versies wordt niet ondersteund door de Adobe.

Let op het schema en de databasestructuur. Het invoeren van een pakket met schema moet door schemageneratie worden gevolgd.

### Pakkettypen {#package-types}

Begin door verschillende typen pakketten te definiëren. Er worden slechts vier typen gebruikt:

**Entiteiten**

* Alle &quot;xtk&quot;- en &quot;nms&quot;-specifieke elementen in Adobe Campaign, zoals schema&#39;s, formulieren, mappen, leveringssjablonen, enz.
* U kunt een entiteit beschouwen als zowel een element &quot;admin&quot; als een element &quot;platform&quot;.
* U mag niet meer dan één entiteit in een pakket opnemen wanneer u het pakket uploadt naar een Campagne-instantie.

Als u uw configuratie op een nieuw geval moet opstellen, kunt u al uw entiteitpakketten invoeren.

**Functies**

Dit type pakket:
* Beantwoord een cliëntvereiste/specificatie.
* Bevat een of meer functies.
* Alle afhankelijkheden moeten worden opgenomen om de functionaliteit zonder enig ander pakket te kunnen uitvoeren.

**Campagnes**

Dit pakket is niet verplicht. Het is soms nuttig om een specifiek type voor alle campagnes te creëren, zelfs als een campagne als eigenschap kan worden gezien.

**Updates**

Zodra gevormd, kan een eigenschap in een ander milieu worden uitgevoerd. Het pakket kan bijvoorbeeld worden geëxporteerd van een ontwikkelomgeving naar een testomgeving. Bij deze test wordt een defect aan het licht gebracht. In de eerste plaats moet het worden aangepast aan de ontwikkelomgeving. Vervolgens moet de pleister op het testplatform worden aangebracht.

De eerste oplossing zou zijn om de hele functie opnieuw te exporteren. Maar om elk risico te vermijden (het bijwerken van ongewenste elementen) is het veiliger om een pakket te hebben dat alleen de correctie bevat.

Daarom raden we u aan een updatepakket te maken dat slechts één entiteitstype van de functie bevat.

Een update kan niet alleen een oplossing zijn, maar ook een nieuw element van uw entiteit/functie/campagnemakket. Als u wilt voorkomen dat het hele pakket wordt geïmplementeerd, kunt u een updatepakket exporteren.

### Naamconventies {#data-package-naming}

Nu er typen zijn gedefinieerd, moeten we een naamgevingsconventie opgeven. Adobe Campaign staat het niet toe om subfolders voor pakketspecificaties tot stand te brengen, betekenend dat de aantallen de beste oplossing voor het blijven georganiseerd zijn. Nummervoorvoegselpakketnamen.

U kunt bijvoorbeeld de volgende conventie gebruiken:

* Entiteit: van 1 tot 99
* Te gedenken gebeurtenis: van 100 tot 199
* Campagne: van 200 tot 299
* Bijwerken: van 5000 tot 5999

#### Volgorde van pakketten voor entiteiten {#entity-packages-order}

Om de invoer te helpen, zouden de entiteitpakketten door bevolen moeten worden aangezien zij zouden moeten worden ingevoerd.

Bijvoorbeeld:

* 001 - Schema
* 002 - Formulier
* 003 - Afbeeldingen
* enz.

>[!NOTE]
>
>Forms mag alleen worden geïmporteerd **na** schema-updates.


#### Pakketdocumentatie {#package-documentation}

Wanneer u een pakket bijwerkt, moet u altijd een opmerking in het beschrijvingsveld plaatsen om eventuele wijzigingen en redenen (bijvoorbeeld &quot;voeg een nieuw schema toe&quot; of &quot;repareer een fout&quot;) nader toe te lichten.

U kunt het beste ook de datum van de update invoeren.

>[!IMPORTANT]
>
>Het beschrijvingsveld mag maximaal 2.000 tekens bevatten.

