# GlobalEventRulesRulesetsRules
(*GlobalEventRulesRulesetsRules*)

## Overview

### Available Operations

* [GlobalEventRulesListRulesetRules](#globaleventruleslistrulesetrules) - List Ruleset Rules
* [GlobalEventRulesCreateRule](#globaleventrulescreaterule) - Create Rule
* [GlobalEventRulesGetRuleByID](#globaleventrulesgetrulebyid) - Get Rule by ID
* [GlobalEventRulesDeleteRuleByID](#globaleventrulesdeleterulebyid) - Delete Rule by ID
* [GlobalEventRulesUpdateRuleByID](#globaleventrulesupdaterulebyid) - Update Rule by ID
* [GlobalEventRulesReorderRulesetByIndex](#globaleventrulesreorderrulesetbyindex) - Reorder Ruleset By Index

## GlobalEventRulesListRulesetRules

Get all rules of a GER Ruleset.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_listRulesetRules" method="get" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules" -->
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

    res, err := s.GlobalEventRulesRulesetsRules.GlobalEventRulesListRulesetRules(ctx, operations.GlobalEventRulesListRulesetRulesRequest{
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

## GlobalEventRulesCreateRule

Create a GER Ruleset Rule.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_createRule" method="post" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules" -->
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

    res, err := s.GlobalEventRulesRulesetsRules.GlobalEventRulesCreateRule(ctx, 934313, "<value>", "<value>", components.V3GlobalEventRulesCreateOrUpdateRuleRequest{
        Description: "ha newsprint within beside scientific",
        Expression: "<value>",
        Action: components.V3GlobalEventRulesRuleAction{
            RouteTo: "<value>",
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

| Parameter                                                                                                                        | Type                                                                                                                             | Required                                                                                                                         | Description                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                                                            | :heavy_check_mark:                                                                                                               | The context to use for the request.                                                                                              |
| `gerID`                                                                                                                          | *int64*                                                                                                                          | :heavy_check_mark:                                                                                                               | N/A                                                                                                                              |
| `alertSourceVersion`                                                                                                             | *string*                                                                                                                         | :heavy_check_mark:                                                                                                               | N/A                                                                                                                              |
| `alertSourceShortname`                                                                                                           | *string*                                                                                                                         | :heavy_check_mark:                                                                                                               | N/A                                                                                                                              |
| `v3GlobalEventRulesCreateOrUpdateRuleRequest`                                                                                    | [components.V3GlobalEventRulesCreateOrUpdateRuleRequest](../../models/components/v3globaleventrulescreateorupdaterulerequest.md) | :heavy_check_mark:                                                                                                               | N/A                                                                                                                              |
| `opts`                                                                                                                           | [][operations.Option](../../models/operations/option.md)                                                                         | :heavy_minus_sign:                                                                                                               | The options for this request.                                                                                                    |

### Response

**[*operations.GlobalEventRulesCreateRuleResponse](../../models/operations/globaleventrulescreateruleresponse.md), error**

### Errors

| Error Type                                                   | Status Code                                                  | Content Type                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| apierrors.GlobalEventRulesCreateRuleBadRequestError          | 400                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleUnauthorizedError        | 401                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRulePaymentRequiredError     | 402                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleForbiddenError           | 403                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleNotFoundError            | 404                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleConflictError            | 409                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleUnprocessableEntityError | 422                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleInternalServerError      | 500                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleBadGatewayError          | 502                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleServiceUnavailableError  | 503                                                          | application/json                                             |
| apierrors.GlobalEventRulesCreateRuleGatewayTimeoutError      | 504                                                          | application/json                                             |
| apierrors.APIError                                           | 4XX, 5XX                                                     | \*/\*                                                        |

## GlobalEventRulesGetRuleByID

Get a GER Ruleset Rule by its ID.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_getRuleById" method="get" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules/{rule_id}" -->
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

    res, err := s.GlobalEventRulesRulesetsRules.GlobalEventRulesGetRuleByID(ctx, 518804, "<value>", "<value>", "<id>")
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
| `ruleID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalEventRulesGetRuleByIDResponse](../../models/operations/globaleventrulesgetrulebyidresponse.md), error**

### Errors

| Error Type                                                    | Status Code                                                   | Content Type                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| apierrors.GlobalEventRulesGetRuleByIDBadRequestError          | 400                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDUnauthorizedError        | 401                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDPaymentRequiredError     | 402                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDForbiddenError           | 403                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDNotFoundError            | 404                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDConflictError            | 409                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDUnprocessableEntityError | 422                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDInternalServerError      | 500                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDBadGatewayError          | 502                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDServiceUnavailableError  | 503                                                           | application/json                                              |
| apierrors.GlobalEventRulesGetRuleByIDGatewayTimeoutError      | 504                                                           | application/json                                              |
| apierrors.APIError                                            | 4XX, 5XX                                                      | \*/\*                                                         |

## GlobalEventRulesDeleteRuleByID

Delete a GER Ruleset Rule by its ID.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_deleteRuleById" method="delete" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules/{rule_id}" -->
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

    res, err := s.GlobalEventRulesRulesetsRules.GlobalEventRulesDeleteRuleByID(ctx, 921538, "<value>", "<value>", "<id>")
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
| `alertSourceVersion`                                     | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `alertSourceShortname`                                   | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `ruleID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalEventRulesDeleteRuleByIDResponse](../../models/operations/globaleventrulesdeleterulebyidresponse.md), error**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| apierrors.GlobalEventRulesDeleteRuleByIDBadRequestError          | 400                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDUnauthorizedError        | 401                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDPaymentRequiredError     | 402                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDForbiddenError           | 403                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDNotFoundError            | 404                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDConflictError            | 409                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDUnprocessableEntityError | 422                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDInternalServerError      | 500                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDBadGatewayError          | 502                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDServiceUnavailableError  | 503                                                              | application/json                                                 |
| apierrors.GlobalEventRulesDeleteRuleByIDGatewayTimeoutError      | 504                                                              | application/json                                                 |
| apierrors.APIError                                               | 4XX, 5XX                                                         | \*/\*                                                            |

## GlobalEventRulesUpdateRuleByID

Update a GER Ruleset Rule by its ID.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_updateRuleById" method="patch" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules/{rule_id}" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"github.com/SquadcastHub/squadcast-sdk-go/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.GlobalEventRulesRulesetsRules.GlobalEventRulesUpdateRuleByID(ctx, operations.GlobalEventRulesUpdateRuleByIDRequest{
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

## GlobalEventRulesReorderRulesetByIndex

Reorder a GER Ruleset Rule by its index in the ruleset.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_reorderRulesetByIndex" method="patch" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules/{rule_id}/priority" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"github.com/SquadcastHub/squadcast-sdk-go/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.GlobalEventRulesRulesetsRules.GlobalEventRulesReorderRulesetByIndex(ctx, operations.GlobalEventRulesReorderRulesetByIndexRequest{
        GerID: 281260,
        AlertSourceVersion: "<value>",
        AlertSourceShortname: "<value>",
        RuleID: "<id>",
        V3GlobalEventRulesReorderRuleRequest: components.V3GlobalEventRulesReorderRuleRequest{},
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

| Parameter                                                                                                                          | Type                                                                                                                               | Required                                                                                                                           | Description                                                                                                                        |
| ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                                                              | :heavy_check_mark:                                                                                                                 | The context to use for the request.                                                                                                |
| `request`                                                                                                                          | [operations.GlobalEventRulesReorderRulesetByIndexRequest](../../models/operations/globaleventrulesreorderrulesetbyindexrequest.md) | :heavy_check_mark:                                                                                                                 | The request object to use for the request.                                                                                         |
| `opts`                                                                                                                             | [][operations.Option](../../models/operations/option.md)                                                                           | :heavy_minus_sign:                                                                                                                 | The options for this request.                                                                                                      |

### Response

**[*operations.GlobalEventRulesReorderRulesetByIndexResponse](../../models/operations/globaleventrulesreorderrulesetbyindexresponse.md), error**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| apierrors.GlobalEventRulesReorderRulesetByIndexBadRequestError          | 400                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexUnauthorizedError        | 401                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexPaymentRequiredError     | 402                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexForbiddenError           | 403                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexNotFoundError            | 404                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexConflictError            | 409                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexUnprocessableEntityError | 422                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexInternalServerError      | 500                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexBadGatewayError          | 502                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexServiceUnavailableError  | 503                                                                     | application/json                                                        |
| apierrors.GlobalEventRulesReorderRulesetByIndexGatewayTimeoutError      | 504                                                                     | application/json                                                        |
| apierrors.APIError                                                      | 4XX, 5XX                                                                | \*/\*                                                                   |