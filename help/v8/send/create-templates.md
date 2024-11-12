---
product: campaign
title: Werken met leveringssjablonen
description: Leer hoe u leveringssjablonen maakt en gebruikt in Campagne
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: 08e04f3642320df94d719a415e878e3a26d2e00f
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 3%

---

# Werken met leveringssjablonen {#work-with-delivery-template}

## Aan de slag met leveringssjablonen

Elke levering wordt gemaakt op basis van een sjabloon. Een sjabloon is een configuratie die opnieuw kan worden gebruikt om uw implementatie te vereenvoudigen en te standaardiseren. U kunt een ingebouwde sjabloon of een aangepaste sjabloon gebruiken.

Een sjabloon kan gehele of gedeeltelijke configuratie-instellingen bevatten, zoals:

* [Typologische regels](../../automation/campaign-opt/campaign-typologies.md)
* Afzender en antwoordadressen
* Basis [ verpersoonlijkingsblokken ](../send/personalization-blocks.md)
* Verbindingen aan [ spiegelpagina&#39;s ](../send/mirror-page.md) en unsubscription verbindingen
* Inhoud, bedrijfslogo of handtekening
* Andere leveringseigenschappen, zoals middelgeldigheid, retry parameters, of quarantaine montages.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#delivery-template-video)

De leveringssjablonen worden opgeslagen in de map **[!UICONTROL Resources > Templates > Delivery templates]** van de Verkenner. In Adobe Campaign kunt u werken met twee typen sjablonen:

1. Adobe Campaign **ingebouwde** leveringsmalplaatjes - ingebouwde malplaatjes zijn beschikbaar voor elk kanaal. Zij mogen niet worden gewijzigd of geschrapt. Zij omvatten een basisconfiguratie voor elk leveringskanaal. Als Beheerder, kunt u standaardwaarden plaatsen, of bepaalde functies beperken tot eind - gebruikers, zoals het wijzigen van de volgende parameters, afzender e-mailadressen, en meer. Ingebouwde sjablonen worden vet weergegeven in de lijst met sjablonen.

1. **leveringsmalplaatjes van de Douane van 0} {- als Beheerder van Adobe Campaign, kunt u nieuwe leveringsmalplaatjes tot stand brengen.** De beste manier is om een ingebouwde sjabloon te dupliceren en bij te werken in plaats van een geheel nieuwe sjabloon te maken. U kunt bijvoorbeeld een sjabloon voor e-maillevering configureren. Wanneer gebruikers een bezorging maken op basis van deze sjabloon, hoeven ze alleen de tekst of HTML-inhoud in te voeren. Alle andere instellingen zijn al gedefinieerd.

>[!NOTE]
>
>De beschikbare malplaatjes hangen van uw toegangsrechten, van uw instantieconfiguratie, en van de context af. Wanneer u bijvoorbeeld een informatiedienst maakt, kunt u een leveringssjabloon koppelen voor bevestigingsberichten: u kunt dan alleen toegang krijgen tot de sjablonen waarvan de doeltoewijzing de abonnementstoewijzing is. Andere sjablonen zijn in deze context niet zichtbaar. Voor meer op dit, verwijs naar [ Werk met doelafbeeldingen ](../audiences/target-mappings.md) en [ beheer abonnementen en afmeldingsopties ](../start/subscriptions.md).


## Een sjabloon maken {#create-a-delivery-template}

Als u een leveringssjabloon wilt maken, kunt u een ingebouwde sjabloon dupliceren of een bestaande levering converteren naar een sjabloon. U kunt ook een volledig nieuwe leveringssjabloon maken, maar dit wordt niet aanbevolen. Deze methoden worden hieronder beschreven.

### Een bestaande sjabloon dupliceren{#copy-an-existing-template}

De campagne wordt geleverd met een reeks ingebouwde sjablonen voor elk kanaal: e-mail, push, SMS, direct mail en nog veel meer.

De gemakkelijkste manier om een leveringsmalplaatje tot stand te brengen is een ingebouwde malplaatje te dupliceren en aan te passen.

Voer de onderstaande stappen uit om een leveringssjabloon te dupliceren:

1. Blader naar **[!UICONTROL Resources > Templates > Delivery templates]** in Adobe Campaign Explorer.
1. Selecteer een ingebouwde leveringssjabloon. Ingebouwde sjablonen worden in de lijst opgenomen.
1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Duplicate]** .

   ![](assets/duplicate-built-in-template.png)

1. Definieer de sjablooninstellingen en sla de nieuwe sjabloon op.

   ![](assets/delivery-template-new.png)

De sjabloon wordt toegevoegd aan de lijst met leveringssjablonen. U kunt deze nu selecteren wanneer u een nieuwe levering maakt.

![](assets/select-the-new-template.png)

### Een bestaande levering converteren naar een sjabloon {#convert-an-existing-delivery}

Een levering kan in een malplaatje voor nieuwe herhaalde leveringsacties worden omgezet.

Volg onderstaande stappen om een levering naar een sjabloon om te zetten:

1. Selecteer de levering in de leveringslijst, toegankelijk via het knooppunt **[!UICONTROL Campaign management]** van de Campagneverkenner.

