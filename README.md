# squadcastsdk

Developer-friendly & type-safe Go SDK specifically catered to leverage *squadcastsdk* API.

<div align="left" style="margin-bottom: 0;">
    <a href="https://www.speakeasy.com/?utm_source=squadcastsdk&utm_campaign=go" class="badge-link">
        <span class="badge-container">
            <span class="badge-icon-section">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 30 30" fill="none" style="vertical-align: middle;"><title>Speakeasy Logo</title><path fill="currentColor" d="m20.639 27.548-19.17-2.724L0 26.1l20.639 2.931 8.456-7.336-1.468-.208-6.988 6.062Z"></path><path fill="currentColor" d="m20.639 23.1 8.456-7.336-1.468-.207-6.988 6.06-6.84-.972-9.394-1.333-2.936-.417L0 20.169l2.937.416L0 23.132l20.639 2.931 8.456-7.334-1.468-.208-6.986 6.062-9.78-1.39 1.468-1.273 8.31 1.18Z"></path><path fill="currentColor" d="m20.639 18.65-19.17-2.724L0 17.201l20.639 2.931 8.456-7.334-1.468-.208-6.988 6.06Z"></path><path fill="currentColor" d="M27.627 6.658 24.69 9.205 20.64 12.72l-7.923-1.126L1.469 9.996 0 11.271l11.246 1.596-1.467 1.275-8.311-1.181L0 14.235l20.639 2.932 8.456-7.334-2.937-.418 2.937-2.549-1.468-.208Z"></path><path fill="currentColor" d="M29.095 3.902 8.456.971 0 8.305l20.639 2.934 8.456-7.337Z"></path></svg>
            </span>
            <span class="badge-text badge-text-section">BUILT BY SPEAKEASY</span>
        </span>
    </a>
    <a href="https://opensource.org/licenses/MIT" class="badge-link">
        <span class="badge-container blue">
            <span class="badge-text badge-text-section">LICENSE // MIT</span>
        </span>
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
  * [Pagination](#pagination)
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
go get github.com/SquadcastHub/squadcast-sdk-go/v1
```
<!-- End SDK Installation [installation] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.GetOrganization(ctx, "<value>", "<value>", nil, nil)
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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.GetOrganization(ctx, "<value>", "<value>", nil, nil)
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

* [GetOrganization](docs/sdks/analytics/README.md#getorganization) - Get Org level analytics
* [GetTeam](docs/sdks/analytics/README.md#getteam) - Get Team level analytics

### [APITokens](docs/sdks/apitokens/README.md)

* [List](docs/sdks/apitokens/README.md#list) - Get All Tokens

### [CommunicationCards](docs/sdks/communicationcards/README.md)

* [CreateSlackChannel](docs/sdks/communicationcards/README.md#createslackchannel) - Create Slack Channel in Communication Card
* [ArchiveSlackChannel](docs/sdks/communicationcards/README.md#archiveslackchannel) - Archive Slack Channel

### [EscalationPolicies](docs/sdks/escalationpolicies/README.md)

* [GetByTeam](docs/sdks/escalationpolicies/README.md#getbyteam) - Get Escalation Policy By team
* [Create](docs/sdks/escalationpolicies/README.md#create) - Create Escalation Policies
* [Remove](docs/sdks/escalationpolicies/README.md#remove) - Remove Escalation Policy
* [GetByID](docs/sdks/escalationpolicies/README.md#getbyid) - Get Escalation Policy By ID
* [Update](docs/sdks/escalationpolicies/README.md#update) - Update Escalation Policy

### [Exports](docs/sdks/exports/README.md)

* [GetDetails](docs/sdks/exports/README.md#getdetails) - Get Export Details

#### [Extensions.Msteams](docs/sdks/extensionsmsteams/README.md)

* [UpsertConfig](docs/sdks/extensionsmsteams/README.md#upsertconfig) - Create Or Update MSTeams Configuration

#### [Extensions.Webhooks](docs/sdks/extensionswebhooks/README.md)

* [Delete](docs/sdks/extensionswebhooks/README.md#delete) - Delete Webhook
* [GetByID](docs/sdks/extensionswebhooks/README.md#getbyid) - Get Webhook By ID

### [GlobalEventRules](docs/sdks/globaleventrules/README.md)

* [List](docs/sdks/globaleventrules/README.md#list) - List Global Event Rules
* [Create](docs/sdks/globaleventrules/README.md#create) - Create Global Event Rule
* [DeleteRule](docs/sdks/globaleventrules/README.md#deleterule) - Delete Global Event Rule by ID
* [GetByID](docs/sdks/globaleventrules/README.md#getbyid) - Get Global Event Rule by ID
* [UpdateByID](docs/sdks/globaleventrules/README.md#updatebyid) - Update Global Event Rule by ID
* [GetRuleset](docs/sdks/globaleventrules/README.md#getruleset) - Get Ruleset
* [UpdateRuleset](docs/sdks/globaleventrules/README.md#updateruleset) - Update Ruleset
* [UpdateRule](docs/sdks/globaleventrules/README.md#updaterule) - Update Rule by ID

#### [GlobalEventRules.Rules](docs/sdks/rules/README.md)

* [ReorderByIndex](docs/sdks/rules/README.md#reorderbyindex) - Reorder Ruleset By Index

#### [GlobalEventRules.Rulesets](docs/sdks/rulesets/README.md)

* [Create](docs/sdks/rulesets/README.md#create) - Create Ruleset
* [Reorder](docs/sdks/rulesets/README.md#reorder) - Reorder Ruleset
* [ListRulesetRules](docs/sdks/rulesets/README.md#listrulesetrules) - List Ruleset Rules

#### [GlobalEventRules.Rulesets.Rules](docs/sdks/rulesetsrules/README.md)

* [Create](docs/sdks/rulesetsrules/README.md#create) - Create Rule
* [GetByID](docs/sdks/rulesetsrules/README.md#getbyid) - Get Rule by ID

### [GlobalEventRulesRulesets](docs/sdks/globaleventrulesrulesets/README.md)

* [Delete](docs/sdks/globaleventrulesrulesets/README.md#delete) - Delete GER Ruleset

### [GlobalEventRulesRulesetsRules](docs/sdks/globaleventrulesrulesetsrules/README.md)

* [DeleteByID](docs/sdks/globaleventrulesrulesetsrules/README.md#deletebyid) - Delete Rule by ID

### [GlobalOncallReminderRules](docs/sdks/globaloncallreminderrules/README.md)

* [Delete](docs/sdks/globaloncallreminderrules/README.md#delete) - Delete Global Oncall Reminder Rules
* [List](docs/sdks/globaloncallreminderrules/README.md#list) - Get Global Oncall Reminder Rules
* [Create](docs/sdks/globaloncallreminderrules/README.md#create) - Create Global Oncall Reminder Rules
* [Update](docs/sdks/globaloncallreminderrules/README.md#update) - Update Global Oncall Reminder Rules

#### [IncidentActions.Circleci](docs/sdks/circleci/README.md)

* [Rebuild](docs/sdks/circleci/README.md#rebuild) - Rebuild a Project In CircleCI

### [Incidents](docs/sdks/incidents/README.md)

* [BulkAcknowledge](docs/sdks/incidents/README.md#bulkacknowledge) - Bulk Acknowledge Incidents
* [Export](docs/sdks/incidents/README.md#export) - Incident Export
* [ExportAsync](docs/sdks/incidents/README.md#exportasync) - Incident Export Async
* [BulkUpdatePriority](docs/sdks/incidents/README.md#bulkupdatepriority) - Bulk Incidents Priority Update
* [BulkResolve](docs/sdks/incidents/README.md#bulkresolve) - Bulk Resolve Incidents
* [GetByID](docs/sdks/incidents/README.md#getbyid) - Get Incident by ID
* [Acknowledge](docs/sdks/incidents/README.md#acknowledge) - Acknowledge Incident
* [MarkSloFalsePositive](docs/sdks/incidents/README.md#markslofalsepositive) - Mark Incident SLO False Positive
* [UpdatePriority](docs/sdks/incidents/README.md#updatepriority) - Incident Priority Update
* [Reassign](docs/sdks/incidents/README.md#reassign) - Reassign Incident
* [Resolve](docs/sdks/incidents/README.md#resolve) - Resolve Incident
* [GetStatusByRequestIds](docs/sdks/incidents/README.md#getstatusbyrequestids) - Get Incidents Status By RequestIDs
* [GetAllPostmortems](docs/sdks/incidents/README.md#getallpostmortems) - Get All Postmortems
* [MarkAsTransient](docs/sdks/incidents/README.md#markastransient) - Mark as Transient
* [UpdatePostmortem](docs/sdks/incidents/README.md#updatepostmortem) - Update Postmortem By Incident
* [UnsnoozeNotifications](docs/sdks/incidents/README.md#unsnoozenotifications) - Unsnooze Incident Notifications

#### [Incidents.Actions](docs/sdks/incidentsactions/README.md)

* [CreateJiraCloudTicket](docs/sdks/incidentsactions/README.md#createjiracloudticket) - Create a Ticket on Jira Cloud
* [CreateJiraServerTicket](docs/sdks/incidentsactions/README.md#createjiraserverticket) - Create a Ticket on Jira Server
* [CreateInServicenow](docs/sdks/incidentsactions/README.md#createinservicenow) - Create an Incident in ServiceNow

#### [Incidents.Actions.Webhook](docs/sdks/webhook/README.md)

* [TriggerManually](docs/sdks/webhook/README.md#triggermanually) - Trigger a Webhook Manually

#### [Incidents.AdditionalResponders](docs/sdks/additionalresponders/README.md)

* [Get](docs/sdks/additionalresponders/README.md#get) - Get Additional Responders
* [Add](docs/sdks/additionalresponders/README.md#add) - Add Additional Responders
* [Delete](docs/sdks/additionalresponders/README.md#delete) - Remove Additional Responders

#### [Incidents.AutoPauseTransientAlerts](docs/sdks/autopausetransientalerts/README.md)

* [MarkAsNotTransient](docs/sdks/autopausetransientalerts/README.md#markasnottransient) - Mark as Not Transient

#### [Incidents.CommunicationCard](docs/sdks/communicationcard/README.md)

* [Update](docs/sdks/communicationcard/README.md#update) - Update Communication Card

#### [Incidents.CommunicationCards](docs/sdks/incidentscommunicationcards/README.md)

* [GetAll](docs/sdks/incidentscommunicationcards/README.md#getall) - Get All Communication Card
* [Create](docs/sdks/incidentscommunicationcards/README.md#create) - Create Communication Card
* [Delete](docs/sdks/incidentscommunicationcards/README.md#delete) - Delete Communication Card

#### [Incidents.Events](docs/sdks/events/README.md)

* [List](docs/sdks/events/README.md#list) - Get Incident Events

#### [Incidents.Notes](docs/sdks/incidentsnotes/README.md)

* [Create](docs/sdks/incidentsnotes/README.md#create) - Create Notes
* [Delete](docs/sdks/incidentsnotes/README.md#delete) - Delete Note
* [Update](docs/sdks/incidentsnotes/README.md#update) - Update Note

#### [Incidents.Postmortems](docs/sdks/postmortems/README.md)

* [DeleteByIncident](docs/sdks/postmortems/README.md#deletebyincident) - Delete Postmortem By Incident
* [GetByIncident](docs/sdks/postmortems/README.md#getbyincident) - Get Postmortem By Incident
* [Create](docs/sdks/postmortems/README.md#create) - Create Postmortem

#### [Incidents.Runbooks](docs/sdks/incidentsrunbooks/README.md)

* [Attach](docs/sdks/incidentsrunbooks/README.md#attach) - Attach Runbooks

#### [Incidents.SnoozeNotifications](docs/sdks/snoozenotifications/README.md)

* [Snooze](docs/sdks/snoozenotifications/README.md#snooze) - Snooze Incident Notifications

#### [Incidents.Tags](docs/sdks/tags/README.md)

* [Update](docs/sdks/tags/README.md#update) - Update Tag
* [Append](docs/sdks/tags/README.md#append) - Append Tag

### [Msteams](docs/sdks/msteams/README.md)

* [GetConfig](docs/sdks/msteams/README.md#getconfig) - Get MSTeams Config

### [Notes](docs/sdks/notes/README.md)

* [List](docs/sdks/notes/README.md#list) - Get All Notes

### [Overlays](docs/sdks/overlays/README.md)

* [DeleteNotificationTemplate](docs/sdks/overlays/README.md#deletenotificationtemplate) - Delete Notification Template Overlay

### [Overrides](docs/sdks/overrides/README.md)

* [GetByID](docs/sdks/overrides/README.md#getbyid) - Get Override by ID
* [Update](docs/sdks/overrides/README.md#update) - Update Schedule Override

### [Rotations](docs/sdks/rotations/README.md)

* [Create](docs/sdks/rotations/README.md#create) - Create Rotation
* [GetByID](docs/sdks/rotations/README.md#getbyid) - Get Schedule Rotation by ID
* [Update](docs/sdks/rotations/README.md#update) - Update Rotation
* [GetParticipants](docs/sdks/rotations/README.md#getparticipants) - Get Rotation Participants
* [UpdateParticipants](docs/sdks/rotations/README.md#updateparticipants) - Update Rotation Participants

### [Runbooks](docs/sdks/runbooks/README.md)

* [ListByTeam](docs/sdks/runbooks/README.md#listbyteam) - Get All Runbooks By Team
* [Create](docs/sdks/runbooks/README.md#create) - Create Runbook
* [Remove](docs/sdks/runbooks/README.md#remove) - Remove Runbook
* [GetByID](docs/sdks/runbooks/README.md#getbyid) - Get Runbook By ID
* [Update](docs/sdks/runbooks/README.md#update) - Update Runbook

### [Schedules](docs/sdks/schedules/README.md)

* [List](docs/sdks/schedules/README.md#list) - List Schedules
* [Create](docs/sdks/schedules/README.md#create) - Create Schedule
* [Delete](docs/sdks/schedules/README.md#delete) - Delete Schedule
* [GetByID](docs/sdks/schedules/README.md#getbyid) - Get Schedule by ID
* [Update](docs/sdks/schedules/README.md#update) - Update Schedule
* [PauseResume](docs/sdks/schedules/README.md#pauseresume) - Pause/Resume Schedule
* [ChangeTimezone](docs/sdks/schedules/README.md#changetimezone) - Change Timezone
* [Clone](docs/sdks/schedules/README.md#clone) - Clone Schedule
* [GetIcalLink](docs/sdks/schedules/README.md#geticallink) - Get Schedule ICal Link
* [RefreshIcalLink](docs/sdks/schedules/README.md#refreshicallink) - Refresh Schedule ICal Link
* [CreateIcalLink](docs/sdks/schedules/README.md#createicallink) - Create Schedule ICal Link
* [CreateScheduleOverride](docs/sdks/schedules/README.md#createscheduleoverride) - Create Schedule Override
* [DeleteRotation](docs/sdks/schedules/README.md#deleterotation) - Delete Rotation

#### [Schedules.Export](docs/sdks/export/README.md)

* [DeleteIcalLink](docs/sdks/export/README.md#deleteicallink) - Delete ICal Link

#### [Schedules.Overrides](docs/sdks/schedulesoverrides/README.md)

* [List](docs/sdks/schedulesoverrides/README.md#list) - List Overrides
* [Delete](docs/sdks/schedulesoverrides/README.md#delete) - Delete Schedule Override

#### [Schedules.Rotations](docs/sdks/schedulesrotations/README.md)

* [List](docs/sdks/schedulesrotations/README.md#list) - List Schedule Rotations

### [Services](docs/sdks/services/README.md)

* [List](docs/sdks/services/README.md#list) - Get All Services
* [Create](docs/sdks/services/README.md#create) - Create Service
* [GetByName](docs/sdks/services/README.md#getbyname) - Get Services By Name
* [GetByID](docs/sdks/services/README.md#getbyid) - Get Service By ID
* [Update](docs/sdks/services/README.md#update) - Update Service
* [Delete](docs/sdks/services/README.md#delete) - Delete Service
* [CreateOrUpdateAptaConfig](docs/sdks/services/README.md#createorupdateaptaconfig) - Auto Pause Transient Alerts (APTA)
* [UpsertIagConfig](docs/sdks/services/README.md#upsertiagconfig) - Intelligent Alert Grouping (IAG)
* [UpdateNotificationDelayConfig](docs/sdks/services/README.md#updatenotificationdelayconfig) - Delayed Notification Config
* [CreateOrUpdateDependencies](docs/sdks/services/README.md#createorupdatedependencies) - Create or Update Dependencies
* [CreateOrUpdateNotificationTemplateOverlay](docs/sdks/services/README.md#createorupdatenotificationtemplateoverlay) - Create or Update Notification Template Overlay
* [GetAllDedupKeyOverlays](docs/sdks/services/README.md#getalldedupkeyoverlays) - Get All Dedup Key Overlay by Service
* [UpdateDedupKeyOverlay](docs/sdks/services/README.md#updatededupkeyoverlay) - Update Dedup Key Overlay
* [GetRoutingRules](docs/sdks/services/README.md#getroutingrules) - Get Routing Rules
* [CreateOrUpdateSuppressionRules](docs/sdks/services/README.md#createorupdatesuppressionrules) - Create or Update Suppression Rules
* [CreateOrUpdateTaggingRules](docs/sdks/services/README.md#createorupdatetaggingrules) - Create or Update Tagging Rules

#### [Services.DeduplicationRules](docs/sdks/deduplicationrules/README.md)

* [Get](docs/sdks/deduplicationrules/README.md#get) - Get Deduplication Rules
* [CreateOrUpdate](docs/sdks/deduplicationrules/README.md#createorupdate) - Create or Update Deduplication Rules

#### [Services.Extensions](docs/sdks/servicesextensions/README.md)

* [UpdateSlack](docs/sdks/servicesextensions/README.md#updateslack) - Update Slack Extension

#### [Services.MaintenanceMode](docs/sdks/maintenancemode/README.md)

* [Get](docs/sdks/maintenancemode/README.md#get) - Get Maintenance Mode
* [CreateOrUpdate](docs/sdks/maintenancemode/README.md#createorupdate) - Create or Update Maintenance Mode

#### [Services.Overlay](docs/sdks/overlay/README.md)

* [GetKeyBasedDeduplicationOptin](docs/sdks/overlay/README.md#getkeybaseddeduplicationoptin) - Get Opt-in for Key Based Deduplication for a service
* [OptInForKeyBasedDeduplication](docs/sdks/overlay/README.md#optinforkeybaseddeduplication) - Opt-in for Key Based Deduplication for a service

#### [Services.Overlays](docs/sdks/servicesoverlays/README.md)

* [GetCustomContentTemplates](docs/sdks/servicesoverlays/README.md#getcustomcontenttemplates) - Get All Custom Content Template Overlay by Service
* [GetCustomContent](docs/sdks/servicesoverlays/README.md#getcustomcontent) - Get Custom Content Template Overlay
* [GetDedupKey](docs/sdks/servicesoverlays/README.md#getdedupkey) - Get Dedup Key Overlay for Alert Source

#### [Services.Overlays.CustomContent](docs/sdks/customcontent/README.md)

* [Render](docs/sdks/customcontent/README.md#render) - Render Custom Content Overlay

#### [Services.Overlays.DedupKey](docs/sdks/dedupkey/README.md)

* [Render](docs/sdks/dedupkey/README.md#render) - Render Dedup Key template
* [Delete](docs/sdks/dedupkey/README.md#delete) - Delete Dedup Key Overlay

#### [Services.RoutingRules](docs/sdks/routingrules/README.md)

* [CreateOrUpdate](docs/sdks/routingrules/README.md#createorupdate) - Create or Update Routing Rules

#### [Services.SuppressionRules](docs/sdks/suppressionrules/README.md)

* [Get](docs/sdks/suppressionrules/README.md#get) - Get Suppression Rules

#### [Services.TaggingRules](docs/sdks/taggingrules/README.md)

* [Get](docs/sdks/taggingrules/README.md#get) - Get Tagging Rules

### [Slos](docs/sdks/slos/README.md)

* [ListAll](docs/sdks/slos/README.md#listall) - Get All SLOs
* [Create](docs/sdks/slos/README.md#create) - Create SLO
* [Update](docs/sdks/slos/README.md#update) - Update SLO
* [Remove](docs/sdks/slos/README.md#remove) - Remove SLO
* [GetByID](docs/sdks/slos/README.md#getbyid) - Get SLO By ID
* [MarkAffected](docs/sdks/slos/README.md#markaffected) - Mark SLO Affected
* [MarkFalsePositive](docs/sdks/slos/README.md#markfalsepositive) - Mark SLO False Positive

### [Squads](docs/sdks/squads/README.md)

* [List](docs/sdks/squads/README.md#list) - Get All Squads
* [RemoveMember](docs/sdks/squads/README.md#removemember) - Remove Squad Member
* [UpdateMemberRole](docs/sdks/squads/README.md#updatememberrole) - Update Squad Member
* [UpdateName](docs/sdks/squads/README.md#updatename) - Update Squad Name
* [Delete](docs/sdks/squads/README.md#delete) - Delete Squad

#### [Squads.V4](docs/sdks/squadsv4/README.md)

* [Create](docs/sdks/squadsv4/README.md#create) - Create Squad
* [GetByID](docs/sdks/squadsv4/README.md#getbyid) - Get Squad By ID

### [StatusPages](docs/sdks/statuspages/README.md)

* [List](docs/sdks/statuspages/README.md#list) - List Status Pages
* [Create](docs/sdks/statuspages/README.md#create) - Create Status Page
* [DeleteByID](docs/sdks/statuspages/README.md#deletebyid) - Delete Status Page By ID
* [GetByID](docs/sdks/statuspages/README.md#getbyid) - Get Status Page By ID
* [UpdateByID](docs/sdks/statuspages/README.md#updatebyid) - Update Status Page By ID
* [CreateIssue](docs/sdks/statuspages/README.md#createissue) - Create Issue
* [UpdateIssue](docs/sdks/statuspages/README.md#updateissue) - Update Issue
* [ListMaintenances](docs/sdks/statuspages/README.md#listmaintenances) - List Maintenances
* [GetMaintenanceByID](docs/sdks/statuspages/README.md#getmaintenancebyid) - Get Maintenance By ID
* [GetStatuses](docs/sdks/statuspages/README.md#getstatuses) - List Status Page Statuses

#### [StatusPages.ComponentGroups](docs/sdks/componentgroups/README.md)

* [List](docs/sdks/componentgroups/README.md#list) - List Component Groups
* [Create](docs/sdks/componentgroups/README.md#create) - Create Component Group
* [DeleteByID](docs/sdks/componentgroups/README.md#deletebyid) - Delete Component Group By ID
* [GetByID](docs/sdks/componentgroups/README.md#getbyid) - Get Component Group By ID

#### [StatusPages.Components](docs/sdks/components/README.md)

* [List](docs/sdks/components/README.md#list) - List Components
* [Create](docs/sdks/components/README.md#create) - Create Component
* [DeleteByID](docs/sdks/components/README.md#deletebyid) - Delete Component By ID
* [GetByID](docs/sdks/components/README.md#getbyid) - Get Component By ID
* [UpdateByID](docs/sdks/components/README.md#updatebyid) - Update Component By ID

#### [StatusPages.Issues](docs/sdks/issues/README.md)

* [List](docs/sdks/issues/README.md#list) - List Issues
* [Delete](docs/sdks/issues/README.md#delete) - Delete Issue By ID
* [GetByID](docs/sdks/issues/README.md#getbyid) - Get Issue By ID
* [ListStates](docs/sdks/issues/README.md#liststates) - List Status Page Issue States

#### [StatusPages.Maintenances](docs/sdks/maintenances/README.md)

* [Create](docs/sdks/maintenances/README.md#create) - Create Maintenance
* [DeleteByID](docs/sdks/maintenances/README.md#deletebyid) - Delete Maintenance By ID
* [UpdateByID](docs/sdks/maintenances/README.md#updatebyid) - Update Maintenance By ID

#### [StatusPages.Subscribers](docs/sdks/subscribers/README.md)

* [List](docs/sdks/subscribers/README.md#list) - List Subscribers

### [Teams](docs/sdks/teams/README.md)

* [GetAll](docs/sdks/teams/README.md#getall) - Get All Teams
* [Create](docs/sdks/teams/README.md#create) - Create Team
* [GetByID](docs/sdks/teams/README.md#getbyid) - Get Team By ID
* [Update](docs/sdks/teams/README.md#update) - Update Team
* [Delete](docs/sdks/teams/README.md#delete) - Remove Team
* [AddMember](docs/sdks/teams/README.md#addmember) - Add Team Member
* [AddBulkMember](docs/sdks/teams/README.md#addbulkmember) - Add Bulk Team Member
* [RemoveMember](docs/sdks/teams/README.md#removemember) - Remove Team Member
* [UpdateMember](docs/sdks/teams/README.md#updatemember) - Update Team Member
* [GetAllRoles](docs/sdks/teams/README.md#getallroles) - Get All Team Roles
* [CreateRole](docs/sdks/teams/README.md#createrole) - Create Team Role
* [RemoveRole](docs/sdks/teams/README.md#removerole) - Remove Team Role
* [UpdateRole](docs/sdks/teams/README.md#updaterole) - Update Team Role

#### [Teams.Members](docs/sdks/members/README.md)

* [GetAll](docs/sdks/members/README.md#getall) - Get All Team Members

### [Tokens](docs/sdks/tokens/README.md)

* [CreateUserToken](docs/sdks/tokens/README.md#createusertoken) - Create Token

### [Users](docs/sdks/users/README.md)

* [GetAll](docs/sdks/users/README.md#getall) - Get All Users
* [Add](docs/sdks/users/README.md#add) - Add User
* [UpdateOrgLevelPermissions](docs/sdks/users/README.md#updateorglevelpermissions) - Update Org Level Permissions
* [Delete](docs/sdks/users/README.md#delete) - Delete User
* [GetRoles](docs/sdks/users/README.md#getroles) - Get User Roles
* [RemoveFromOrg](docs/sdks/users/README.md#removefromorg) - Remove User From Org
* [GetByID](docs/sdks/users/README.md#getbyid) - Get User By ID
* [Update](docs/sdks/users/README.md#update) - Update User by userID

#### [Users.APIToken](docs/sdks/apitoken/README.md)

* [Remove](docs/sdks/apitoken/README.md#remove) - Remove Token

#### [V4.Squads](docs/sdks/v4squads/README.md)

* [Update](docs/sdks/v4squads/README.md#update) - Update Squad

### [Webforms](docs/sdks/webforms/README.md)

* [GetAll](docs/sdks/webforms/README.md#getall) - Get All Webforms
* [Create](docs/sdks/webforms/README.md#create) - Create Webform
* [Update](docs/sdks/webforms/README.md#update) - Update Webform
* [Remove](docs/sdks/webforms/README.md#remove) - Remove Webform
* [Get](docs/sdks/webforms/README.md#get) - Get Webform By ID

### [Webhooks](docs/sdks/webhooks/README.md)

* [GetAll](docs/sdks/webhooks/README.md#getall) - Get All Webhooks
* [Create](docs/sdks/webhooks/README.md#create) - Create Webhook
* [Update](docs/sdks/webhooks/README.md#update) - Update Webhook

### [Workflows](docs/sdks/workflows/README.md)

* [List](docs/sdks/workflows/README.md#list) - List Workflows
* [Create](docs/sdks/workflows/README.md#create) - Create Workflow
* [BulkEnableDisable](docs/sdks/workflows/README.md#bulkenabledisable) - Bulk Enable/Disable Workflows
* [Delete](docs/sdks/workflows/README.md#delete) - Delete Workflow
* [GetByID](docs/sdks/workflows/README.md#getbyid) - Get Workflow By ID
* [Update](docs/sdks/workflows/README.md#update) - Update Workflow
* [UpdateActionsOrder](docs/sdks/workflows/README.md#updateactionsorder) - Update Actions Order
* [DeleteAction](docs/sdks/workflows/README.md#deleteaction) - Delete Workflow Action
* [GetAction](docs/sdks/workflows/README.md#getaction) - Get Workflow Action By ID
* [UpdateAction](docs/sdks/workflows/README.md#updateaction) - Update Workflow Action
* [ToggleEnable](docs/sdks/workflows/README.md#toggleenable) - Enable/Disable Workflow
* [GetLogs](docs/sdks/workflows/README.md#getlogs) - Get Workflow Logs

#### [Workflows.Actions](docs/sdks/workflowsactions/README.md)

* [Create](docs/sdks/workflowsactions/README.md#create) - Create Action

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Pagination [pagination] -->
## Pagination

Some of the endpoints in this SDK support pagination. To use pagination, you make your SDK calls as usual, but the
returned response object will have a `Next` method that can be called to pull down the next group of results. If the
return value of `Next` is `nil`, then there are no more pages to be fetched.

Here's an example of one such pagination call:
```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.EscalationPolicies.GetByTeam(ctx, "<id>", nil, nil)
	if err != nil {
		log.Fatal(err)
	}
	if res.Object != nil {
		for {
			// handle items

			res, err = res.Next()

			if err != nil {
				// handle error
			}

			if res == nil {
				break
			}
		}
	}
}

