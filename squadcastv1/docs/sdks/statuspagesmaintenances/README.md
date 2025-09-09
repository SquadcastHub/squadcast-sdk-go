# StatusPagesMaintenances
(*StatusPagesMaintenances*)

## Overview

### Available Operations

* [MaintenancesListMaintenances](#maintenanceslistmaintenances) - List Maintenances
* [MaintenancesCreateMaintenance](#maintenancescreatemaintenance) - Create Maintenance
* [MaintenancesDeleteMaintenanceByID](#maintenancesdeletemaintenancebyid) - Delete Maintenance By ID
* [MaintenancesGetMaintenanceByID](#maintenancesgetmaintenancebyid) - Get Maintenance By ID
* [MaintenancesUpdateMaintenanceByID](#maintenancesupdatemaintenancebyid) - Update Maintenance By ID

## MaintenancesListMaintenances

List Maintenances

### Example Usage

<!-- UsageSnippet language="go" operationID="Maintenances_listMaintenances" method="get" path="/v4/statuspages/{statuspageID}/maintenance" -->
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

    res, err := s.StatusPagesMaintenances.MaintenancesListMaintenances(ctx, "<id>", "<value>", "<value>")
    if err != nil {
        log.Fatal(err)
    }
    if res.V4StatusPagesMaintenancesListMaintenancesResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `statuspageID`                                           | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `startTime`                                              | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `endTime`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.MaintenancesListMaintenancesResponse](../../models/operations/maintenanceslistmaintenancesresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.MaintenancesListMaintenancesBadRequestError          | 400                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesForbiddenError           | 403                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesNotFoundError            | 404                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesConflictError            | 409                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesInternalServerError      | 500                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## MaintenancesCreateMaintenance

Create Maintenance

### Example Usage

<!-- UsageSnippet language="go" operationID="Maintenances_createMaintenance" method="post" path="/v4/statuspages/{statuspageID}/maintenance" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/types"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.StatusPagesMaintenances.MaintenancesCreateMaintenance(ctx, "<id>", components.V4StatusPagesMaintenancesCreateMaintenanceRequest{
        Title: "<value>",
        Note: "<value>",
        Components: []int64{
            191583,
            227211,
            362920,
        },
        StartTime: types.MustTimeFromString("2024-08-24T09:07:30.992Z"),
        EndTime: types.MustTimeFromString("2024-04-27T16:39:01.283Z"),
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

| Parameter                                                                                                                                    | Type                                                                                                                                         | Required                                                                                                                                     | Description                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                                                        | :heavy_check_mark:                                                                                                                           | The context to use for the request.                                                                                                          |
| `statuspageID`                                                                                                                               | *string*                                                                                                                                     | :heavy_check_mark:                                                                                                                           | N/A                                                                                                                                          |
| `v4StatusPagesMaintenancesCreateMaintenanceRequest`                                                                                          | [components.V4StatusPagesMaintenancesCreateMaintenanceRequest](../../models/components/v4statuspagesmaintenancescreatemaintenancerequest.md) | :heavy_check_mark:                                                                                                                           | N/A                                                                                                                                          |
| `opts`                                                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                                                     | :heavy_minus_sign:                                                                                                                           | The options for this request.                                                                                                                |

### Response

**[*operations.MaintenancesCreateMaintenanceResponse](../../models/operations/maintenancescreatemaintenanceresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.MaintenancesCreateMaintenanceBadRequestError          | 400                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenancePaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceForbiddenError           | 403                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceNotFoundError            | 404                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceConflictError            | 409                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceInternalServerError      | 500                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.MaintenancesCreateMaintenanceGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## MaintenancesDeleteMaintenanceByID

Delete Maintenance By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Maintenances_deleteMaintenanceById" method="delete" path="/v4/statuspages/{statuspageID}/maintenance/{maintenance_id}" -->
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

    res, err := s.StatusPagesMaintenances.MaintenancesDeleteMaintenanceByID(ctx, "<id>", "<id>")
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
| `statuspageID`                                           | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `maintenanceID`                                          | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.MaintenancesDeleteMaintenanceByIDResponse](../../models/operations/maintenancesdeletemaintenancebyidresponse.md), error**

### Errors

| Error Type                                                          | Status Code                                                         | Content Type                                                        |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| apierrors.MaintenancesDeleteMaintenanceByIDBadRequestError          | 400                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDUnauthorizedError        | 401                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDPaymentRequiredError     | 402                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDForbiddenError           | 403                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDNotFoundError            | 404                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDConflictError            | 409                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDUnprocessableEntityError | 422                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDInternalServerError      | 500                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDBadGatewayError          | 502                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDServiceUnavailableError  | 503                                                                 | application/json                                                    |
| apierrors.MaintenancesDeleteMaintenanceByIDGatewayTimeoutError      | 504                                                                 | application/json                                                    |
| apierrors.APIError                                                  | 4XX, 5XX                                                            | \*/\*                                                               |

## MaintenancesGetMaintenanceByID

Get Maintenance By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Maintenances_getMaintenanceById" method="get" path="/v4/statuspages/{statuspageID}/maintenance/{maintenance_id}" -->
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

    res, err := s.StatusPagesMaintenances.MaintenancesGetMaintenanceByID(ctx, "<id>", "<id>")
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
| `statuspageID`                                           | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `maintenanceID`                                          | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.MaintenancesGetMaintenanceByIDResponse](../../models/operations/maintenancesgetmaintenancebyidresponse.md), error**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| apierrors.MaintenancesGetMaintenanceByIDBadRequestError          | 400                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDUnauthorizedError        | 401                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDPaymentRequiredError     | 402                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDForbiddenError           | 403                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDNotFoundError            | 404                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDConflictError            | 409                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDUnprocessableEntityError | 422                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDInternalServerError      | 500                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDBadGatewayError          | 502                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDServiceUnavailableError  | 503                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDGatewayTimeoutError      | 504                                                              | application/json                                                 |
| apierrors.APIError                                               | 4XX, 5XX                                                         | \*/\*                                                            |

## MaintenancesUpdateMaintenanceByID

Update Maintenance By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Maintenances_updateMaintenanceById" method="put" path="/v4/statuspages/{statuspageID}/maintenance/{maintenance_id}" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/types"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.StatusPagesMaintenances.MaintenancesUpdateMaintenanceByID(ctx, "<id>", "<id>", components.V4StatusPagesMaintenancesUpdateMaintenanceByIDRequest{
        Title: "<value>",
        Note: "<value>",
        StartTime: types.MustTimeFromString("2024-07-22T17:12:15.919Z"),
        EndTime: types.MustTimeFromString("2024-06-11T21:00:35.262Z"),
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

| Parameter                                                                                                                                            | Type                                                                                                                                                 | Required                                                                                                                                             | Description                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                                | :heavy_check_mark:                                                                                                                                   | The context to use for the request.                                                                                                                  |
| `statuspageID`                                                                                                                                       | *string*                                                                                                                                             | :heavy_check_mark:                                                                                                                                   | N/A                                                                                                                                                  |
| `maintenanceID`                                                                                                                                      | *string*                                                                                                                                             | :heavy_check_mark:                                                                                                                                   | N/A                                                                                                                                                  |
| `v4StatusPagesMaintenancesUpdateMaintenanceByIDRequest`                                                                                              | [components.V4StatusPagesMaintenancesUpdateMaintenanceByIDRequest](../../models/components/v4statuspagesmaintenancesupdatemaintenancebyidrequest.md) | :heavy_check_mark:                                                                                                                                   | N/A                                                                                                                                                  |
| `opts`                                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                                             | :heavy_minus_sign:                                                                                                                                   | The options for this request.                                                                                                                        |

### Response

**[*operations.MaintenancesUpdateMaintenanceByIDResponse](../../models/operations/maintenancesupdatemaintenancebyidresponse.md), error**

### Errors

| Error Type                                                          | Status Code                                                         | Content Type                                                        |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| apierrors.MaintenancesUpdateMaintenanceByIDBadRequestError          | 400                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDUnauthorizedError        | 401                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDPaymentRequiredError     | 402                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDForbiddenError           | 403                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDNotFoundError            | 404                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDConflictError            | 409                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDUnprocessableEntityError | 422                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDInternalServerError      | 500                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDBadGatewayError          | 502                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDServiceUnavailableError  | 503                                                                 | application/json                                                    |
| apierrors.MaintenancesUpdateMaintenanceByIDGatewayTimeoutError      | 504                                                                 | application/json                                                    |
| apierrors.APIError                                                  | 4XX, 5XX                                                            | \*/\*                                                               |