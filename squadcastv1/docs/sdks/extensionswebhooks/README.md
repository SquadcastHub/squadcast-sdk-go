# ExtensionsWebhooks
(*Extensions.Webhooks*)

## Overview

### Available Operations

* [Delete](#delete) - Delete Webhook
* [GetByID](#getbyid) - Get Webhook By ID

## Delete

Remove webhook from the organization. Upon success, the webhook will be removed from the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webhooks_deleteWebhook" method="delete" path="/v3/extensions/event-webhooks/{eventWebhookID}" -->
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

    res, err := s.Extensions.Webhooks.Delete(ctx, "<id>")
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

## GetByID

Returns a webhooks details of the given `eventWebhookID` in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webhooks_getWebhookById" method="get" path="/v3/extensions/event-webhooks/{eventWebhookID}" -->
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

    res, err := s.Extensions.Webhooks.GetByID(ctx, "<id>")
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