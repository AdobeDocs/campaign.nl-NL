---
title: Rechten verlenen aan Campagne v8
description: Leer hoe u machtigingen verleent aan Campagne v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 4%

---

# Aan de slag met machtigingen

In Adobe Campaign zijn gebruikers **operatoren** en **groepen met operatoren** vertegenwoordigen gebruikersrollen.

Een operator is een Adobe Campaign-gebruiker die gemachtigd is om zich aan te melden en handelingen uit te voeren. Operatoren worden standaard opgeslagen in de **[!UICONTROL Administration > Access management > Operators]** knooppunt.

Adobe Campaign wordt geleverd met ingebouwde groepen operatoren, zoals Campagne Managers of Workflowsupervisors. Meer informatie over machtigingen in [deze sectie](../start/gs-permissions.md)

Als lid van een exploitantgroep, heeft een gebruiker rechten om verrichtingen uit te voeren, genoemd &quot;Benoemde Rechten&quot;, en heeft toegang tot gegevens, die in omslagen in **Verkenner** weergeven. Een operator kan lid zijn van meerdere groepen operatoren: rechten en toegangsrechten zijn additief .

Rechten verlenen machtigingen aan:

* Voer bijvoorbeeld bewerkingen uit op de knop **Analyseren** wordt geactiveerd voor leden van de **Leveringsoperator** groep met de **Levering voorbereiden** Benoemd rechts

* De toegang tot omslagen Lidmaatschap van de Groepen van de Exploitant kan toegangsrechten tot omslagen verlenen of beperken, door de veiligheidsmontages op omslagen te veranderen. Meer informatie in [deze pagina](../start/folder-permissions.md). Het kan bijvoorbeeld invloed hebben op: **Schrijftoegang** nieuwe entiteiten te creëren (zoals leveringen, profielen, enz.); **Leestoegang** entiteiten te gebruiken; **Toegang verwijderen** om entiteiten te verwijderen.

## Beveiligingszones

Elke exploitant moet met een streek worden verbonden om aan een geval te login en exploitant IP moet in de adressen of adresreeksen worden omvat die in de veiligheidsstreek worden bepaald. Configuratie van de beveiligingszone wordt uitgevoerd in het configuratiebestand van de Adobe Campaign-server.

De exploitanten worden verbonden met een veiligheidsstreek van zijn profiel in de console, die in **[!UICONTROL Administration > Access management > Operators]** knooppunt.

![](../assets/do-not-localize/speech.png)  Als Beheerde gebruiker van Cloud Services, plaatst Adobe de veiligheidsstreken voor u. Voor meer informatie, [contact Adobe](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Meer informatie**

* [Ingebouwde rechten met naam](../start/gs-permissions.md)

* [Stappen voor instelmachtigingen](../start/manage-permissions.md)
