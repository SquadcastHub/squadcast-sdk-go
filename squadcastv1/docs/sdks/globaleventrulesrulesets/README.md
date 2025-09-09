# GlobalEventRulesRulesets
(*GlobalEventRulesRulesets*)

## Overview

### Available Operations

* [Delete](#delete) - Delete GER Ruleset

## Delete

Delete a GER Ruleset

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_deleteGerRuleset" method="delete" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}" -->
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

    res, err := s.GlobalEventRulesRulesets.Delete(ctx, 198518, "<value>", "<value>")
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
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalEventRulesDeleteGerRulesetResponse](../../models/operations/globaleventrulesdeletegerrulesetresponse.md), error**

### Errors

| Error Type                                                         | Status Code                                                        | Content Type                                                       |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| apierrors.GlobalEventRulesDeleteGerRulesetBadRequestError          | 400                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetUnauthorizedError        | 401                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetPaymentRequiredError     | 402                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetForbiddenError           | 403                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetNotFoundError            | 404                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetConflictError            | 409                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetUnprocessableEntityError | 422                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetInternalServerError      | 500                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetBadGatewayError          | 502                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetServiceUnavailableError  | 503                                                                | application/json                                                   |
| apierrors.GlobalEventRulesDeleteGerRulesetGatewayTimeoutError      | 504                                                                | application/json                                                   |
| apierrors.APIError                                                 | 4XX, 5XX                                                           | \*/\*                                                              |