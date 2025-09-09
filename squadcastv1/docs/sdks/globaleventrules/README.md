# GlobalEventRules
(*GlobalEventRules*)

## Overview

### Available Operations

* [List](#list) - List Global Event Rules
* [Create](#create) - Create Global Event Rule
* [DeleteRule](#deleterule) - Delete Global Event Rule by ID
* [GetByID](#getbyid) - Get Global Event Rule by ID
* [UpdateByID](#updatebyid) - Update Global Event Rule by ID
* [GetRuleset](#getruleset) - Get Ruleset
* [UpdateRuleset](#updateruleset) - Update Ruleset
* [UpdateRule](#updaterule) - Update Rule by ID

## List

Get a list of all GERs

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_listGlobalEventRules" method="get" path="/v3/global-event-rules" -->
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

    res, err := s.GlobalEventRules.List(ctx, operations.GlobalEventRulesListGlobalEventRulesRequest{
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

## Create

Create a GER

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_createGlobalEventRule" method="post" path="/v3/global-event-rules" -->
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

    res, err := s.GlobalEventRules.Create(ctx, components.V3GlobalEventRulesCreateGlobalEventRuleRequest{
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

## DeleteRule

Delete a GER by its ID

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_deleteGlobalEventRuleById" method="delete" path="/v3/global-event-rules/{ger_id}" -->
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

    res, err := s.GlobalEventRules.DeleteRule(ctx, 491102)
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

## GetByID

Get a GER by its ID

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_getGlobalEventRuleById" method="get" path="/v3/global-event-rules/{ger_id}" -->
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

    res, err := s.GlobalEventRules.GetByID(ctx, 292040)
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

## UpdateByID

Update a GER by its ID

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_updateGlobalEventRuleById" method="patch" path="/v3/global-event-rules/{ger_id}" -->
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

    res, err := s.GlobalEventRules.UpdateByID(ctx, 885894, components.V3GlobalEventRulesUpdateGlobalEventRuleRequest{})
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

## GetRuleset

Get a GER Ruleset

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_getRuleset" method="get" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}" -->
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

    res, err := s.GlobalEventRules.GetRuleset(ctx, 294223, "<value>", "<value>")
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
| `alertSourceVersion`                                     | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `alertSourceShortname`                                   | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalEventRulesGetRulesetResponse](../../models/operations/globaleventrulesgetrulesetresponse.md), error**

### Errors

| Error Type                                                   | Status Code                                                  | Content Type                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| apierrors.GlobalEventRulesGetRulesetBadRequestError          | 400                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetUnauthorizedError        | 401                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetPaymentRequiredError     | 402                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetForbiddenError           | 403                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetNotFoundError            | 404                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetConflictError            | 409                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetUnprocessableEntityError | 422                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetInternalServerError      | 500                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetBadGatewayError          | 502                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetServiceUnavailableError  | 503                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetGatewayTimeoutError      | 504                                                          | application/json                                             |
| apierrors.APIError                                           | 4XX, 5XX                                                     | \*/\*                                                        |

## UpdateRuleset

Update a GER Ruleset

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_updateRuleset" method="patch" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}" -->
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

    res, err := s.GlobalEventRules.UpdateRuleset(ctx, 489958, "<value>", "<value>", components.V3GlobalEventRulesUpdateRulesetRequest{})
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
| `gerID`                                                                                                                | *int64*                                                                                                                | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `alertSourceVersion`                                                                                                   | *string*                                                                                                               | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `alertSourceShortname`                                                                                                 | *string*                                                                                                               | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `v3GlobalEventRulesUpdateRulesetRequest`                                                                               | [components.V3GlobalEventRulesUpdateRulesetRequest](../../models/components/v3globaleventrulesupdaterulesetrequest.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `opts`                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                               | :heavy_minus_sign:                                                                                                     | The options for this request.                                                                                          |

### Response

**[*operations.GlobalEventRulesUpdateRulesetResponse](../../models/operations/globaleventrulesupdaterulesetresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.GlobalEventRulesUpdateRulesetBadRequestError          | 400                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetForbiddenError           | 403                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetNotFoundError            | 404                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetConflictError            | 409                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetInternalServerError      | 500                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## UpdateRule

Update a GER Ruleset Rule by its ID.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_updateRuleById" method="patch" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules/{rule_id}" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/components"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.GlobalEventRules.UpdateRule(ctx, operations.GlobalEventRulesUpdateRuleByIDRequest{
        GerID: 140241,
        AlertSourceVersion: "<value>",
        AlertSourceShortname: "<value>",
        RuleID: "<id>",
        V3GlobalEventRulesUpdateRuleRequest: components.V3GlobalEventRulesUpdateRuleRequest{},
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

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                | :heavy_check_mark:                                                                                                   | The context to use for the request.                                                                                  |
| `request`                                                                                                            | [operations.GlobalEventRulesUpdateRuleByIDRequest](../../models/operations/globaleventrulesupdaterulebyidrequest.md) | :heavy_check_mark:                                                                                                   | The request object to use for the request.                                                                           |
| `opts`                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                             | :heavy_minus_sign:                                                                                                   | The options for this request.                                                                                        |

### Response

**[*operations.GlobalEventRulesUpdateRuleByIDResponse](../../models/operations/globaleventrulesupdaterulebyidresponse.md), error**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| apierrors.GlobalEventRulesUpdateRuleByIDBadRequestError          | 400                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDUnauthorizedError        | 401                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDPaymentRequiredError     | 402                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDForbiddenError           | 403                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDNotFoundError            | 404                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDConflictError            | 409                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDUnprocessableEntityError | 422                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDInternalServerError      | 500                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDBadGatewayError          | 502                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDServiceUnavailableError  | 503                                                              | application/json                                                 |
| apierrors.GlobalEventRulesUpdateRuleByIDGatewayTimeoutError      | 504                                                              | application/json                                                 |
| apierrors.APIError                                               | 4XX, 5XX                                                         | \*/\*                                                            |