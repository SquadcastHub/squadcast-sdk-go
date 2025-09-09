# V3Squads
(*V3.Squads*)

## Overview

### Available Operations

* [ListByTeam](#listbyteam) - Get Squad By team

## ListByTeam

This endpoint is used to get the squads details by team.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_getSquadByTeam" method="get" path="/v3/squads" -->
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

    res, err := s.V3.Squads.ListByTeam(ctx, "<id>")
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