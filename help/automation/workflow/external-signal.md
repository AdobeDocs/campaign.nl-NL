---
product: campaign
title: Extern signaal
description: Meer informatie over de activiteit van de externe signaalworkflow
feature: Workflows
exl-id: 45cb95ec-77bf-4bab-895f-b94f6ce660fd
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 2%

---

# Extern signaal{#external-signal}



De **Extern signaal** activiteit laat u uitvoering van een reeks taken in een werkschema aan een programma teweegbrengen.

Wanneer een &quot;Externe signaaltaak&quot;wordt geactiveerd, wordt het voor onbepaalde tijd gepauzeerd of tot het eind van de gespecificeerde tijdspanne. De overgang ervan wordt geactiveerd door de SOAP-aanroep **PostEvent(sessionToken, workflowId, activiteit, overgang, parameters, voltooid).** De **[!UICONTROL complete]** parameter laat de taak toe worden gebeëindigd, zodat zal het niet op verdere vraag reageren.

Raadpleeg de online documentatie over SOAP-oproepen voor meer informatie over de PostEvent-functie.

U kunt deze activiteit vormen om gebeurtenissen te bepalen als geen signaal wordt ontvangen. Hiervoor bewerkt u de activiteit en klikt u op de knop **[!UICONTROL Expiration]** tab. Klik op de knop **[!UICONTROL Insert]** om een gebeurtenis te maken en te configureren.

![](assets/edit_signal.png)

De configuratie van verlopen wordt in detail beschreven in [Verlopen](define-approvals.md).

De **Vertraging** kunt u een vervalvertraging opgeven in de gewenste eenheden. Zie [Wachten](wait.md).

Elke regel vertegenwoordigt een type vervaldatum en valt samen met een overgang.

![](assets/external_sign_diag.png)
