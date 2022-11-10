---
product: campaign
title: Discussieforums
description: Meer informatie over het gebruik van discussieforums voor campagnes
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 72fc29c49fca5767133be4a9927b57b3cfb51a14
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Discussieforums{#discussion-forums}

Adobe Campaign-operatoren kunnen discussieforums gebruiken om informatie te delen. De volgende elementen hebben elk hun eigen forum: plannen, programma&#39;s, campagnes, marketingmiddelen, simulaties, voorraden. Elke exploitant heeft ook een persoonlijk forum. Alle discussies zijn openbaar, zelfs op persoonlijke forums.

Operatoren kunnen zich op een forum abonneren om elke keer dat een bericht wordt gepost, een e-mailbericht te ontvangen.

## Toegang tot een forum {#accessing-a-forum}

Als u een forum wilt openen, bladert u naar een dashboard en klikt u op de knop **[!UICONTROL Forum]** in de rechterbovenhoek.

![](assets/mrm-forum-icon.png)

Berichten en de reacties daarop worden van Nieuwst naar Oudst weergegeven.

Als u een nieuwe thread wilt starten, klikt u op de knop **[!UICONTROL Add a discussion]** in de rechterbovenhoek. De **[!UICONTROL Discussion forum]** wordt weergegeven (zie hieronder).

![](assets/mrm-forum-new-thread.png)


Voer de tekst in het dialoogvenster **[!UICONTROL Message]** en een titel van het debat in het **[!UICONTROL Subject]** veld.

Operatoren die al een bericht in dit forum hebben geplaatst, worden hiervan standaard op de hoogte gesteld. U kunt een extra operator selecteren voor meldingen. Selecteer een groep operatoren als u meerdere operatoren wilt melden.

U kunt een bijlage aan het bericht toevoegen, gebruikend  **[!UICONTROL Browse...]** knop. De bijlage wordt ook opgenomen in de e-mail met het bericht. Bijlagen mogen alleen afzonderlijk worden verzonden: om verscheidene dossiers te verzenden, moet u hen in een .zip dossier comprimeren.

>[!CAUTION]
>
>Zodra een bericht aan het forum is gepost, kan het niet meer worden veranderd of worden geschrapt.

## Plaatsen op het persoonlijke forum van een exploitant {#posting-to-the-personal-forum-of-an-operator}

U kunt een bericht plaatsen aan het forum van een exploitant. Persoonlijke forums zijn openbaar en alle operatoren kunnen uw bericht zien. De exploitant ontvangt een e-mailbericht telkens als iemand aan zijn persoonlijk forum post.

Als u toegang wilt tot het forum van een operator, kunt u:

* Bladeren naar de **[!UICONTROL Administration > Access management > Operators]** map Campaign Explorer, selecteert u de operator om het dashboard te openen en klikt u vervolgens op de knop **[!UICONTROL Forum]** in de rechterbovenhoek.
* Zoek de naam van de operator in de gebruikersinterface van Adobe Campaign (via een bericht dat door deze operator aan het forum is gepost, een taak die aan hen is toegewezen) en klik erop om het dashboard van de operator te openen.

## Abonneren op een forum {#subscribing-to-a-forum}

Als u zich abonneert op een forum, kunt u alle besprekingen volgen. Zodra u bent geabonneerd, ontvangt u een e-mailbericht telkens wanneer een bericht naar het forum wordt gepost.

Als u een bericht wilt beantwoorden, klikt u in de hoofdtekst van de e-mail en meldt u zich vervolgens aan bij de Adobe Campaign-webinterface.

* Als u zich wilt abonneren op een forum, klikt u op de knop **[!UICONTROL Follow discussions]** in de rechterbovensectie boven de lijst met berichten.

   De sectie gaat blauw en toont aan dat u aan het forum wordt geabonneerd.

* Als u uw abonnement op een forum wilt opzeggen, klikt u op de knop **[!UICONTROL Unsubscribe]** knop.

* Het persoonlijke dashboard bevat de forums waarop u zich hebt geabonneerd. Klik op de knop **[!UICONTROL Subscription to discussion forums]** Klik vervolgens op het gewenste item om het forum te openen.

   ![](assets/forum-subscribed.png)


## Problemen met meldingslevering oplossen {#checking-notification-delivery}

Als exploitanten die zijn geabonneerd op een forum geen meldingen ontvangen zoals verwacht:

* Controleer of de e-mailadressen zijn ingevoerd in de profielen van de operator.
* Bladeren naar de **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** map Campagneverkenner en controleer de **[!UICONTROL Jobs in discussion forums]** de workflow wordt zonder fouten gestart.
* Controleer de leveringslogboeken:

   * Blader op de startpagina van Adobe Campaign naar **[!UICONTROL Campaigns > Navigation > Deliveries]** en open vervolgens de **[!UICONTROL Discussion forum notification]** levering.
   * Blader in Campaign Explorer naar **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]** en klik vervolgens op **[!UICONTROL Discussion forum notifications]**.
   In de **[!UICONTROL Discussion forum notifications]** de leveringslogboeken vindt u in het dialoogvenster **[!UICONTROL Edit > Delivery]** tab. U kunt ook de **[!UICONTROL Tracking > Log]** en de **[!UICONTROL Exclusion causes]** tabs.
