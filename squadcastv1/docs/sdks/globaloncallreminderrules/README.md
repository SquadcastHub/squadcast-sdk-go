# GlobalOncallReminderRules
(*GlobalOncallReminderRules*)

## Overview

### Available Operations

* [Delete](#delete) - Delete Global Oncall Reminder Rules
* [List](#list) - Get Global Oncall Reminder Rules
* [Create](#create) - Create Global Oncall Reminder Rules
* [Update](#update) - Update Global Oncall Reminder Rules

## Delete

Delete Global Oncall Reminder Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalOncallReminderRules_deleteGlobalOncallReminderRules" method="delete" path="/v3/global-oncall-reminder-rules" -->
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

    res, err := s.GlobalOncallReminderRules.Delete(ctx, "<id>")
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
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesResponse](../../models/operations/globaloncallreminderrulesdeleteglobaloncallreminderrulesresponse.md), error**

### Errors

| Error Type                                                                                 | Status Code                                                                                | Content Type                                                                               |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesBadRequestError          | 400                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesUnauthorizedError        | 401                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesPaymentRequiredError     | 402                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesForbiddenError           | 403                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesNotFoundError            | 404                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesConflictError            | 409                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesUnprocessableEntityError | 422                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesInternalServerError      | 500                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesBadGatewayError          | 502                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesServiceUnavailableError  | 503                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesDeleteGlobalOncallReminderRulesGatewayTimeoutError      | 504                                                                                        | application/json                                                                           |
| apierrors.APIError                                                                         | 4XX, 5XX                                                                                   | \*/\*                                                                                      |

## List

Get Global Oncall Reminder Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalOncallReminderRules_getGlobalOncallReminderRules" method="get" path="/v3/global-oncall-reminder-rules" -->
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

    res, err := s.GlobalOncallReminderRules.List(ctx, "<id>")
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
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | required *                                               |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.GlobalOncallReminderRulesGetGlobalOncallReminderRulesResponse](../../models/operations/globaloncallreminderrulesgetglobaloncallreminderrulesresponse.md), error**

### Errors

| Error Type                                                                              | Status Code                                                                             | Content Type                                                                            |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesBadRequestError          | 400                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesUnauthorizedError        | 401                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesPaymentRequiredError     | 402                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesForbiddenError           | 403                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesNotFoundError            | 404                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesConflictError            | 409                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesUnprocessableEntityError | 422                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesInternalServerError      | 500                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesBadGatewayError          | 502                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesServiceUnavailableError  | 503                                                                                     | application/json                                                                        |
| apierrors.GlobalOncallReminderRulesGetGlobalOncallReminderRulesGatewayTimeoutError      | 504                                                                                     | application/json                                                                        |
| apierrors.APIError                                                                      | 4XX, 5XX                                                                                | \*/\*                                                                                   |

## Create

Create Global Oncall Reminder Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalOncallReminderRules_createGlobalOncallReminderRules" method="post" path="/v3/global-oncall-reminder-rules" -->
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

    res, err := s.GlobalOncallReminderRules.Create(ctx, components.V3GlobalOncallReminderRulesCreateGlobalOncallReminderRulesRequest{
        IsEnabled: true,
        OwnerID: "<id>",
        Rules: []components.V3GlobalOncallReminderRulesRule{},
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

| Parameter                                                                                                                                                                    | Type                                                                                                                                                                         | Required                                                                                                                                                                     | Description                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                                                                                        | :heavy_check_mark:                                                                                                                                                           | The context to use for the request.                                                                                                                                          |
| `request`                                                                                                                                                                    | [components.V3GlobalOncallReminderRulesCreateGlobalOncallReminderRulesRequest](../../models/components/v3globaloncallreminderrulescreateglobaloncallreminderrulesrequest.md) | :heavy_check_mark:                                                                                                                                                           | The request object to use for the request.                                                                                                                                   |
| `opts`                                                                                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                                                                                     | :heavy_minus_sign:                                                                                                                                                           | The options for this request.                                                                                                                                                |

### Response

**[*operations.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesResponse](../../models/operations/globaloncallreminderrulescreateglobaloncallreminderrulesresponse.md), error**

### Errors

| Error Type                                                                                 | Status Code                                                                                | Content Type                                                                               |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesBadRequestError          | 400                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesUnauthorizedError        | 401                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesPaymentRequiredError     | 402                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesForbiddenError           | 403                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesNotFoundError            | 404                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesConflictError            | 409                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesUnprocessableEntityError | 422                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesInternalServerError      | 500                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesBadGatewayError          | 502                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesServiceUnavailableError  | 503                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesCreateGlobalOncallReminderRulesGatewayTimeoutError      | 504                                                                                        | application/json                                                                           |
| apierrors.APIError                                                                         | 4XX, 5XX                                                                                   | \*/\*                                                                                      |

## Update

Update Global Oncall Reminder Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalOncallReminderRules_updateGlobalOncallReminderRules" method="put" path="/v3/global-oncall-reminder-rules" -->
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

    res, err := s.GlobalOncallReminderRules.Update(ctx, "<id>", components.V3GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesRequest{
        IsEnabled: true,
        Rules: []components.V3GlobalOncallReminderRulesRule{},
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

| Parameter                                                                                                                                                                    | Type                                                                                                                                                                         | Required                                                                                                                                                                     | Description                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                                                                                        | :heavy_check_mark:                                                                                                                                                           | The context to use for the request.                                                                                                                                          |
| `ownerID`                                                                                                                                                                    | *string*                                                                                                                                                                     | :heavy_check_mark:                                                                                                                                                           | N/A                                                                                                                                                                          |
| `v3GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesRequest`                                                                                                          | [components.V3GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesRequest](../../models/components/v3globaloncallreminderrulesupdateglobaloncallreminderrulesrequest.md) | :heavy_check_mark:                                                                                                                                                           | N/A                                                                                                                                                                          |
| `opts`                                                                                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                                                                                     | :heavy_minus_sign:                                                                                                                                                           | The options for this request.                                                                                                                                                |

### Response

**[*operations.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesResponse](../../models/operations/globaloncallreminderrulesupdateglobaloncallreminderrulesresponse.md), error**

### Errors

| Error Type                                                                                 | Status Code                                                                                | Content Type                                                                               |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesBadRequestError          | 400                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesUnauthorizedError        | 401                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesPaymentRequiredError     | 402                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesForbiddenError           | 403                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesNotFoundError            | 404                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesConflictError            | 409                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesUnprocessableEntityError | 422                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesInternalServerError      | 500                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesBadGatewayError          | 502                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesServiceUnavailableError  | 503                                                                                        | application/json                                                                           |
| apierrors.GlobalOncallReminderRulesUpdateGlobalOncallReminderRulesGatewayTimeoutError      | 504                                                                                        | application/json                                                                           |
| apierrors.APIError                                                                         | 4XX, 5XX                                                                                   | \*/\*                                                                                      |