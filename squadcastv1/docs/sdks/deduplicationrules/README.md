# DeduplicationRules
(*Services.DeduplicationRules*)

## Overview

### Available Operations

* [Get](#get) - Get Deduplication Rules
* [CreateOrUpdate](#createorupdate) - Create or Update Deduplication Rules

## Get

Get Deduplication Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="DeduplicationRules_getDeduplicationRules" method="get" path="/v3/services/{serviceID}/deduplication-rules" -->
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

    res, err := s.Services.DeduplicationRules.Get(ctx, "<id>")
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

**[*operations.DeduplicationRulesGetDeduplicationRulesResponse](../../models/operations/deduplicationrulesgetdeduplicationrulesresponse.md), error**

### Errors

| Error Type                                                                | Status Code                                                               | Content Type                                                              |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| apierrors.DeduplicationRulesGetDeduplicationRulesBadRequestError          | 400                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesUnauthorizedError        | 401                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesPaymentRequiredError     | 402                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesForbiddenError           | 403                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesNotFoundError            | 404                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesConflictError            | 409                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesUnprocessableEntityError | 422                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesInternalServerError      | 500                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesBadGatewayError          | 502                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesServiceUnavailableError  | 503                                                                       | application/json                                                          |
| apierrors.DeduplicationRulesGetDeduplicationRulesGatewayTimeoutError      | 504                                                                       | application/json                                                          |
| apierrors.APIError                                                        | 4XX, 5XX                                                                  | \*/\*                                                                     |

## CreateOrUpdate

Create or Update Deduplication Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="DeduplicationRules_createOrUpdateDeduplicationRules" method="post" path="/v3/services/{serviceID}/deduplication-rules" -->
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

    res, err := s.Services.DeduplicationRules.CreateOrUpdate(ctx, "<id>", components.V3ServicesDeduplicationRulesCreateDeduplicationRulesRequest{
        Rules: []components.V3ServicesDeduplicationRulesDeduplicationRule{},
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

| Parameter                                                                                                                                                        | Type                                                                                                                                                             | Required                                                                                                                                                         | Description                                                                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                                                                                            | :heavy_check_mark:                                                                                                                                               | The context to use for the request.                                                                                                                              |
| `serviceID`                                                                                                                                                      | *string*                                                                                                                                                         | :heavy_check_mark:                                                                                                                                               | N/A                                                                                                                                                              |
| `v3ServicesDeduplicationRulesCreateDeduplicationRulesRequest`                                                                                                    | [components.V3ServicesDeduplicationRulesCreateDeduplicationRulesRequest](../../models/components/v3servicesdeduplicationrulescreatededuplicationrulesrequest.md) | :heavy_check_mark:                                                                                                                                               | N/A                                                                                                                                                              |
| `opts`                                                                                                                                                           | [][operations.Option](../../models/operations/option.md)                                                                                                         | :heavy_minus_sign:                                                                                                                                               | The options for this request.                                                                                                                                    |

### Response

**[*operations.DeduplicationRulesCreateOrUpdateDeduplicationRulesResponse](../../models/operations/deduplicationrulescreateorupdatededuplicationrulesresponse.md), error**

### Errors

| Error Type                                                                           | Status Code                                                                          | Content Type                                                                         |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesBadRequestError          | 400                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesUnauthorizedError        | 401                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesPaymentRequiredError     | 402                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesForbiddenError           | 403                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesNotFoundError            | 404                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesConflictError            | 409                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesUnprocessableEntityError | 422                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesInternalServerError      | 500                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesBadGatewayError          | 502                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesServiceUnavailableError  | 503                                                                                  | application/json                                                                     |
| apierrors.DeduplicationRulesCreateOrUpdateDeduplicationRulesGatewayTimeoutError      | 504                                                                                  | application/json                                                                     |
| apierrors.APIError                                                                   | 4XX, 5XX                                                                             | \*/\*                                                                                |