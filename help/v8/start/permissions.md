---
title: Rechten verlenen aan Campagne v8
description: Leer hoe u machtigingen verleent aan Campagne v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---

# Aan de slag met machtigingen

In Adobe Campaign zijn gebruikers **operatoren** en **operatorgroepen** vertegenwoordigen gebruikersrollen.

Een operator is een Adobe Campaign-gebruiker die gemachtigd is om zich aan te melden en handelingen uit te voeren. Operatoren worden standaard opgeslagen in het knooppunt **[!UICONTROL Administration > Access management > Operators]**.

Adobe Campaign wordt geleverd met ingebouwde groepen operatoren, zoals Campagne Managers of Workflowsupervisors. Alle ingebouwde groepen worden vermeld in [Campaign Classic v7 documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}.

Als lid van een exploitantgroep, heeft een gebruiker rechten om verrichtingen uit te voeren, genoemd &quot;Benoemde Rechten&quot;, en heeft toegang tot gegevens, die in omslagen in **Ontdekkingsreiziger** mening bevat. Een operator kan lid zijn van meerdere groepen operatoren: rechten en toegangsrechten zijn additief .

Rechten verlenen machtigingen aan:

* Bewerkingen uitvoeren
De knop **Analyseren** in de leveringseditor wordt bijvoorbeeld geactiveerd voor leden van de groep **Leveringsoperator** die de **Aflevering voorbereiden** Benoemd rechts hebben

* Toegang tot mappen
Lidmaatschap van groepen met operatoren kan toegangsrechten verlenen of beperken tot mappen door de beveiligingsinstellingen voor mappen te wijzigen. [Meer informatie in de Campaign Classic v7-documentatie](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}. Het kan bijvoorbeeld invloed hebben op: **Schrijf toegang** om nieuwe entiteiten te maken (zoals leveringen, profielen, enz.), **Leestoegang** om entiteiten te gebruiken, **Verwijder toegang** om entiteiten te verwijderen.

## Beveiligingszones

Elke exploitant moet met een streek worden verbonden om aan een geval te login en exploitant IP moet in de adressen of adresreeksen worden omvat die in de veiligheidsstreek worden bepaald. Configuratie van de beveiligingszone wordt uitgevoerd in het configuratiebestand van de Adobe Campaign-server.

Operatoren zijn verbonden met een beveiligingszone vanuit het profiel in de console, toegankelijk via het knooppunt **[!UICONTROL Administration > Access management > Operators]**.

![](../assets/do-not-localize/speech.png)  Als Beheerde gebruiker van Cloud Services, plaatst Adobe de veiligheidsstreken voor u. Voor meer informatie, [contact Adobe](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}.

**Meer informatie in de Campaign Classic v7-documentatie**

* [Ingebouwde benoemde rechten](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [Geïntegreerde operatorgroepen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [Stappen voor het instellen van machtigingen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
