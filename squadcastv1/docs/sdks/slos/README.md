# SLOs
(*SLOs*)

## Overview

### Available Operations

* [SLOGetAllSLOs](#slogetallslos) - Get All SLOs
* [SLOCreateSLO](#slocreateslo) - Create SLO
* [SLOUpdateSLO](#sloupdateslo) - Update SLO
* [SLORemoveSLO](#sloremoveslo) - Remove SLO
* [SLOGetSLOByID](#slogetslobyid) - Get SLO By ID
* [SLOMarkSLOAffected](#slomarksloaffected) - Mark SLO Affected
* [SLOMarkSLOFalsePositive](#slomarkslofalsepositive) - Mark SLO False Positive

## SLOGetAllSLOs

Returns all the SLOs of the passed owner_id in the params.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="SLO_getAllSLOs" method="get" path="/v3/slo" -->
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

    res, err := s.SLOs.SLOGetAllSLOs(ctx, "<id>", "<value>", "<value>")
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
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `offset`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `limit`                                                  | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SLOGetAllSLOsResponse](../../models/operations/slogetallslosresponse.md), error**

### Errors

| Error Type                                      | Status Code                                     | Content Type                                    |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| apierrors.SLOGetAllSLOsBadRequestError          | 400                                             | application/json                                |
| apierrors.SLOGetAllSLOsUnauthorizedError        | 401                                             | application/json                                |
| apierrors.SLOGetAllSLOsPaymentRequiredError     | 402                                             | application/json                                |
| apierrors.SLOGetAllSLOsForbiddenError           | 403                                             | application/json                                |
| apierrors.SLOGetAllSLOsNotFoundError            | 404                                             | application/json                                |
| apierrors.SLOGetAllSLOsConflictError            | 409                                             | application/json                                |
| apierrors.SLOGetAllSLOsUnprocessableEntityError | 422                                             | application/json                                |
| apierrors.SLOGetAllSLOsInternalServerError      | 500                                             | application/json                                |
| apierrors.SLOGetAllSLOsBadGatewayError          | 502                                             | application/json                                |
| apierrors.SLOGetAllSLOsServiceUnavailableError  | 503                                             | application/json                                |
| apierrors.SLOGetAllSLOsGatewayTimeoutError      | 504                                             | application/json                                |
| apierrors.APIError                              | 4XX, 5XX                                        | \*/\*                                           |

## SLOCreateSLO

- This API will create SLO.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="SLO_createSLO" method="post" path="/v3/slo" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"github.com/SquadcastHub/squadcast-sdk-go/types"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.SLOs.SLOCreateSLO(ctx, components.V3SLOCreateSLORequest{
        Name: "<value>",
        TimeIntervalType: components.V3SLOTimeIntervalTypeRolling,
        ServiceIds: []string{
            "<value 1>",
        },
        Slis: []string{},
        TargetSlo: 6924.37,
        StartTime: types.MustTimeFromString("2023-06-03T10:41:05.981Z"),
        EndTime: types.MustTimeFromString("2023-11-20T07:09:22.422Z"),
        DurationInDays: 574042,
        OwnerType: "<value>",
        OwnerID: "<id>",
        SloOwnerID: "<id>",
        SloOwnerType: components.V3SLOSLOOwnerTypeSquad,
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

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `request`                                                                            | [components.V3SLOCreateSLORequest](../../models/components/v3slocreateslorequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.SLOCreateSLOResponse](../../models/operations/slocreatesloresponse.md), error**

### Errors

| Error Type                                     | Status Code                                    | Content Type                                   |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| apierrors.SLOCreateSLOBadRequestError          | 400                                            | application/json                               |
| apierrors.SLOCreateSLOUnauthorizedError        | 401                                            | application/json                               |
| apierrors.SLOCreateSLOPaymentRequiredError     | 402                                            | application/json                               |
| apierrors.SLOCreateSLOForbiddenError           | 403                                            | application/json                               |
| apierrors.SLOCreateSLONotFoundError            | 404                                            | application/json                               |
| apierrors.SLOCreateSLOConflictError            | 409                                            | application/json                               |
| apierrors.SLOCreateSLOUnprocessableEntityError | 422                                            | application/json                               |
| apierrors.SLOCreateSLOInternalServerError      | 500                                            | application/json                               |
| apierrors.SLOCreateSLOBadGatewayError          | 502                                            | application/json                               |
| apierrors.SLOCreateSLOServiceUnavailableError  | 503                                            | application/json                               |
| apierrors.SLOCreateSLOGatewayTimeoutError      | 504                                            | application/json                               |
| apierrors.APIError                             | 4XX, 5XX                                       | \*/\*                                          |

## SLOUpdateSLO

- This API will update SLO.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="SLO_updateSLO" method="put" path="/v3/slo/{sloID}" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"github.com/SquadcastHub/squadcast-sdk-go/types"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.SLOs.SLOUpdateSLO(ctx, 16112, "<id>", components.V3SLOCreateSLORequest{
        Name: "<value>",
        TimeIntervalType: components.V3SLOTimeIntervalTypeRolling,
        ServiceIds: []string{
            "<value 1>",
            "<value 2>",
            "<value 3>",
        },
        Slis: []string{
            "<value 1>",
        },
        TargetSlo: 2464.03,
        StartTime: types.MustTimeFromString("2025-10-31T03:29:37.701Z"),
        EndTime: types.MustTimeFromString("2024-03-30T19:04:36.297Z"),
        DurationInDays: 271064,
        OwnerType: "<value>",
        OwnerID: "<id>",
        SloOwnerID: "<id>",
        SloOwnerType: components.V3SLOSLOOwnerTypeUser,
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

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `sloID`                                                                              | *int64*                                                                              | :heavy_check_mark:                                                                   | N/A                                                                                  |
| `ownerID`                                                                            | *string*                                                                             | :heavy_check_mark:                                                                   | N/A                                                                                  |
| `v3SLOCreateSLORequest`                                                              | [components.V3SLOCreateSLORequest](../../models/components/v3slocreateslorequest.md) | :heavy_check_mark:                                                                   | N/A                                                                                  |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.SLOUpdateSLOResponse](../../models/operations/sloupdatesloresponse.md), error**

### Errors

| Error Type                                     | Status Code                                    | Content Type                                   |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| apierrors.SLOUpdateSLOBadRequestError          | 400                                            | application/json                               |
| apierrors.SLOUpdateSLOUnauthorizedError        | 401                                            | application/json                               |
| apierrors.SLOUpdateSLOPaymentRequiredError     | 402                                            | application/json                               |
| apierrors.SLOUpdateSLOForbiddenError           | 403                                            | application/json                               |
| apierrors.SLOUpdateSLONotFoundError            | 404                                            | application/json                               |
| apierrors.SLOUpdateSLOConflictError            | 409                                            | application/json                               |
| apierrors.SLOUpdateSLOUnprocessableEntityError | 422                                            | application/json                               |
| apierrors.SLOUpdateSLOInternalServerError      | 500                                            | application/json                               |
| apierrors.SLOUpdateSLOBadGatewayError          | 502                                            | application/json                               |
| apierrors.SLOUpdateSLOServiceUnavailableError  | 503                                            | application/json                               |
| apierrors.SLOUpdateSLOGatewayTimeoutError      | 504                                            | application/json                               |
| apierrors.APIError                             | 4XX, 5XX                                       | \*/\*                                          |

## SLORemoveSLO

Remove SLO from passed owner_id (team_id) in the params . Upon sccess the slo will be removed.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="SLO_removeSLO" method="delete" path="/v3/slo/{sloID}" -->
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

    res, err := s.SLOs.SLORemoveSLO(ctx, 938544, "<id>")
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
| `sloID`                                                  | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SLORemoveSLOResponse](../../models/operations/sloremovesloresponse.md), error**

### Errors

| Error Type                                     | Status Code                                    | Content Type                                   |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| apierrors.SLORemoveSLOBadRequestError          | 400                                            | application/json                               |
| apierrors.SLORemoveSLOUnauthorizedError        | 401                                            | application/json                               |
| apierrors.SLORemoveSLOPaymentRequiredError     | 402                                            | application/json                               |
| apierrors.SLORemoveSLOForbiddenError           | 403                                            | application/json                               |
| apierrors.SLORemoveSLONotFoundError            | 404                                            | application/json                               |
| apierrors.SLORemoveSLOConflictError            | 409                                            | application/json                               |
| apierrors.SLORemoveSLOUnprocessableEntityError | 422                                            | application/json                               |
| apierrors.SLORemoveSLOInternalServerError      | 500                                            | application/json                               |
| apierrors.SLORemoveSLOBadGatewayError          | 502                                            | application/json                               |
| apierrors.SLORemoveSLOServiceUnavailableError  | 503                                            | application/json                               |
| apierrors.SLORemoveSLOGatewayTimeoutError      | 504                                            | application/json                               |
| apierrors.APIError                             | 4XX, 5XX                                       | \*/\*                                          |

## SLOGetSLOByID

Returns a SLO details of the given `sloID` in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="SLO_getSLOById" method="get" path="/v3/slo/{sloID}" -->
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

    res, err := s.SLOs.SLOGetSLOByID(ctx, 586718, "<id>")
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
| `sloID`                                                  | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SLOGetSLOByIDResponse](../../models/operations/slogetslobyidresponse.md), error**

### Errors

| Error Type                                      | Status Code                                     | Content Type                                    |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| apierrors.SLOGetSLOByIDBadRequestError          | 400                                             | application/json                                |
| apierrors.SLOGetSLOByIDUnauthorizedError        | 401                                             | application/json                                |
| apierrors.SLOGetSLOByIDPaymentRequiredError     | 402                                             | application/json                                |
| apierrors.SLOGetSLOByIDForbiddenError           | 403                                             | application/json                                |
| apierrors.SLOGetSLOByIDNotFoundError            | 404                                             | application/json                                |
| apierrors.SLOGetSLOByIDConflictError            | 409                                             | application/json                                |
| apierrors.SLOGetSLOByIDUnprocessableEntityError | 422                                             | application/json                                |
| apierrors.SLOGetSLOByIDInternalServerError      | 500                                             | application/json                                |
| apierrors.SLOGetSLOByIDBadGatewayError          | 502                                             | application/json                                |
| apierrors.SLOGetSLOByIDServiceUnavailableError  | 503                                             | application/json                                |
| apierrors.SLOGetSLOByIDGatewayTimeoutError      | 504                                             | application/json                                |
| apierrors.APIError                              | 4XX, 5XX                                        | \*/\*                                           |

## SLOMarkSLOAffected

This endpoint is used for mark slo affected.

Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="SLO_markSLOAffected" method="post" path="/v3/slo/{sloID}/incident" -->
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

    res, err := s.SLOs.SLOMarkSLOAffected(ctx, 294670, "<id>", components.V3SLOMarkSLOAffectedRequest{
        IncidentID: "<id>",
        Slis: []string{
            "<value 1>",
            "<value 2>",
        },
        ErrorBudgetSpent: 3480.26,
        OwnerType: "<value>",
        OwnerID: "<id>",
        OrgID: "<id>",
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

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `sloID`                                                                                          | *int64*                                                                                          | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `ownerID`                                                                                        | *string*                                                                                         | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `v3SLOMarkSLOAffectedRequest`                                                                    | [components.V3SLOMarkSLOAffectedRequest](../../models/components/v3slomarksloaffectedrequest.md) | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `opts`                                                                                           | [][operations.Option](../../models/operations/option.md)                                         | :heavy_minus_sign:                                                                               | The options for this request.                                                                    |

### Response

**[*operations.SLOMarkSLOAffectedResponse](../../models/operations/slomarksloaffectedresponse.md), error**

### Errors

| Error Type                                           | Status Code                                          | Content Type                                         |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| apierrors.SLOMarkSLOAffectedBadRequestError          | 400                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedUnauthorizedError        | 401                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedPaymentRequiredError     | 402                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedForbiddenError           | 403                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedNotFoundError            | 404                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedConflictError            | 409                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedUnprocessableEntityError | 422                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedInternalServerError      | 500                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedBadGatewayError          | 502                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedServiceUnavailableError  | 503                                                  | application/json                                     |
| apierrors.SLOMarkSLOAffectedGatewayTimeoutError      | 504                                                  | application/json                                     |
| apierrors.APIError                                   | 4XX, 5XX                                             | \*/\*                                                |

## SLOMarkSLOFalsePositive

Value is a boolean (true or false)

### Example Usage

<!-- UsageSnippet language="go" operationID="SLO_markSLOFalsePositive" method="patch" path="/v3/slo/{sloID}/incident/{incidentID}/false-positive/{value}" -->
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

    res, err := s.SLOs.SLOMarkSLOFalsePositive(ctx, operations.SLOMarkSLOFalsePositiveRequest{
        SloID: 825843,
        IncidentID: 505067,
        Value: true,
        OwnerID: "<id>",
        RequestBody: operations.SLOMarkSLOFalsePositiveRequestBody{},
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

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `request`                                                                                              | [operations.SLOMarkSLOFalsePositiveRequest](../../models/operations/slomarkslofalsepositiverequest.md) | :heavy_check_mark:                                                                                     | The request object to use for the request.                                                             |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.SLOMarkSLOFalsePositiveResponse](../../models/operations/slomarkslofalsepositiveresponse.md), error**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| apierrors.SLOMarkSLOFalsePositiveBadRequestError          | 400                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveUnauthorizedError        | 401                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositivePaymentRequiredError     | 402                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveForbiddenError           | 403                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveNotFoundError            | 404                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveConflictError            | 409                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveUnprocessableEntityError | 422                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveInternalServerError      | 500                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveBadGatewayError          | 502                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveServiceUnavailableError  | 503                                                       | application/json                                          |
| apierrors.SLOMarkSLOFalsePositiveGatewayTimeoutError      | 504                                                       | application/json                                          |
| apierrors.APIError                                        | 4XX, 5XX                                                  | \*/\*                                                     |