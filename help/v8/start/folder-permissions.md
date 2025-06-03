---
title: Machtigingen verlenen en beperken voor campagnemappen
description: Leer hoe u machtigingen voor mappen toekent of beperkt
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Mapmachtigingen beheren{#manage-folder-permissions}

## Toegang tot een map beperken{#restrict-access-to-a-folder}

De toestemmingen van het gebruik op omslagen om toegang tot de gegevens van de Campagne te organiseren en te controleren.

Het beheer van de omslag is gedetailleerd in [ deze pagina ](../audiences/folders-and-views.md).

Voer de volgende stappen uit als u machtigingen voor een specifieke map Campagne wilt bewerken:

1. Klik met de rechtermuisknop op de map en selecteer **[!UICONTROL Properties...]** .
1. Blader naar het tabblad **[!UICONTROL Security]** om de machtigingen voor deze map weer te geven.

   ![](assets/folder-permissions.png)

* Om **een groep of een exploitant** goed te keuren, klik de **[!UICONTROL Add]** knoop en selecteer de groep of de exploitant om toestemmingen voor deze omslag toe te wijzen.
* Om **een groep of een exploitant** te verbieden, klik **[!UICONTROL Delete]** en selecteer de groep of de exploitant om vergunning voor deze omslag te verwijderen.
* Om **te selecteren de rechten die aan een groep of een exploitant** worden toegewezen, de groep of de exploitant selecteren, de toegangsrechten selecteren u, en anderen willen verlenen unselect.

>[!NOTE]
>
>U mag geen object maken waarvoor u niet ten minste één map met schrijfrechten hebt.
>
>U hoeft geen beheerder te zijn om fragmenten te maken, maar u moet schrijfrechten hebben voor ten minste één map voor visueel fragment &quot;Inhoud&quot;. Anders kunt u geen visueel fragment maken.

## Machtigingen voor doorgeven {#propagate-permissions}

Als u machtigingen en toegangsrechten wilt doorgeven, selecteert u de optie **[!UICONTROL Propagate]** in de mapeigenschappen.

De autorisaties die in dit venster worden gedefinieerd, worden vervolgens toegepast op alle submappen van het huidige knooppunt. U kunt deze machtigingen altijd voor elk van de submappen te veel laden.

>[!NOTE]
>
>Als u de optie **[!UICONTROL Propagate]** voor een map uitschakelt, wordt deze niet gewist voor de submappen: u moet deze expliciet wissen voor elk van de submappen.

## Toegang verlenen aan alle marktdeelnemers {#grant-access-to-all-operators}

Selecteer op het tabblad **[!UICONTROL Security]** de optie **[!UICONTROL System folder]** om toegang tot alle operatoren toe te staan, ongeacht hun machtigingen.

Als deze optie wordt ontruimd, moet u de exploitant (of hun groep) terug aan de lijst van toestemmingen uitdrukkelijk toevoegen opdat zij toegang hebben.
