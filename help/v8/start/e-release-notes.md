---
title: Opmerkingen bij de release Vroege campagne v8
description: release van Early Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---

# Vroege aanvullende informatie {#e-new-release}

Op deze pagina vindt u een beschrijving van de verbeteringen en correcties die zijn opgenomen in de volgende versie van Campagne v8. Deze inhoud kan tot de releasedatum zonder voorafgaande kennisgeving worden gewijzigd. De officiële opmerkingen bij de release staan in dit [page](../start/release-notes.md).

## Release 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> De upgrade van de clientconsole is verplicht. Leer hoe u uw clientconsole in deze versie kunt upgraden [page](../start/connect.md#download-ac-console).

_7 oktober 2022_

**Verbeteringen**

* Probleem verholpen dat invloed had op de statusupdates van het leveringslogboek voor de MID-instantie toen de optie FeatureFlag_GZIP_Compression was ingeschakeld. (NEO-49183)
* De **Database opschonen** in de technische workflow worden nu ook aangepaste staging-schema&#39;s afgehandeld. (NEO-48974)
* Probleem verholpen waarbij leveringen konden blijven **In behandeling** zelfs als de contactdatum is bereikt. (NEO-48079, NEO-48251)
* Verbeterde stabiliteit bij het verwerken van ongeldige XML-tekenreeksen tijdens SOAP-aanroepen. (NEO-48027)
* Probleem verholpen dat de leveringanalyse zou kunnen vertragen, tijdens de uitsluitingsfase van op de lijst met ongewenste personen staan ontvangers, wanneer grote aantallen ontvangers als doelgroep zouden worden genomen. (NEO-48019)
* Om vertraging te verhinderen wanneer het verzenden van bewijs naar zaadadressen, worden alle opeenvolgende replicaties van zaadleden nu gegroepeerd in één replicatieverzoek. (NEO-44844)
* Probleem verholpen dat tot personalisatieproblemen leidde bij het verzenden van SMS-berichten via een externe leveringsmodus. (NEO-46415)
* Probleem verholpen waarbij een fout werd weergegeven tijdens een voorvertoning van een levering in een gearchiveerde gebeurtenis in het Message Center. (NEO-43620)
* Probleem verholpen in workflows waardoor bestanden niet konden worden bijgewerkt op de server wanneer de **Gegevens laden (bestand)** activiteit. Het proces is gestopt bij 100%, maar is nooit beëindigd. (NEO-47269)
* Probleem opgelost dat leidde tot het maken van onnodige DeliveryParts wanneer de levering de kalender- en splitsingsmodi gebruikte. (NEO-48634)
* Oplossing voor een prestatieprobleem bij het gebruik van op kalender gebaseerde golven. (NEO-48451)
* Probleem verholpen die tot een foutbericht in het scherm met de leveringslijst kon leiden nadat een nieuwe doeltoewijzing op een aangepast schema was gemaakt. (NEO-49237)
* Probleem verholpen dat zich kon voordoen als een levering een specifieke grootte bereikte tijdens het MTA-proces. (NEO-46097)
* Probleem verholpen waarbij het bijhouden van logbestanden gegevens met betrekking tot de browser van de ontvanger niet kon retourneren. (NEO-46612)
* Probleem verholpen tijdens postupgrade op Japanse omgevingen. (NEO-46640)
* Probleem verholpen tijdens het gebruik van de **Query** en een tabel filteren. Wanneer een kolomnaam het woord &quot;Update&quot;bevatte, kwam een compilatiefout met een ongeldige herkenningsteken en het volgende bericht voor: &quot;aantal bijgewerkte rijen&quot;. (NEO-46485)
* Het probleem dat de **[!UICONTROL Replicate Staging data]** De technische workflow (ffdaReplicateStagingData) kan niet worden gestopt, zelfs als er een fout is opgetreden tijdens de uitvoering. (NEO-46280)
* Probleem verholpen waarbij gegevensverlies kan optreden als de testworkflow fout was en de bewaarperiode volledig is verstreken. (NEO-48975)
* Probleem verholpen bij het injecteren van gegevens in de Snowflake cloud-database met een campagne **Query** en **Gegevensbron wijzigen** activiteit: het proces mislukte wanneer een backslash-teken in de gegevens aanwezig was. De brontekenreeks is niet gevonden en gegevens zijn niet correct verwerkt op Snowflake. (NEO-45549)
