# ScheduleExportSchedule
(*ScheduleExportSchedule*)

## Overview

### Available Operations

* [ExportDeleteIcalLink](#exportdeleteicallink) - Delete ICal Link
* [ExportGetScheduleIcalLink](#exportgetscheduleicallink) - Get Schedule ICal Link
* [ExportRefreshScheduleIcalLink](#exportrefreshscheduleicallink) - Refresh Schedule ICal Link
* [ExportCreateScheduleIcalLink](#exportcreatescheduleicallink) - Create Schedule ICal Link

## ExportDeleteIcalLink

Delete ICal Link

### Example Usage

<!-- UsageSnippet language="go" operationID="Export_deleteIcalLink" method="delete" path="/v4/schedules/{scheduleID}/ical-link" -->
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

    res, err := s.ScheduleExportSchedule.ExportDeleteIcalLink(ctx, "<id>", true)
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
| `myOnCall`                                               | *bool*                                                   | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ExportDeleteIcalLinkResponse](../../models/operations/exportdeleteicallinkresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## ExportGetScheduleIcalLink

Get Schedule ICal Link

### Example Usage

<!-- UsageSnippet language="go" operationID="Export_getScheduleIcalLink" method="get" path="/v4/schedules/{scheduleID}/ical-link" -->
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

    res, err := s.ScheduleExportSchedule.ExportGetScheduleIcalLink(ctx, "<id>", false)
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
| `myOnCall`                                               | *bool*                                                   | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ExportGetScheduleIcalLinkResponse](../../models/operations/exportgetscheduleicallinkresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## ExportRefreshScheduleIcalLink

Refresh Schedule ICal Link

### Example Usage

<!-- UsageSnippet language="go" operationID="Export_refreshScheduleIcalLink" method="patch" path="/v4/schedules/{scheduleID}/ical-link" -->
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

    res, err := s.ScheduleExportSchedule.ExportRefreshScheduleIcalLink(ctx, "<id>", true, operations.ExportRefreshScheduleIcalLinkRequestBody{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                  | Type                                                                                                                       | Required                                                                                                                   | Description                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                                                      | :heavy_check_mark:                                                                                                         | The context to use for the request.                                                                                        |
| `scheduleID`                                                                                                               | *string*                                                                                                                   | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `myOnCall`                                                                                                                 | *bool*                                                                                                                     | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `requestBody`                                                                                                              | [operations.ExportRefreshScheduleIcalLinkRequestBody](../../models/operations/exportrefreshscheduleicallinkrequestbody.md) | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `opts`                                                                                                                     | [][operations.Option](../../models/operations/option.md)                                                                   | :heavy_minus_sign:                                                                                                         | The options for this request.                                                                                              |

### Response

**[*operations.ExportRefreshScheduleIcalLinkResponse](../../models/operations/exportrefreshscheduleicallinkresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## ExportCreateScheduleIcalLink

Create Schedule ICal Link

### Example Usage

<!-- UsageSnippet language="go" operationID="Export_createScheduleIcalLink" method="post" path="/v4/schedules/{scheduleID}/ical-link" -->
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

    res, err := s.ScheduleExportSchedule.ExportCreateScheduleIcalLink(ctx, "<id>", true, operations.ExportCreateScheduleIcalLinkRequestBody{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                | Type                                                                                                                     | Required                                                                                                                 | Description                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                    | :heavy_check_mark:                                                                                                       | The context to use for the request.                                                                                      |
| `scheduleID`                                                                                                             | *string*                                                                                                                 | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `myOnCall`                                                                                                               | *bool*                                                                                                                   | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `requestBody`                                                                                                            | [operations.ExportCreateScheduleIcalLinkRequestBody](../../models/operations/exportcreatescheduleicallinkrequestbody.md) | :heavy_check_mark:                                                                                                       | N/A                                                                                                                      |
| `opts`                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                 | :heavy_minus_sign:                                                                                                       | The options for this request.                                                                                            |

### Response

**[*operations.ExportCreateScheduleIcalLinkResponse](../../models/operations/exportcreatescheduleicallinkresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |