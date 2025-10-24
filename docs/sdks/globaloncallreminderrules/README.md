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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| apierrors.BadRequestError          | 400                                | application/json                   |
| apierrors.UnauthorizedError        | 401                                | application/json                   |
| apierrors.PaymentRequiredError     | 402                                | application/json                   |
| apierrors.ForbiddenError           | 403                                | application/json                   |
| apierrors.NotFoundError            | 404                                | application/json                   |
| apierrors.ConflictError            | 409                                | application/json                   |
| apierrors.UnprocessableEntityError | 422                                | application/json                   |
| apierrors.InternalServerError      | 500                                | application/json                   |
| apierrors.BadGatewayError          | 502                                | application/json                   |
| apierrors.ServiceUnavailableError  | 503                                | application/json                   |
| apierrors.GatewayTimeoutError      | 504                                | application/json                   |
| apierrors.APIError                 | 4XX, 5XX                           | \*/\*                              |

## List

Get Global Oncall Reminder Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalOncallReminderRules_getGlobalOncallReminderRules" method="get" path="/v3/global-oncall-reminder-rules" -->
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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| apierrors.BadRequestError          | 400                                | application/json                   |
| apierrors.UnauthorizedError        | 401                                | application/json                   |
| apierrors.PaymentRequiredError     | 402                                | application/json                   |
| apierrors.ForbiddenError           | 403                                | application/json                   |
| apierrors.NotFoundError            | 404                                | application/json                   |
| apierrors.ConflictError            | 409                                | application/json                   |
| apierrors.UnprocessableEntityError | 422                                | application/json                   |
| apierrors.InternalServerError      | 500                                | application/json                   |
| apierrors.BadGatewayError          | 502                                | application/json                   |
| apierrors.ServiceUnavailableError  | 503                                | application/json                   |
| apierrors.GatewayTimeoutError      | 504                                | application/json                   |
| apierrors.APIError                 | 4XX, 5XX                           | \*/\*                              |

## Create

Create Global Oncall Reminder Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalOncallReminderRules_createGlobalOncallReminderRules" method="post" path="/v3/global-oncall-reminder-rules" -->
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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| apierrors.BadRequestError          | 400                                | application/json                   |
| apierrors.UnauthorizedError        | 401                                | application/json                   |
| apierrors.PaymentRequiredError     | 402                                | application/json                   |
| apierrors.ForbiddenError           | 403                                | application/json                   |
| apierrors.NotFoundError            | 404                                | application/json                   |
| apierrors.ConflictError            | 409                                | application/json                   |
| apierrors.UnprocessableEntityError | 422                                | application/json                   |
| apierrors.InternalServerError      | 500                                | application/json                   |
| apierrors.BadGatewayError          | 502                                | application/json                   |
| apierrors.ServiceUnavailableError  | 503                                | application/json                   |
| apierrors.GatewayTimeoutError      | 504                                | application/json                   |
| apierrors.APIError                 | 4XX, 5XX                           | \*/\*                              |

## Update

Update Global Oncall Reminder Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="GlobalOncallReminderRules_updateGlobalOncallReminderRules" method="put" path="/v3/global-oncall-reminder-rules" -->
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

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| apierrors.BadRequestError          | 400                                | application/json                   |
| apierrors.UnauthorizedError        | 401                                | application/json                   |
| apierrors.PaymentRequiredError     | 402                                | application/json                   |
| apierrors.ForbiddenError           | 403                                | application/json                   |
| apierrors.NotFoundError            | 404                                | application/json                   |
| apierrors.ConflictError            | 409                                | application/json                   |
| apierrors.UnprocessableEntityError | 422                                | application/json                   |
| apierrors.InternalServerError      | 500                                | application/json                   |
| apierrors.BadGatewayError          | 502                                | application/json                   |
| apierrors.ServiceUnavailableError  | 503                                | application/json                   |
| apierrors.GatewayTimeoutError      | 504                                | application/json                   |
| apierrors.APIError                 | 4XX, 5XX                           | \*/\*                              |