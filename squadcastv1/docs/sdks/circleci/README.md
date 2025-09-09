# Circleci
(*IncidentActions.Circleci*)

## Overview

### Available Operations

* [Rebuild](#rebuild) - Rebuild a Project In CircleCI

## Rebuild

Rebuild a Project In CircleCI

### Example Usage

<!-- UsageSnippet language="go" operationID="IncidentActions_rebuildAProjectInCircleci" method="post" path="/v3/incidents/{incidentID}/actions/circleci/rebuild/{buildNumber}" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.IncidentActions.Circleci.Rebuild(ctx, "<id>", "<value>", components.V3IncidentsIncidentActionsRebuildCircleCIProjectRequest{
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