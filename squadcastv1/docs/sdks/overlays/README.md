# Overlays
(*Overlays*)

## Overview

### Available Operations

* [DeleteNotificationTemplate](#deletenotificationtemplate) - Delete Notification Template Overlay

## DeleteNotificationTemplate

Delete Notification Template Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_deleteNotificationTemplateOverlay" method="delete" path="/v3/services/{serviceID}/overlays/custom-content/{alertSource}" -->
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

    res, err := s.Overlays.DeleteNotificationTemplate(ctx, "<id>", "<value>")
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