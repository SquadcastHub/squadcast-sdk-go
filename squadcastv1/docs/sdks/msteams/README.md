# Msteams
(*Msteams*)

## Overview

### Available Operations

* [GetConfig](#getconfig) - Get MSTeams Config

## GetConfig

Returns MSTeams config of the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="MSTeams_getMsteamsConfig" method="get" path="/v3/extensions/msteams/config" -->
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

    res, err := s.Msteams.GetConfig(ctx)
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

**[*operations.MSTeamsGetMsteamsConfigResponse](../../models/operations/msteamsgetmsteamsconfigresponse.md), error**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| apierrors.MSTeamsGetMsteamsConfigBadRequestError          | 400                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigUnauthorizedError        | 401                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigPaymentRequiredError     | 402                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigForbiddenError           | 403                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigNotFoundError            | 404                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigConflictError            | 409                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigUnprocessableEntityError | 422                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigInternalServerError      | 500                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigBadGatewayError          | 502                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigServiceUnavailableError  | 503                                                       | application/json                                          |
| apierrors.MSTeamsGetMsteamsConfigGatewayTimeoutError      | 504                                                       | application/json                                          |
| apierrors.APIError                                        | 4XX, 5XX                                                  | \*/\*                                                     |