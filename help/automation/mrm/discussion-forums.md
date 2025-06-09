---
product: campaign
title: Discussieforums
description: Meer informatie over het gebruik van discussieforums voor campagnes
feature: Campaigns, Resource Management
role: User
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Discussieforums{#discussion-forums}

Adobe Campaign-operatoren kunnen discussieforums gebruiken om informatie te delen. De volgende elementen hebben elk hun eigen forum: plannen, programma&#39;s, campagnes, marketingmiddelen, simulaties, voorraden. Elke exploitant heeft ook een persoonlijk forum. Alle discussies zijn openbaar, zelfs op persoonlijke forums.

Operatoren kunnen zich op een forum abonneren om elke keer dat een bericht wordt gepost, een e-mailbericht te ontvangen.

## Toegang tot een forum {#accessing-a-forum}

Als u een forum wilt openen, bladert u naar een dashboard en klikt u op de koppeling **[!UICONTROL Forum]** in de rechterbovenhoek.

![](assets/mrm-forum-icon.png)

Berichten en de reacties daarop worden van Nieuwst naar Oudst weergegeven.

Als u een nieuwe verbinding wilt maken, klikt u op de knop **[!UICONTROL Add a discussion]** in de rechterbovenhoek. Het vak **[!UICONTROL Discussion forum]** wordt weergegeven (zie verderop).

![](assets/mrm-forum-new-thread.png)


Typ uw tekst in het veld **[!UICONTROL Message]** en voer een titel voor de beschrijving in het veld **[!UICONTROL Subject]** in.

Operatoren die al een bericht in dit forum hebben geplaatst, worden hiervan standaard op de hoogte gesteld. U kunt een extra operator selecteren voor meldingen. Selecteer een groep operatoren als u meerdere operatoren wilt melden.

Met de knop **[!UICONTROL Browse...]** kunt u een bijlage aan het bericht toevoegen. De bijlage wordt ook opgenomen in de e-mail met het bericht. Bijlagen kunnen alleen afzonderlijk worden verzonden: als u meerdere bestanden wilt verzenden, moet u deze comprimeren in een ZIP-bestand.

>[!CAUTION]
>
>Zodra een bericht aan het forum is gepost, kan het niet meer worden veranderd of worden geschrapt.

## Plaatsen op het persoonlijke forum van een exploitant {#posting-to-the-personal-forum-of-an-operator}

U kunt een bericht plaatsen aan het forum van een exploitant. Persoonlijke forums zijn openbaar en alle operatoren kunnen uw bericht zien. De exploitant ontvangt een e-mailbericht telkens als iemand aan zijn persoonlijk forum post.

Als u toegang wilt tot het forum van een operator, kunt u:

* Blader naar de map **[!UICONTROL Administration > Access management > Operators]** van de Campagneverkenner, selecteer de operator om het dashboard te openen en klik vervolgens op de koppeling **[!UICONTROL Forum]** in de rechterbovenhoek.
* Zoek de naam van de operator in de gebruikersinterface van Adobe Campaign (via een bericht dat door deze operator aan het forum is gepost, een taak die aan hen is toegewezen) en klik erop om het dashboard van de operator te openen.

## Abonneren op een forum {#subscribing-to-a-forum}

Als u zich abonneert op een forum, kunt u alle discussies volgen. Zodra u bent geabonneerd, ontvangt u een e-mailbericht telkens wanneer een bericht naar het forum wordt gepost.

Als u een bericht wilt beantwoorden, klikt u in de hoofdtekst van de e-mail en meldt u zich vervolgens aan bij de Adobe Campaign-webinterface.

* Als u zich wilt abonneren op een forum, klikt u op de knop **[!UICONTROL Follow discussions]** in de rechterbovensectie boven de lijst met berichten.

  De sectie gaat blauw en toont aan dat u aan het forum wordt geabonneerd.

* Klik op de knop **[!UICONTROL Unsubscribe]** als u het abonnement op een forum wilt opzeggen.

* Het persoonlijke dashboard bevat de forums waarop u zich hebt geabonneerd. Klik op de koppeling **[!UICONTROL Subscription to discussion forums]** om de lijst weer te geven en klik vervolgens op het gewenste item voor toegang tot het forum.

  ![](assets/forum-subscribed.png)


## Problemen met meldingslevering oplossen {#checking-notification-delivery}

Als exploitanten die zijn geabonneerd op een forum geen meldingen ontvangen zoals verwacht:

* Controleer of de e-mailadressen zijn ingevoerd in de profielen van de operator.
* Blader naar de map **[!UICONTROL Administration > Production > Technical workflows > Campaign processes]** van de Campagneverkenner en controleer of de **[!UICONTROL Jobs in discussion forums]** -workflow zonder fouten is gestart.
* Controleer de leveringslogboeken:

   * Blader op de startpagina van Adobe Campaign naar **[!UICONTROL Campaigns > Navigation > Deliveries]** en open vervolgens de levering **[!UICONTROL Discussion forum notification]** .
   * Blader in Campaign Explorer naar **[!UICONTROL Administration > Production > Objects created automatically > Technical deliveries > Workflow notifications]** en klik op **[!UICONTROL Discussion forum notifications]** .

  In het vak **[!UICONTROL Discussion forum notifications]** vindt u de leveringslogboeken op het tabblad **[!UICONTROL Edit > Delivery]** . U kunt ook de tabbladen **[!UICONTROL Tracking > Log]** en **[!UICONTROL Exclusion causes]** weergeven.
