# ExtensionsWebhooks
(*ExtensionsWebhooks*)

## Overview

### Available Operations

* [WebhooksGetAllWebhooks](#webhooksgetallwebhooks) - Get All Webhooks
* [WebhooksCreateWebhook](#webhookscreatewebhook) - Create Webhook
* [WebhooksDeleteWebhook](#webhooksdeletewebhook) - Delete Webhook
* [WebhooksGetWebhookByID](#webhooksgetwebhookbyid) - Get Webhook By ID
* [WebhooksUpdateWebhook](#webhooksupdatewebhook) - Update Webhook

## WebhooksGetAllWebhooks

Returns all the webhooks of the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webhooks_getAllWebhooks" method="get" path="/v3/extensions/event-webhooks" -->
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

    res, err := s.ExtensionsWebhooks.WebhooksGetAllWebhooks(ctx, nil, nil)
    if err != nil {
        log.Fatal(err)
    }
    if res.V3ExtensionsWebhooksGetAllWebhooksResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `pageLimit`                                              | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `offset`                                                 | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WebhooksGetAllWebhooksResponse](../../models/operations/webhooksgetallwebhooksresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.WebhooksGetAllWebhooksBadRequestError          | 400                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksForbiddenError           | 403                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksNotFoundError            | 404                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksConflictError            | 409                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksInternalServerError      | 500                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.WebhooksGetAllWebhooksGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## WebhooksCreateWebhook

Add webhook to the organization. Returns the webhook object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webhooks_createWebhook" method="post" path="/v3/extensions/event-webhooks" -->
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

    res, err := s.ExtensionsWebhooks.WebhooksCreateWebhook(ctx, components.V3ExtensionsWebhooksWebhook{
        Name: "<value>",
        Triggers: []components.V3ExtensionsWebhooksWebhookTrigger{},
        Urls: []components.V3ExtensionsWebhooksWebhookURL{
            components.V3ExtensionsWebhooksWebhookURL{},
        },
        TriggerType: "<value>",
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

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `request`                                                                                        | [components.V3ExtensionsWebhooksWebhook](../../models/components/v3extensionswebhookswebhook.md) | :heavy_check_mark:                                                                               | The request object to use for the request.                                                       |
| `opts`                                                                                           | [][operations.Option](../../models/operations/option.md)                                         | :heavy_minus_sign:                                                                               | The options for this request.                                                                    |

### Response

**[*operations.WebhooksCreateWebhookResponse](../../models/operations/webhookscreatewebhookresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.WebhooksCreateWebhookBadRequestError          | 400                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookForbiddenError           | 403                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookNotFoundError            | 404                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookConflictError            | 409                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookInternalServerError      | 500                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.WebhooksCreateWebhookGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## WebhooksDeleteWebhook

Remove webhook from the organization. Upon success, the webhook will be removed from the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webhooks_deleteWebhook" method="delete" path="/v3/extensions/event-webhooks/{eventWebhookID}" -->
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

    res, err := s.ExtensionsWebhooks.WebhooksDeleteWebhook(ctx, "<id>")
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
| `eventWebhookID`                                         | *string*                                                 | :heavy_check_mark:                                       | (Required) event webhook ID                              |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WebhooksDeleteWebhookResponse](../../models/operations/webhooksdeletewebhookresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.WebhooksDeleteWebhookBadRequestError          | 400                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookForbiddenError           | 403                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookNotFoundError            | 404                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookConflictError            | 409                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookInternalServerError      | 500                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.WebhooksDeleteWebhookGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## WebhooksGetWebhookByID

Returns a webhooks details of the given `eventWebhookID` in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webhooks_getWebhookById" method="get" path="/v3/extensions/event-webhooks/{eventWebhookID}" -->
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

    res, err := s.ExtensionsWebhooks.WebhooksGetWebhookByID(ctx, "<id>")
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
| `eventWebhookID`                                         | *string*                                                 | :heavy_check_mark:                                       | (Required) event webhook ID                              |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WebhooksGetWebhookByIDResponse](../../models/operations/webhooksgetwebhookbyidresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.WebhooksGetWebhookByIDBadRequestError          | 400                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDForbiddenError           | 403                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDNotFoundError            | 404                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDConflictError            | 409                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDInternalServerError      | 500                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.WebhooksGetWebhookByIDGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## WebhooksUpdateWebhook

Update organization webhook details.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webhooks_updateWebhook" method="put" path="/v3/extensions/event-webhooks/{eventWebhookID}" -->
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

    res, err := s.ExtensionsWebhooks.WebhooksUpdateWebhook(ctx, "<id>", components.V3ExtensionsWebhooksWebhook{
        Name: "<value>",
        Triggers: []components.V3ExtensionsWebhooksWebhookTrigger{
            components.V3ExtensionsWebhooksWebhookTrigger{
                EventClass: "<value>",
                EventType: "<value>",
            },
        },
        Urls: []components.V3ExtensionsWebhooksWebhookURL{
            components.V3ExtensionsWebhooksWebhookURL{},
        },
        TriggerType: "<value>",
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

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `eventWebhookID`                                                                                 | *string*                                                                                         | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `v3ExtensionsWebhooksWebhook`                                                                    | [components.V3ExtensionsWebhooksWebhook](../../models/components/v3extensionswebhookswebhook.md) | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `opts`                                                                                           | [][operations.Option](../../models/operations/option.md)                                         | :heavy_minus_sign:                                                                               | The options for this request.                                                                    |

### Response

**[*operations.WebhooksUpdateWebhookResponse](../../models/operations/webhooksupdatewebhookresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.WebhooksUpdateWebhookBadRequestError          | 400                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookForbiddenError           | 403                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookNotFoundError            | 404                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookConflictError            | 409                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookInternalServerError      | 500                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.WebhooksUpdateWebhookGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |