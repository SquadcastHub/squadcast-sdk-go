# WorkflowsActions
(*Workflows.Actions*)

## Overview

### Available Operations

* [Create](#create) - Create Action

## Create

Create an Action for a workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_createAction" method="post" path="/v3/workflows/{workflowID}/actions" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/v1"
	"github.com/SquadcastHub/squadcast-sdk-go/v1/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Workflows.Actions.Create(ctx, "<id>", components.CreateV3WorkflowsActionRequestV3WorkflowsSqCreateStatusPageIssue(
        components.V3WorkflowsSqCreateStatusPageIssue{
            Name: components.V3WorkflowsSqCreateStatusPageIssueNameSqAddStatusPageIssue,
            Data: components.V3WorkflowsSqCreateStatusPageIssueData{
                ComponentAndImpact: []components.V3WorkflowsComponentAndImpact{},
                IssueTitle: "<value>",
                PageStatusID: 179034,
                StatusAndMessage: []components.V3WorkflowsIssueStatusAndMessage{
                    components.V3WorkflowsIssueStatusAndMessage{
                        Messages: []string{
                            "<value 1>",
                            "<value 2>",
                            "<value 3>",
                        },
                        StatusID: 692068,
                    },
                },
                StatusPageID: 368871,
            },
        },
    ))
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `ctx`                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                      | :heavy_check_mark:                                                                         | The context to use for the request.                                                        |
| `workflowID`                                                                               | *string*                                                                                   | :heavy_check_mark:                                                                         | N/A                                                                                        |
| `v3WorkflowsActionRequest`                                                                 | [components.V3WorkflowsActionRequest](../../models/components/v3workflowsactionrequest.md) | :heavy_check_mark:                                                                         | N/A                                                                                        |
| `opts`                                                                                     | [][operations.Option](../../models/operations/option.md)                                   | :heavy_minus_sign:                                                                         | The options for this request.                                                              |

### Response

**[*operations.WorkflowsCreateActionResponse](../../models/operations/workflowscreateactionresponse.md), error**

### Errors

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| apierrors.BadRequestError          | 400                                | application/json                   |
| apierrors.UnauthorizedError        | 401                                | application/json                   |
| apierrors.PaymentRequiredError     | 402                                | application/json                   |
| apierrors.ForbiddenError           | 403                                | application/json                   |
| apierrors.NotFoundError            | 404                                | application/json                   |
| apierrors.ConflictError            | 409                                | application/json                   |
| apierrors.UnprocessableEntityError | 422                                | application/json                   |
| apierrors.InternalServerError      | 500                                | application/json                   |
| apierrors.BadGatewayError          | 502                                | application/json                   |
| apierrors.ServiceUnavailableError  | 503                                | application/json                   |
| apierrors.GatewayTimeoutError      | 504                                | application/json                   |
| apierrors.APIError                 | 4XX, 5XX                           | \*/\*                              |