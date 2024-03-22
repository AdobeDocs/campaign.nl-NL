---
title: Werken met campagne en Adobe Experience Manager
description: Leer hoe u kunt werken met Campagne en Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Werken met campagne en Adobe Experience Manager {#ac-aem}

Dankzij de integratie tussen Adobe Campaign en Adobe Experience Manager kunt u de inhoud van uw e-mailleveringen en uw formulieren direct in Adobe Experience Manager beheren. U hebt de optie om uw **Adobe Experience Manager** inhoud in Campagne of verbind uw **Adobe Experience Manager als Cloud-service** account, waarmee u uw inhoud rechtstreeks in de webinterface kunt bewerken.

[Ontdek hoe u uw Adobe Experience Manager kunt bewerken als Cloud Service-inhoud binnen de Campagne Web Interface](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-content.html){target="_blank"}.

[Meer informatie over Adobe Experience Manager in dit document](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>Als gebruiker van beheerde Cloud Servicen, [contact Adobe](../start/campaign-faq.md#support) om Adobe Experience Manager te integreren met Campagne.

## Inhoud importeren uit Adobe Experience Manager {#integrating-with-aem}

Deze integratie kan bijvoorbeeld worden gebruikt voor het maken van een nieuwsbrief in Adobe Experience Manager die vervolgens in Adobe Campaign wordt gebruikt als onderdeel van een e-mailcampagne.

**Uit Adobe Experience Manager:**

1. Ga naar uw [!DNL Adobe Experience Manager] auteur en klik op Adobe Experience in de linkerbovenhoek van de pagina. Kies **[!UICONTROL Sites]** in het menu.

   ![](assets/aem_authoring_1.png)

1. Toegang **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. Klikken **[!UICONTROL Create]** en selecteert u **[!UICONTROL Page]** in het vervolgkeuzemenu.

   ![](assets/aem_authoring_2.png)

1. Selecteer de **[!UICONTROL Adobe Campaign Email]** sjabloon en naam van nieuwsbrief.

1. Nadat u de pagina hebt gemaakt, opent u de **[!UICONTROL Page information]** menu en klik op **[!UICONTROL Open Properties]**.

   ![](assets/aem_authoring_3.png)

1. Pas uw e-mailinhoud aan door componenten toe te voegen, zoals personalisatievelden van Adobe Campaign. Meer informatie in [Adobe Experience Manager-documentatie](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html#editing-email-content){target="_blank"}.

1. Als uw e-mail gereed is, navigeert u naar de **[!UICONTROL Page information]** menu en klik op **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_4.png)

1. Selecteer in de eerste vervolgkeuzelijst de optie **[!UICONTROL Approve Adobe Campaign]** als workflowmodel en klik op **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_5.png)

1. Boven aan de pagina wordt een disclaimer weergegeven die aangeeft: `This page is subject to the workflow Approve for Adobe Campaign`. Klikken **[!UICONTROL Complete]** naast de disclaimer om de revisie te bevestigen en klik op **[!UICONTROL Ok]**.

1. Klikken **[!UICONTROL Complete]** nogmaals en selecteert u **[!UICONTROL Newsletter approval]** in de **[!UICONTROL Next Step]** vervolgkeuzelijst.

   ![](assets/aem_authoring_6.png)

Uw nieuwsbrief is nu klaar en gesynchroniseerd in Adobe Campaign.

**Uit Adobe Campaign:**

1. Van de **[!UICONTROL Campaigns]** tabblad, klikt u op **[!UICONTROL Deliveries]** dan **[!UICONTROL Create]**.

1. Kies de optie **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** sjabloon uit de **[!UICONTROL Delivery template]** vervolgkeuzelijst.

   ![](assets/aem_authoring_7.png)

1. Voeg een **[!UICONTROL Label]** aan uw levering en klik op **[!UICONTROL Continue]**.

1. Klikken **[!UICONTROL Synchronize]** om toegang te krijgen tot uw AEM.

   Als de knop niet zichtbaar is in uw interface, navigeert u naar de knop **[!UICONTROL Properties]** en de knop **[!UICONTROL Advanced]** tab. Zorg ervoor dat de **[!UICONTROL Content editing mode]** veld is geconfigureerd voor **[!UICONTROL AEM]** en voer de AEM-instantiedetails in de **[!UICONTROL AEM account]** veld.

   ![](assets/aem_authoring_8.png)

1. Selecteer de AEM die eerder zijn gemaakt in [!DNL Adobe Experience Manager] en bevestigen door op **[!UICONTROL Ok]**.

   ![](assets/aem_authoring_11.png)

1. Zorg ervoor dat u op de knop **[!UICONTROL Refresh content]** wanneer er wijzigingen worden aangebracht in de AEM.

   ![](assets/aem_authoring_12.png)

1. Om verbinding tussen Experience Manager en Campagne te verwijderen, klik **[!UICONTROL Desynchronize]**.

Uw e-mail kan nu naar uw publiek worden verzonden.

## Elementen importeren uit Adobe Experience Manager Assets-bibliotheek {#assets-library}

U kunt ook rechtstreeks elementen invoegen vanuit uw [!DNL Adobe Experience Manager Assets Library] tijdens het bewerken van een e-mail- of landingspagina in Adobe Campaign. Deze functionaliteit wordt nader beschreven in [Adobe Experience Manager Assets-documentatie](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html){target="_blank"}.

**Uit Adobe Experience Manager:**

1. Ga naar uw [!DNL Adobe Experience Manager] auteur en klik op Adobe Experience in de linkerbovenhoek van de pagina. Kies **[!UICONTROL Assets]** `>` **[!UICONTROL Files]** in het menu.

   ![](assets/aem_assets_1.png)

1. Klikken **Maken** dan **Bestanden** om uw element te importeren in uw **Adobe Experience Manager Assets Library**. Meer informatie in [Adobe Experience Manager-documentatie](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html#uploading-assets){target="_blank"}.

   ![](assets/aem_assets_2.png)

1. Wijzig indien nodig de naam van uw element en selecteer **Uploaden**.

Uw element is nu geüpload naar uw **Adobe Experience Manager Assets Library**.

**Uit Adobe Campaign:**

1. In Adobe Campaign kunt u een nieuwe levering maken door naar de **Campagnes** tabblad, klikt u op **Leveringen** en klik op de knop **Maken** boven de lijst met bestaande leveringen.

   ![](assets/aem_assets_3.png)

1. Selecteer een **Afleveringssjabloon** en geef vervolgens een naam op voor de levering.

1. Definieer en pas de inhoud van het bericht aan. [Meer informatie](../send/email.md)

1. Als u uw **Adobe Experience Manager Assets-bibliotheek**, toegang tot de **[!UICONTROL Properties]** van uw AEM levering en selecteer de **[!UICONTROL Advanced]** tab.

   Kies uw **AEM account** en de **[!UICONTROL Use above AEM instance as shared asset library]** -optie.

   ![](assets/aem_authoring_9.png)

1. Van de **Afbeelding** pictogram, toegang tot **[!UICONTROL Select a shared asset]** -menu.

   ![](assets/aem_assets_4.png)

1. Selecteer in het selectievenster een afbeelding in de **Adobe Experience Manager Assets-bibliotheek** vervolgens **Selecteren**.

   ![](assets/aem_assets_5.png)

Uw middel wordt nu geüpload naar uw e-maillevering. U kunt nu het doelpubliek opgeven, de levering bevestigen en doorgaan met het verzenden ervan.