```
<!-- End Pagination [pagination] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries. If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API. However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a `retry.Config` object to the call by using the `WithRetries` option:
```go
package main

import (
	"context"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"github.com/SquadcastHub/squadcast-sdk-go/v1/retry"
	"log"
	"models/operations"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.GetOrganization(ctx, "<value>", "<value>", nil, nil, operations.WithRetries(
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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"github.com/SquadcastHub/squadcast-sdk-go/v1/retry"
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

	res, err := s.Analytics.GetOrganization(ctx, "<value>", "<value>", nil, nil)
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

For example, the `GetOrganization` function may return the following errors:

| Error Type                         | Status Code | Content Type     |
| ---------------------------------- | ----------- | ---------------- |
| apierrors.BadRequestError          | 400         | application/json |
| apierrors.UnauthorizedError        | 401         | application/json |
| apierrors.PaymentRequiredError     | 402         | application/json |
| apierrors.ForbiddenError           | 403         | application/json |
| apierrors.NotFoundError            | 404         | application/json |
| apierrors.ConflictError            | 409         | application/json |
| apierrors.UnprocessableEntityError | 422         | application/json |
| apierrors.InternalServerError      | 500         | application/json |
| apierrors.BadGatewayError          | 502         | application/json |
| apierrors.ServiceUnavailableError  | 503         | application/json |
| apierrors.GatewayTimeoutError      | 504         | application/json |
| apierrors.APIError                 | 4XX, 5XX    | \*/\*            |

### Example

```go
package main

import (
	"context"
	"errors"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"github.com/SquadcastHub/squadcast-sdk-go/v1/models/apierrors"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.GetOrganization(ctx, "<value>", "<value>", nil, nil)
	if err != nil {

		var e *apierrors.BadRequestError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.UnauthorizedError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.PaymentRequiredError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.ForbiddenError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.NotFoundError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.ConflictError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.UnprocessableEntityError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.InternalServerError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.BadGatewayError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.ServiceUnavailableError
		if errors.As(err, &e) {
			// handle error
			log.Fatal(e.Error())
		}

		var e *apierrors.GatewayTimeoutError
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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"log"
	"os"
)

func main() {
	ctx := context.Background()

	s := squadcastsdk.New(
		squadcastsdk.WithServerURL("https://api.squadcast.com"),
		squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
	)

	res, err := s.Analytics.GetOrganization(ctx, "<value>", "<value>", nil, nil)
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

	"github.com/SquadcastHub/squadcast-sdk-go/v1"
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

<style>
  :root {
    --badge-gray-bg: #f3f4f6;
    --badge-gray-border: #d1d5db;
    --badge-gray-text: #374151;
    --badge-blue-bg: #eff6ff;
    --badge-blue-border: #3b82f6;
    --badge-blue-text: #3b82f6;
  }

  @media (prefers-color-scheme: dark) {
    :root {
      --badge-gray-bg: #374151;
      --badge-gray-border: #4b5563;
      --badge-gray-text: #f3f4f6;
      --badge-blue-bg: #1e3a8a;
      --badge-blue-border: #3b82f6;
      --badge-blue-text: #93c5fd;
    }
  }
  
  h1 {
    border-bottom: none !important;
    margin-bottom: 4px;
    margin-top: 0;
    letter-spacing: 0.5px;
    font-weight: 600;
  }
  
  .badge-text {
    letter-spacing: 1px;
    font-weight: 300;
  }
  
  .badge-container {
    display: inline-flex;
    align-items: center;
    background: var(--badge-gray-bg);
    border: 1px solid var(--badge-gray-border);
    border-radius: 6px;
    overflow: hidden;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif;
    font-size: 11px;
    text-decoration: none;
    vertical-align: middle;
  }

  .badge-container.blue {
    background: var(--badge-blue-bg);
    border-color: var(--badge-blue-border);
  }

  .badge-icon-section {
    padding: 4px 8px;
    border-right: 1px solid var(--badge-gray-border);
    display: flex;
    align-items: center;
  }

  .badge-text-section {
    padding: 4px 10px;
    color: var(--badge-gray-text);
    font-weight: 400;
  }

  .badge-container.blue .badge-text-section {
    color: var(--badge-blue-text);
  }
  
  .badge-link {
    text-decoration: none;
    margin-left: 8px;
    display: inline-flex;
    vertical-align: middle;
  }

  .badge-link:hover {
    text-decoration: none;
  }
  
  .badge-link:first-child {
    margin-left: 0;
  }
  
  .badge-icon-section svg {
    color: var(--badge-gray-text);
  }

  .badge-container.blue .badge-icon-section svg {
    color: var(--badge-blue-text);
  }
</style> 