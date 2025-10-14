---
title: Rechten verlenen aan Campagne v8
description: Leer hoe u machtigingen verleent aan Campagne v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 2%

---

# Aan de slag met machtigingen

In Adobe Campaign, zijn de gebruikers **exploitanten** en **exploitantgroepen** vertegenwoordigen gebruikersrollen.

Een operator is een Adobe Campaign-gebruiker die gemachtigd is om zich aan te melden en handelingen uit te voeren. Operatoren worden standaard opgeslagen in het knooppunt **[!UICONTROL Administration > Access management > Operators]** .

Adobe Campaign wordt geleverd met ingebouwde groepen operatoren, zoals Campagne Managers of Workflowsupervisors. Leer meer over toestemmingen in [&#x200B; deze sectie &#x200B;](../start/gs-permissions.md)

Als lid van een exploitantgroep, heeft een gebruiker rechten om verrichtingen uit te voeren, genoemd &quot;Benoemde Rechten&quot;, en heeft toegang tot gegevens, die in omslagen in de **mening van de Ontdekkingsreiziger** bevat is. Een operator kan lid zijn van meerdere groepen operatoren: rechten en toegangsmachtigingen zijn additief.

Rechten verlenen machtigingen aan:

* Bewerkingen uitvoeren
Bijvoorbeeld, analyseert **&#x200B;**&#x200B;knoop in de redacteur van de Levering wordt geactiveerd voor leden van de **3&rbrace; groep van de Exploitant van de Levering die** Gelegde Levering **hebben**

* Toegang tot mappen
Lidmaatschap van groepen met operatoren kan toegangsrechten verlenen of beperken tot mappen door de beveiligingsinstellingen voor mappen te wijzigen. Leer meer in [&#x200B; deze pagina &#x200B;](../start/folder-permissions.md). Bijvoorbeeld kan het beïnvloeden: **schrijf toegang** om nieuwe entiteiten (zoals leveringen, profielen, enz.) tot stand te brengen, **Gelezen toegang** om entiteiten te gebruiken, **schrapt toegang** om entiteiten te schrappen.

## Beveiligingszones

Elke exploitant moet met een streek worden verbonden om aan een geval te login en exploitant IP moet in de adressen of adresreeksen worden omvat die in de veiligheidsstreek worden bepaald. Configuratie van de beveiligingszone wordt uitgevoerd in het configuratiebestand van de Adobe Campaign-server.

Operatoren zijn vanuit hun profiel in de console gekoppeld aan een beveiligingszone, die toegankelijk is in het knooppunt **[!UICONTROL Administration > Access management > Operators]** .

>[!NOTE]
>
>Als gebruiker van Managed Cloud Services stelt Adobe de beveiligingszones voor u in. Voor meer informatie, [&#x200B; contact Adobe &#x200B;](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Meer informatie**

* [Ingebouwde rechten met naam](../start/gs-permissions.md)

* [Stappen voor instelmachtigingen](../start/manage-permissions.md)
