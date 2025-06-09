---
title: Profielen importeren in campagne
description: Leer hoe u contactpersonen importeert in Campagne
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 7%

---

# Profielen importeren uit een bestand{#create-profiles}

Om uw gegevensbestand van de Campagne te bevolken, kunt u [ profielen manueel ](create-profiles.md) toevoegen of profielen invoeren zoals hieronder gedetailleerd. U kunt ook geïmporteerde bestanden gebruiken om contactgegevens bij te werken.

## Profielen importeren met een workflow {#import-profiles-with-a-wf}

Workflows kunnen handig zijn om een aantal importprocessen te automatiseren. Of u nu gegevens uit een lokaal bestand of uit een SFTP importeert, u kunt workflows gebruiken om de procedures voor gegevensbeheer te standaardiseren.

### Gegevens uit een lijst gebruiken: lijst lezen {#data-from-read-list}

Bereid en structureer uw gegevens in een dossier om het met een werkschema in te voeren. [Meer informatie](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html){target="_blank"}.

### Gegevens uit een bestand laden {#data-from-a-file}

De gegevens die in een werkstroom worden verwerkt, kunnen uit een gestructureerd bestand worden geëxtraheerd, zodat het bestand in Adobe Campaign kan worden geïmporteerd. [Meer informatie](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html){target="_blank"}.

Nadat gegevens zijn verzameld, kunt u deze gebruiken in uw workflows, bijvoorbeeld om een levering te verrijken of de database bij te werken. Raadpleeg [deze sectie](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html){target="_blank"} voor meer informatie.

## Invoer met één opname{#import-jobs}

Adobe Campaign biedt algemene importmogelijkheden waarmee u bijvoorbeeld een lijst met klanten of vooruitzichten kunt ophalen die vervolgens deel gaan uitmaken van een doelpopulatie, of gegevens uit externe bestanden aan uw database kunt leveren.

Algemene importbewerkingen worden beheerd via het menu **[!UICONTROL Profiles and Targets > Jobs]** van de startpagina van Adobe Campaign.

![](assets/new-import-job.png)

De stappen om een generische invoer uit te voeren zijn gedetailleerd in [ Campaign Classic v7 documentatie ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html){target="_blank"}.
