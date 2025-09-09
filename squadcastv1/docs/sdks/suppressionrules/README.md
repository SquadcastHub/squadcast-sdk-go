# SuppressionRules
(*Services.SuppressionRules*)

## Overview

### Available Operations

* [Get](#get) - Get Suppression Rules

## Get

Get Suppression Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="SuppressionRules_getSuppressionRules" method="get" path="/v3/services/{serviceID}/suppression-rules" -->
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

    res, err := s.Services.SuppressionRules.Get(ctx, "<id>")
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