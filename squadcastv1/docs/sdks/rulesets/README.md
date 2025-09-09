# Rulesets
(*GlobalEventRules.Rulesets*)

## Overview

### Available Operations

* [Create](#create) - Create Ruleset
* [Reorder](#reorder) - Reorder Ruleset
* [ListRulesetRules](#listrulesetrules) - List Ruleset Rules

## Create

Create a GER Ruleset.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_createRuleset" method="post" path="/v3/global-event-rules/{ger_id}/rulesets" -->
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

    res, err := s.GlobalEventRules.Rulesets.Create(ctx, 216762, components.V3GlobalEventRulesCreateRulesetRequest{
        AlertSourceShortname: "<value>",
        AlertSourceVersion: "<value>",
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

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                  | :heavy_check_mark:                                                                                                     | The context to use for the request.                                                                                    |
| `gerID`                                                                                                                | *int64*                                                                                                                | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `v3GlobalEventRulesCreateRulesetRequest`                                                                               | [components.V3GlobalEventRulesCreateRulesetRequest](../../models/components/v3globaleventrulescreaterulesetrequest.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `opts`                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                               | :heavy_minus_sign:                                                                                                     | The options for this request.                                                                                          |

### Response

**[*operations.GlobalEventRulesCreateRulesetResponse](../../models/operations/globaleventrulescreaterulesetresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.GlobalEventRulesCreateRulesetBadRequestError          | 400                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetForbiddenError           | 403                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetNotFoundError            | 404                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetConflictError            | 409                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetInternalServerError      | 500                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## Reorder

Reorder rules of a GER Ruleset

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_reorderRuleset" method="patch" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/priority" -->
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

    res, err := s.GlobalEventRules.Rulesets.Reorder(ctx, 572014, "<value>", "<value>", components.V3GlobalEventRulesReorderRulesetRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                | Type                                                                                                                     | Required                                                                                                                 | Description                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                    | :heavy_check_mark:                                                                                                       | The context to use for the request.                                                                                      |
| `gerID`                                                                                                                  | *int64*                                                                                                                  | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `alertSourceVersion`                                                                                                     | *string*                                                                                                                 | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `alertSourceShortname`                                                                                                   | *string*                                                                                                                 | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `v3GlobalEventRulesReorderRulesetRequest`                                                                                | [components.V3GlobalEventRulesReorderRulesetRequest](../../models/components/v3globaleventrulesreorderrulesetrequest.md) | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `opts`                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                 | :heavy_minus_sign:                                                                                                       | The options for this request.                                                                                            |

### Response

**[*operations.GlobalEventRulesReorderRulesetResponse](../../models/operations/globaleventrulesreorderrulesetresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| apierrors.APIError | 4XX, 5XX           | \*/\*              |

## ListRulesetRules

Get all rules of a GER Ruleset.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_listRulesetRules" method="get" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules" -->
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

    res, err := s.GlobalEventRules.Rulesets.ListRulesetRules(ctx, operations.GlobalEventRulesListRulesetRulesRequest{
        GerID: 894010,
        AlertSourceVersion: "<value>",
        AlertSourceShortname: "<value>",
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

| Parameter                                                                                                                | Type                                                                                                                     | Required                                                                                                                 | Description                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                    | :heavy_check_mark:                                                                                                       | The context to use for the request.                                                                                      |
| `request`                                                                                                                | [operations.GlobalEventRulesListRulesetRulesRequest](../../models/operations/globaleventruleslistrulesetrulesrequest.md) | :heavy_check_mark:                                                                                                       | The request object to use for the request.                                                                               |
| `opts`                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                 | :heavy_minus_sign:                                                                                                       | The options for this request.                                                                                            |

### Response

**[*operations.GlobalEventRulesListRulesetRulesResponse](../../models/operations/globaleventruleslistrulesetrulesresponse.md), error**

### Errors

| Error Type                                                         | Status Code                                                        | Content Type                                                       |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| apierrors.GlobalEventRulesListRulesetRulesBadRequestError          | 400                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesUnauthorizedError        | 401                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesPaymentRequiredError     | 402                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesForbiddenError           | 403                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesNotFoundError            | 404                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesConflictError            | 409                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesUnprocessableEntityError | 422                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesInternalServerError      | 500                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesBadGatewayError          | 502                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesServiceUnavailableError  | 503                                                                | application/json                                                   |
| apierrors.GlobalEventRulesListRulesetRulesGatewayTimeoutError      | 504                                                                | application/json                                                   |
| apierrors.APIError                                                 | 4XX, 5XX                                                           | \*/\*                                                              |