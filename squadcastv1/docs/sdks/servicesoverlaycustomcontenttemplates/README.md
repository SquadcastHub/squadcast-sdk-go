# ServicesOverlayCustomContentTemplates
(*ServicesOverlayCustomContentTemplates*)

## Overview

### Available Operations

* [OverlayGetAllCustomContentTemplateOverlayByService](#overlaygetallcustomcontenttemplateoverlaybyservice) - Get All Custom Content Template Overlay by Service
* [OverlayRenderCustomContentOverlay](#overlayrendercustomcontentoverlay) - Render Custom Content Overlay
* [OverlayDeleteNotificationTemplateOverlay](#overlaydeletenotificationtemplateoverlay) - Delete Notification Template Overlay
* [OverlayGetCustomContentTemplateOverlay](#overlaygetcustomcontenttemplateoverlay) - Get Custom Content Template Overlay
* [OverlayCreateOrUpdateNotificationTemplateOverlay](#overlaycreateorupdatenotificationtemplateoverlay) - Create or Update Notification Template Overlay

## OverlayGetAllCustomContentTemplateOverlayByService

Get All Custom Content Template Overlay by Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_getAllCustomContentTemplateOverlayByService" method="get" path="/v3/services/{serviceID}/overlays/custom-content" -->
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

    res, err := s.ServicesOverlayCustomContentTemplates.OverlayGetAllCustomContentTemplateOverlayByService(ctx, "<id>")
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

**[*operations.OverlayGetAllCustomContentTemplateOverlayByServiceResponse](../../models/operations/overlaygetallcustomcontenttemplateoverlaybyserviceresponse.md), error**

### Errors

| Error Type                                                                           | Status Code                                                                          | Content Type                                                                         |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceBadRequestError          | 400                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceUnauthorizedError        | 401                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServicePaymentRequiredError     | 402                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceForbiddenError           | 403                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceNotFoundError            | 404                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceConflictError            | 409                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceUnprocessableEntityError | 422                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceInternalServerError      | 500                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceBadGatewayError          | 502                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceServiceUnavailableError  | 503                                                                                  | application/json                                                                     |
| apierrors.OverlayGetAllCustomContentTemplateOverlayByServiceGatewayTimeoutError      | 504                                                                                  | application/json                                                                     |
| apierrors.APIError                                                                   | 4XX, 5XX                                                                             | \*/\*                                                                                |

## OverlayRenderCustomContentOverlay

Render Custom Content Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_renderCustomContentOverlay" method="post" path="/v3/services/{serviceID}/overlays/custom-content/render" -->
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

    res, err := s.ServicesOverlayCustomContentTemplates.OverlayRenderCustomContentOverlay(ctx, "<id>", components.V3ServicesOverlayRenderCustomContentOverlayRequest{
        OverlayTemplateType: "<value>",
        Template: "<value>",
        Payload: "<value>",
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

| Parameter                                                                                                                                      | Type                                                                                                                                           | Required                                                                                                                                       | Description                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                                                                          | :heavy_check_mark:                                                                                                                             | The context to use for the request.                                                                                                            |
| `serviceID`                                                                                                                                    | *string*                                                                                                                                       | :heavy_check_mark:                                                                                                                             | N/A                                                                                                                                            |
| `v3ServicesOverlayRenderCustomContentOverlayRequest`                                                                                           | [components.V3ServicesOverlayRenderCustomContentOverlayRequest](../../models/components/v3servicesoverlayrendercustomcontentoverlayrequest.md) | :heavy_check_mark:                                                                                                                             | N/A                                                                                                                                            |
| `opts`                                                                                                                                         | [][operations.Option](../../models/operations/option.md)                                                                                       | :heavy_minus_sign:                                                                                                                             | The options for this request.                                                                                                                  |

### Response

**[*operations.OverlayRenderCustomContentOverlayResponse](../../models/operations/overlayrendercustomcontentoverlayresponse.md), error**

### Errors

| Error Type                                                          | Status Code                                                         | Content Type                                                        |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| apierrors.OverlayRenderCustomContentOverlayBadRequestError          | 400                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayUnauthorizedError        | 401                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayPaymentRequiredError     | 402                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayForbiddenError           | 403                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayNotFoundError            | 404                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayConflictError            | 409                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayUnprocessableEntityError | 422                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayInternalServerError      | 500                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayBadGatewayError          | 502                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayServiceUnavailableError  | 503                                                                 | application/json                                                    |
| apierrors.OverlayRenderCustomContentOverlayGatewayTimeoutError      | 504                                                                 | application/json                                                    |
| apierrors.APIError                                                  | 4XX, 5XX                                                            | \*/\*                                                               |

## OverlayDeleteNotificationTemplateOverlay

Delete Notification Template Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_deleteNotificationTemplateOverlay" method="delete" path="/v3/services/{serviceID}/overlays/custom-content/{alertSource}" -->
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

    res, err := s.ServicesOverlayCustomContentTemplates.OverlayDeleteNotificationTemplateOverlay(ctx, "<id>", "<value>")
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
| `serviceID`                                              | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `alertSource`                                            | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.OverlayDeleteNotificationTemplateOverlayResponse](../../models/operations/overlaydeletenotificationtemplateoverlayresponse.md), error**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| apierrors.OverlayDeleteNotificationTemplateOverlayBadRequestError          | 400                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayUnauthorizedError        | 401                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayPaymentRequiredError     | 402                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayForbiddenError           | 403                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayNotFoundError            | 404                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayConflictError            | 409                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayUnprocessableEntityError | 422                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayInternalServerError      | 500                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayBadGatewayError          | 502                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayServiceUnavailableError  | 503                                                                        | application/json                                                           |
| apierrors.OverlayDeleteNotificationTemplateOverlayGatewayTimeoutError      | 504                                                                        | application/json                                                           |
| apierrors.APIError                                                         | 4XX, 5XX                                                                   | \*/\*                                                                      |

## OverlayGetCustomContentTemplateOverlay

Get Custom Content Template Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_getCustomContentTemplateOverlay" method="get" path="/v3/services/{serviceID}/overlays/custom-content/{alertSource}" -->
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

    res, err := s.ServicesOverlayCustomContentTemplates.OverlayGetCustomContentTemplateOverlay(ctx, "<id>", "<value>")
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
| `alertSource`                                            | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.OverlayGetCustomContentTemplateOverlayResponse](../../models/operations/overlaygetcustomcontenttemplateoverlayresponse.md), error**

### Errors

| Error Type                                                               | Status Code                                                              | Content Type                                                             |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| apierrors.OverlayGetCustomContentTemplateOverlayBadRequestError          | 400                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayUnauthorizedError        | 401                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayPaymentRequiredError     | 402                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayForbiddenError           | 403                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayNotFoundError            | 404                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayConflictError            | 409                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayUnprocessableEntityError | 422                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayInternalServerError      | 500                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayBadGatewayError          | 502                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayServiceUnavailableError  | 503                                                                      | application/json                                                         |
| apierrors.OverlayGetCustomContentTemplateOverlayGatewayTimeoutError      | 504                                                                      | application/json                                                         |
| apierrors.APIError                                                       | 4XX, 5XX                                                                 | \*/\*                                                                    |

## OverlayCreateOrUpdateNotificationTemplateOverlay

Create or Update Notification Template Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_createOrUpdateNotificationTemplateOverlay" method="put" path="/v3/services/{serviceID}/overlays/custom-content/{alertSource}" -->
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

    res, err := s.ServicesOverlayCustomContentTemplates.OverlayCreateOrUpdateNotificationTemplateOverlay(ctx, "<id>", "<value>", components.V3ServicesOverlayUpdateCustomContentTemplateOverlayRequest{
        OverlayTemplateType: "<value>",
        MessageOverlay: components.MessageOverlay{
            Template: "<value>",
        },
        DescriptionOverlay: components.DescriptionOverlay{
            Template: "<value>",
        },
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

| Parameter                                                                                                                                                      | Type                                                                                                                                                           | Required                                                                                                                                                       | Description                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                                                                                          | :heavy_check_mark:                                                                                                                                             | The context to use for the request.                                                                                                                            |
| `serviceID`                                                                                                                                                    | *string*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                             | N/A                                                                                                                                                            |
| `alertSource`                                                                                                                                                  | *string*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                             | N/A                                                                                                                                                            |
| `v3ServicesOverlayUpdateCustomContentTemplateOverlayRequest`                                                                                                   | [components.V3ServicesOverlayUpdateCustomContentTemplateOverlayRequest](../../models/components/v3servicesoverlayupdatecustomcontenttemplateoverlayrequest.md) | :heavy_check_mark:                                                                                                                                             | N/A                                                                                                                                                            |
| `opts`                                                                                                                                                         | [][operations.Option](../../models/operations/option.md)                                                                                                       | :heavy_minus_sign:                                                                                                                                             | The options for this request.                                                                                                                                  |

### Response

**[*operations.OverlayCreateOrUpdateNotificationTemplateOverlayResponse](../../models/operations/overlaycreateorupdatenotificationtemplateoverlayresponse.md), error**

### Errors

| Error Type                                                                         | Status Code                                                                        | Content Type                                                                       |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayBadRequestError          | 400                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayUnauthorizedError        | 401                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayPaymentRequiredError     | 402                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayForbiddenError           | 403                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayNotFoundError            | 404                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayConflictError            | 409                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayUnprocessableEntityError | 422                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayInternalServerError      | 500                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayBadGatewayError          | 502                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayServiceUnavailableError  | 503                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayGatewayTimeoutError      | 504                                                                                | application/json                                                                   |
| apierrors.APIError                                                                 | 4XX, 5XX                                                                           | \*/\*                                                                              |