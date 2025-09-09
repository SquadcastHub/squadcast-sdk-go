# MaintenanceMode
(*Services.MaintenanceMode*)

## Overview

### Available Operations

* [Get](#get) - Get Maintenance Mode
* [CreateOrUpdate](#createorupdate) - Create or Update Maintenance Mode

## Get

Get Maintenance Mode

### Example Usage

<!-- UsageSnippet language="go" operationID="MaintenanceMode_getMaintenanceMode" method="get" path="/v3/services/{serviceID}/maintenance" -->
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

    res, err := s.Services.MaintenanceMode.Get(ctx, "<id>")
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

**[*operations.MaintenanceModeGetMaintenanceModeResponse](../../models/operations/maintenancemodegetmaintenancemoderesponse.md), error**

### Errors

| Error Type                                                          | Status Code                                                         | Content Type                                                        |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| apierrors.MaintenanceModeGetMaintenanceModeBadRequestError          | 400                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeUnauthorizedError        | 401                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModePaymentRequiredError     | 402                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeForbiddenError           | 403                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeNotFoundError            | 404                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeConflictError            | 409                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeUnprocessableEntityError | 422                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeInternalServerError      | 500                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeBadGatewayError          | 502                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeServiceUnavailableError  | 503                                                                 | application/json                                                    |
| apierrors.MaintenanceModeGetMaintenanceModeGatewayTimeoutError      | 504                                                                 | application/json                                                    |
| apierrors.APIError                                                  | 4XX, 5XX                                                            | \*/\*                                                               |

## CreateOrUpdate

Create or Update Maintenance Mode

### Example Usage

<!-- UsageSnippet language="go" operationID="MaintenanceMode_createOrUpdateMaintenanceMode" method="post" path="/v3/services/{serviceID}/maintenance" -->
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

    res, err := s.Services.MaintenanceMode.CreateOrUpdate(ctx, "<id>", components.V3ServicesMaintenanceModeCreateOrUpdateMaintenanceModeRequest{
        OnMaintenance: true,
        ServiceMaintenance: []components.V3ServicesMaintenanceModeServiceMaintenance{
            components.V3ServicesMaintenanceModeServiceMaintenance{
                MaintenanceStartDate: "<value>",
                Daily: false,
                Weekly: true,
                TwoWeekly: false,
                ThreeWeekly: true,
                Monthly: true,
                Deleted: false,
                RepeatTill: "<value>",
            },
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

| Parameter                                                                                                                                                            | Type                                                                                                                                                                 | Required                                                                                                                                                             | Description                                                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                                                | :heavy_check_mark:                                                                                                                                                   | The context to use for the request.                                                                                                                                  |
| `serviceID`                                                                                                                                                          | *string*                                                                                                                                                             | :heavy_check_mark:                                                                                                                                                   | N/A                                                                                                                                                                  |
| `v3ServicesMaintenanceModeCreateOrUpdateMaintenanceModeRequest`                                                                                                      | [components.V3ServicesMaintenanceModeCreateOrUpdateMaintenanceModeRequest](../../models/components/v3servicesmaintenancemodecreateorupdatemaintenancemoderequest.md) | :heavy_check_mark:                                                                                                                                                   | N/A                                                                                                                                                                  |
| `opts`                                                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                                                             | :heavy_minus_sign:                                                                                                                                                   | The options for this request.                                                                                                                                        |

### Response

**[*operations.MaintenanceModeCreateOrUpdateMaintenanceModeResponse](../../models/operations/maintenancemodecreateorupdatemaintenancemoderesponse.md), error**

### Errors

| Error Type                                                                     | Status Code                                                                    | Content Type                                                                   |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeBadRequestError          | 400                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeUnauthorizedError        | 401                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModePaymentRequiredError     | 402                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeForbiddenError           | 403                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeNotFoundError            | 404                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeConflictError            | 409                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeUnprocessableEntityError | 422                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeInternalServerError      | 500                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeBadGatewayError          | 502                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeServiceUnavailableError  | 503                                                                            | application/json                                                               |
| apierrors.MaintenanceModeCreateOrUpdateMaintenanceModeGatewayTimeoutError      | 504                                                                            | application/json                                                               |
| apierrors.APIError                                                             | 4XX, 5XX                                                                       | \*/\*                                                                          |