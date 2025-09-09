# Workflows
(*Workflows*)

## Overview

### Available Operations

* [WorkflowsListWorkflows](#workflowslistworkflows) - List Workflows
* [WorkflowsCreateWorkflow](#workflowscreateworkflow) - Create Workflow
* [WorkflowsBulkEnabledisableWorkflows](#workflowsbulkenabledisableworkflows) - Bulk Enable/Disable Workflows
* [WorkflowsDeleteWorkflow](#workflowsdeleteworkflow) - Delete Workflow
* [WorkflowsGetWorkflowByID](#workflowsgetworkflowbyid) - Get Workflow By ID
* [WorkflowsUpdateWorkflow](#workflowsupdateworkflow) - Update Workflow
* [WorkflowsCreateAction](#workflowscreateaction) - Create Action
* [WorkflowsUpdateActionsOrder](#workflowsupdateactionsorder) - Update Actions Order
* [WorkflowsDeleteWorkflowAction](#workflowsdeleteworkflowaction) - Delete Workflow Action
* [WorkflowsGetWorkflowActionByID](#workflowsgetworkflowactionbyid) - Get Workflow Action By ID
* [WorkflowsUpdateWorkflowAction](#workflowsupdateworkflowaction) - Update Workflow Action
* [WorkflowsEnabledisableWorkflow](#workflowsenabledisableworkflow) - Enable/Disable Workflow
* [WorkflowsGetWorkflowLogs](#workflowsgetworkflowlogs) - Get Workflow Logs

## WorkflowsListWorkflows

Get a list of all Workflows

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_listWorkflows" method="get" path="/v3/workflows" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Workflows.WorkflowsListWorkflows(ctx, operations.WorkflowsListWorkflowsRequest{
        OwnerID: "<id>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.V3WorkflowsListWorkflowAPIResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                            | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                | :heavy_check_mark:                                                                                   | The context to use for the request.                                                                  |
| `request`                                                                                            | [operations.WorkflowsListWorkflowsRequest](../../models/operations/workflowslistworkflowsrequest.md) | :heavy_check_mark:                                                                                   | The request object to use for the request.                                                           |
| `opts`                                                                                               | [][operations.Option](../../models/operations/option.md)                                             | :heavy_minus_sign:                                                                                   | The options for this request.                                                                        |

### Response

**[*operations.WorkflowsListWorkflowsResponse](../../models/operations/workflowslistworkflowsresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.WorkflowsListWorkflowsBadRequestError          | 400                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsForbiddenError           | 403                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsNotFoundError            | 404                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsConflictError            | 409                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsInternalServerError      | 500                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.WorkflowsListWorkflowsGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## WorkflowsCreateWorkflow

Create a Workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_createWorkflow" method="post" path="/v3/workflows" -->
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

    res, err := s.Workflows.WorkflowsCreateWorkflow(ctx, components.V3WorkflowsCreateWorkflowRequest{
        Title: "<value>",
        OwnerID: "<id>",
        Trigger: components.V3WorkflowsWorkflowTriggerIncidentAcknowledged,
        Filters: components.V3WorkflowsCreateWorkflowFilter{},
        Actions: []components.V3WorkflowsActionRequest{
            components.CreateV3WorkflowsActionRequestV3WorkflowsSqTriggerManualWebhook(
                components.V3WorkflowsSqTriggerManualWebhook{
                    Name: components.V3WorkflowsSqTriggerManualWebhookNameSqTriggerManualWebhook,
                    Data: components.V3WorkflowsSqTriggerManualWebhookData{
                        ID: "<id>",
                    },
                },
            ),
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

| Parameter                                                                                                  | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                                      | :heavy_check_mark:                                                                                         | The context to use for the request.                                                                        |
| `request`                                                                                                  | [components.V3WorkflowsCreateWorkflowRequest](../../models/components/v3workflowscreateworkflowrequest.md) | :heavy_check_mark:                                                                                         | The request object to use for the request.                                                                 |
| `opts`                                                                                                     | [][operations.Option](../../models/operations/option.md)                                                   | :heavy_minus_sign:                                                                                         | The options for this request.                                                                              |

### Response

**[*operations.WorkflowsCreateWorkflowResponse](../../models/operations/workflowscreateworkflowresponse.md), error**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| apierrors.WorkflowsCreateWorkflowBadRequestError          | 400                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowUnauthorizedError        | 401                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowPaymentRequiredError     | 402                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowForbiddenError           | 403                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowNotFoundError            | 404                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowConflictError            | 409                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowUnprocessableEntityError | 422                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowInternalServerError      | 500                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowBadGatewayError          | 502                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowServiceUnavailableError  | 503                                                       | application/json                                          |
| apierrors.WorkflowsCreateWorkflowGatewayTimeoutError      | 504                                                       | application/json                                          |
| apierrors.APIError                                        | 4XX, 5XX                                                  | \*/\*                                                     |

## WorkflowsBulkEnabledisableWorkflows

Bulk enable or disable workflows

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_bulkEnabledisableWorkflows" method="put" path="/v3/workflows/enable" -->
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

    res, err := s.Workflows.WorkflowsBulkEnabledisableWorkflows(ctx, components.V3WorkflowsBulkEnableDisableWorkflowsRequest{
        OwnerID: "<id>",
        Enabled: false,
        WorkflowIds: []int{
            124939,
        },
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                          | Type                                                                                                                               | Required                                                                                                                           | Description                                                                                                                        |
| ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                                                              | :heavy_check_mark:                                                                                                                 | The context to use for the request.                                                                                                |
| `request`                                                                                                                          | [components.V3WorkflowsBulkEnableDisableWorkflowsRequest](../../models/components/v3workflowsbulkenabledisableworkflowsrequest.md) | :heavy_check_mark:                                                                                                                 | The request object to use for the request.                                                                                         |
| `opts`                                                                                                                             | [][operations.Option](../../models/operations/option.md)                                                                           | :heavy_minus_sign:                                                                                                                 | The options for this request.                                                                                                      |

### Response

**[*operations.WorkflowsBulkEnabledisableWorkflowsResponse](../../models/operations/workflowsbulkenabledisableworkflowsresponse.md), error**

### Errors

| Error Type                                                            | Status Code                                                           | Content Type                                                          |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| apierrors.WorkflowsBulkEnabledisableWorkflowsBadRequestError          | 400                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsUnauthorizedError        | 401                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsPaymentRequiredError     | 402                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsForbiddenError           | 403                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsNotFoundError            | 404                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsConflictError            | 409                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsUnprocessableEntityError | 422                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsInternalServerError      | 500                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsBadGatewayError          | 502                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsServiceUnavailableError  | 503                                                                   | application/json                                                      |
| apierrors.WorkflowsBulkEnabledisableWorkflowsGatewayTimeoutError      | 504                                                                   | application/json                                                      |
| apierrors.APIError                                                    | 4XX, 5XX                                                              | \*/\*                                                                 |

## WorkflowsDeleteWorkflow

Delete a workflow by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_deleteWorkflow" method="delete" path="/v3/workflows/{workflowID}" -->
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

    res, err := s.Workflows.WorkflowsDeleteWorkflow(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `workflowID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WorkflowsDeleteWorkflowResponse](../../models/operations/workflowsdeleteworkflowresponse.md), error**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| apierrors.WorkflowsDeleteWorkflowBadRequestError          | 400                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowUnauthorizedError        | 401                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowPaymentRequiredError     | 402                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowForbiddenError           | 403                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowNotFoundError            | 404                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowConflictError            | 409                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowUnprocessableEntityError | 422                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowInternalServerError      | 500                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowBadGatewayError          | 502                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowServiceUnavailableError  | 503                                                       | application/json                                          |
| apierrors.WorkflowsDeleteWorkflowGatewayTimeoutError      | 504                                                       | application/json                                          |
| apierrors.APIError                                        | 4XX, 5XX                                                  | \*/\*                                                     |

## WorkflowsGetWorkflowByID

Get a workflow by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_getWorkflowById" method="get" path="/v3/workflows/{workflowID}" -->
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

    res, err := s.Workflows.WorkflowsGetWorkflowByID(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.V3WorkflowsGetWorkflowByIDResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `workflowID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WorkflowsGetWorkflowByIDResponse](../../models/operations/workflowsgetworkflowbyidresponse.md), error**

### Errors

| Error Type                                                 | Status Code                                                | Content Type                                               |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| apierrors.WorkflowsGetWorkflowByIDBadRequestError          | 400                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDUnauthorizedError        | 401                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDPaymentRequiredError     | 402                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDForbiddenError           | 403                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDNotFoundError            | 404                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDConflictError            | 409                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDUnprocessableEntityError | 422                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDInternalServerError      | 500                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDBadGatewayError          | 502                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDServiceUnavailableError  | 503                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowByIDGatewayTimeoutError      | 504                                                        | application/json                                           |
| apierrors.APIError                                         | 4XX, 5XX                                                   | \*/\*                                                      |

## WorkflowsUpdateWorkflow

Update a Workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_updateWorkflow" method="patch" path="/v3/workflows/{workflowID}" -->
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

    res, err := s.Workflows.WorkflowsUpdateWorkflow(ctx, "<id>", components.V3WorkflowsCreateWorkflowRequestUpdate{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                  | :heavy_check_mark:                                                                                                     | The context to use for the request.                                                                                    |
| `workflowID`                                                                                                           | *string*                                                                                                               | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `v3WorkflowsCreateWorkflowRequestUpdate`                                                                               | [components.V3WorkflowsCreateWorkflowRequestUpdate](../../models/components/v3workflowscreateworkflowrequestupdate.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `opts`                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                               | :heavy_minus_sign:                                                                                                     | The options for this request.                                                                                          |

### Response

**[*operations.WorkflowsUpdateWorkflowResponse](../../models/operations/workflowsupdateworkflowresponse.md), error**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| apierrors.WorkflowsUpdateWorkflowBadRequestError          | 400                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowUnauthorizedError        | 401                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowPaymentRequiredError     | 402                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowForbiddenError           | 403                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowNotFoundError            | 404                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowConflictError            | 409                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowUnprocessableEntityError | 422                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowInternalServerError      | 500                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowBadGatewayError          | 502                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowServiceUnavailableError  | 503                                                       | application/json                                          |
| apierrors.WorkflowsUpdateWorkflowGatewayTimeoutError      | 504                                                       | application/json                                          |
| apierrors.APIError                                        | 4XX, 5XX                                                  | \*/\*                                                     |

## WorkflowsCreateAction

Create an Action for a workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_createAction" method="post" path="/v3/workflows/{workflowID}/actions" -->
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

    res, err := s.Workflows.WorkflowsCreateAction(ctx, "<id>", components.CreateV3WorkflowsActionRequestV3WorkflowsSqCreateStatusPageIssue(
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

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.WorkflowsCreateActionBadRequestError          | 400                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionForbiddenError           | 403                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionNotFoundError            | 404                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionConflictError            | 409                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionInternalServerError      | 500                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.WorkflowsCreateActionGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## WorkflowsUpdateActionsOrder

Update action order in a workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_updateActionsOrder" method="patch" path="/v3/workflows/{workflowID}/actions/reorder" -->
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

    res, err := s.Workflows.WorkflowsUpdateActionsOrder(ctx, "<id>", components.V3WorkflowsUpdateActionsOrderRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.V3WorkflowsUpdateActionsOrderResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                          | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                                              | :heavy_check_mark:                                                                                                 | The context to use for the request.                                                                                |
| `workflowID`                                                                                                       | *string*                                                                                                           | :heavy_check_mark:                                                                                                 | N/A                                                                                                                |
| `v3WorkflowsUpdateActionsOrderRequest`                                                                             | [components.V3WorkflowsUpdateActionsOrderRequest](../../models/components/v3workflowsupdateactionsorderrequest.md) | :heavy_check_mark:                                                                                                 | N/A                                                                                                                |
| `opts`                                                                                                             | [][operations.Option](../../models/operations/option.md)                                                           | :heavy_minus_sign:                                                                                                 | The options for this request.                                                                                      |

### Response

**[*operations.WorkflowsUpdateActionsOrderResponse](../../models/operations/workflowsupdateactionsorderresponse.md), error**

### Errors

| Error Type                                                    | Status Code                                                   | Content Type                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| apierrors.WorkflowsUpdateActionsOrderBadRequestError          | 400                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderUnauthorizedError        | 401                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderPaymentRequiredError     | 402                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderForbiddenError           | 403                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderNotFoundError            | 404                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderConflictError            | 409                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderUnprocessableEntityError | 422                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderInternalServerError      | 500                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderBadGatewayError          | 502                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderServiceUnavailableError  | 503                                                           | application/json                                              |
| apierrors.WorkflowsUpdateActionsOrderGatewayTimeoutError      | 504                                                           | application/json                                              |
| apierrors.APIError                                            | 4XX, 5XX                                                      | \*/\*                                                         |

## WorkflowsDeleteWorkflowAction

Delete an action by action ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_deleteWorkflowAction" method="delete" path="/v3/workflows/{workflowID}/actions/{actionID}" -->
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

    res, err := s.Workflows.WorkflowsDeleteWorkflowAction(ctx, "<id>", "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `workflowID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `actionID`                                               | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WorkflowsDeleteWorkflowActionResponse](../../models/operations/workflowsdeleteworkflowactionresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.WorkflowsDeleteWorkflowActionBadRequestError          | 400                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionForbiddenError           | 403                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionNotFoundError            | 404                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionConflictError            | 409                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionInternalServerError      | 500                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.WorkflowsDeleteWorkflowActionGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## WorkflowsGetWorkflowActionByID

Get workflow action by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_getWorkflowActionById" method="get" path="/v3/workflows/{workflowID}/actions/{actionID}" -->
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

    res, err := s.Workflows.WorkflowsGetWorkflowActionByID(ctx, "<id>", "<id>")
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
| `workflowID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `actionID`                                               | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WorkflowsGetWorkflowActionByIDResponse](../../models/operations/workflowsgetworkflowactionbyidresponse.md), error**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| apierrors.WorkflowsGetWorkflowActionByIDBadRequestError          | 400                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDUnauthorizedError        | 401                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDPaymentRequiredError     | 402                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDForbiddenError           | 403                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDNotFoundError            | 404                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDConflictError            | 409                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDUnprocessableEntityError | 422                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDInternalServerError      | 500                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDBadGatewayError          | 502                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDServiceUnavailableError  | 503                                                              | application/json                                                 |
| apierrors.WorkflowsGetWorkflowActionByIDGatewayTimeoutError      | 504                                                              | application/json                                                 |
| apierrors.APIError                                               | 4XX, 5XX                                                         | \*/\*                                                            |

## WorkflowsUpdateWorkflowAction

Update an action by action ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_updateWorkflowAction" method="patch" path="/v3/workflows/{workflowID}/actions/{actionID}" -->
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

    res, err := s.Workflows.WorkflowsUpdateWorkflowAction(ctx, "<id>", "<id>", components.CreateV3WorkflowsActionRequestUpdateAny(
        map[string]any{
            "name": "slack_message_channel",
        },
    ))
    if err != nil {
        log.Fatal(err)
    }
    if res.V3WorkflowsActionResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `workflowID`                                                                                           | *string*                                                                                               | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `actionID`                                                                                             | *string*                                                                                               | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `v3WorkflowsActionRequestUpdate`                                                                       | [components.V3WorkflowsActionRequestUpdate](../../models/components/v3workflowsactionrequestupdate.md) | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.WorkflowsUpdateWorkflowActionResponse](../../models/operations/workflowsupdateworkflowactionresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.WorkflowsUpdateWorkflowActionBadRequestError          | 400                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionForbiddenError           | 403                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionNotFoundError            | 404                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionConflictError            | 409                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionInternalServerError      | 500                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.WorkflowsUpdateWorkflowActionGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## WorkflowsEnabledisableWorkflow

Enable or disable workflow by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_enabledisableWorkflow" method="patch" path="/v3/workflows/{workflowID}/enable" -->
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

    res, err := s.Workflows.WorkflowsEnabledisableWorkflow(ctx, "<id>", components.V3WorkflowsEnableDisableWorkflowRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                | Type                                                                                                                     | Required                                                                                                                 | Description                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                    | :heavy_check_mark:                                                                                                       | The context to use for the request.                                                                                      |
| `workflowID`                                                                                                             | *string*                                                                                                                 | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `v3WorkflowsEnableDisableWorkflowRequest`                                                                                | [components.V3WorkflowsEnableDisableWorkflowRequest](../../models/components/v3workflowsenabledisableworkflowrequest.md) | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `opts`                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                 | :heavy_minus_sign:                                                                                                       | The options for this request.                                                                                            |

### Response

**[*operations.WorkflowsEnabledisableWorkflowResponse](../../models/operations/workflowsenabledisableworkflowresponse.md), error**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| apierrors.WorkflowsEnabledisableWorkflowBadRequestError          | 400                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowUnauthorizedError        | 401                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowPaymentRequiredError     | 402                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowForbiddenError           | 403                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowNotFoundError            | 404                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowConflictError            | 409                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowUnprocessableEntityError | 422                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowInternalServerError      | 500                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowBadGatewayError          | 502                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowServiceUnavailableError  | 503                                                              | application/json                                                 |
| apierrors.WorkflowsEnabledisableWorkflowGatewayTimeoutError      | 504                                                              | application/json                                                 |
| apierrors.APIError                                               | 4XX, 5XX                                                         | \*/\*                                                            |

## WorkflowsGetWorkflowLogs

Get workflow logs

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_getWorkflowLogs" method="get" path="/v3/workflows/{workflowID}/logs" -->
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

    res, err := s.Workflows.WorkflowsGetWorkflowLogs(ctx, "<id>", nil, nil)
    if err != nil {
        log.Fatal(err)
    }
    if res.V3WorkflowsGetWorkflowLogsResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `workflowID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `pageSize`                                               | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `pageNumber`                                             | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WorkflowsGetWorkflowLogsResponse](../../models/operations/workflowsgetworkflowlogsresponse.md), error**

### Errors

| Error Type                                                 | Status Code                                                | Content Type                                               |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| apierrors.WorkflowsGetWorkflowLogsBadRequestError          | 400                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsUnauthorizedError        | 401                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsPaymentRequiredError     | 402                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsForbiddenError           | 403                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsNotFoundError            | 404                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsConflictError            | 409                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsUnprocessableEntityError | 422                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsInternalServerError      | 500                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsBadGatewayError          | 502                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsServiceUnavailableError  | 503                                                        | application/json                                           |
| apierrors.WorkflowsGetWorkflowLogsGatewayTimeoutError      | 504                                                        | application/json                                           |
| apierrors.APIError                                         | 4XX, 5XX                                                   | \*/\*                                                      |