# Webhook
(*Incidents.Actions.Webhook*)

## Overview

### Available Operations

* [TriggerManually](#triggermanually) - Trigger a Webhook Manually

## TriggerManually

Trigger a Webhook Manually

### Example Usage

<!-- UsageSnippet language="go" operationID="IncidentActions_triggerAWebhookManually" method="post" path="/v3/incidents/{incidentID}/actions/webhook/{eventWebhookID}" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Incidents.Actions.Webhook.TriggerManually(ctx, "<id>", "<id>")
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