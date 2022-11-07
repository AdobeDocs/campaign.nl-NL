---
audience: end-user
user-guide-title: Campaign v8
description: Documentatie voor Campaign v8
breadcrumb-title: Overzicht van campagnes
title: Campagne v8 docs
source-git-commit: 43e515339a2483e82910603daf6009cad63eeeae
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 25%

---


# Adobe Campaign v8-documentatie {#campaign-v8}

+ [Documentatie voor Campaign v8](campaign-home.md)
+ releases en nieuwste updates {#releases}
   + [Vroege aanvullende informatie](start/e-release-notes.md)
   + [Aanvullende informatie ](start/release-notes.md)
   + [Guardrails](start/ac-guardrails.md)
   + [Bekende problemen](start/known-issues.md)
   + [Compatibiliteitsmatrix](start/compatibility-matrix.md)
+ Aan de slag {#new}
   + [Aan de slag met Adobe Campaign](start/get-started.md)
   + [Belangrijkste mogelijkheden](start/whats-new.md)
   + [Onderdelen en processen](start/ac-components.md)
   + [Verbinding maken met Campaign](start/connect.md)
   + Campagne-interface {#ac-ui}
      + [Campagne-interface detecteren](start/campaign-ui.md)
      + [Campagne-interface aanpassen](start/customize-ui.md)
      + [Mappen en weergaven beheren](audiences/folders-and-views.md)
   + [Van Classic v7 naar v8](start/v7-to-v8.md)
   + [Veelgestelde vragen](start/campaign-faq.md)
+ Campaign Management {#campaigns}
   + [Aan de slag met campagnes](start/campaigns.md)
   + [Documentatie over campagneorchestratie](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html)
   + Berichten verzenden{#send}
      + [Aan de slag met berichten](start/create-message.md)
      + [Werken met leveringssjablonen](send/create-templates.md)
      + E-mails {#emails}
         + [E-mails ontwerpen en valideren](send/email.md)
         + [E-mails verzenden en controleren](send/send.md)
      + [Sms](send/sms.md)
      + [Pushmeldingen](send/push.md)
      + [REGELS](send/line.md)
      + [Direct mail](send/direct-mail.md)
      + [Twitter](send/twitter.md)
      + [Transactionele berichten](send/transactional.md)
      + Mislukking, stort en quarantaine{#failures}
         + [Quarantines](send/quarantines.md)
         + [Leveringsfouten](send/delivery-failures.md)
      + [Tijdoptimalisatie verzenden](send/predictive.md)
      + [Lidmaatschappen beheren](start/subscriptions.md)
+ Profiel- en publieksbeheer {#audience}
   + [Aan de slag met profielen en doelgroepen](audiences/gs-audiences.md)
   + [Werken met het publiek](start/audiences.md)
   + [Toegangsprofielen](audiences/view-profiles.md)
   + Profielen toevoegen {#add-profiles}
      + [Profielen handmatig maken](audiences/create-profiles.md)
      + [Profielen importeren uit een bestand](audiences/import-profiles.md)
      + [Werken met externe profielen](audiences/external-profiles.md)
      + [Profielgegevens verzamelen in webformulieren](audiences/collect-profiles.md)
      + [Werken met doeltoewijzingen](audiences/target-mappings.md)
   + Soorten publiek maken {#create-audiences}
      + [Een lijst met contactpersonen maken](audiences/create-audiences.md)
      + [Filters maken en beheren](audiences/create-filters.md)
   + [Stimulering delen met Adobe-oplossingen](start/shared-audiences.md)
   + [Best practices](audiences/audiences-best-practices.md)
+ Contentmanagement {#content}
   + [Webtoepassingen en -formulieren ontwerpen](dev/webapps.md)
+ Privacy- en beveiligingsbeheer {#privacy}
   + [Privacyverzoeken beheren](start/privacy.md)
   + [Beveiligingsrichtlijnen](config/security.md)
+ Beslissingsbeheer {#offers}
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
+ Rapportage en analyse {#analytics}
   + [Track &amp; monitor](start/tracking.md)
   + Werken met rapporten{#reports}
      + [Aan de slag met rapporten](reporting/gs-reporting.md)
      + Kubussen maken{#cubes}
         + [Aan de slag met kubussen](reporting/gs-cubes.md)
         + [Een kubus maken](reporting/cube-indicators.md)
         + [Kubussen gebruiken om rapporten te maken](reporting/cube-tables.md)
         + [Kubussen aanpassen](reporting/customize-cubes.md)
      + Ingebouwde rapporten{#ac-reports}
         + [Lijst met ingebouwde rapporten](reporting/built-in-reports.md)
         + [Algemene rapporten](reporting/global-reports.md)
         + [Leveringsrapporten](reporting/delivery-reports.md)
         + [Berekening van ingebouwde metriek](reporting/metrics-calculation.md)
      + [Aangepaste rapporten](reporting/custom-reports.md)
+ Data management {#data}
   + [Aan de slag met workflows](config/workflows.md)
   + [Gegevens importeren](start/import.md)
   + [Workflowdocumentatie](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)
+ Integraties {#connect}
   + [Campagne verbinden met andere oplossingen](connect/integration.md)
   + [Campagne + Experience Platform](connect/ac-aep.md)
   + [Campagne + Journey Optimizer](connect/ac-ajo.md)
   + [Campagne + Analyse](connect/ac-aa.md)
   + [Campagne + Experience Manager](connect/ac-aem.md)
   + [Campagne + Doel](connect/ac-at.md)
   + [Campagne + Experience Cloud-triggers](connect/ac-triggers.md)
   + [Campagne + Twitter](connect/ac-tw.md)
   + [Campagne + externe database](connect/fda.md)
   + Campagne + uw CRM {#ac-crm}
      + [Aan de slag met CRM-connectors](connect/crm.md)
      + [Werken met campagne en SFDC](connect/ac-sfdc.md)
      + [Werken met Campagne en Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Gegevens synchroniseren](connect/crm-data-sync.md)
+ Beheer {#admin}
   + [Machtigingen](start/permissions.md)
   + [Configuratiescherm ](config/self-service.md)
+ Architectuur en configuratie {#config}
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
   + Implementatie {#implement}
      + [Implementatiestappen](start/implement.md)
      + [Instantie aanpassen](dev/customize.md)
      + [Aanbevolen werkwijzen voor DataModel](dev/datamodel-best-practices.md)
   + Configuratie {#configuration}
      + [E-mailinstellingen](config/email-settings.md)
      + [Transactionele berichtinstellingen](config/transactional-msg-settings.md)
      + [SDK&#39;s voor campagnes integreren met uw app](config/push-config.md)
      + [Externe accounts](config/external-accounts.md)
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
