# ServicesExtensions
(*ServicesExtensions*)

## Overview

### Available Operations

* [ExtensionsUpdateSlackExtension](#extensionsupdateslackextension) - Update Slack Extension

## ExtensionsUpdateSlackExtension

Update Slack Extension

### Example Usage

<!-- UsageSnippet language="go" operationID="Extensions_updateSlackExtension" method="put" path="/v3/services/{serviceID}/extensions" -->
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

    res, err := s.ServicesExtensions.ExtensionsUpdateSlackExtension(ctx, "<id>", components.V3ServicesExtensionsUpdateSlackExtensionRequest{
        ChannelID: "<id>",
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

| Parameter                                                                                                                                | Type                                                                                                                                     | Required                                                                                                                                 | Description                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                                    | :heavy_check_mark:                                                                                                                       | The context to use for the request.                                                                                                      |
| `serviceID`                                                                                                                              | *string*                                                                                                                                 | :heavy_check_mark:                                                                                                                       | N/A                                                                                                                                      |
| `v3ServicesExtensionsUpdateSlackExtensionRequest`                                                                                        | [components.V3ServicesExtensionsUpdateSlackExtensionRequest](../../models/components/v3servicesextensionsupdateslackextensionrequest.md) | :heavy_check_mark:                                                                                                                       | N/A                                                                                                                                      |
| `opts`                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                 | :heavy_minus_sign:                                                                                                                       | The options for this request.                                                                                                            |

### Response

**[*operations.ExtensionsUpdateSlackExtensionResponse](../../models/operations/extensionsupdateslackextensionresponse.md), error**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| apierrors.ExtensionsUpdateSlackExtensionBadRequestError          | 400                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionUnauthorizedError        | 401                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionPaymentRequiredError     | 402                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionForbiddenError           | 403                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionNotFoundError            | 404                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionConflictError            | 409                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionUnprocessableEntityError | 422                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionInternalServerError      | 500                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionBadGatewayError          | 502                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionServiceUnavailableError  | 503                                                              | application/json                                                 |
| apierrors.ExtensionsUpdateSlackExtensionGatewayTimeoutError      | 504                                                              | application/json                                                 |
| apierrors.APIError                                               | 4XX, 5XX                                                         | \*/\*                                                            |