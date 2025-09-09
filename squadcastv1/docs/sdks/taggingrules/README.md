# TaggingRules
(*Services.TaggingRules*)

## Overview

### Available Operations

* [Get](#get) - Get Tagging Rules

## Get

Get Tagging Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="TaggingRules_getTaggingRules" method="get" path="/v3/services/{serviceID}/tagging-rules" -->
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

    res, err := s.Services.TaggingRules.Get(ctx, "<id>")
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

**[*operations.TaggingRulesGetTaggingRulesResponse](../../models/operations/taggingrulesgettaggingrulesresponse.md), error**

### Errors

| Error Type                                                    | Status Code                                                   | Content Type                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| apierrors.TaggingRulesGetTaggingRulesBadRequestError          | 400                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesUnauthorizedError        | 401                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesPaymentRequiredError     | 402                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesForbiddenError           | 403                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesNotFoundError            | 404                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesConflictError            | 409                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesUnprocessableEntityError | 422                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesInternalServerError      | 500                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesBadGatewayError          | 502                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesServiceUnavailableError  | 503                                                           | application/json                                              |
| apierrors.TaggingRulesGetTaggingRulesGatewayTimeoutError      | 504                                                           | application/json                                              |
| apierrors.APIError                                            | 4XX, 5XX                                                      | \*/\*                                                         |