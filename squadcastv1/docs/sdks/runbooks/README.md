# Runbooks
(*Runbooks*)

## Overview

### Available Operations

* [RunbooksGetAllRunbooksByTeam](#runbooksgetallrunbooksbyteam) - Get All Runbooks By Team
* [RunbooksCreateRunbook](#runbookscreaterunbook) - Create Runbook
* [RunbooksRemoveRunbook](#runbooksremoverunbook) - Remove Runbook
* [RunbooksGetRunbookByID](#runbooksgetrunbookbyid) - Get Runbook By ID
* [RunbooksUpdateRunbook](#runbooksupdaterunbook) - Update Runbook

## RunbooksGetAllRunbooksByTeam

Returns all the runbooks of the team.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Runbooks_getAllRunbooksByTeam" method="get" path="/v3/runbooks" -->
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

    res, err := s.Runbooks.RunbooksGetAllRunbooksByTeam(ctx)
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
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.RunbooksGetAllRunbooksByTeamResponse](../../models/operations/runbooksgetallrunbooksbyteamresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.RunbooksGetAllRunbooksByTeamBadRequestError          | 400                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamForbiddenError           | 403                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamNotFoundError            | 404                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamConflictError            | 409                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamInternalServerError      | 500                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.RunbooksGetAllRunbooksByTeamGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## RunbooksCreateRunbook

Add runbook to the team. Returns the runbook object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Runbooks_createRunbook" method="post" path="/v3/runbooks" -->
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

    res, err := s.Runbooks.RunbooksCreateRunbook(ctx, components.V3RunbooksCreateRunbookRequest{
        Name: "<value>",
        Steps: []components.V3RunbooksStep{
            components.V3RunbooksStep{
                Content: "<value>",
            },
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

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `request`                                                                                              | [components.V3RunbooksCreateRunbookRequest](../../models/components/v3runbookscreaterunbookrequest.md) | :heavy_check_mark:                                                                                     | The request object to use for the request.                                                             |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.RunbooksCreateRunbookResponse](../../models/operations/runbookscreaterunbookresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.RunbooksCreateRunbookBadRequestError          | 400                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookForbiddenError           | 403                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookNotFoundError            | 404                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookConflictError            | 409                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookInternalServerError      | 500                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.RunbooksCreateRunbookGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## RunbooksRemoveRunbook

Remove runbook from team.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Runbooks_removeRunbook" method="delete" path="/v3/runbooks/{runbookID}" -->
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

    res, err := s.Runbooks.RunbooksRemoveRunbook(ctx, "<id>")
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
| `runbookID`                                              | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.RunbooksRemoveRunbookResponse](../../models/operations/runbooksremoverunbookresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.RunbooksRemoveRunbookBadRequestError          | 400                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookForbiddenError           | 403                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookNotFoundError            | 404                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookConflictError            | 409                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookInternalServerError      | 500                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.RunbooksRemoveRunbookGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## RunbooksGetRunbookByID

Returns a runbook details of the given `runbookID` in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Runbooks_getRunbookById" method="get" path="/v3/runbooks/{runbookID}" -->
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

    res, err := s.Runbooks.RunbooksGetRunbookByID(ctx, "<id>")
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
| `runbookID`                                              | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.RunbooksGetRunbookByIDResponse](../../models/operations/runbooksgetrunbookbyidresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.RunbooksGetRunbookByIDBadRequestError          | 400                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDForbiddenError           | 403                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDNotFoundError            | 404                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDConflictError            | 409                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDInternalServerError      | 500                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.RunbooksGetRunbookByIDGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## RunbooksUpdateRunbook

Update runbook details.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Runbooks_updateRunbook" method="put" path="/v3/runbooks/{runbookID}" -->
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

    res, err := s.Runbooks.RunbooksUpdateRunbook(ctx, "<id>", components.V3RunbooksUpdateRunbookRequest{
        Name: "<value>",
        Steps: []components.V3RunbooksStep{
            components.V3RunbooksStep{
                Content: "<value>",
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

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `runbookID`                                                                                            | *string*                                                                                               | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `v3RunbooksUpdateRunbookRequest`                                                                       | [components.V3RunbooksUpdateRunbookRequest](../../models/components/v3runbooksupdaterunbookrequest.md) | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.RunbooksUpdateRunbookResponse](../../models/operations/runbooksupdaterunbookresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.RunbooksUpdateRunbookBadRequestError          | 400                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookForbiddenError           | 403                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookNotFoundError            | 404                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookConflictError            | 409                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookInternalServerError      | 500                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.RunbooksUpdateRunbookGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |