# Overrides
(*Overrides*)

## Overview

### Available Operations

* [OverridesListOverrides](#overrideslistoverrides) - List Overrides
* [OverridesCreateScheduleOverride](#overridescreatescheduleoverride) - Create Schedule Override
* [OverridesDeleteScheduleOverride](#overridesdeletescheduleoverride) - Delete Schedule Override
* [OverridesGetOverrideByID](#overridesgetoverridebyid) - Get Override by ID
* [OverridesUpdateScheduleOverride](#overridesupdatescheduleoverride) - Update Schedule Override

## OverridesListOverrides

List Overrides

### Example Usage

<!-- UsageSnippet language="go" operationID="Overrides_listOverrides" method="get" path="/v4/schedules/{scheduleID}/overrides" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Overrides.OverridesListOverrides(ctx, operations.OverridesListOverridesRequest{
        ScheduleID: "<id>",
        StartTime: "<value>",
        EndTime: "<value>",
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

| Parameter                                                                                            | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                | :heavy_check_mark:                                                                                   | The context to use for the request.                                                                  |
| `request`                                                                                            | [operations.OverridesListOverridesRequest](../../models/operations/overrideslistoverridesrequest.md) | :heavy_check_mark:                                                                                   | The request object to use for the request.                                                           |
| `opts`                                                                                               | [][operations.Option](../../models/operations/option.md)                                             | :heavy_minus_sign:                                                                                   | The options for this request.                                                                        |

### Response

**[*operations.OverridesListOverridesResponse](../../models/operations/overrideslistoverridesresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## OverridesCreateScheduleOverride

Create Schedule Override

### Example Usage

<!-- UsageSnippet language="go" operationID="Overrides_createScheduleOverride" method="post" path="/v4/schedules/{scheduleID}/overrides" -->
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

    res, err := s.Overrides.OverridesCreateScheduleOverride(ctx, "<id>", components.V4CreateScheduleOverrideRequest{
        StartTime: "<value>",
        EndTime: "<value>",
        Reason: "<value>",
        OverriddenParticipant: components.V4OverrideParticipantGroup{
            Group: []components.V4Participant{
                components.V4Participant{
                    ID: "<id>",
                    Type: "<value>",
                },
            },
        },
        OverrideWith: components.V4OverrideParticipantGroup{
            Group: []components.V4Participant{
                components.V4Participant{
                    ID: "<id>",
                    Type: "<value>",
                },
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

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                    | :heavy_check_mark:                                                                                       | The context to use for the request.                                                                      |
| `scheduleID`                                                                                             | *string*                                                                                                 | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `v4CreateScheduleOverrideRequest`                                                                        | [components.V4CreateScheduleOverrideRequest](../../models/components/v4createscheduleoverriderequest.md) | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `opts`                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                 | :heavy_minus_sign:                                                                                       | The options for this request.                                                                            |

### Response

**[*operations.OverridesCreateScheduleOverrideResponse](../../models/operations/overridescreatescheduleoverrideresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## OverridesDeleteScheduleOverride

Delete Schedule Override

### Example Usage

<!-- UsageSnippet language="go" operationID="Overrides_deleteScheduleOverride" method="delete" path="/v4/schedules/{scheduleID}/overrides/{overrideID}" -->
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

    res, err := s.Overrides.OverridesDeleteScheduleOverride(ctx, "<id>", "<id>")
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
| `scheduleID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `overrideID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.OverridesDeleteScheduleOverrideResponse](../../models/operations/overridesdeletescheduleoverrideresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## OverridesGetOverrideByID

Get Override by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Overrides_getOverrideById" method="get" path="/v4/schedules/{scheduleID}/overrides/{overrideID}" -->
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

    res, err := s.Overrides.OverridesGetOverrideByID(ctx, "<id>", "<id>")
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
| `scheduleID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `overrideID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.OverridesGetOverrideByIDResponse](../../models/operations/overridesgetoverridebyidresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## OverridesUpdateScheduleOverride

Update Schedule Override

### Example Usage

<!-- UsageSnippet language="go" operationID="Overrides_updateScheduleOverride" method="put" path="/v4/schedules/{scheduleID}/overrides/{overrideID}" -->
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

    res, err := s.Overrides.OverridesUpdateScheduleOverride(ctx, "<id>", "<id>", components.V4UpdateScheduleOverrideRequest{
        StartTime: "<value>",
        EndTime: "<value>",
        Reason: "<value>",
        OverriddenParticipant: components.V4OverrideParticipantGroup{
            Group: []components.V4Participant{
                components.V4Participant{
                    ID: "<id>",
                    Type: "<value>",
                },
            },
        },
        OverrideWith: components.V4OverrideParticipantGroup{
            Group: []components.V4Participant{},
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

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                    | :heavy_check_mark:                                                                                       | The context to use for the request.                                                                      |
| `scheduleID`                                                                                             | *string*                                                                                                 | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `overrideID`                                                                                             | *string*                                                                                                 | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `v4UpdateScheduleOverrideRequest`                                                                        | [components.V4UpdateScheduleOverrideRequest](../../models/components/v4updatescheduleoverriderequest.md) | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `opts`                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                 | :heavy_minus_sign:                                                                                       | The options for this request.                                                                            |

### Response

**[*operations.OverridesUpdateScheduleOverrideResponse](../../models/operations/overridesupdatescheduleoverrideresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |