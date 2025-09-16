# Workflows
(*Workflows*)

## Overview

### Available Operations

* [List](#list) - List Workflows
* [Create](#create) - Create Workflow
* [BulkEnableDisable](#bulkenabledisable) - Bulk Enable/Disable Workflows
* [Delete](#delete) - Delete Workflow
* [GetByID](#getbyid) - Get Workflow By ID
* [Update](#update) - Update Workflow
* [UpdateActionsOrder](#updateactionsorder) - Update Actions Order
* [DeleteAction](#deleteaction) - Delete Workflow Action
* [GetAction](#getaction) - Get Workflow Action By ID
* [UpdateAction](#updateaction) - Update Workflow Action
* [ToggleEnable](#toggleenable) - Enable/Disable Workflow
* [GetLogs](#getlogs) - Get Workflow Logs

## List

Get a list of all Workflows

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_listWorkflows" method="get" path="/v3/workflows" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Workflows.List(ctx, operations.WorkflowsListWorkflowsRequest{
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

## Create

Create a Workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_createWorkflow" method="post" path="/v3/workflows" -->
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

    res, err := s.Workflows.Create(ctx, components.V3WorkflowsCreateWorkflowRequest{
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

## BulkEnableDisable

Bulk enable or disable workflows

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_bulkEnabledisableWorkflows" method="put" path="/v3/workflows/enable" -->
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

    res, err := s.Workflows.BulkEnableDisable(ctx, components.V3WorkflowsBulkEnableDisableWorkflowsRequest{
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

## Delete

Delete a workflow by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_deleteWorkflow" method="delete" path="/v3/workflows/{workflowID}" -->
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

    res, err := s.Workflows.Delete(ctx, "<id>")
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

## GetByID

Get a workflow by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_getWorkflowById" method="get" path="/v3/workflows/{workflowID}" -->
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

    res, err := s.Workflows.GetByID(ctx, "<id>")
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

## Update

Update a Workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_updateWorkflow" method="patch" path="/v3/workflows/{workflowID}" -->
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

    res, err := s.Workflows.Update(ctx, "<id>", components.V3WorkflowsCreateWorkflowRequestUpdate{})
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

## UpdateActionsOrder

Update action order in a workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_updateActionsOrder" method="patch" path="/v3/workflows/{workflowID}/actions/reorder" -->
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

    res, err := s.Workflows.UpdateActionsOrder(ctx, "<id>", components.V3WorkflowsUpdateActionsOrderRequest{})
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

## DeleteAction

Delete an action by action ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_deleteWorkflowAction" method="delete" path="/v3/workflows/{workflowID}/actions/{actionID}" -->
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

    res, err := s.Workflows.DeleteAction(ctx, "<id>", "<id>")
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

## GetAction

Get workflow action by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_getWorkflowActionById" method="get" path="/v3/workflows/{workflowID}/actions/{actionID}" -->
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

    res, err := s.Workflows.GetAction(ctx, "<id>", "<id>")
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

## UpdateAction

Update an action by action ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_updateWorkflowAction" method="patch" path="/v3/workflows/{workflowID}/actions/{actionID}" -->
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

    res, err := s.Workflows.UpdateAction(ctx, "<id>", "<id>", components.CreateV3WorkflowsActionRequestUpdateAny(
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

## ToggleEnable

Enable or disable workflow by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_enabledisableWorkflow" method="patch" path="/v3/workflows/{workflowID}/enable" -->
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

    res, err := s.Workflows.ToggleEnable(ctx, "<id>", components.V3WorkflowsEnableDisableWorkflowRequest{})
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

## GetLogs

Get workflow logs

### Example Usage

<!-- UsageSnippet language="go" operationID="Workflows_getWorkflowLogs" method="get" path="/v3/workflows/{workflowID}/logs" -->
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

    res, err := s.Workflows.GetLogs(ctx, "<id>", nil, nil)
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