# ServicesSuppressionRules
(*ServicesSuppressionRules*)

## Overview

### Available Operations

* [SuppressionRulesGetSuppressionRules](#suppressionrulesgetsuppressionrules) - Get Suppression Rules
* [SuppressionRulesCreateOrUpdateSuppressionRules](#suppressionrulescreateorupdatesuppressionrules) - Create or Update Suppression Rules

## SuppressionRulesGetSuppressionRules

Get Suppression Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="SuppressionRules_getSuppressionRules" method="get" path="/v3/services/{serviceID}/suppression-rules" -->
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

    res, err := s.ServicesSuppressionRules.SuppressionRulesGetSuppressionRules(ctx, "<id>")
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

**[*operations.SuppressionRulesGetSuppressionRulesResponse](../../models/operations/suppressionrulesgetsuppressionrulesresponse.md), error**

### Errors

| Error Type                                                            | Status Code                                                           | Content Type                                                          |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| apierrors.SuppressionRulesGetSuppressionRulesBadRequestError          | 400                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesUnauthorizedError        | 401                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesPaymentRequiredError     | 402                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesForbiddenError           | 403                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesNotFoundError            | 404                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesConflictError            | 409                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesUnprocessableEntityError | 422                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesInternalServerError      | 500                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesBadGatewayError          | 502                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesServiceUnavailableError  | 503                                                                   | application/json                                                      |
| apierrors.SuppressionRulesGetSuppressionRulesGatewayTimeoutError      | 504                                                                   | application/json                                                      |
| apierrors.APIError                                                    | 4XX, 5XX                                                              | \*/\*                                                                 |

## SuppressionRulesCreateOrUpdateSuppressionRules

Create or Update Suppression Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="SuppressionRules_createOrUpdateSuppressionRules" method="post" path="/v3/services/{serviceID}/suppression-rules" -->
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

    res, err := s.ServicesSuppressionRules.SuppressionRulesCreateOrUpdateSuppressionRules(ctx, "<id>", components.V3ServicesSuppressionRulesCreateOrUpdateSuppressionRulesRequest{
        Rules: []components.V3ServicesSuppressionRulesSuppressionRule{},
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

| Parameter                                                                                                                                                                | Type                                                                                                                                                                     | Required                                                                                                                                                                 | Description                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                                                                    | :heavy_check_mark:                                                                                                                                                       | The context to use for the request.                                                                                                                                      |
| `serviceID`                                                                                                                                                              | *string*                                                                                                                                                                 | :heavy_check_mark:                                                                                                                                                       | N/A                                                                                                                                                                      |
| `v3ServicesSuppressionRulesCreateOrUpdateSuppressionRulesRequest`                                                                                                        | [components.V3ServicesSuppressionRulesCreateOrUpdateSuppressionRulesRequest](../../models/components/v3servicessuppressionrulescreateorupdatesuppressionrulesrequest.md) | :heavy_check_mark:                                                                                                                                                       | N/A                                                                                                                                                                      |
| `opts`                                                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                                                 | :heavy_minus_sign:                                                                                                                                                       | The options for this request.                                                                                                                                            |

### Response

**[*operations.SuppressionRulesCreateOrUpdateSuppressionRulesResponse](../../models/operations/suppressionrulescreateorupdatesuppressionrulesresponse.md), error**

### Errors

| Error Type                                                                       | Status Code                                                                      | Content Type                                                                     |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesBadRequestError          | 400                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesUnauthorizedError        | 401                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesPaymentRequiredError     | 402                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesForbiddenError           | 403                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesNotFoundError            | 404                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesConflictError            | 409                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesUnprocessableEntityError | 422                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesInternalServerError      | 500                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesBadGatewayError          | 502                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesServiceUnavailableError  | 503                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesGatewayTimeoutError      | 504                                                                              | application/json                                                                 |
| apierrors.APIError                                                               | 4XX, 5XX                                                                         | \*/\*                                                                            |