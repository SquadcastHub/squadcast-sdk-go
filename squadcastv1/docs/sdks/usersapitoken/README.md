# UsersAPIToken
(*UsersAPIToken*)

## Overview

### Available Operations

* [UsersGetAllTokens](#usersgetalltokens) - Get All Tokens
* [UsersCreateToken](#userscreatetoken) - Create Token
* [UsersRemoveToken](#usersremovetoken) - Remove Token

## UsersGetAllTokens

Returns generated api tokens of all the users of the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_getAllTokens" method="get" path="/v3/refresh-token" -->
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

    res, err := s.UsersAPIToken.UsersGetAllTokens(ctx)
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

**[*operations.UsersGetAllTokensResponse](../../models/operations/usersgetalltokensresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.UsersGetAllTokensBadRequestError          | 400                                                 | application/json                                    |
| apierrors.UsersGetAllTokensUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.UsersGetAllTokensPaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.UsersGetAllTokensForbiddenError           | 403                                                 | application/json                                    |
| apierrors.UsersGetAllTokensNotFoundError            | 404                                                 | application/json                                    |
| apierrors.UsersGetAllTokensConflictError            | 409                                                 | application/json                                    |
| apierrors.UsersGetAllTokensUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.UsersGetAllTokensInternalServerError      | 500                                                 | application/json                                    |
| apierrors.UsersGetAllTokensBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.UsersGetAllTokensServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.UsersGetAllTokensGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

## UsersCreateToken

Generates refresh token for a user of the organization. Returns the refresh token object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_createToken" method="post" path="/v3/refresh-token" -->
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

    res, err := s.UsersAPIToken.UsersCreateToken(ctx, operations.UsersCreateTokenRequest{
        UserID: "<id>",
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

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `ctx`                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                    | :heavy_check_mark:                                                                       | The context to use for the request.                                                      |
| `request`                                                                                | [operations.UsersCreateTokenRequest](../../models/operations/userscreatetokenrequest.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |
| `opts`                                                                                   | [][operations.Option](../../models/operations/option.md)                                 | :heavy_minus_sign:                                                                       | The options for this request.                                                            |

### Response

**[*operations.UsersCreateTokenResponse](../../models/operations/userscreatetokenresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.UsersCreateTokenBadRequestError          | 400                                                | application/json                                   |
| apierrors.UsersCreateTokenUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.UsersCreateTokenPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.UsersCreateTokenForbiddenError           | 403                                                | application/json                                   |
| apierrors.UsersCreateTokenNotFoundError            | 404                                                | application/json                                   |
| apierrors.UsersCreateTokenConflictError            | 409                                                | application/json                                   |
| apierrors.UsersCreateTokenUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.UsersCreateTokenInternalServerError      | 500                                                | application/json                                   |
| apierrors.UsersCreateTokenBadGatewayError          | 502                                                | application/json                                   |
| apierrors.UsersCreateTokenServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.UsersCreateTokenGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |

## UsersRemoveToken

Removes refresh token of a user from organization. Upon success the refresh token of a user will be removed from the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_removeToken" method="delete" path="/v3/refresh-token/{refreshTokenID}" -->
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

    res, err := s.UsersAPIToken.UsersRemoveToken(ctx, "<id>")
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
| `refreshTokenID`                                         | *string*                                                 | :heavy_check_mark:                                       | (Required) refresh token id                              |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.UsersRemoveTokenResponse](../../models/operations/usersremovetokenresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.UsersRemoveTokenBadRequestError          | 400                                                | application/json                                   |
| apierrors.UsersRemoveTokenUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.UsersRemoveTokenPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.UsersRemoveTokenForbiddenError           | 403                                                | application/json                                   |
| apierrors.UsersRemoveTokenNotFoundError            | 404                                                | application/json                                   |
| apierrors.UsersRemoveTokenConflictError            | 409                                                | application/json                                   |
| apierrors.UsersRemoveTokenUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.UsersRemoveTokenInternalServerError      | 500                                                | application/json                                   |
| apierrors.UsersRemoveTokenBadGatewayError          | 502                                                | application/json                                   |
| apierrors.UsersRemoveTokenServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.UsersRemoveTokenGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |