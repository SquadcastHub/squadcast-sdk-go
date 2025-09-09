# CommunicationCards
(*CommunicationCards*)

## Overview

### Available Operations

* [CreateSlackChannel](#createslackchannel) - Create Slack Channel in Communication Card
* [ArchiveSlackChannel](#archiveslackchannel) - Archive Slack Channel

## CreateSlackChannel

Create Slack Channel in Communication Card

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_createSlackChannelInCommunicationCard" method="post" path="/v3/extensions/slack_v2/channel" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.CommunicationCards.CreateSlackChannel(ctx, components.V3IncidentsCommunicationCardsCreateSlackChannelRequest{
        ChannelName: "<value>",
        IncidentID: "<id>",
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

| Parameter                                                                                                                                              | Type                                                                                                                                                   | Required                                                                                                                                               | Description                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                                                  | :heavy_check_mark:                                                                                                                                     | The context to use for the request.                                                                                                                    |
| `request`                                                                                                                                              | [components.V3IncidentsCommunicationCardsCreateSlackChannelRequest](../../models/components/v3incidentscommunicationcardscreateslackchannelrequest.md) | :heavy_check_mark:                                                                                                                                     | The request object to use for the request.                                                                                                             |
| `opts`                                                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                                                               | :heavy_minus_sign:                                                                                                                                     | The options for this request.                                                                                                                          |

### Response

**[*operations.CommunicationCardsCreateSlackChannelInCommunicationCardResponse](../../models/operations/communicationcardscreateslackchannelincommunicationcardresponse.md), error**

### Errors

| Error Type                                                                                | Status Code                                                                               | Content Type                                                                              |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardBadRequestError          | 400                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardUnauthorizedError        | 401                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardPaymentRequiredError     | 402                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardForbiddenError           | 403                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardNotFoundError            | 404                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardConflictError            | 409                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardUnprocessableEntityError | 422                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardInternalServerError      | 500                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardBadGatewayError          | 502                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardServiceUnavailableError  | 503                                                                                       | application/json                                                                          |
| apierrors.CommunicationCardsCreateSlackChannelInCommunicationCardGatewayTimeoutError      | 504                                                                                       | application/json                                                                          |
| apierrors.APIError                                                                        | 4XX, 5XX                                                                                  | \*/\*                                                                                     |

## ArchiveSlackChannel

Archive Slack Channel

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_archiveSlackChannel" method="post" path="/v3/extensions/slack_v2/channel/archive" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.CommunicationCards.ArchiveSlackChannel(ctx, components.V3IncidentsCommunicationCardsArchiveSlackChannelRequest{
        SlackChannelID: "<id>",
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

| Parameter                                                                                                                                                | Type                                                                                                                                                     | Required                                                                                                                                                 | Description                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                                                    | :heavy_check_mark:                                                                                                                                       | The context to use for the request.                                                                                                                      |
| `request`                                                                                                                                                | [components.V3IncidentsCommunicationCardsArchiveSlackChannelRequest](../../models/components/v3incidentscommunicationcardsarchiveslackchannelrequest.md) | :heavy_check_mark:                                                                                                                                       | The request object to use for the request.                                                                                                               |
| `opts`                                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                                 | :heavy_minus_sign:                                                                                                                                       | The options for this request.                                                                                                                            |

### Response

**[*operations.CommunicationCardsArchiveSlackChannelResponse](../../models/operations/communicationcardsarchiveslackchannelresponse.md), error**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| apierrors.CommunicationCardsArchiveSlackChannelBadRequestError          | 400                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelUnauthorizedError        | 401                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelPaymentRequiredError     | 402                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelForbiddenError           | 403                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelNotFoundError            | 404                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelConflictError            | 409                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelUnprocessableEntityError | 422                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelInternalServerError      | 500                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelBadGatewayError          | 502                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelServiceUnavailableError  | 503                                                                     | application/json                                                        |
| apierrors.CommunicationCardsArchiveSlackChannelGatewayTimeoutError      | 504                                                                     | application/json                                                        |
| apierrors.APIError                                                      | 4XX, 5XX                                                                | \*/\*                                                                   |