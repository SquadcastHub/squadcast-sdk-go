# GlobalEventRulesRulesets
(*GlobalEventRulesRulesets*)

## Overview

### Available Operations

* [GlobalEventRulesCreateRuleset](#globaleventrulescreateruleset) - Create Ruleset
* [GlobalEventRulesDeleteGerRuleset](#globaleventrulesdeletegerruleset) - Delete GER Ruleset
* [GlobalEventRulesGetRuleset](#globaleventrulesgetruleset) - Get Ruleset
* [GlobalEventRulesUpdateRuleset](#globaleventrulesupdateruleset) - Update Ruleset
* [GlobalEventRulesReorderRuleset](#globaleventrulesreorderruleset) - Reorder Ruleset

## GlobalEventRulesCreateRuleset

Create a GER Ruleset.

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_createRuleset" method="post" path="/v3/global-event-rules/{ger_id}/rulesets" -->
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

    res, err := s.GlobalEventRulesRulesets.GlobalEventRulesCreateRuleset(ctx, 216762, components.V3GlobalEventRulesCreateRulesetRequest{
        AlertSourceShortname: "<value>",
        AlertSourceVersion: "<value>",
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

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                  | :heavy_check_mark:                                                                                                     | The context to use for the request.                                                                                    |
| `gerID`                                                                                                                | *int64*                                                                                                                | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `v3GlobalEventRulesCreateRulesetRequest`                                                                               | [components.V3GlobalEventRulesCreateRulesetRequest](../../models/components/v3globaleventrulescreaterulesetrequest.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `opts`                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                               | :heavy_minus_sign:                                                                                                     | The options for this request.                                                                                          |

### Response

**[*operations.GlobalEventRulesCreateRulesetResponse](../../models/operations/globaleventrulescreaterulesetresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.GlobalEventRulesCreateRulesetBadRequestError          | 400                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetForbiddenError           | 403                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetNotFoundError            | 404                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetConflictError            | 409                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetInternalServerError      | 500                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.GlobalEventRulesCreateRulesetGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## GlobalEventRulesDeleteGerRuleset

Delete a GER Ruleset

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_deleteGerRuleset" method="delete" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}" -->
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

    res, err := s.GlobalEventRulesRulesets.GlobalEventRulesDeleteGerRuleset(ctx, 198518, "<value>", "<value>")
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

## GlobalEventRulesGetRuleset

Get a GER Ruleset

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_getRuleset" method="get" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}" -->
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

    res, err := s.GlobalEventRulesRulesets.GlobalEventRulesGetRuleset(ctx, 294223, "<value>", "<value>")
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
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalEventRulesGetRulesetResponse](../../models/operations/globaleventrulesgetrulesetresponse.md), error**

### Errors

| Error Type                                                   | Status Code                                                  | Content Type                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| apierrors.GlobalEventRulesGetRulesetBadRequestError          | 400                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetUnauthorizedError        | 401                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetPaymentRequiredError     | 402                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetForbiddenError           | 403                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetNotFoundError            | 404                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetConflictError            | 409                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetUnprocessableEntityError | 422                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetInternalServerError      | 500                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetBadGatewayError          | 502                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetServiceUnavailableError  | 503                                                          | application/json                                             |
| apierrors.GlobalEventRulesGetRulesetGatewayTimeoutError      | 504                                                          | application/json                                             |
| apierrors.APIError                                           | 4XX, 5XX                                                     | \*/\*                                                        |

## GlobalEventRulesUpdateRuleset

Update a GER Ruleset

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_updateRuleset" method="patch" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}" -->
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

    res, err := s.GlobalEventRulesRulesets.GlobalEventRulesUpdateRuleset(ctx, 489958, "<value>", "<value>", components.V3GlobalEventRulesUpdateRulesetRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                  | :heavy_check_mark:                                                                                                     | The context to use for the request.                                                                                    |
| `gerID`                                                                                                                | *int64*                                                                                                                | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `alertSourceVersion`                                                                                                   | *string*                                                                                                               | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `alertSourceShortname`                                                                                                 | *string*                                                                                                               | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `v3GlobalEventRulesUpdateRulesetRequest`                                                                               | [components.V3GlobalEventRulesUpdateRulesetRequest](../../models/components/v3globaleventrulesupdaterulesetrequest.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `opts`                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                               | :heavy_minus_sign:                                                                                                     | The options for this request.                                                                                          |

### Response

**[*operations.GlobalEventRulesUpdateRulesetResponse](../../models/operations/globaleventrulesupdaterulesetresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.GlobalEventRulesUpdateRulesetBadRequestError          | 400                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetForbiddenError           | 403                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetNotFoundError            | 404                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetConflictError            | 409                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetInternalServerError      | 500                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.GlobalEventRulesUpdateRulesetGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## GlobalEventRulesReorderRuleset

Reorder rules of a GER Ruleset

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalEventRules_reorderRuleset" method="patch" path="/v3/global-event-rules/{ger_id}/rulesets/{alert_source_version}/{alert_source_shortname}/priority" -->
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

    res, err := s.GlobalEventRulesRulesets.GlobalEventRulesReorderRuleset(ctx, 572014, "<value>", "<value>", components.V3GlobalEventRulesReorderRulesetRequest{})
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
| `gerID`                                                                                                                  | *int64*                                                                                                                  | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `alertSourceVersion`                                                                                                     | *string*                                                                                                                 | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `alertSourceShortname`                                                                                                   | *string*                                                                                                                 | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `v3GlobalEventRulesReorderRulesetRequest`                                                                                | [components.V3GlobalEventRulesReorderRulesetRequest](../../models/components/v3globaleventrulesreorderrulesetrequest.md) | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `opts`                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                 | :heavy_minus_sign:                                                                                                       | The options for this request.                                                                                            |

### Response

**[*operations.GlobalEventRulesReorderRulesetResponse](../../models/operations/globaleventrulesreorderrulesetresponse.md), error**

### Errors

| Error Type         | Status Code        | Content Type       |
| ------------------ | ------------------ | ------------------ |
| apierrors.APIError | 4XX, 5XX           | \*/\*              |