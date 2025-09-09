# APIToken
(*Users.APIToken*)

## Overview

### Available Operations

* [Remove](#remove) - Remove Token

## Remove

Removes refresh token of a user from organization. Upon success the refresh token of a user will be removed from the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_removeToken" method="delete" path="/v3/refresh-token/{refreshTokenID}" -->
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

    res, err := s.Users.APIToken.Remove(ctx, "<id>")
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