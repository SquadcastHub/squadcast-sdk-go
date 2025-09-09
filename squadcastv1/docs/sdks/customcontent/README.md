# CustomContent
(*Services.Overlays.CustomContent*)

## Overview

### Available Operations

* [Render](#render) - Render Custom Content Overlay

## Render

Render Custom Content Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_renderCustomContentOverlay" method="post" path="/v3/services/{serviceID}/overlays/custom-content/render" -->
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

    res, err := s.Services.Overlays.CustomContent.Render(ctx, "<id>", components.V3ServicesOverlayRenderCustomContentOverlayRequest{
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