# GlobalEventRulesRulesetsRules
(*GlobalEventRulesRulesetsRules*)

## Overview

### Available Operations

* [DeleteByID](#deletebyid) - Delete Rule by ID

## DeleteByID

Delete a GER Ruleset Rule by its ID.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_deleteRuleById" method="delete" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/rules/{rule_id}" -->
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

    res, err := s.GlobalEventRulesRulesetsRules.DeleteByID(ctx, 921538, "<value>", "<value>", "<id>")
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