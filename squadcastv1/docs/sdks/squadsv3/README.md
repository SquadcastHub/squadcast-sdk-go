# SquadsV3
(*SquadsV3*)

## Overview

### Available Operations

* [SquadsGetSquadByTeam](#squadsgetsquadbyteam) - Get Squad By team
* [SquadsCreateSquad](#squadscreatesquad) - Create Squad
* [SquadsDeleteSquad](#squadsdeletesquad) - Delete Squad
* [SquadsGetSquadByID](#squadsgetsquadbyid) - Get Squad By ID
* [SquadsUpdateSquad](#squadsupdatesquad) - Update Squad

## SquadsGetSquadByTeam

This endpoint is used to get the squads details by team.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_getSquadByTeam" method="get" path="/v3/squads" -->
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

    res, err := s.SquadsV3.SquadsGetSquadByTeam(ctx, "<id>")
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
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SquadsGetSquadByTeamResponse](../../models/operations/squadsgetsquadbyteamresponse.md), error**

### Errors

| Error Type                                             | Status Code                                            | Content Type                                           |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| apierrors.SquadsGetSquadByTeamBadRequestError          | 400                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamUnauthorizedError        | 401                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamPaymentRequiredError     | 402                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamForbiddenError           | 403                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamNotFoundError            | 404                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamConflictError            | 409                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamUnprocessableEntityError | 422                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamInternalServerError      | 500                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamBadGatewayError          | 502                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamServiceUnavailableError  | 503                                                    | application/json                                       |
| apierrors.SquadsGetSquadByTeamGatewayTimeoutError      | 504                                                    | application/json                                       |
| apierrors.APIError                                     | 4XX, 5XX                                               | \*/\*                                                  |

## SquadsCreateSquad

This endpoint is used to create a new squad.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-create` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_createSquad" method="post" path="/v3/squads" -->
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

    res, err := s.SquadsV3.SquadsCreateSquad(ctx, components.V3SquadsCreateSquadRequest{
        Name: "<value>",
        Members: []string{
            "<value 1>",
        },
        OwnerID: "<id>",
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

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `request`                                                                                      | [components.V3SquadsCreateSquadRequest](../../models/components/v3squadscreatesquadrequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.SquadsCreateSquadResponse](../../models/operations/squadscreatesquadresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.SquadsCreateSquadBadRequestError          | 400                                                 | application/json                                    |
| apierrors.SquadsCreateSquadUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.SquadsCreateSquadPaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.SquadsCreateSquadForbiddenError           | 403                                                 | application/json                                    |
| apierrors.SquadsCreateSquadNotFoundError            | 404                                                 | application/json                                    |
| apierrors.SquadsCreateSquadConflictError            | 409                                                 | application/json                                    |
| apierrors.SquadsCreateSquadUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.SquadsCreateSquadInternalServerError      | 500                                                 | application/json                                    |
| apierrors.SquadsCreateSquadBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.SquadsCreateSquadServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.SquadsCreateSquadGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

## SquadsDeleteSquad

This endpoint is used to delete the squad. Squad should not be assigned to any incident or part of any escalation policy.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-update` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_deleteSquad" method="delete" path="/v3/squads/{squadID}" -->
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

    res, err := s.SquadsV3.SquadsDeleteSquad(ctx, "<id>")
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
| `squadID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SquadsDeleteSquadResponse](../../models/operations/squadsdeletesquadresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.SquadsDeleteSquadBadRequestError          | 400                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadPaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadForbiddenError           | 403                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadNotFoundError            | 404                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadConflictError            | 409                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadInternalServerError      | 500                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

## SquadsGetSquadByID

This endpoint is used to get the squads details by id.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_getSquadById" method="get" path="/v3/squads/{squadID}" -->
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

    res, err := s.SquadsV3.SquadsGetSquadByID(ctx, "<id>")
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
| `squadID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SquadsGetSquadByIDResponse](../../models/operations/squadsgetsquadbyidresponse.md), error**

### Errors

| Error Type                                           | Status Code                                          | Content Type                                         |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| apierrors.SquadsGetSquadByIDBadRequestError          | 400                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDUnauthorizedError        | 401                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDPaymentRequiredError     | 402                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDForbiddenError           | 403                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDNotFoundError            | 404                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDConflictError            | 409                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDUnprocessableEntityError | 422                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDInternalServerError      | 500                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDBadGatewayError          | 502                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDServiceUnavailableError  | 503                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDGatewayTimeoutError      | 504                                                  | application/json                                     |
| apierrors.APIError                                   | 4XX, 5XX                                             | \*/\*                                                |

## SquadsUpdateSquad

This endpoint is used to update the squads details.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-update` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_updateSquad" method="put" path="/v3/squads/{squadID}" -->
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

    res, err := s.SquadsV3.SquadsUpdateSquad(ctx, "<id>", components.V3SquadsUpdateSquadRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `squadID`                                                                                      | *string*                                                                                       | :heavy_check_mark:                                                                             | N/A                                                                                            |
| `v3SquadsUpdateSquadRequest`                                                                   | [components.V3SquadsUpdateSquadRequest](../../models/components/v3squadsupdatesquadrequest.md) | :heavy_check_mark:                                                                             | N/A                                                                                            |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.SquadsUpdateSquadResponse](../../models/operations/squadsupdatesquadresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.SquadsUpdateSquadBadRequestError          | 400                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadPaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadForbiddenError           | 403                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadNotFoundError            | 404                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadConflictError            | 409                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadInternalServerError      | 500                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |