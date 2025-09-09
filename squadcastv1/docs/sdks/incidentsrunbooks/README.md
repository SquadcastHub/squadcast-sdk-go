# IncidentsRunbooks
(*Incidents.Runbooks*)

## Overview

### Available Operations

* [Attach](#attach) - Attach Runbooks

## Attach

Attach Runbooks

### Example Usage

<!-- UsageSnippet language="go" operationID="Runbooks_attachRunbooks" method="post" path="/v3/incidents/{IncidentId}/runbooks" -->
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

    res, err := s.Incidents.Runbooks.Attach(ctx, "<id>", components.V3IncidentsRunbooksAttachRunbooksRequest{
        Runbooks: []string{
            "<value 1>",
            "<value 2>",
        },
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

| Parameter                                                                                                                  | Type                                                                                                                       | Required                                                                                                                   | Description                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                                                      | :heavy_check_mark:                                                                                                         | The context to use for the request.                                                                                        |
| `incidentID`                                                                                                               | *string*                                                                                                                   | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `v3IncidentsRunbooksAttachRunbooksRequest`                                                                                 | [components.V3IncidentsRunbooksAttachRunbooksRequest](../../models/components/v3incidentsrunbooksattachrunbooksrequest.md) | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `opts`                                                                                                                     | [][operations.Option](../../models/operations/option.md)                                                                   | :heavy_minus_sign:                                                                                                         | The options for this request.                                                                                              |

### Response

**[*operations.RunbooksAttachRunbooksResponse](../../models/operations/runbooksattachrunbooksresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.RunbooksAttachRunbooksBadRequestError          | 400                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksForbiddenError           | 403                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksNotFoundError            | 404                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksConflictError            | 409                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksInternalServerError      | 500                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.RunbooksAttachRunbooksGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |