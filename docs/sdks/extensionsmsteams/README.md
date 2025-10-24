# ExtensionsMsteams
(*Extensions.Msteams*)

## Overview

### Available Operations

* [UpsertConfig](#upsertconfig) - Create Or Update MSTeams Configuration

## UpsertConfig

Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="MSTeams_createOrUpdateMsteamsConfiguration" method="post" path="/v3/extensions/msteams/config" -->
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

    res, err := s.Extensions.Msteams.UpsertConfig(ctx, components.V3ExtensionsMSTeamsCreateOrUpdateMSTeamsConfigRequest{
        DefaultConversationName: "<value>",
        DefaultConversationID: "<id>",
        IsActive: false,
        IsDefaultActive: false,
        IsCustomChannelsActive: true,
        Triggers: components.V3ExtensionsMSTeamsTriggers{
            AllActive: false,
            Custom: []components.V3ExtensionsMSTeamsEventClass{},
        },
        TenantID: "<id>",
        FromID: "<id>",
        ConnectedTeams: []components.V3ExtensionsMSTeamsConnectedTeams{
            components.V3ExtensionsMSTeamsConnectedTeams{
                TeamID: "<id>",
                TeamName: "<value>",
                ChannelConfigurations: []components.V3ExtensionsMSTeamsChannelConfiguration{
                    components.V3ExtensionsMSTeamsChannelConfiguration{
                        SquadcastTeamID: "<id>",
                        SquadcastTeamName: "<value>",
                        IsAllServices: true,
                        Services: []components.V3ExtensionsMSTeamsSquadCastServiceMapping{
                            components.V3ExtensionsMSTeamsSquadCastServiceMapping{
                                SquadcastServiceID: "<id>",
                                SquadcastServiceName: "<value>",
                            },
                        },
                        MsteamsChannelID: "<id>",
                        MsteamsChannelName: "<value>",
                    },
                },
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

| Parameter                                                                                                                                            | Type                                                                                                                                                 | Required                                                                                                                                             | Description                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                                | :heavy_check_mark:                                                                                                                                   | The context to use for the request.                                                                                                                  |
| `request`                                                                                                                                            | [components.V3ExtensionsMSTeamsCreateOrUpdateMSTeamsConfigRequest](../../models/components/v3extensionsmsteamscreateorupdatemsteamsconfigrequest.md) | :heavy_check_mark:                                                                                                                                   | The request object to use for the request.                                                                                                           |
| `opts`                                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                                             | :heavy_minus_sign:                                                                                                                                   | The options for this request.                                                                                                                        |

### Response

**[*operations.MSTeamsCreateOrUpdateMsteamsConfigurationResponse](../../models/operations/msteamscreateorupdatemsteamsconfigurationresponse.md), error**

### Errors

| Error Type                         | Status Code                        | Content Type                       |
| ---------------------------------- | ---------------------------------- | ---------------------------------- |
| apierrors.BadRequestError          | 400                                | application/json                   |
| apierrors.UnauthorizedError        | 401                                | application/json                   |
| apierrors.PaymentRequiredError     | 402                                | application/json                   |
| apierrors.ForbiddenError           | 403                                | application/json                   |
| apierrors.NotFoundError            | 404                                | application/json                   |
| apierrors.ConflictError            | 409                                | application/json                   |
| apierrors.UnprocessableEntityError | 422                                | application/json                   |
| apierrors.InternalServerError      | 500                                | application/json                   |
| apierrors.BadGatewayError          | 502                                | application/json                   |
| apierrors.ServiceUnavailableError  | 503                                | application/json                   |
| apierrors.GatewayTimeoutError      | 504                                | application/json                   |
| apierrors.APIError                 | 4XX, 5XX                           | \*/\*                              |