---
audience: user
user-guide-title: Handleiding Campagne Automation Guide
user-guide-description: Handleiding Campagne Automation Guide
feature: Overview
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 79%

---


# Campagneautomatiseringshulplijnen {#automation}

+ [Handleiding Campagne Automation Guide](home.md)
+ Automatiseren met workflows {#workflows}
   + Aan de slag met workflows {#introduction}
      + [Workflows](workflow/about-workflows.md)
      + Typen workflows {#wf-type}
         + [Workflows voorbereiden](workflow/targeting-workflows.md)
         + [Workflows voor campagnes](workflow/campaign-workflows.md)
         + [Technische workflows](workflow/technical-workflows.md)
      + [Een workflow maken](workflow/build-a-workflow.md)
      + [Best practices](workflow/workflow-best-practices.md)
      + [Workflowgegevens gebruiken](workflow/use-workflow-data.md)
   + Een workflow uitvoeren {#executing-a-workflow}
      + [Een workflow starten](workflow/start-a-workflow.md)
      + [Levenscyclus van workflow](workflow/workflow-life-cycle.md)
      + [Goedkeuringen instellen](workflow/define-approvals.md)
   + Workflows bewaken {#monitoring-workflows}
      + [Workflowuitvoering controleren](workflow/monitor-workflow-execution.md)
      + [Technische workflows controleren](workflow/monitor-technical-workflows.md)
      + [Workflowheatmap](workflow/heatmap.md)
   + Workflowactiviteiten {#wf-activities}
      + [Aan de slag met activiteiten](workflow/activities.md)
      + Targetingactiviteiten {#targeting-activities}
         + [Lijst van gerichte activiteiten](workflow/targeting-activities.md)
         + [Cellen](workflow/cells.md)
         + [Databron wijzigen](workflow/change-data-source.md)
         + [Dimensie wijzigen](workflow/change-dimension.md)
         + [CRM-connector](workflow/crm-connector.md)
         + [Deduplicatie](workflow/deduplication.md)
         + [Overzicht van levering](workflow/delivery-outline.md)
         + [Schema bewerken](workflow/edit-schema.md)
         + [Verrijking](workflow/enrichment.md)
         + [Uitsluiting](workflow/exclusion.md)
         + [Incrementele query](workflow/incremental-query.md)
         + [Doorsnede](workflow/intersection.md)
         + [Lijstupdate](workflow/list-update.md)
         + [Aanbiedingen per cel](workflow/offers-by-cell.md)
         + [Aanbiedingsengine](workflow/offer-engine.md)
         + [Query](workflow/query.md)
         + [Lijst lezen](workflow/read-list.md)
         + [Splitsen](workflow/split.md)
         + [Lidmaatschapsservices](workflow/subscription-services.md)
         + [Samenvoegen](workflow/union.md)
         + [Gegevens bijwerken](workflow/update-data.md)
      + Workflowbeheeractiviteiten {#flow-control-activities}
         + [Lijst van activiteiten op het gebied van stroombeheersing](workflow/flow-control-activities.md)
         + [Melding](workflow/alert.md)
         + [AND-join](workflow/and-join.md)
         + [Goedkeuring](workflow/approval.md)
         + [Extern signaal](workflow/external-signal.md)
         + [Vertakking](workflow/fork.md)
         + [Springen (begin- en eindpunt)](workflow/jump-start-point-and-end-point.md)
         + [Start en einde](workflow/start-and-end.md)
         + [Planner](workflow/scheduler.md)
         + [Subworkflow](workflow/sub-workflow.md)
         + [Testen](workflow/test.md)
         + [Tijdsbeperking](workflow/time-constraint.md)
         + [Wachten](workflow/wait.md)
      + Actieactiviteiten {#action-activities}
         + [Lijst van activiteiten](workflow/action-activities.md)
         + [Contentmanagement](workflow/content-management.md)
         + [Doorlopende levering](workflow/continuous-delivery.md)
         + [Cross-channel leveringen](workflow/cross-channel-deliveries.md)
         + [Gegevensextractie (bestand)](workflow/extraction-file.md)
         + [Gegevens laden (bestand)](workflow/data-loading-file.md)
         + [Gegevens laden (RDBMS)](workflow/data-loading-rdbms.md)
         + [Levering](workflow/delivery.md)
         + [Leveringscontrole](workflow/delivery-control.md)
         + [Lokale goedkeuring](workflow/local-approval.md)
         + [Laden (SOAP)](workflow/loading-soap.md)
         + [Nlserver-module](workflow/nlserver-module.md)
         + [Terugkerende levering](workflow/recurring-delivery.md)
         + [SQL-code en JavaScript-code](workflow/sql-code-and-javascript-code.md)
         + [SQL Data Management](workflow/sql-data-management.md)
         + [Samenvoeging bijwerken](workflow/update-aggregate.md)
      + Gebeurtenisactiviteiten {#event-activities}
         + [Lijst van activiteiten van evenementen](workflow/event-activities.md)
         + [Bestandsophaler](workflow/file-collector.md)
         + [Bestandsoverdracht](workflow/file-transfer.md)
         + [Binnenkomende e-mails](workflow/inbound-emails.md)
         + [Binnenkomende sms](workflow/inbound-sms.md)
         + [Webdownload](workflow/web-download.md)
   + Gebruiksscenario’s {#use-cases}
      + [Gebruiksscenario’s voor workflows](workflow/workflow-use-cases.md)
      + Leveringen {#deliveries}
         + [De lokale goedkeuringsactiviteit gebruiken](workflow/local-approval-activity.md)
         + [Een verjaardags-e-mail verzenden](workflow/send-a-birthday-email.md)
         + [Leveringscontent laden](workflow/load-delivery-content.md)
         + [Cross-channel leveringsworkflow](workflow/cross-channel-delivery-workflow.md)
         + [E-mailverrijking met aangepaste datumvelden](workflow/email-enrichment-with-custom-date-fields.md)
      + Controle {#monitoring}
         + [Een rapport naar een lijst verzenden](workflow/send-a-report-to-a-list.md)
         + [Uw workflows controleren](workflow/workflow-supervision.md)
         + [Gepersonaliseerde waarschuwingen verzenden naar operatoren](workflow/send-alerts-to-operators.md)
      + Data management {#data-management}
         + [Gegevensupdates coördineren](workflow/coordinate-data-updates.md)
         + [Een overzichtslijst maken](workflow/create-a-summary-list.md)
         + [Gegevens verrijken](workflow/enrich-data.md)
         + [Aggregaten gebruiken](workflow/using-aggregates.md)
         + [De samenvoegfunctionaliteit van de deduplicatieactiviteit gebruiken](workflow/deduplication-merge.md)
         + [Een workflow instellen voor terugkerende importactiviteiten](workflow/recurring-import-workflow.md)
      + Query&#39;s ontwerpen {#designing-queries}
         + [Driemaandelijkse lijstupdate met een incrementele query](workflow/quarterly-list-update.md)
      + Query&#39;s uitvoeren en filteren {#designing-queries}
         + [Een query uitvoeren op de tabel met ontvangers](workflow/querying-recipient-table.md)
         + [Een query uitvoeren op de leveringssinformatie](workflow/query-delivery-info.md)
         + [Samengevoegde aggregaten berekenen](workflow/compute-aggregates.md)
         + [Een query uitvoeren met behulp van groeperingsbeheer](workflow/query-grouping-management.md)
         + [Een query uitvoeren met behulp van een veel-op-veel-relatie](workflow/query-many-to-many-relationship.md)
         + [Een berekend veld voor een opsommingstype toevoegen](workflow/adding-enumeration-type-calculated-field.md)
         + [Een filter maken](workflow/create-a-filter.md)
         + [Gedupliceerde ontvangers filteren](workflow/filter-duplicated-recipients.md)
   + Geavanceerde instellingen {#advanced-management}
      + [Workfloweigenschappen](workflow/workflow-properties.md)
      + [Geavanceerde parameters](workflow/advanced-parameters.md)
      + [JavaScript-scripts en -sjablonen](workflow/javascript-scripts-and-templates.md)
      + [Voorbeelden van JavaScript-code in workflows](workflow/javascript-in-workflows.md)
      + [Een externe database openen](workflow/accessing-an-external-database-fda.md)
      + [Machtigingen beheren](workflow/managing-rights.md)
      + [Activiteitsafbeeldingen wijzigen](workflow/change-activity-images.md)
      + [Tijdzones beheren](workflow/managing-time-zones.md)
+ Campagne-orkestatie {#campaign-orchestration}
   + [Aan de slag met marketingcampagnes](campaigns/set-up-campaigns.md)
   + [Programma&#39;s en campagnes maken](campaigns/marketing-campaign-create.md)
   + [Sjablonen maken en configureren](campaigns/marketing-campaign-templates.md)
   + [Leveringen toevoegen](campaigns/marketing-campaign-deliveries.md)
   + [De doelgroep selecteren](campaigns/marketing-campaign-target.md)
   + [Documenten en assets beheren](campaigns/marketing-campaign-assets.md)
   + [Goedkeuringen instellen en beheren](campaigns/marketing-campaign-approval.md)
   + [Herhalings- en periodieke campagnes](campaigns/recurring-periodic-campaigns.md)
   + [Uw campagnes controleren](campaigns/marketing-campaign-monitoring.md)
   + [Providers, voorraden en budgetten](campaigns/providers-stocks-and-budgets.md)
+ Campagne optimaliseren (add-on){#campaign-optimization}
   + [Aan de slag met campagnetypen](campaign-opt/campaign-typologies.md)
   + [Filterregels](campaign-opt/filtering-rules.md)
   + [Controleregels](campaign-opt/control-rules.md)
   + [Drukregels](campaign-opt/pressure-rules.md)
   + [Consistentieregels](campaign-opt/consistency-rules.md)
   + [Regels toepassen](campaign-opt/apply-rules.md)
   + [Campagnesimulaties](campaign-opt/campaign-simulations.md)
+ Marketing Resource Management (add-on){#mrm}
   + [Aan de slag met beheer van marketingbronnen](mrm/about-marketing-resource-management.md)
   + [Taken maken en beheren](mrm/creating-and-managing-tasks.md)
   + [Kosten beheersen](mrm/controlling-costs.md)
   + [Marketingbronnen beheren](mrm/managing-marketing-resources.md)
   + [Discussieforums](mrm/discussion-forums.md)
+ Distributed Marketing (add-on) {#distributed-marketing}
   + [Aan de slag met gedistribueerde marketing](distributed-marketing/about-distributed-marketing.md)
   + [Een lokale campagne maken](distributed-marketing/creating-a-local-campaign.md)
   + [Een collaboratieve campagne maken](distributed-marketing/creating-a-collaborative-campaign.md)
   + [Het campagnepakket publiceren](distributed-marketing/publishing-the-campaign-package.md)
   + [Campagnes openen](distributed-marketing/accessing-campaigns.md)
   + [Een campagne bijhouden](distributed-marketing/tracking-a-campaign.md)
   + [Gebruiksscenario’s](distributed-marketing/examples.md)
+ [&lt; Terug naar de documentatie bij Campagne v8 &#x200B;](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/campaign-home)
