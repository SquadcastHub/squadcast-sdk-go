# Export
(*Export*)

## Overview

### Available Operations

* [ExportGetExportDetails](#exportgetexportdetails) - Get Export Details

## ExportGetExportDetails

Get Export Details

### Example Usage

<!-- UsageSnippet language="go" operationID="Export_getExportDetails" method="get" path="/v3/exports/{export_id}" -->
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

    res, err := s.Export.ExportGetExportDetails(ctx, "<id>")
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
| `exportID`                                               | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ExportGetExportDetailsResponse](../../models/operations/exportgetexportdetailsresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.ExportGetExportDetailsBadRequestError          | 400                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsForbiddenError           | 403                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsNotFoundError            | 404                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsConflictError            | 409                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsInternalServerError      | 500                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.ExportGetExportDetailsGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |