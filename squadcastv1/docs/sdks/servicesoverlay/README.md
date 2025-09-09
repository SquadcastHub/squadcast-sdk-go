# ServicesOverlay
(*ServicesOverlay*)

## Overview

### Available Operations

* [OverlayGetOptinForKeyBasedDeduplicationForAService](#overlaygetoptinforkeybaseddeduplicationforaservice) - Get Opt-in for Key Based Deduplication for a service
* [OverlayOptinForKeyBasedDeduplicationForAService](#overlayoptinforkeybaseddeduplicationforaservice) - Opt-in for Key Based Deduplication for a service

## OverlayGetOptinForKeyBasedDeduplicationForAService

Get Opt-in for Key Based Deduplication for a service

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_getOptinForKeyBasedDeduplicationForAService" method="get" path="/v3/services/{serviceID}/config" -->
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

    res, err := s.ServicesOverlay.OverlayGetOptinForKeyBasedDeduplicationForAService(ctx, "<id>")
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

**[*operations.OverlayGetOptinForKeyBasedDeduplicationForAServiceResponse](../../models/operations/overlaygetoptinforkeybaseddeduplicationforaserviceresponse.md), error**

### Errors

| Error Type                                                                           | Status Code                                                                          | Content Type                                                                         |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceBadRequestError          | 400                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceUnauthorizedError        | 401                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServicePaymentRequiredError     | 402                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceForbiddenError           | 403                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceNotFoundError            | 404                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceConflictError            | 409                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceUnprocessableEntityError | 422                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceInternalServerError      | 500                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceBadGatewayError          | 502                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceServiceUnavailableError  | 503                                                                                  | application/json                                                                     |
| apierrors.OverlayGetOptinForKeyBasedDeduplicationForAServiceGatewayTimeoutError      | 504                                                                                  | application/json                                                                     |
| apierrors.APIError                                                                   | 4XX, 5XX                                                                             | \*/\*                                                                                |

## OverlayOptinForKeyBasedDeduplicationForAService

Opt-in for Key Based Deduplication for a service

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_optinForKeyBasedDeduplicationForAService" method="patch" path="/v3/services/{serviceID}/config" -->
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

    res, err := s.ServicesOverlay.OverlayOptinForKeyBasedDeduplicationForAService(ctx, "<id>", components.V3ServicesOverlayOptInForKeyBasedDeduplicationRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                                            | Type                                                                                                                                                 | Required                                                                                                                                             | Description                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                                | :heavy_check_mark:                                                                                                                                   | The context to use for the request.                                                                                                                  |
| `serviceID`                                                                                                                                          | *string*                                                                                                                                             | :heavy_check_mark:                                                                                                                                   | N/A                                                                                                                                                  |
| `v3ServicesOverlayOptInForKeyBasedDeduplicationRequest`                                                                                              | [components.V3ServicesOverlayOptInForKeyBasedDeduplicationRequest](../../models/components/v3servicesoverlayoptinforkeybaseddeduplicationrequest.md) | :heavy_check_mark:                                                                                                                                   | N/A                                                                                                                                                  |
| `opts`                                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                                             | :heavy_minus_sign:                                                                                                                                   | The options for this request.                                                                                                                        |

### Response

**[*operations.OverlayOptinForKeyBasedDeduplicationForAServiceResponse](../../models/operations/overlayoptinforkeybaseddeduplicationforaserviceresponse.md), error**

### Errors

| Error Type                                                                        | Status Code                                                                       | Content Type                                                                      |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceBadRequestError          | 400                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceUnauthorizedError        | 401                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServicePaymentRequiredError     | 402                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceForbiddenError           | 403                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceNotFoundError            | 404                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceConflictError            | 409                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceUnprocessableEntityError | 422                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceInternalServerError      | 500                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceBadGatewayError          | 502                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceServiceUnavailableError  | 503                                                                               | application/json                                                                  |
| apierrors.OverlayOptinForKeyBasedDeduplicationForAServiceGatewayTimeoutError      | 504                                                                               | application/json                                                                  |
| apierrors.APIError                                                                | 4XX, 5XX                                                                          | \*/\*                                                                             |