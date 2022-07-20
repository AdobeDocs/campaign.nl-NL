---
audience: end-user
user-guide-title: Campaign v8
description: Documentatie voor Campaign v8
breadcrumb-title: Overzicht van campagnes
title: Campagne v8 docs
source-git-commit: ca52da16933f57181a0c4228bda9a2d33ebcedef
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 27%

---


# Adobe Campaign v8-documentatie {#campaign-v8}

+ [Documentatie voor Campaign v8](campaign-home.md)
+ Nieuwe functies? {#new}
   + [Belangrijkste mogelijkheden](start/whats-new.md)
   + [Aanvullende informatie ](start/release-notes.md)
   + [Guardrails](start/ac-guardrails.md)
   + [Bekende problemen](start/known-issues.md)
   + [Klassiek v7 naar v8](start/v7-to-v8.md)
+ Starten {#start}
   + [Aan de slag](start/get-started.md)
   + [Onderdelen en processen](start/ac-components.md)
   + Campagne-interface {#ac-ui}
      + [Campagne-interface detecteren](start/campaign-ui.md)
      + [Campagne-interface aanpassen](start/customize-ui.md)
   + [Werken met het publiek](start/audiences.md)
   + [Privacyverzoeken beheren](start/privacy.md)
   + [Gegevens importeren](start/import.md)
   + [Campagnes maken](start/campaigns.md)
   + [Berichten verzenden](start/create-message.md)
   + [Lidmaatschappen beheren](start/subscriptions.md)
   + [Track &amp; monitor](start/tracking.md)
   + [Metriek en rapporten](start/reporting.md)
   + [Veelgestelde vragen](start/campaign-faq.md)
+ Architectuur {#architecture}
   + [Algemene beginselen](architecture/general-architecture.md)
   + [Architectuur](architecture/architecture.md)
   + FDA Snowflake-implementatie {#fda}
      + [Wat is FDA-Snowflake?](architecture/fda-deployment.md)
   + Implementatie van ondernemingen (FFDA) {#ffda}
      + [Wat is Campagne FDA?](architecture/enterprise-deployment.md)
      + Kenmerken {#ffda-characteristics}
         + [Sleutelbeheer en eenheid](architecture/keys.md)
         + [Nieuwe API&#39;s](architecture/new-apis.md)
         + [API-stagingmechanisme](architecture/staging.md)
         + [Replicatiemechanisme](architecture/replication.md)
+ Implementeren {#implement}
   + [Implementatiestappen](start/implement.md)
   + [Instantie aanpassen](dev/customize.md)
   + [Beveiligingsrichtlijnen](config/security.md)
   + [Webtoepassingen en -formulieren ontwerpen](dev/webapps.md)
   + [Aanbevolen werkwijzen voor DataModel](dev/datamodel-best-practices.md)
+ Implementeren {#deploy}
   + [Compatibiliteitsmatrix](start/compatibility-matrix.md)
   + [Verbinding maken met Campaign](start/connect.md)
   + [Machtigingen](start/permissions.md)
   + [Configuratiescherm ](config/self-service.md)
+ Profielen en soorten publiek {#profiles-and-audiences}
   + [Aan de slag](audiences/gs-audiences.md)
   + [Toegangsprofielen](audiences/view-profiles.md)
   + Profielen toevoegen {#add-profiles}
      + [Profielen handmatig maken](audiences/create-profiles.md)
      + [Profielen importeren uit een bestand](audiences/import-profiles.md)
      + [Werken met externe profielen](audiences/external-profiles.md)
      + [Profielgegevens verzamelen in webformulieren](audiences/collect-profiles.md)
   + Soorten publiek maken {#create-audiences}
      + [Een lijst met contactpersonen maken](audiences/create-audiences.md)
      + [Filters maken en beheren](audiences/create-filters.md)
   + [Mappen en weergaven beheren](audiences/folders-and-views.md)
   + [Best practices](audiences/audiences-best-practices.md)
+ Berichten verzenden{#send}
   + E-mails {#emails}
      + [E-mails ontwerpen en valideren](send/email.md)
      + [E-mails verzenden en controleren](send/send.md)
   + [Sms](send/sms.md)
   + [Pushmeldingen](send/push.md)
   + [REGELS](send/line.md)
   + [Direct mail](send/direct-mail.md)
   + [Sociale marketing](send/twitter.md)
   + [Transactionele berichten](send/transactional.md)
   + Mislukking, stort en quarantaine{#failures}
      + [Quarantines](send/quarantines.md)
      + [Leveringsfouten](send/delivery-failures.md)
+ Interactie in realtime{#interaction}
   + [Aan de slag met realtime interactie](interaction/interaction.md)
   + [Milieu en architectuur](interaction/interaction-architecture.md)
   + [Aanbevolen procedures](interaction/interaction-best-practices.md)
   + Instellingen definiëren{#interaction-settings}
      + [Operatoren maken](interaction/interaction-operators.md)
      + [Omgevingen maken](interaction/interaction-env.md)
      + [Vooraf gedefinieerde filters maken](interaction/interaction-predefined-filters.md)
      + [Plaatsingen voor aanbiedingen maken](interaction/interaction-offer-spaces.md)
   + [Een aanbiedingencatalogus maken](interaction/interaction-offer-catalog.md)
   + [Een aanbieding maken](interaction/interaction-offer.md)
   + [Een voorstel verzenden (uitgaand)](interaction/interaction-send-offers.md)
   + Een aanbieding presenteren (binnenkomend){#inbound}
      + [Context](interaction/interaction-present-offers.md)
      + [Een aanbieding bellen op een webpagina](interaction/interaction-integration.md)
      + [Anonieme interacties beheren](interaction/anonymous-interactions.md)
   + [Rapporten en geschiedenis](interaction/interaction-tracking.md)
   + [Gebruiksscenario’s](interaction/interaction-use-cases.md)
+ Configureren {#config}
   + [Automatiseren met workflows](config/workflows.md)
   + [E-mailinstellingen](config/email-settings.md)
   + [Transactionele berichtinstellingen](config/transactional-msg-settings.md)
   + [SDK&#39;s voor campagnes integreren met uw app](config/push-config.md)
   + [Externe accounts](config/external-accounts.md)
+ Verbinden {#connect}
   + [Verbinden met andere oplossingen](connect/integration.md)
   + [Campagne + Analyse](connect/ac-aa.md)
   + [Campagne + Experience Manager](connect/ac-aem.md)
   + [Campagne + Doel](connect/ac-at.md)
   + [Campagne + Experience Cloud-triggers](connect/ac-triggers.md)
   + [Campagne + RTCDP](connect/ac-rtcdp.md)
   + [Campagne + Twitter](connect/ac-tw.md)
   + [Campagne + externe database](connect/fda.md)
   + Campagne + uw CRM {#ac-crm}
      + [Aan de slag met CRM-connectors](connect/crm.md)
      + [Werken met campagne en SFDC](connect/ac-sfdc.md)
      + [Werken met Campagne en Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Gegevens synchroniseren](connect/crm-data-sync.md)
+ Bronnen voor ontwikkelaars {#developer}
   + [Campaign datamodel](dev/datamodel.md)
   + Schema&#39;s en formulieren {#shemas-forms}
      + [Werken met schema&#39;s](dev/schemas.md)
      + [Schema&#39;s maken](dev/create-schema.md)
      + [Schema&#39;s uitbreiden](dev/extend-schema.md)
      + [Filterschema&#39;s](dev/filter-schema.md)
      + [Schemastructuur](dev/schema-structure.md)
      + [Databasetoewijzing](dev/database-mapping.md)
      + [PI-weergave beperken](dev/restrict-pi-view.md)
      + [Een aangepaste tabel voor ontvangers gebruiken](dev/custom-recipient.md)
      + [De database bijwerken](dev/update-database-structure.md)
      + [Invoerformulieren](dev/forms.md)
   + [Campaign-API&#39;s](dev/api.md)
+ [Campaign-configuratiescherm](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl)
+ [Handleiding Campagne Automation Guide](https://experienceleague.adobe.com/docs/campaign/automation/home.html)
