---
title: Machtigingen verlenen en beperken voor campagnemappen
description: Leer hoe u machtigingen voor mappen toekent of beperkt
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: 0513b9f65e9431f5207b384a0e2d8c5aeb8e209f
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Mapmachtigingen beheren{#manage-folder-permissions}

## Toegang tot een map beperken{#restrict-access-to-a-folder}

De toestemmingen van het gebruik op omslagen om toegang tot de gegevens van de Campagne te organiseren en te controleren.

Mapbeheer wordt gedetailleerd in [deze pagina](../audiences/folders-and-views.md).

Voer de volgende stappen uit als u machtigingen voor een specifieke map Campagne wilt bewerken:

1. Klik met de rechtermuisknop op de map en selecteer **[!UICONTROL Properties...]**.
1. Bladeren naar de **[!UICONTROL Security]** om machtigingen voor deze map weer te geven.

   ![](assets/folder-permissions.png)

* Naar **een groep of een operator autoriseren** klikt u op de knop **[!UICONTROL Add]** en selecteert u de groep of operator om machtigingen voor deze map toe te wijzen.
* Naar **een groep of een exploitant verbieden**, klikt u op **[!UICONTROL Delete]** en selecteert u de groep of operator om de autorisatie voor deze map te verwijderen.
* Naar **de rechten selecteren die aan een groep of een exploitant zijn toegewezen** selecteert u de groep of operator, selecteert u de toegangsrechten die u wilt verlenen en deselecteert u de andere rechten.

## Machtigingen voor doorgeven {#propagate-permissions}

Om toestemmingen en toegangsrechten te verspreiden, selecteer **[!UICONTROL Propagate]** in de mapeigenschappen.

De autorisaties die in dit venster worden gedefinieerd, worden vervolgens toegepast op alle submappen van het huidige knooppunt. U kunt deze machtigingen altijd voor elk van de submappen te veel laden.

>[!NOTE]
>
>De optie Ongedaan maken **[!UICONTROL Propagate]** voor een map wordt deze niet gewist voor de submappen: u moet deze expliciet wissen voor elk van de submappen.

## Toegang verlenen aan alle marktdeelnemers {#grant-access-to-all-operators}

In de **[!UICONTROL Security]** selecteert u de **[!UICONTROL System folder]** toegang verlenen tot alle operatoren, ongeacht hun machtigingen.

Als deze optie wordt ontruimd, moet u de exploitant (of hun groep) terug aan de lijst van toestemmingen uitdrukkelijk toevoegen opdat zij toegang hebben.