1. Klik met de rechtermuisknop en selecteer **[!UICONTROL Actions > Save as template...]** .

   ![](assets/save-as-template.png)

1. Bewerk de leveringseigenschappen en selecteer de map waarin de nieuwe sjabloon moet worden opgeslagen (in het veld **[!UICONTROL Folder]** ) en de map waarin de op deze sjabloon gebaseerde items moeten worden gemaakt (in het veld **[!UICONTROL Execution folder]** ).

   ![](assets/template-select-folders.png)

### Een nieuwe sjabloon maken {#create-a-new-template}

>[!NOTE]
>
>Om configuratiefouten te vermijden, adviseert de Adobe dat u [ een ingebouwd malplaatje ](#copy-an-existing-template) dupliceert en zijn eigenschappen eerder dan tot een nieuw malplaatje leidt.

Voer de onderstaande stappen uit om een volledig nieuwe leveringssjabloon te configureren:

1. Blader aan de **omslag van Middelen** in de ontdekkingsreiziger van de Campagne, en selecteer **Malplaatjes** toen **de malplaatjes van de Levering**.
1. Klik **Nieuw** in de toolbar om een nieuw leveringsmalplaatje tot stand te brengen.
1. Plaats het **Etiket** en de **Interne naam** van de omslag.
1. Sla de sjabloon op en open deze opnieuw.
1. Van de **knoop van Eigenschappen**, pas de montages aan.
1. In het **Algemene** lusje, bevestig of verander de plaatsen die in de **omslag van de Uitvoering** worden geselecteerd, **Omslag**, en **Verpletterend** drop-down menu&#39;s.
1. Voltooi de **categorie van de Parameters van de E-mail** met uw e-mailonderwerp en gerichte bevolking.
1. Voeg uw **inhoud van de HTML** toe om uw malplaatje te personaliseren, kunt u a [ spiegelpagina verbinding ](../send/mirror-page.md) en een unsubscription verbinding tonen.
1. Selecteer het **lusje van de Voorproef**. In het **verpersoonlijking van de Test** drop-down menu, uitgezochte **Ontvanger** om uw malplaatje als gekozen profiel voor te vertonen.
1. Klik **sparen**. Je template is nu klaar om te worden gebruikt in een levering.


## Sjablonen gebruiken {#use-a-delivery-template}

### Een levering maken met een sjabloon {#create-a-delivery-from-a-template}

Als u een levering wilt maken op basis van een bestaande sjabloon, selecteert u de sjabloon in de lijst met beschikbare leveringssjablonen.

![](assets/select-the-new-template.png)

Als de sjabloon niet zichtbaar is, klikt u op de map **[!UICONTROL Select link]** rechts van het veld om door de campagnemappen te bladeren.

![](assets/browse-templates.png)

Selecteer de gewenste map in het veld **[!UICONTROL Folder]** of klik op het pictogram **[!UICONTROL Display sub-levels]** om de inhoud van de mappen in de substructuren van de huidige map weer te geven.

Selecteer de leveringssjabloon die u wilt gebruiken en klik op **[!UICONTROL Ok]** .

### Een sjabloon uitvoeren {#execute-a-template}

U kunt de uitvoering van een sjabloon rechtstreeks vanuit de sjabloonlijst starten zonder eerst een levering te maken. Het leveringsmalplaatje kan manueel, zoals hieronder gedetailleerd worden uitgevoerd, of door een gebeurtenis (uitgevoerd op een vastgestelde tijd, wanneer een dossier in de server, enz.) beschikbaar is, zoals die in [ wordt verklaard deze sectie ](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/wf-activities/action-activities/delivery).

Voer de volgende stappen uit om een sjabloon handmatig uit te voeren:

1. Selecteer de sjabloon die u wilt uitvoeren en klik met de rechtermuisknop. Selecteer **[!UICONTROL Actions>Execute the delivery template...]**.

   U kunt ook **[!UICONTROL File>Actions>Execute the delivery template...]** gebruiken.

   ![](assets/execute-delivery-template.png)

1. Voer de leveringsparameters in en klik op **[!UICONTROL Send]** .

Deze actie produceert een levering in de omslag verbonden aan het malplaatje. De naam van deze levering is de naam van het leveringsmalplaatje waarvan het werd gecreeerd.

## Zelfstudievideo&#39;s {#delivery-template-video}

### Hoe te om een leveringsmalplaatje te vormen

De volgende video toont hoe u een sjabloon voor een ad-hoclevering kunt configureren.

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### Eigenschappen voor leveringssjablonen instellen

In de volgende video ziet u hoe u de eigenschappen van de leveringssjabloon instelt en wordt elke eigenschap in detail uitgelegd.

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### Hoe te om een ad hoc leveringsmalplaatje op te stellen

In deze video wordt uitgelegd hoe u een sjabloon voor ad-hoce-maillevering kunt implementeren. In deze video wordt het verschil tussen een e-maillevering en een leveringsworkflow uitgelegd.

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

De extra Campagne hoe-aan video&#39;s is beschikbaar [ hier ](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html) {target="_blank"}.
