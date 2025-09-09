# squadcastsdk

Developer-friendly & type-safe Go SDK specifically catered to leverage *squadcastsdk* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=squadcastsdk&utm_campaign=go"><img src="https://www.speakeasy.com/assets/badges/built-by-speakeasy.svg" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/swo/incident-response). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary


<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [squadcastsdk](#squadcastsdk)
  * [SDK Installation](#sdk-installation)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Retries](#retries)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
  * [Custom HTTP Client](#custom-http-client)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

To add the SDK as a dependency to your project:
```bash
go get github.com/SquadcastHub/squadcast-sdk-go
```
<!-- End SDK Installation [installation] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.AnalyticsGetOrgAnalytics(ctx, "<value>", "<value>", nil, nil)
	if err != nil {
		log.Fatal(err)
	}
	if res.Object != nil {
		// handle response
	}
}

```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name         | Type | Scheme      | Environment Variable       |
| ------------ | ---- | ----------- | -------------------------- |
| `BearerAuth` | http | HTTP Bearer | `SQUADCASTSDK_BEARER_AUTH` |

You can configure it using the `WithSecurity` option when initializing the SDK client instance. For example:
```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.AnalyticsGetOrgAnalytics(ctx, "<value>", "<value>", nil, nil)
	if err != nil {
		log.Fatal(err)
	}
	if res.Object != nil {
		// handle response
	}
}

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [Analytics](docs/sdks/analytics/README.md)

* [AnalyticsGetOrgAnalytics](docs/sdks/analytics/README.md#analyticsgetorganalytics) - Get Org level analytics
* [AnalyticsGetTeamAnalytics](docs/sdks/analytics/README.md#analyticsgetteamanalytics) - Get Team level analytics

### [EscalationPolicies](docs/sdks/escalationpolicies/README.md)

* [EscalationPoliciesGetEscalationPolicyByTeam](docs/sdks/escalationpolicies/README.md#escalationpoliciesgetescalationpolicybyteam) - Get Escalation Policy By team
* [EscalationPoliciesCreateEscalationPolicies](docs/sdks/escalationpolicies/README.md#escalationpoliciescreateescalationpolicies) - Create Escalation Policies
* [EscalationPoliciesRemoveEscalationPolicy](docs/sdks/escalationpolicies/README.md#escalationpoliciesremoveescalationpolicy) - Remove Escalation Policy
* [EscalationPoliciesGetEscalationPolicyByID](docs/sdks/escalationpolicies/README.md#escalationpoliciesgetescalationpolicybyid) - Get Escalation Policy By ID
* [EscalationPoliciesUpdateEscalationPolicy](docs/sdks/escalationpolicies/README.md#escalationpoliciesupdateescalationpolicy) - Update Escalation Policy

### [Export](docs/sdks/export/README.md)

* [ExportGetExportDetails](docs/sdks/export/README.md#exportgetexportdetails) - Get Export Details

### [ExtensionsMSTeams](docs/sdks/extensionsmsteams/README.md)

* [MSTeamsGetMsteamsConfig](docs/sdks/extensionsmsteams/README.md#msteamsgetmsteamsconfig) - Get MSTeams Config
* [MSTeamsCreateOrUpdateMsteamsConfiguration](docs/sdks/extensionsmsteams/README.md#msteamscreateorupdatemsteamsconfiguration) - Create Or Update MSTeams Configuration

### [ExtensionsWebhooks](docs/sdks/extensionswebhooks/README.md)

* [WebhooksGetAllWebhooks](docs/sdks/extensionswebhooks/README.md#webhooksgetallwebhooks) - Get All Webhooks
* [WebhooksCreateWebhook](docs/sdks/extensionswebhooks/README.md#webhookscreatewebhook) - Create Webhook
* [WebhooksDeleteWebhook](docs/sdks/extensionswebhooks/README.md#webhooksdeletewebhook) - Delete Webhook
* [WebhooksGetWebhookByID](docs/sdks/extensionswebhooks/README.md#webhooksgetwebhookbyid) - Get Webhook By ID
* [WebhooksUpdateWebhook](docs/sdks/extensionswebhooks/README.md#webhooksupdatewebhook) - Update Webhook

### [GlobalEventRules](docs/sdks/globaleventrules/README.md)

* [GlobalEventRulesListGlobalEventRules](docs/sdks/globaleventrules/README.md#globaleventruleslistglobaleventrules) - List Global Event Rules
* [GlobalEventRulesCreateGlobalEventRule](docs/sdks/globaleventrules/README.md#globaleventrulescreateglobaleventrule) - Create Global Event Rule
* [GlobalEventRulesDeleteGlobalEventRuleByID](docs/sdks/globaleventrules/README.md#globaleventrulesdeleteglobaleventrulebyid) - Delete Global Event Rule by ID
* [GlobalEventRulesGetGlobalEventRuleByID](docs/sdks/globaleventrules/README.md#globaleventrulesgetglobaleventrulebyid) - Get Global Event Rule by ID
* [GlobalEventRulesUpdateGlobalEventRuleByID](docs/sdks/globaleventrules/README.md#globaleventrulesupdateglobaleventrulebyid) - Update Global Event Rule by ID

### [GlobalEventRulesRulesets](docs/sdks/globaleventrulesrulesets/README.md)

* [GlobalEventRulesCreateRuleset](docs/sdks/globaleventrulesrulesets/README.md#globaleventrulescreateruleset) - Create Ruleset
* [GlobalEventRulesDeleteGerRuleset](docs/sdks/globaleventrulesrulesets/README.md#globaleventrulesdeletegerruleset) - Delete GER Ruleset
* [GlobalEventRulesGetRuleset](docs/sdks/globaleventrulesrulesets/README.md#globaleventrulesgetruleset) - Get Ruleset
* [GlobalEventRulesUpdateRuleset](docs/sdks/globaleventrulesrulesets/README.md#globaleventrulesupdateruleset) - Update Ruleset
* [GlobalEventRulesReorderRuleset](docs/sdks/globaleventrulesrulesets/README.md#globaleventrulesreorderruleset) - Reorder Ruleset

### [GlobalEventRulesRulesetsRules](docs/sdks/globaleventrulesrulesetsrules/README.md)

* [GlobalEventRulesListRulesetRules](docs/sdks/globaleventrulesrulesetsrules/README.md#globaleventruleslistrulesetrules) - List Ruleset Rules
* [GlobalEventRulesCreateRule](docs/sdks/globaleventrulesrulesetsrules/README.md#globaleventrulescreaterule) - Create Rule
* [GlobalEventRulesGetRuleByID](docs/sdks/globaleventrulesrulesetsrules/README.md#globaleventrulesgetrulebyid) - Get Rule by ID
* [GlobalEventRulesDeleteRuleByID](docs/sdks/globaleventrulesrulesetsrules/README.md#globaleventrulesdeleterulebyid) - Delete Rule by ID
* [GlobalEventRulesUpdateRuleByID](docs/sdks/globaleventrulesrulesetsrules/README.md#globaleventrulesupdaterulebyid) - Update Rule by ID
* [GlobalEventRulesReorderRulesetByIndex](docs/sdks/globaleventrulesrulesetsrules/README.md#globaleventrulesreorderrulesetbyindex) - Reorder Ruleset By Index

### [GlobalOncallReminderRules](docs/sdks/globaloncallreminderrules/README.md)

* [GlobalOncallReminderRulesDeleteGlobalOncallReminderRules](docs/sdks/globaloncallreminderrules/README.md#globaloncallreminderrulesdeleteglobaloncallreminderrules) - Delete Global Oncall Reminder Rules
* [GlobalOncallReminderRulesGetGlobalOncallReminderRules](docs/sdks/globaloncallreminderrules/README.md#globaloncallreminderrulesgetglobaloncallreminderrules) - Get Global Oncall Reminder Rules
* [GlobalOncallReminderRulesCreateGlobalOncallReminderRules](docs/sdks/globaloncallreminderrules/README.md#globaloncallreminderrulescreateglobaloncallreminderrules) - Create Global Oncall Reminder Rules
* [GlobalOncallReminderRulesUpdateGlobalOncallReminderRules](docs/sdks/globaloncallreminderrules/README.md#globaloncallreminderrulesupdateglobaloncallreminderrules) - Update Global Oncall Reminder Rules

### [Incidents](docs/sdks/incidents/README.md)

* [IncidentsBulkAcknowledgeIncidents](docs/sdks/incidents/README.md#incidentsbulkacknowledgeincidents) - Bulk Acknowledge Incidents
* [IncidentsIncidentExport](docs/sdks/incidents/README.md#incidentsincidentexport) - Incident Export
* [IncidentsIncidentExportAsync](docs/sdks/incidents/README.md#incidentsincidentexportasync) - Incident Export Async
* [IncidentsBulkIncidentsPriorityUpdate](docs/sdks/incidents/README.md#incidentsbulkincidentspriorityupdate) - Bulk Incidents Priority Update
* [IncidentsBulkResolveIncidents](docs/sdks/incidents/README.md#incidentsbulkresolveincidents) - Bulk Resolve Incidents
* [IncidentsGetIncidentByID](docs/sdks/incidents/README.md#incidentsgetincidentbyid) - Get Incident by ID
* [IncidentsAcknowledgeIncident](docs/sdks/incidents/README.md#incidentsacknowledgeincident) - Acknowledge Incident
* [IncidentsGetIncidentEvents](docs/sdks/incidents/README.md#incidentsgetincidentevents) - Get Incident Events
* [IncidentsMarkIncidentSloFalsePositive](docs/sdks/incidents/README.md#incidentsmarkincidentslofalsepositive) - Mark Incident SLO False Positive
* [IncidentsIncidentPriorityUpdate](docs/sdks/incidents/README.md#incidentsincidentpriorityupdate) - Incident Priority Update
* [IncidentsReassignIncident](docs/sdks/incidents/README.md#incidentsreassignincident) - Reassign Incident
* [IncidentsResolveIncident](docs/sdks/incidents/README.md#incidentsresolveincident) - Resolve Incident
* [IncidentsGetIncidentsStatusByRequestids](docs/sdks/incidents/README.md#incidentsgetincidentsstatusbyrequestids) - Get Incidents Status By RequestIDs

### [IncidentsAdditionalResponders](docs/sdks/incidentsadditionalresponders/README.md)

* [AdditionalRespondersGetAdditionalResponders](docs/sdks/incidentsadditionalresponders/README.md#additionalrespondersgetadditionalresponders) - Get Additional Responders
* [AdditionalRespondersAddAdditionalResponders](docs/sdks/incidentsadditionalresponders/README.md#additionalrespondersaddadditionalresponders) - Add Additional Responders
* [AdditionalRespondersRemoveAdditionalResponders](docs/sdks/incidentsadditionalresponders/README.md#additionalrespondersremoveadditionalresponders) - Remove Additional Responders

### [IncidentsAutoPauseTransientAlertsAPTA](docs/sdks/incidentsautopausetransientalertsapta/README.md)

* [AptaMarkAsNotTransient](docs/sdks/incidentsautopausetransientalertsapta/README.md#aptamarkasnottransient) - Mark as Not Transient
* [AptaMarkAsTransient](docs/sdks/incidentsautopausetransientalertsapta/README.md#aptamarkastransient) - Mark as Transient

### [IncidentsCommunicationCard](docs/sdks/incidentscommunicationcard/README.md)

* [CommunicationCardsCreateSlackChannelInCommunicationCard](docs/sdks/incidentscommunicationcard/README.md#communicationcardscreateslackchannelincommunicationcard) - Create Slack Channel in Communication Card
* [CommunicationCardsArchiveSlackChannel](docs/sdks/incidentscommunicationcard/README.md#communicationcardsarchiveslackchannel) - Archive Slack Channel
* [CommunicationCardsGetAllCommunicationCard](docs/sdks/incidentscommunicationcard/README.md#communicationcardsgetallcommunicationcard) - Get All Communication Card
* [CommunicationCardsCreateCommunicationCard](docs/sdks/incidentscommunicationcard/README.md#communicationcardscreatecommunicationcard) - Create Communication Card
* [CommunicationCardsDeleteCommunicationCard](docs/sdks/incidentscommunicationcard/README.md#communicationcardsdeletecommunicationcard) - Delete Communication Card
* [CommunicationCardsUpdateCommunicationCard](docs/sdks/incidentscommunicationcard/README.md#communicationcardsupdatecommunicationcard) - Update Communication Card

### [IncidentsIncidentActions](docs/sdks/incidentsincidentactions/README.md)

* [IncidentActionsRebuildAProjectInCircleci](docs/sdks/incidentsincidentactions/README.md#incidentactionsrebuildaprojectincircleci) - Rebuild a Project In CircleCI
* [IncidentActionsCreateATicketOnJiraCloud](docs/sdks/incidentsincidentactions/README.md#incidentactionscreateaticketonjiracloud) - Create a Ticket on Jira Cloud
* [IncidentActionsCreateATicketOnJiraServer](docs/sdks/incidentsincidentactions/README.md#incidentactionscreateaticketonjiraserver) - Create a Ticket on Jira Server
* [IncidentActionsCreateAnIncidentInServicenow](docs/sdks/incidentsincidentactions/README.md#incidentactionscreateanincidentinservicenow) - Create an Incident in ServiceNow
* [IncidentActionsTriggerAWebhookManually](docs/sdks/incidentsincidentactions/README.md#incidentactionstriggerawebhookmanually) - Trigger a Webhook Manually

### [IncidentsNotes](docs/sdks/incidentsnotes/README.md)

* [NotesCreateNotes](docs/sdks/incidentsnotes/README.md#notescreatenotes) - Create Notes
* [NotesGetAllNotes](docs/sdks/incidentsnotes/README.md#notesgetallnotes) - Get All Notes
* [NotesDeleteNote](docs/sdks/incidentsnotes/README.md#notesdeletenote) - Delete Note
* [NotesUpdateNote](docs/sdks/incidentsnotes/README.md#notesupdatenote) - Update Note

### [IncidentsPostmortems](docs/sdks/incidentspostmortems/README.md)

* [PostmortemsGetAllPostmortems](docs/sdks/incidentspostmortems/README.md#postmortemsgetallpostmortems) - Get All Postmortems
* [PostmortemsDeletePostmortemByIncident](docs/sdks/incidentspostmortems/README.md#postmortemsdeletepostmortembyincident) - Delete Postmortem By Incident
* [PostmortemsGetPostmortemByIncident](docs/sdks/incidentspostmortems/README.md#postmortemsgetpostmortembyincident) - Get Postmortem By Incident
* [PostmortemsCreatePostmortem](docs/sdks/incidentspostmortems/README.md#postmortemscreatepostmortem) - Create Postmortem
* [PostmortemsUpdatePostmortemByIncident](docs/sdks/incidentspostmortems/README.md#postmortemsupdatepostmortembyincident) - Update Postmortem By Incident

### [IncidentsRunbooks](docs/sdks/incidentsrunbooks/README.md)

* [RunbooksAttachRunbooks](docs/sdks/incidentsrunbooks/README.md#runbooksattachrunbooks) - Attach Runbooks

### [IncidentsSnoozeNotifications](docs/sdks/incidentssnoozenotifications/README.md)

* [SnoozeNotificationsSnoozeIncidentNotifications](docs/sdks/incidentssnoozenotifications/README.md#snoozenotificationssnoozeincidentnotifications) - Snooze Incident Notifications
* [SnoozeNotificationsUnsnoozeIncidentNotifications](docs/sdks/incidentssnoozenotifications/README.md#snoozenotificationsunsnoozeincidentnotifications) - Unsnooze Incident Notifications

### [IncidentsTags](docs/sdks/incidentstags/README.md)

* [TagsUpdateTag](docs/sdks/incidentstags/README.md#tagsupdatetag) - Update Tag
* [TagsAppendTag](docs/sdks/incidentstags/README.md#tagsappendtag) - Append Tag

### [Overrides](docs/sdks/overrides/README.md)

* [OverridesListOverrides](docs/sdks/overrides/README.md#overrideslistoverrides) - List Overrides
* [OverridesCreateScheduleOverride](docs/sdks/overrides/README.md#overridescreatescheduleoverride) - Create Schedule Override
* [OverridesDeleteScheduleOverride](docs/sdks/overrides/README.md#overridesdeletescheduleoverride) - Delete Schedule Override
* [OverridesGetOverrideByID](docs/sdks/overrides/README.md#overridesgetoverridebyid) - Get Override by ID
* [OverridesUpdateScheduleOverride](docs/sdks/overrides/README.md#overridesupdatescheduleoverride) - Update Schedule Override

### [Rotation](docs/sdks/rotation/README.md)

* [RotationsGetScheduleRotations](docs/sdks/rotation/README.md#rotationsgetschedulerotations) - List Schedule Rotations
* [RotationsCreateRotation](docs/sdks/rotation/README.md#rotationscreaterotation) - Create Rotation
* [RotationsDeleteRotation](docs/sdks/rotation/README.md#rotationsdeleterotation) - Delete Rotation
* [RotationsGetScheduleRotationByID](docs/sdks/rotation/README.md#rotationsgetschedulerotationbyid) - Get Schedule Rotation by ID
* [RotationsUpdateRotation](docs/sdks/rotation/README.md#rotationsupdaterotation) - Update Rotation
* [RotationsGetRotationParticipants](docs/sdks/rotation/README.md#rotationsgetrotationparticipants) - Get Rotation Participants
* [RotationsUpdateRotationParticipants](docs/sdks/rotation/README.md#rotationsupdaterotationparticipants) - Update Rotation Participants

### [Runbooks](docs/sdks/runbooks/README.md)

* [RunbooksGetAllRunbooksByTeam](docs/sdks/runbooks/README.md#runbooksgetallrunbooksbyteam) - Get All Runbooks By Team
* [RunbooksCreateRunbook](docs/sdks/runbooks/README.md#runbookscreaterunbook) - Create Runbook
* [RunbooksRemoveRunbook](docs/sdks/runbooks/README.md#runbooksremoverunbook) - Remove Runbook
* [RunbooksGetRunbookByID](docs/sdks/runbooks/README.md#runbooksgetrunbookbyid) - Get Runbook By ID
* [RunbooksUpdateRunbook](docs/sdks/runbooks/README.md#runbooksupdaterunbook) - Update Runbook

### [Schedule](docs/sdks/schedule/README.md)

* [SchedulesListSchedules](docs/sdks/schedule/README.md#scheduleslistschedules) - List Schedules
* [SchedulesCreateSchedule](docs/sdks/schedule/README.md#schedulescreateschedule) - Create Schedule
* [SchedulesDeleteSchedule](docs/sdks/schedule/README.md#schedulesdeleteschedule) - Delete Schedule
* [SchedulesGetScheduleByID](docs/sdks/schedule/README.md#schedulesgetschedulebyid) - Get Schedule by ID
* [SchedulesUpdateSchedule](docs/sdks/schedule/README.md#schedulesupdateschedule) - Update Schedule
* [SchedulesPauseresumeSchedule](docs/sdks/schedule/README.md#schedulespauseresumeschedule) - Pause/Resume Schedule
* [SchedulesChangeTimezone](docs/sdks/schedule/README.md#scheduleschangetimezone) - Change Timezone
* [SchedulesCloneSchedule](docs/sdks/schedule/README.md#schedulescloneschedule) - Clone Schedule

### [ScheduleExportSchedule](docs/sdks/scheduleexportschedule/README.md)

* [ExportDeleteIcalLink](docs/sdks/scheduleexportschedule/README.md#exportdeleteicallink) - Delete ICal Link
* [ExportGetScheduleIcalLink](docs/sdks/scheduleexportschedule/README.md#exportgetscheduleicallink) - Get Schedule ICal Link
* [ExportRefreshScheduleIcalLink](docs/sdks/scheduleexportschedule/README.md#exportrefreshscheduleicallink) - Refresh Schedule ICal Link
* [ExportCreateScheduleIcalLink](docs/sdks/scheduleexportschedule/README.md#exportcreatescheduleicallink) - Create Schedule ICal Link

### [Services](docs/sdks/services/README.md)

* [ServicesGetServices](docs/sdks/services/README.md#servicesgetservices) - Get All Services
* [ServicesCreateService](docs/sdks/services/README.md#servicescreateservice) - Create Service
* [ServicesGetServicesByName](docs/sdks/services/README.md#servicesgetservicesbyname) - Get Services By Name
* [ServicesGetServiceByID](docs/sdks/services/README.md#servicesgetservicebyid) - Get Service By ID
* [ServicesUpdateService](docs/sdks/services/README.md#servicesupdateservice) - Update Service
* [ServicesDeleteService](docs/sdks/services/README.md#servicesdeleteservice) - Delete Service
* [ServicesCreateOrUpdateAPTAConfig](docs/sdks/services/README.md#servicescreateorupdateaptaconfig) - Auto Pause Transient Alerts (APTA)
* [ServicesCreateOrUpdateIAGConfig](docs/sdks/services/README.md#servicescreateorupdateiagconfig) - Intelligent Alert Grouping (IAG)
* [ServicesDelayedNotificationConfig](docs/sdks/services/README.md#servicesdelayednotificationconfig) - Delayed Notification Config

### [ServicesDeduplicationRules](docs/sdks/servicesdeduplicationrules/README.md)

* [DeduplicationRulesGetDeduplicationRules](docs/sdks/servicesdeduplicationrules/README.md#deduplicationrulesgetdeduplicationrules) - Get Deduplication Rules
* [DeduplicationRulesCreateOrUpdateDeduplicationRules](docs/sdks/servicesdeduplicationrules/README.md#deduplicationrulescreateorupdatededuplicationrules) - Create or Update Deduplication Rules

### [ServicesDependencies](docs/sdks/servicesdependencies/README.md)

* [DependenciesCreateOrUpdateDependencies](docs/sdks/servicesdependencies/README.md#dependenciescreateorupdatedependencies) - Create or Update Dependencies

### [ServicesExtensions](docs/sdks/servicesextensions/README.md)

* [ExtensionsUpdateSlackExtension](docs/sdks/servicesextensions/README.md#extensionsupdateslackextension) - Update Slack Extension

### [ServicesMaintenanceMode](docs/sdks/servicesmaintenancemode/README.md)

* [MaintenanceModeGetMaintenanceMode](docs/sdks/servicesmaintenancemode/README.md#maintenancemodegetmaintenancemode) - Get Maintenance Mode
* [MaintenanceModeCreateOrUpdateMaintenanceMode](docs/sdks/servicesmaintenancemode/README.md#maintenancemodecreateorupdatemaintenancemode) - Create or Update Maintenance Mode

### [ServicesOverlay](docs/sdks/servicesoverlay/README.md)

* [OverlayGetOptinForKeyBasedDeduplicationForAService](docs/sdks/servicesoverlay/README.md#overlaygetoptinforkeybaseddeduplicationforaservice) - Get Opt-in for Key Based Deduplication for a service
* [OverlayOptinForKeyBasedDeduplicationForAService](docs/sdks/servicesoverlay/README.md#overlayoptinforkeybaseddeduplicationforaservice) - Opt-in for Key Based Deduplication for a service

### [ServicesOverlayCustomContentTemplates](docs/sdks/servicesoverlaycustomcontenttemplates/README.md)

* [OverlayGetAllCustomContentTemplateOverlayByService](docs/sdks/servicesoverlaycustomcontenttemplates/README.md#overlaygetallcustomcontenttemplateoverlaybyservice) - Get All Custom Content Template Overlay by Service
* [OverlayRenderCustomContentOverlay](docs/sdks/servicesoverlaycustomcontenttemplates/README.md#overlayrendercustomcontentoverlay) - Render Custom Content Overlay
* [OverlayDeleteNotificationTemplateOverlay](docs/sdks/servicesoverlaycustomcontenttemplates/README.md#overlaydeletenotificationtemplateoverlay) - Delete Notification Template Overlay
* [OverlayGetCustomContentTemplateOverlay](docs/sdks/servicesoverlaycustomcontenttemplates/README.md#overlaygetcustomcontenttemplateoverlay) - Get Custom Content Template Overlay
* [OverlayCreateOrUpdateNotificationTemplateOverlay](docs/sdks/servicesoverlaycustomcontenttemplates/README.md#overlaycreateorupdatenotificationtemplateoverlay) - Create or Update Notification Template Overlay

### [ServicesOverlayDedupKeyOverlay](docs/sdks/servicesoverlaydedupkeyoverlay/README.md)

* [OverlayGetAllDedupKeyOverlayByService](docs/sdks/servicesoverlaydedupkeyoverlay/README.md#overlaygetalldedupkeyoverlaybyservice) - Get All Dedup Key Overlay by Service
* [OverlayRenderDedupKeyTemplate](docs/sdks/servicesoverlaydedupkeyoverlay/README.md#overlayrenderdedupkeytemplate) - Render Dedup Key template
* [OverlayDeleteDedupKeyOverlay](docs/sdks/servicesoverlaydedupkeyoverlay/README.md#overlaydeletededupkeyoverlay) - Delete Dedup Key Overlay
* [OverlayGetDedupKeyOverlayForAlertSource](docs/sdks/servicesoverlaydedupkeyoverlay/README.md#overlaygetdedupkeyoverlayforalertsource) - Get Dedup Key Overlay for Alert Source
* [OverlayUpdateDedupKeyOverlay](docs/sdks/servicesoverlaydedupkeyoverlay/README.md#overlayupdatededupkeyoverlay) - Update Dedup Key Overlay

### [ServicesRoutingRules](docs/sdks/servicesroutingrules/README.md)

* [RoutingRulesGetRoutingRules](docs/sdks/servicesroutingrules/README.md#routingrulesgetroutingrules) - Get Routing Rules
* [RoutingRulesCreateOrUpdateRoutingRules](docs/sdks/servicesroutingrules/README.md#routingrulescreateorupdateroutingrules) - Create or Update Routing Rules

### [ServicesSuppressionRules](docs/sdks/servicessuppressionrules/README.md)

* [SuppressionRulesGetSuppressionRules](docs/sdks/servicessuppressionrules/README.md#suppressionrulesgetsuppressionrules) - Get Suppression Rules
* [SuppressionRulesCreateOrUpdateSuppressionRules](docs/sdks/servicessuppressionrules/README.md#suppressionrulescreateorupdatesuppressionrules) - Create or Update Suppression Rules

### [ServicesTaggingRules](docs/sdks/servicestaggingrules/README.md)

* [TaggingRulesGetTaggingRules](docs/sdks/servicestaggingrules/README.md#taggingrulesgettaggingrules) - Get Tagging Rules
* [TaggingRulesCreateOrUpdateTaggingRules](docs/sdks/servicestaggingrules/README.md#taggingrulescreateorupdatetaggingrules) - Create or Update Tagging Rules

### [SLOs](docs/sdks/slos/README.md)

* [SLOGetAllSLOs](docs/sdks/slos/README.md#slogetallslos) - Get All SLOs
* [SLOCreateSLO](docs/sdks/slos/README.md#slocreateslo) - Create SLO
* [SLOUpdateSLO](docs/sdks/slos/README.md#sloupdateslo) - Update SLO
* [SLORemoveSLO](docs/sdks/slos/README.md#sloremoveslo) - Remove SLO
* [SLOGetSLOByID](docs/sdks/slos/README.md#slogetslobyid) - Get SLO By ID
* [SLOMarkSLOAffected](docs/sdks/slos/README.md#slomarksloaffected) - Mark SLO Affected
* [SLOMarkSLOFalsePositive](docs/sdks/slos/README.md#slomarkslofalsepositive) - Mark SLO False Positive


### [SquadsV3](docs/sdks/squadsv3/README.md)

* [SquadsGetSquadByTeam](docs/sdks/squadsv3/README.md#squadsgetsquadbyteam) - Get Squad By team
* [SquadsCreateSquad](docs/sdks/squadsv3/README.md#squadscreatesquad) - Create Squad
* [SquadsDeleteSquad](docs/sdks/squadsv3/README.md#squadsdeletesquad) - Delete Squad
* [SquadsGetSquadByID](docs/sdks/squadsv3/README.md#squadsgetsquadbyid) - Get Squad By ID
* [SquadsUpdateSquad](docs/sdks/squadsv3/README.md#squadsupdatesquad) - Update Squad

### [SquadsV4](docs/sdks/squadsv4/README.md)

* [SquadsGetAllSquads](docs/sdks/squadsv4/README.md#squadsgetallsquads) - Get All Squads
* [SquadsCreateSquadV4](docs/sdks/squadsv4/README.md#squadscreatesquadv4) - Create Squad
* [SquadsGetSquadByIDV4](docs/sdks/squadsv4/README.md#squadsgetsquadbyidv4) - Get Squad By ID
* [SquadsUpdateSquadV4](docs/sdks/squadsv4/README.md#squadsupdatesquadv4) - Update Squad
* [SquadsRemoveSquadMember](docs/sdks/squadsv4/README.md#squadsremovesquadmember) - Remove Squad Member
* [SquadsUpdateSquadMember](docs/sdks/squadsv4/README.md#squadsupdatesquadmember) - Update Squad Member
* [SquadsUpdateSquadName](docs/sdks/squadsv4/README.md#squadsupdatesquadname) - Update Squad Name

### [StatusPages](docs/sdks/statuspages/README.md)

* [StatusPagesListStatusPages](docs/sdks/statuspages/README.md#statuspagesliststatuspages) - List Status Pages
* [StatusPagesCreateStatusPage](docs/sdks/statuspages/README.md#statuspagescreatestatuspage) - Create Status Page
* [StatusPagesDeleteStatusPageByID](docs/sdks/statuspages/README.md#statuspagesdeletestatuspagebyid) - Delete Status Page By ID
* [StatusPagesGetStatusPageByID](docs/sdks/statuspages/README.md#statuspagesgetstatuspagebyid) - Get Status Page By ID
* [StatusPagesUpdateStatusPageByID](docs/sdks/statuspages/README.md#statuspagesupdatestatuspagebyid) - Update Status Page By ID
* [StatusPagesListStatusPageStatuses](docs/sdks/statuspages/README.md#statuspagesliststatuspagestatuses) - List Status Page Statuses

### [StatusPagesComponentGroups](docs/sdks/statuspagescomponentgroups/README.md)

* [ComponentGroupsListComponentGroups](docs/sdks/statuspagescomponentgroups/README.md#componentgroupslistcomponentgroups) - List Component Groups
* [ComponentGroupsCreateComponentGroup](docs/sdks/statuspagescomponentgroups/README.md#componentgroupscreatecomponentgroup) - Create Component Group
* [ComponentGroupsDeleteComponentGroupByID](docs/sdks/statuspagescomponentgroups/README.md#componentgroupsdeletecomponentgroupbyid) - Delete Component Group By ID
* [ComponentGroupsGetComponentGroupByID](docs/sdks/statuspagescomponentgroups/README.md#componentgroupsgetcomponentgroupbyid) - Get Component Group By ID

### [StatusPagesComponents](docs/sdks/statuspagescomponents/README.md)

* [ComponentsListComponents](docs/sdks/statuspagescomponents/README.md#componentslistcomponents) - List Components
* [ComponentsCreateComponent](docs/sdks/statuspagescomponents/README.md#componentscreatecomponent) - Create Component
* [ComponentsDeleteComponentByID](docs/sdks/statuspagescomponents/README.md#componentsdeletecomponentbyid) - Delete Component By ID
* [ComponentsGetComponentByID](docs/sdks/statuspagescomponents/README.md#componentsgetcomponentbyid) - Get Component By ID
* [ComponentsUpdateComponentByID](docs/sdks/statuspagescomponents/README.md#componentsupdatecomponentbyid) - Update Component By ID

### [StatusPagesIssues](docs/sdks/statuspagesissues/README.md)

* [IssuesListIssues](docs/sdks/statuspagesissues/README.md#issueslistissues) - List Issues
* [IssuesCreateIssue](docs/sdks/statuspagesissues/README.md#issuescreateissue) - Create Issue
* [IssuesDeleteIssueByID](docs/sdks/statuspagesissues/README.md#issuesdeleteissuebyid) - Delete Issue By ID
* [IssuesGetIssueByID](docs/sdks/statuspagesissues/README.md#issuesgetissuebyid) - Get Issue By ID
* [IssuesUpdateIssue](docs/sdks/statuspagesissues/README.md#issuesupdateissue) - Update Issue
* [IssuesListStatusPageIssueStates](docs/sdks/statuspagesissues/README.md#issuesliststatuspageissuestates) - List Status Page Issue States

### [StatusPagesMaintenances](docs/sdks/statuspagesmaintenances/README.md)

* [MaintenancesListMaintenances](docs/sdks/statuspagesmaintenances/README.md#maintenanceslistmaintenances) - List Maintenances
* [MaintenancesCreateMaintenance](docs/sdks/statuspagesmaintenances/README.md#maintenancescreatemaintenance) - Create Maintenance
* [MaintenancesDeleteMaintenanceByID](docs/sdks/statuspagesmaintenances/README.md#maintenancesdeletemaintenancebyid) - Delete Maintenance By ID
* [MaintenancesGetMaintenanceByID](docs/sdks/statuspagesmaintenances/README.md#maintenancesgetmaintenancebyid) - Get Maintenance By ID
* [MaintenancesUpdateMaintenanceByID](docs/sdks/statuspagesmaintenances/README.md#maintenancesupdatemaintenancebyid) - Update Maintenance By ID

### [StatusPagesSubscribers](docs/sdks/statuspagessubscribers/README.md)

* [StatusPagesListSubscribers](docs/sdks/statuspagessubscribers/README.md#statuspageslistsubscribers) - List Subscribers

### [Teams](docs/sdks/teams/README.md)

* [TeamsGetAllTeams](docs/sdks/teams/README.md#teamsgetallteams) - Get All Teams
* [TeamsCreateTeam](docs/sdks/teams/README.md#teamscreateteam) - Create Team
* [TeamsGetTeamByID](docs/sdks/teams/README.md#teamsgetteambyid) - Get Team By ID
* [TeamsUpdateTeam](docs/sdks/teams/README.md#teamsupdateteam) - Update Team
* [TeamsRemoveTeam](docs/sdks/teams/README.md#teamsremoveteam) - Remove Team
* [TeamsGetAllTeamMembers](docs/sdks/teams/README.md#teamsgetallteammembers) - Get All Team Members
* [TeamsAddTeamMember](docs/sdks/teams/README.md#teamsaddteammember) - Add Team Member
* [TeamsAddBulkTeamMember](docs/sdks/teams/README.md#teamsaddbulkteammember) - Add Bulk Team Member
* [TeamsRemoveTeamMember](docs/sdks/teams/README.md#teamsremoveteammember) - Remove Team Member
* [TeamsUpdateTeamMember](docs/sdks/teams/README.md#teamsupdateteammember) - Update Team Member
* [TeamsGetAllTeamRoles](docs/sdks/teams/README.md#teamsgetallteamroles) - Get All Team Roles
* [TeamsCreateTeamRole](docs/sdks/teams/README.md#teamscreateteamrole) - Create Team Role
* [TeamsRemoveTeamRole](docs/sdks/teams/README.md#teamsremoveteamrole) - Remove Team Role
* [TeamsUpdateTeamRole](docs/sdks/teams/README.md#teamsupdateteamrole) - Update Team Role

### [Users](docs/sdks/users/README.md)

* [UsersGetAllUsers](docs/sdks/users/README.md#usersgetallusers) - Get All Users
* [UsersAddUser](docs/sdks/users/README.md#usersadduser) - Add User
* [UsersUpdateOrgLevelPermissions](docs/sdks/users/README.md#usersupdateorglevelpermissions) - Update Org Level Permissions
* [UsersDeleteUser](docs/sdks/users/README.md#usersdeleteuser) - Delete User
* [UsersGetUserRoles](docs/sdks/users/README.md#usersgetuserroles) - Get User Roles
* [UsersRemoveUserFromOrg](docs/sdks/users/README.md#usersremoveuserfromorg) - Remove User From Org
* [UsersGetUserByID](docs/sdks/users/README.md#usersgetuserbyid) - Get User By ID
* [UsersUpdateUserByID](docs/sdks/users/README.md#usersupdateuserbyid) - Update User by userID

### [UsersAPIToken](docs/sdks/usersapitoken/README.md)

* [UsersGetAllTokens](docs/sdks/usersapitoken/README.md#usersgetalltokens) - Get All Tokens
* [UsersCreateToken](docs/sdks/usersapitoken/README.md#userscreatetoken) - Create Token
* [UsersRemoveToken](docs/sdks/usersapitoken/README.md#usersremovetoken) - Remove Token

### [Webforms](docs/sdks/webforms/README.md)

* [WebformsGetAllWebforms](docs/sdks/webforms/README.md#webformsgetallwebforms) - Get All Webforms
* [WebformsCreateWebform](docs/sdks/webforms/README.md#webformscreatewebform) - Create Webform
* [WebformsUpdateWebform](docs/sdks/webforms/README.md#webformsupdatewebform) - Update Webform
* [WebformsRemoveWebform](docs/sdks/webforms/README.md#webformsremovewebform) - Remove Webform
* [WebformsGetWebformByID](docs/sdks/webforms/README.md#webformsgetwebformbyid) - Get Webform By ID

### [Workflows](docs/sdks/workflows/README.md)

* [WorkflowsListWorkflows](docs/sdks/workflows/README.md#workflowslistworkflows) - List Workflows
* [WorkflowsCreateWorkflow](docs/sdks/workflows/README.md#workflowscreateworkflow) - Create Workflow
* [WorkflowsBulkEnabledisableWorkflows](docs/sdks/workflows/README.md#workflowsbulkenabledisableworkflows) - Bulk Enable/Disable Workflows
* [WorkflowsDeleteWorkflow](docs/sdks/workflows/README.md#workflowsdeleteworkflow) - Delete Workflow
* [WorkflowsGetWorkflowByID](docs/sdks/workflows/README.md#workflowsgetworkflowbyid) - Get Workflow By ID
* [WorkflowsUpdateWorkflow](docs/sdks/workflows/README.md#workflowsupdateworkflow) - Update Workflow
* [WorkflowsCreateAction](docs/sdks/workflows/README.md#workflowscreateaction) - Create Action
* [WorkflowsUpdateActionsOrder](docs/sdks/workflows/README.md#workflowsupdateactionsorder) - Update Actions Order
* [WorkflowsDeleteWorkflowAction](docs/sdks/workflows/README.md#workflowsdeleteworkflowaction) - Delete Workflow Action
* [WorkflowsGetWorkflowActionByID](docs/sdks/workflows/README.md#workflowsgetworkflowactionbyid) - Get Workflow Action By ID
* [WorkflowsUpdateWorkflowAction](docs/sdks/workflows/README.md#workflowsupdateworkflowaction) - Update Workflow Action
* [WorkflowsEnabledisableWorkflow](docs/sdks/workflows/README.md#workflowsenabledisableworkflow) - Enable/Disable Workflow
* [WorkflowsGetWorkflowLogs](docs/sdks/workflows/README.md#workflowsgetworkflowlogs) - Get Workflow Logs

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries. If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API. However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a `retry.Config` object to the call by using the `WithRetries` option:
```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/retry"
	"log"
	"models/operations"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.AnalyticsGetOrgAnalytics(ctx, "<value>", "<value>", nil, nil, operations.WithRetries(
		retry.Config{
			Strategy: "backoff",
			Backoff: &retry.BackoffStrategy{
				InitialInterval: 1,
				MaxInterval:     50,
				Exponent:        1.1,
				MaxElapsedTime:  100,
			},
			RetryConnectionErrors: false,
		}))
	if err != nil {
		log.Fatal(err)
	}
	if res.Object != nil {
		// handle response
	}
}

```

If you'd like to override the default retry strategy for all operations that support retries, you can use the `WithRetryConfig` option at SDK initialization:
```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/retry"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithRetryConfig(
			retry.Config{
				Strategy: "backoff",
				Backoff: &retry.BackoffStrategy{
					InitialInterval: 1,
					MaxInterval:     50,
					Exponent:        1.1,
					MaxElapsedTime:  100,
				},
				RetryConnectionErrors: false,
			}),
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.AnalyticsGetOrgAnalytics(ctx, "<value>", "<value>", nil, nil)
	if err != nil {
		log.Fatal(err)
	}
	if res.Object != nil {
		// handle response
	}
}

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations. All operations return a response object or an error, they will never return both.

By Default, an API error will return `apierrors.APIError`. When custom error responses are specified for an operation, the SDK may also return their associated error. You can refer to respective *Errors* tables in SDK docs for more details on possible error types for each operation.

For example, the `AnalyticsGetOrgAnalytics` function may return the following errors:

| Error Type                                                 | Status Code | Content Type     |
| ---------------------------------------------------------- | ----------- | ---------------- |
| apierrors.AnalyticsGetOrgAnalyticsBadRequestError          | 400         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsUnauthorizedError        | 401         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsPaymentRequiredError     | 402         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsForbiddenError           | 403         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsNotFoundError            | 404         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsConflictError            | 409         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsUnprocessableEntityError | 422         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsInternalServerError      | 500         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsBadGatewayError          | 502         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsServiceUnavailableError  | 503         | application/json |
| apierrors.AnalyticsGetOrgAnalyticsGatewayTimeoutError      | 504         | application/json |
| apierrors.APIError                                         | 4XX, 5XX    | \*/\*            |

### Example

```go
package main

import (
	"context"
	"errors"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/apierrors"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.AnalyticsGetOrgAnalytics(ctx, "<value>", "<value>", nil, nil)
	if err != nil {

		var e *apierrors.AnalyticsGetOrgAnalyticsBadRequestError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsUnauthorizedError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsPaymentRequiredError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsForbiddenError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsNotFoundError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsConflictError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsUnprocessableEntityError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsInternalServerError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsBadGatewayError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsServiceUnavailableError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.AnalyticsGetOrgAnalyticsGatewayTimeoutError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.APIError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}
	}
}

```
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Override Server URL Per-Client

The default server can be overridden globally using the `WithServerURL(serverURL string)` option when initializing the SDK client instance. For example:
```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithServerURL("https://api.squadcast.tech"),
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.AnalyticsGetOrgAnalytics(ctx, "<value>", "<value>", nil, nil)
	if err != nil {
		log.Fatal(err)
	}
	if res.Object != nil {
		// handle response
	}
}

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The Go SDK makes API calls that wrap an internal HTTP client. The requirements for the HTTP client are very simple. It must match this interface:

```go
type HTTPClient interface {
	Do(req *http.Request) (*http.Response, error)
}
```

The built-in `net/http` client satisfies this interface and a default client based on the built-in is provided by default. To replace this default with a client of your own, you can implement this interface yourself or provide your own client configured as desired. Here's a simple example, which adds a client with a 30 second timeout.

```go
import (
	"net/http"
	"time"

	"github.com/SquadcastHub/squadcast-sdk-go"
)

var (
	httpClient = &http.Client{Timeout: 30 * time.Second}
	sdkClient  = squadcastsdk.New(squadcastsdk.WithClient(httpClient))
)
```

This can be a convenient way to configure timeouts, cookies, proxies, custom headers, and other low-level configuration.
<!-- End Custom HTTP Client [http-client] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=squadcastsdk&utm_campaign=go)
