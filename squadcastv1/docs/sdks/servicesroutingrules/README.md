# ServicesRoutingRules
(*ServicesRoutingRules*)

## Overview

### Available Operations

* [RoutingRulesGetRoutingRules](#routingrulesgetroutingrules) - Get Routing Rules
* [RoutingRulesCreateOrUpdateRoutingRules](#routingrulescreateorupdateroutingrules) - Create or Update Routing Rules

## RoutingRulesGetRoutingRules

Get Routing Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="RoutingRules_getRoutingRules" method="get" path="/v3/services/{serviceID}/routing-rules" -->
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

    res, err := s.ServicesRoutingRules.RoutingRulesGetRoutingRules(ctx, "<id>")
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
| `serviceID`                                              | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.RoutingRulesGetRoutingRulesResponse](../../models/operations/routingrulesgetroutingrulesresponse.md), error**

### Errors

| Error Type                                                    | Status Code                                                   | Content Type                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| apierrors.RoutingRulesGetRoutingRulesBadRequestError          | 400                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesUnauthorizedError        | 401                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesPaymentRequiredError     | 402                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesForbiddenError           | 403                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesNotFoundError            | 404                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesConflictError            | 409                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesUnprocessableEntityError | 422                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesInternalServerError      | 500                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesBadGatewayError          | 502                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesServiceUnavailableError  | 503                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesGatewayTimeoutError      | 504                                                           | application/json                                              |
| apierrors.APIError                                            | 4XX, 5XX                                                      | \*/\*                                                         |

## RoutingRulesCreateOrUpdateRoutingRules

Create or Update Routing Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="RoutingRules_createOrUpdateRoutingRules" method="post" path="/v3/services/{serviceID}/routing-rules" -->
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

    res, err := s.ServicesRoutingRules.RoutingRulesCreateOrUpdateRoutingRules(ctx, "<id>", components.V3ServicesRoutingRulesCreateOrUpdateRoutingRulesRequest{
        Rules: []components.V3ServicesRoutingRulesRoutingRule{
            components.V3ServicesRoutingRulesRoutingRule{
                Expression: "<value>",
                RouteTo: components.V3ServicesRoutingRulesRoutingRuleRouteTo{
                    EntityType: components.V3ServicesRoutingRulesRoutingRuleEntityTypeEscalationPolicy,
                    EntityID: "<id>",
                },
                IsBasic: false,
            },
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

| Parameter                                                                                                                                                | Type                                                                                                                                                     | Required                                                                                                                                                 | Description                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                                                    | :heavy_check_mark:                                                                                                                                       | The context to use for the request.                                                                                                                      |
| `serviceID`                                                                                                                                              | *string*                                                                                                                                                 | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `v3ServicesRoutingRulesCreateOrUpdateRoutingRulesRequest`                                                                                                | [components.V3ServicesRoutingRulesCreateOrUpdateRoutingRulesRequest](../../models/components/v3servicesroutingrulescreateorupdateroutingrulesrequest.md) | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `opts`                                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                                 | :heavy_minus_sign:                                                                                                                                       | The options for this request.                                                                                                                            |

### Response

**[*operations.RoutingRulesCreateOrUpdateRoutingRulesResponse](../../models/operations/routingrulescreateorupdateroutingrulesresponse.md), error**

### Errors

| Error Type                                                               | Status Code                                                              | Content Type                                                             |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesBadRequestError          | 400                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesUnauthorizedError        | 401                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesPaymentRequiredError     | 402                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesForbiddenError           | 403                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesNotFoundError            | 404                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesConflictError            | 409                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesUnprocessableEntityError | 422                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesInternalServerError      | 500                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesBadGatewayError          | 502                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesServiceUnavailableError  | 503                                                                      | application/json                                                         |
| apierrors.RoutingRulesCreateOrUpdateRoutingRulesGatewayTimeoutError      | 504                                                                      | application/json                                                         |
| apierrors.APIError                                                       | 4XX, 5XX                                                                 | \*/\*                                                                    |