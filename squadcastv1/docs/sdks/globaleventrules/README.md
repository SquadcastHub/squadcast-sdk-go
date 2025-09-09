# GlobalEventRules
(*GlobalEventRules*)

## Overview

### Available Operations

* [GlobalEventRulesListGlobalEventRules](#globaleventruleslistglobaleventrules) - List Global Event Rules
* [GlobalEventRulesCreateGlobalEventRule](#globaleventrulescreateglobaleventrule) - Create Global Event Rule
* [GlobalEventRulesDeleteGlobalEventRuleByID](#globaleventrulesdeleteglobaleventrulebyid) - Delete Global Event Rule by ID
* [GlobalEventRulesGetGlobalEventRuleByID](#globaleventrulesgetglobaleventrulebyid) - Get Global Event Rule by ID
* [GlobalEventRulesUpdateGlobalEventRuleByID](#globaleventrulesupdateglobaleventrulebyid) - Update Global Event Rule by ID

## GlobalEventRulesListGlobalEventRules

Get a list of all GERs

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_listGlobalEventRules" method="get" path="/v3/global-event-rules" -->
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

    res, err := s.GlobalEventRules.GlobalEventRulesListGlobalEventRules(ctx, operations.GlobalEventRulesListGlobalEventRulesRequest{
        OwnerID: "<id>",
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

| Parameter                                                                                                                        | Type                                                                                                                             | Required                                                                                                                         | Description                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                                                            | :heavy_check_mark:                                                                                                               | The context to use for the request.                                                                                              |
| `request`                                                                                                                        | [operations.GlobalEventRulesListGlobalEventRulesRequest](../../models/operations/globaleventruleslistglobaleventrulesrequest.md) | :heavy_check_mark:                                                                                                               | The request object to use for the request.                                                                                       |
| `opts`                                                                                                                           | [][operations.Option](../../models/operations/option.md)                                                                         | :heavy_minus_sign:                                                                                                               | The options for this request.                                                                                                    |

### Response

**[*operations.GlobalEventRulesListGlobalEventRulesResponse](../../models/operations/globaleventruleslistglobaleventrulesresponse.md), error**

### Errors

| Error Type                                                             | Status Code                                                            | Content Type                                                           |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| apierrors.GlobalEventRulesListGlobalEventRulesBadRequestError          | 400                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesUnauthorizedError        | 401                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesPaymentRequiredError     | 402                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesForbiddenError           | 403                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesNotFoundError            | 404                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesConflictError            | 409                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesUnprocessableEntityError | 422                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesInternalServerError      | 500                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesBadGatewayError          | 502                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesServiceUnavailableError  | 503                                                                    | application/json                                                       |
| apierrors.GlobalEventRulesListGlobalEventRulesGatewayTimeoutError      | 504                                                                    | application/json                                                       |
| apierrors.APIError                                                     | 4XX, 5XX                                                               | \*/\*                                                                  |

## GlobalEventRulesCreateGlobalEventRule

Create a GER

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_createGlobalEventRule" method="post" path="/v3/global-event-rules" -->
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

    res, err := s.GlobalEventRules.GlobalEventRulesCreateGlobalEventRule(ctx, components.V3GlobalEventRulesCreateGlobalEventRuleRequest{
        Name: "<value>",
        Description: "majestically effector headline dampen eek middle like shrill",
        OwnerID: "<id>",
        EntityOwner: components.V3GlobalEventRulesEntityOwner{
            ID: "<id>",
            Type: components.V3GlobalEventRulesEntityOwnerTypeUser,
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

| Parameter                                                                                                                              | Type                                                                                                                                   | Required                                                                                                                               | Description                                                                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                                  | :heavy_check_mark:                                                                                                                     | The context to use for the request.                                                                                                    |
| `request`                                                                                                                              | [components.V3GlobalEventRulesCreateGlobalEventRuleRequest](../../models/components/v3globaleventrulescreateglobaleventrulerequest.md) | :heavy_check_mark:                                                                                                                     | The request object to use for the request.                                                                                             |
| `opts`                                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                                               | :heavy_minus_sign:                                                                                                                     | The options for this request.                                                                                                          |

### Response

**[*operations.GlobalEventRulesCreateGlobalEventRuleResponse](../../models/operations/globaleventrulescreateglobaleventruleresponse.md), error**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| apierrors.GlobalEventRulesCreateGlobalEventRuleBadRequestError          | 400                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleUnauthorizedError        | 401                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRulePaymentRequiredError     | 402                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleForbiddenError           | 403                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleNotFoundError            | 404                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleConflictError            | 409                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleUnprocessableEntityError | 422                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleInternalServerError      | 500                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleBadGatewayError          | 502                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleServiceUnavailableError  | 503                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesCreateGlobalEventRuleGatewayTimeoutError      | 504                                                                     | application/json                                                        |
| apierrors.APIError                                                      | 4XX, 5XX                                                                | \*/\*                                                                   |

## GlobalEventRulesDeleteGlobalEventRuleByID

Delete a GER by its ID

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_deleteGlobalEventRuleById" method="delete" path="/v3/global-event-rules/{ger_id}" -->
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

    res, err := s.GlobalEventRules.GlobalEventRulesDeleteGlobalEventRuleByID(ctx, 491102)
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
| `gerID`                                                  | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalEventRulesDeleteGlobalEventRuleByIDResponse](../../models/operations/globaleventrulesdeleteglobaleventrulebyidresponse.md), error**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDBadRequestError          | 400                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDUnauthorizedError        | 401                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDPaymentRequiredError     | 402                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDForbiddenError           | 403                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDNotFoundError            | 404                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDConflictError            | 409                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDUnprocessableEntityError | 422                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDInternalServerError      | 500                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDBadGatewayError          | 502                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDServiceUnavailableError  | 503                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesDeleteGlobalEventRuleByIDGatewayTimeoutError      | 504                                                                         | application/json                                                            |
| apierrors.APIError                                                          | 4XX, 5XX                                                                    | \*/\*                                                                       |

## GlobalEventRulesGetGlobalEventRuleByID

Get a GER by its ID

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_getGlobalEventRuleById" method="get" path="/v3/global-event-rules/{ger_id}" -->
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

    res, err := s.GlobalEventRules.GlobalEventRulesGetGlobalEventRuleByID(ctx, 292040)
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
| `gerID`                                                  | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalEventRulesGetGlobalEventRuleByIDResponse](../../models/operations/globaleventrulesgetglobaleventrulebyidresponse.md), error**

### Errors

| Error Type                                                               | Status Code                                                              | Content Type                                                             |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDBadRequestError          | 400                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDUnauthorizedError        | 401                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDPaymentRequiredError     | 402                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDForbiddenError           | 403                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDNotFoundError            | 404                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDConflictError            | 409                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDUnprocessableEntityError | 422                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDInternalServerError      | 500                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDBadGatewayError          | 502                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDServiceUnavailableError  | 503                                                                      | application/json                                                         |
| apierrors.GlobalEventRulesGetGlobalEventRuleByIDGatewayTimeoutError      | 504                                                                      | application/json                                                         |
| apierrors.APIError                                                       | 4XX, 5XX                                                                 | \*/\*                                                                    |

## GlobalEventRulesUpdateGlobalEventRuleByID

Update a GER by its ID

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_updateGlobalEventRuleById" method="patch" path="/v3/global-event-rules/{ger_id}" -->
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

    res, err := s.GlobalEventRules.GlobalEventRulesUpdateGlobalEventRuleByID(ctx, 885894, components.V3GlobalEventRulesUpdateGlobalEventRuleRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                              | Type                                                                                                                                   | Required                                                                                                                               | Description                                                                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                                  | :heavy_check_mark:                                                                                                                     | The context to use for the request.                                                                                                    |
| `gerID`                                                                                                                                | *int64*                                                                                                                                | :heavy_check_mark:                                                                                                                     | N/A                                                                                                                                    |
| `v3GlobalEventRulesUpdateGlobalEventRuleRequest`                                                                                       | [components.V3GlobalEventRulesUpdateGlobalEventRuleRequest](../../models/components/v3globaleventrulesupdateglobaleventrulerequest.md) | :heavy_check_mark:                                                                                                                     | N/A                                                                                                                                    |
| `opts`                                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                                               | :heavy_minus_sign:                                                                                                                     | The options for this request.                                                                                                          |

### Response

**[*operations.GlobalEventRulesUpdateGlobalEventRuleByIDResponse](../../models/operations/globaleventrulesupdateglobaleventrulebyidresponse.md), error**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDBadRequestError          | 400                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDUnauthorizedError        | 401                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDPaymentRequiredError     | 402                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDForbiddenError           | 403                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDNotFoundError            | 404                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDConflictError            | 409                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDUnprocessableEntityError | 422                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDInternalServerError      | 500                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDBadGatewayError          | 502                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDServiceUnavailableError  | 503                                                                         | application/json                                                            |
| apierrors.GlobalEventRulesUpdateGlobalEventRuleByIDGatewayTimeoutError      | 504                                                                         | application/json                                                            |
| apierrors.APIError                                                          | 4XX, 5XX                                                                    | \*/\*                                                                       |