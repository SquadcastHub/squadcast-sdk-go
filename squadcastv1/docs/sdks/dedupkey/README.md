# DedupKey
(*Services.Overlays.DedupKey*)

## Overview

### Available Operations

* [Render](#render) - Render Dedup Key template
* [Delete](#delete) - Delete Dedup Key Overlay

## Render

Render Dedup Key template

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_renderDedupKeyTemplate" method="post" path="/v3/services/{serviceID}/overlays/dedup-key/render" -->
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

    res, err := s.Services.Overlays.DedupKey.Render(ctx, "<id>", components.V3ServicesOverlayRenderDedupKeyTemplateRequest{
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

## Delete

Delete Dedup Key Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_deleteDedupKeyOverlay" method="delete" path="/v3/services/{serviceID}/overlays/dedup-key/{alertSource}" -->
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

    res, err := s.Services.Overlays.DedupKey.Delete(ctx, "<id>", "<value>")
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