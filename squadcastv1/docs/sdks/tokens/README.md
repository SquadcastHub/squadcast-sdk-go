# Tokens
(*Tokens*)

## Overview

### Available Operations

* [CreateUserToken](#createusertoken) - Create Token

## CreateUserToken

Generates refresh token for a user of the organization. Returns the refresh token object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_createToken" method="post" path="/v3/refresh-token" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Tokens.CreateUserToken(ctx, operations.UsersCreateTokenRequest{
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