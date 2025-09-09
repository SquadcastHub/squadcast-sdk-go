# Rules
(*GlobalEventRules.Rules*)

## Overview

### Available Operations

* [ReorderByIndex](#reorderbyindex) - Reorder Ruleset By Index

## ReorderByIndex

Reorder a GER Ruleset Rule by its index in the ruleset.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_reorderRulesetByIndex" method="patch" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules/{rule_id}/priority" -->
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

    res, err := s.GlobalEventRules.Rules.ReorderByIndex(ctx, operations.GlobalEventRulesReorderRulesetByIndexRequest{
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