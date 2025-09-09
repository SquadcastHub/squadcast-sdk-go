# APITokens
(*APITokens*)

## Overview

### Available Operations

* [List](#list) - Get All Tokens

## List

Returns generated api tokens of all the users of the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_getAllTokens" method="get" path="/v3/refresh-token" -->
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

    res, err := s.APITokens.List(ctx)
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