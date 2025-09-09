# ServicesOverlayDedupKeyOverlay
(*ServicesOverlayDedupKeyOverlay*)

## Overview

### Available Operations

* [OverlayGetAllDedupKeyOverlayByService](#overlaygetalldedupkeyoverlaybyservice) - Get All Dedup Key Overlay by Service
* [OverlayRenderDedupKeyTemplate](#overlayrenderdedupkeytemplate) - Render Dedup Key template
* [OverlayDeleteDedupKeyOverlay](#overlaydeletededupkeyoverlay) - Delete Dedup Key Overlay
* [OverlayGetDedupKeyOverlayForAlertSource](#overlaygetdedupkeyoverlayforalertsource) - Get Dedup Key Overlay for Alert Source
* [OverlayUpdateDedupKeyOverlay](#overlayupdatededupkeyoverlay) - Update Dedup Key Overlay

## OverlayGetAllDedupKeyOverlayByService

Get All Dedup Key Overlay by Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_getAllDedupKeyOverlayByService" method="get" path="/v3/services/{serviceID}/overlays/dedup-key" -->
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

    res, err := s.ServicesOverlayDedupKeyOverlay.OverlayGetAllDedupKeyOverlayByService(ctx, "<id>")
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

**[*operations.OverlayGetAllDedupKeyOverlayByServiceResponse](../../models/operations/overlaygetalldedupkeyoverlaybyserviceresponse.md), error**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceBadRequestError          | 400                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceUnauthorizedError        | 401                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServicePaymentRequiredError     | 402                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceForbiddenError           | 403                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceNotFoundError            | 404                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceConflictError            | 409                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceUnprocessableEntityError | 422                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceInternalServerError      | 500                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceBadGatewayError          | 502                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceServiceUnavailableError  | 503                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceGatewayTimeoutError      | 504                                                                     | application/json                                                        |
| apierrors.APIError                                                      | 4XX, 5XX                                                                | \*/\*                                                                   |

## OverlayRenderDedupKeyTemplate

Render Dedup Key template

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_renderDedupKeyTemplate" method="post" path="/v3/services/{serviceID}/overlays/dedup-key/render" -->
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

    res, err := s.ServicesOverlayDedupKeyOverlay.OverlayRenderDedupKeyTemplate(ctx, "<id>", components.V3ServicesOverlayRenderDedupKeyTemplateRequest{
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

| Parameter                                                                                                                              | Type                                                                                                                                   | Required                                                                                                                               | Description                                                                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                                  | :heavy_check_mark:                                                                                                                     | The context to use for the request.                                                                                                    |
| `serviceID`                                                                                                                            | *string*                                                                                                                               | :heavy_check_mark:                                                                                                                     | N/A                                                                                                                                    |
| `v3ServicesOverlayRenderDedupKeyTemplateRequest`                                                                                       | [components.V3ServicesOverlayRenderDedupKeyTemplateRequest](../../models/components/v3servicesoverlayrenderdedupkeytemplaterequest.md) | :heavy_check_mark:                                                                                                                     | N/A                                                                                                                                    |
| `opts`                                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                                               | :heavy_minus_sign:                                                                                                                     | The options for this request.                                                                                                          |

### Response

**[*operations.OverlayRenderDedupKeyTemplateResponse](../../models/operations/overlayrenderdedupkeytemplateresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.OverlayRenderDedupKeyTemplateBadRequestError          | 400                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplatePaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateForbiddenError           | 403                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateNotFoundError            | 404                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateConflictError            | 409                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateInternalServerError      | 500                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.OverlayRenderDedupKeyTemplateGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## OverlayDeleteDedupKeyOverlay

Delete Dedup Key Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_deleteDedupKeyOverlay" method="delete" path="/v3/services/{serviceID}/overlays/dedup-key/{alertSource}" -->
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

    res, err := s.ServicesOverlayDedupKeyOverlay.OverlayDeleteDedupKeyOverlay(ctx, "<id>", "<value>")
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

**[*operations.OverlayDeleteDedupKeyOverlayResponse](../../models/operations/overlaydeletededupkeyoverlayresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.OverlayDeleteDedupKeyOverlayBadRequestError          | 400                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayForbiddenError           | 403                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayNotFoundError            | 404                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayConflictError            | 409                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayInternalServerError      | 500                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.OverlayDeleteDedupKeyOverlayGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## OverlayGetDedupKeyOverlayForAlertSource

Get Dedup Key Overlay for Alert Source

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_getDedupKeyOverlayForAlertSource" method="get" path="/v3/services/{serviceID}/overlays/dedup-key/{alertSource}" -->
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

    res, err := s.ServicesOverlayDedupKeyOverlay.OverlayGetDedupKeyOverlayForAlertSource(ctx, "<id>", "<value>")
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

**[*operations.OverlayGetDedupKeyOverlayForAlertSourceResponse](../../models/operations/overlaygetdedupkeyoverlayforalertsourceresponse.md), error**

### Errors

| Error Type                                                                | Status Code                                                               | Content Type                                                              |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceBadRequestError          | 400                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceUnauthorizedError        | 401                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourcePaymentRequiredError     | 402                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceForbiddenError           | 403                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceNotFoundError            | 404                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceConflictError            | 409                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceUnprocessableEntityError | 422                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceInternalServerError      | 500                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceBadGatewayError          | 502                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceServiceUnavailableError  | 503                                                                       | application/json                                                          |
| apierrors.OverlayGetDedupKeyOverlayForAlertSourceGatewayTimeoutError      | 504                                                                       | application/json                                                          |
| apierrors.APIError                                                        | 4XX, 5XX                                                                  | \*/\*                                                                     |

## OverlayUpdateDedupKeyOverlay

Update Dedup Key Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_updateDedupKeyOverlay" method="put" path="/v3/services/{serviceID}/overlays/dedup-key/{alertSource}" -->
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

    res, err := s.ServicesOverlayDedupKeyOverlay.OverlayUpdateDedupKeyOverlay(ctx, "<id>", "<value>", components.V3ServicesOverlayUpdateDedupKeyOverlayRequest{
        OverlayTemplateType: "<value>",
        DedupKeyOverlay: components.DedupKeyOverlay{
            Template: "<value>",
            Duration: 360400,
        },
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.OneOf != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                            | Type                                                                                                                                 | Required                                                                                                                             | Description                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                | :heavy_check_mark:                                                                                                                   | The context to use for the request.                                                                                                  |
| `serviceID`                                                                                                                          | *string*                                                                                                                             | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `alertSource`                                                                                                                        | *string*                                                                                                                             | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `v3ServicesOverlayUpdateDedupKeyOverlayRequest`                                                                                      | [components.V3ServicesOverlayUpdateDedupKeyOverlayRequest](../../models/components/v3servicesoverlayupdatededupkeyoverlayrequest.md) | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `opts`                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                             | :heavy_minus_sign:                                                                                                                   | The options for this request.                                                                                                        |

### Response

**[*operations.OverlayUpdateDedupKeyOverlayResponse](../../models/operations/overlayupdatededupkeyoverlayresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.OverlayUpdateDedupKeyOverlayBadRequestError          | 400                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayForbiddenError           | 403                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayNotFoundError            | 404                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayConflictError            | 409                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayInternalServerError      | 500                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |