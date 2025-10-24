# RulesetsRules
(*GlobalEventRules.Rulesets.Rules*)

## Overview

### Available Operations

* [Create](#create) - Create Rule
* [GetByID](#getbyid) - Get Rule by ID

## Create

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

    res, err := s.GlobalEventRules.Rulesets.Rules.Create(ctx, 934313, "<value>", "<value>", components.V3GlobalEventRulesCreateOrUpdateRuleRequest{
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

    res, err := s.GlobalEventRules.Rulesets.Rules.GetByID(ctx, 518804, "<value>", "<value>", "<id>")
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