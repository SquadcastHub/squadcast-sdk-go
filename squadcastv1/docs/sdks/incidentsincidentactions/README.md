# IncidentsIncidentActions
(*IncidentsIncidentActions*)

## Overview

### Available Operations

* [IncidentActionsRebuildAProjectInCircleci](#incidentactionsrebuildaprojectincircleci) - Rebuild a Project In CircleCI
* [IncidentActionsCreateATicketOnJiraCloud](#incidentactionscreateaticketonjiracloud) - Create a Ticket on Jira Cloud
* [IncidentActionsCreateATicketOnJiraServer](#incidentactionscreateaticketonjiraserver) - Create a Ticket on Jira Server
* [IncidentActionsCreateAnIncidentInServicenow](#incidentactionscreateanincidentinservicenow) - Create an Incident in ServiceNow
* [IncidentActionsTriggerAWebhookManually](#incidentactionstriggerawebhookmanually) - Trigger a Webhook Manually

## IncidentActionsRebuildAProjectInCircleci

Rebuild a Project In CircleCI

### Example Usage

<!-- UsageSnippet language="go" operationID="IncidentActions_rebuildAProjectInCircleci" method="post" path="/v3/incidents/{incidentID}/actions/circleci/rebuild/{buildNumber}" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.IncidentsIncidentActions.IncidentActionsRebuildAProjectInCircleci(ctx, "<id>", "<value>", components.V3IncidentsIncidentActionsRebuildCircleCIProjectRequest{
        VcsType: "<value>",
        Username: "Dora.Waelchi",
        Reponame: "<value>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                                                | Type                                                                                                                                                     | Required                                                                                                                                                 | Description                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                                                    | :heavy_check_mark:                                                                                                                                       | The context to use for the request.                                                                                                                      |
| `incidentID`                                                                                                                                             | *string*                                                                                                                                                 | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `buildNumber`                                                                                                                                            | *string*                                                                                                                                                 | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `v3IncidentsIncidentActionsRebuildCircleCIProjectRequest`                                                                                                | [components.V3IncidentsIncidentActionsRebuildCircleCIProjectRequest](../../models/components/v3incidentsincidentactionsrebuildcircleciprojectrequest.md) | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `opts`                                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                                 | :heavy_minus_sign:                                                                                                                                       | The options for this request.                                                                                                                            |

### Response

**[*operations.IncidentActionsRebuildAProjectInCircleciResponse](../../models/operations/incidentactionsrebuildaprojectincircleciresponse.md), error**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| apierrors.BadRequest                                                       | 400                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciUnauthorizedError        | 401                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciPaymentRequiredError     | 402                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciForbiddenError           | 403                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciNotFoundError            | 404                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciConflictError            | 409                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciUnprocessableEntityError | 422                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciInternalServerError      | 500                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciBadGatewayError          | 502                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciServiceUnavailableError  | 503                                                                        | application/json                                                           |
| apierrors.IncidentActionsRebuildAProjectInCircleciGatewayTimeoutError      | 504                                                                        | application/json                                                           |
| apierrors.APIError                                                         | 4XX, 5XX                                                                   | \*/\*                                                                      |

## IncidentActionsCreateATicketOnJiraCloud

Create a Ticket on Jira Cloud

### Example Usage

<!-- UsageSnippet language="go" operationID="IncidentActions_createATicketOnJiraCloud" method="post" path="/v3/incidents/{incidentID}/actions/jira/new/jira-cloud" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.IncidentsIncidentActions.IncidentActionsCreateATicketOnJiraCloud(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.IncidentActionsCreateATicketOnJiraCloudResponse](../../models/operations/incidentactionscreateaticketonjiracloudresponse.md), error**

### Errors

| Error Type                                                                | Status Code                                                               | Content Type                                                              |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| apierrors.IncidentActionsCreateATicketOnJiraCloudBadRequestError          | 400                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudUnauthorizedError        | 401                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudPaymentRequiredError     | 402                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudForbiddenError           | 403                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudNotFoundError            | 404                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudConflictError            | 409                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudUnprocessableEntityError | 422                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudInternalServerError      | 500                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudBadGatewayError          | 502                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudServiceUnavailableError  | 503                                                                       | application/json                                                          |
| apierrors.IncidentActionsCreateATicketOnJiraCloudGatewayTimeoutError      | 504                                                                       | application/json                                                          |
| apierrors.APIError                                                        | 4XX, 5XX                                                                  | \*/\*                                                                     |

## IncidentActionsCreateATicketOnJiraServer

Create a Ticket on Jira Server

### Example Usage

<!-- UsageSnippet language="go" operationID="IncidentActions_createATicketOnJiraServer" method="post" path="/v3/incidents/{incidentID}/actions/jira/new/jira-server" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.IncidentsIncidentActions.IncidentActionsCreateATicketOnJiraServer(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.IncidentActionsCreateATicketOnJiraServerResponse](../../models/operations/incidentactionscreateaticketonjiraserverresponse.md), error**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| apierrors.IncidentActionsCreateATicketOnJiraServerBadRequestError          | 400                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerUnauthorizedError        | 401                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerPaymentRequiredError     | 402                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerForbiddenError           | 403                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerNotFoundError            | 404                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerConflictError            | 409                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerUnprocessableEntityError | 422                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerInternalServerError      | 500                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerBadGatewayError          | 502                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerServiceUnavailableError  | 503                                                                        | application/json                                                           |
| apierrors.IncidentActionsCreateATicketOnJiraServerGatewayTimeoutError      | 504                                                                        | application/json                                                           |
| apierrors.APIError                                                         | 4XX, 5XX                                                                   | \*/\*                                                                      |

## IncidentActionsCreateAnIncidentInServicenow

Create an Incident in ServiceNow

### Example Usage

<!-- UsageSnippet language="go" operationID="IncidentActions_createAnIncidentInServicenow" method="post" path="/v3/incidents/{incidentID}/actions/servicenow/new" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.IncidentsIncidentActions.IncidentActionsCreateAnIncidentInServicenow(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.IncidentActionsCreateAnIncidentInServicenowResponse](../../models/operations/incidentactionscreateanincidentinservicenowresponse.md), error**

### Errors

| Error Type                                                                    | Status Code                                                                   | Content Type                                                                  |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| apierrors.IncidentActionsCreateAnIncidentInServicenowBadRequestError          | 400                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowUnauthorizedError        | 401                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowPaymentRequiredError     | 402                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowForbiddenError           | 403                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowNotFoundError            | 404                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowConflictError            | 409                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowUnprocessableEntityError | 422                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowInternalServerError      | 500                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowBadGatewayError          | 502                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowServiceUnavailableError  | 503                                                                           | application/json                                                              |
| apierrors.IncidentActionsCreateAnIncidentInServicenowGatewayTimeoutError      | 504                                                                           | application/json                                                              |
| apierrors.APIError                                                            | 4XX, 5XX                                                                      | \*/\*                                                                         |

## IncidentActionsTriggerAWebhookManually

Trigger a Webhook Manually

### Example Usage

<!-- UsageSnippet language="go" operationID="IncidentActions_triggerAWebhookManually" method="post" path="/v3/incidents/{incidentID}/actions/webhook/{eventWebhookID}" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.IncidentsIncidentActions.IncidentActionsTriggerAWebhookManually(ctx, "<id>", "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `eventWebhookID`                                         | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.IncidentActionsTriggerAWebhookManuallyResponse](../../models/operations/incidentactionstriggerawebhookmanuallyresponse.md), error**

### Errors

| Error Type                                                               | Status Code                                                              | Content Type                                                             |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| apierrors.IncidentActionsTriggerAWebhookManuallyBadRequestError          | 400                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyUnauthorizedError        | 401                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyPaymentRequiredError     | 402                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyForbiddenError           | 403                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyNotFoundError            | 404                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyConflictError            | 409                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyUnprocessableEntityError | 422                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyInternalServerError      | 500                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyBadGatewayError          | 502                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyServiceUnavailableError  | 503                                                                      | application/json                                                         |
| apierrors.IncidentActionsTriggerAWebhookManuallyGatewayTimeoutError      | 504                                                                      | application/json                                                         |
| apierrors.APIError                                                       | 4XX, 5XX                                                                 | \*/\*                                                                    |