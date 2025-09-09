# IncidentsCommunicationCard
(*IncidentsCommunicationCard*)

## Overview

### Available Operations

* [CommunicationCardsCreateSlackChannelInCommunicationCard](#communicationcardscreateslackchannelincommunicationcard) - Create Slack Channel in Communication Card
* [CommunicationCardsArchiveSlackChannel](#communicationcardsarchiveslackchannel) - Archive Slack Channel
* [CommunicationCardsGetAllCommunicationCard](#communicationcardsgetallcommunicationcard) - Get All Communication Card
* [CommunicationCardsCreateCommunicationCard](#communicationcardscreatecommunicationcard) - Create Communication Card
* [CommunicationCardsDeleteCommunicationCard](#communicationcardsdeletecommunicationcard) - Delete Communication Card
* [CommunicationCardsUpdateCommunicationCard](#communicationcardsupdatecommunicationcard) - Update Communication Card

## CommunicationCardsCreateSlackChannelInCommunicationCard

Create Slack Channel in Communication Card

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_createSlackChannelInCommunicationCard" method="post" path="/v3/extensions/slack_v2/channel" -->
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

    res, err := s.IncidentsCommunicationCard.CommunicationCardsCreateSlackChannelInCommunicationCard(ctx, components.V3IncidentsCommunicationCardsCreateSlackChannelRequest{
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

## CommunicationCardsArchiveSlackChannel

Archive Slack Channel

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_archiveSlackChannel" method="post" path="/v3/extensions/slack_v2/channel/archive" -->
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

    res, err := s.IncidentsCommunicationCard.CommunicationCardsArchiveSlackChannel(ctx, components.V3IncidentsCommunicationCardsArchiveSlackChannelRequest{
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

## CommunicationCardsGetAllCommunicationCard

*   This endpoint is used to get all the communication card details for incidentId metioned in params.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_getAllCommunicationCard" method="get" path="/v3/incidents/{IncidentId}/communication_cards" -->
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

    res, err := s.IncidentsCommunicationCard.CommunicationCardsGetAllCommunicationCard(ctx, "<id>")
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
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.CommunicationCardsGetAllCommunicationCardResponse](../../models/operations/communicationcardsgetallcommunicationcardresponse.md), error**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| apierrors.CommunicationCardsGetAllCommunicationCardBadRequestError          | 400                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardUnauthorizedError        | 401                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardPaymentRequiredError     | 402                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardForbiddenError           | 403                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardNotFoundError            | 404                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardConflictError            | 409                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardUnprocessableEntityError | 422                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardInternalServerError      | 500                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardBadGatewayError          | 502                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardServiceUnavailableError  | 503                                                                         | application/json                                                            |
| apierrors.CommunicationCardsGetAllCommunicationCardGatewayTimeoutError      | 504                                                                         | application/json                                                            |
| apierrors.APIError                                                          | 4XX, 5XX                                                                    | \*/\*                                                                       |

## CommunicationCardsCreateCommunicationCard

Create Communication Card

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_createCommunicationCard" method="post" path="/v3/incidents/{IncidentId}/communication_cards" -->
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

    res, err := s.IncidentsCommunicationCard.CommunicationCardsCreateCommunicationCard(ctx, "<id>", components.V3IncidentsCommunicationCardsCreateCommunicationCardRequest{
        Type: "<value>",
        URL: "https://oily-injunction.info",
        Title: "<value>",
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

| Parameter                                                                                                                                                        | Type                                                                                                                                                             | Required                                                                                                                                                         | Description                                                                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                                                                                            | :heavy_check_mark:                                                                                                                                               | The context to use for the request.                                                                                                                              |
| `incidentID`                                                                                                                                                     | *string*                                                                                                                                                         | :heavy_check_mark:                                                                                                                                               | Required                                                                                                                                                         |
| `v3IncidentsCommunicationCardsCreateCommunicationCardRequest`                                                                                                    | [components.V3IncidentsCommunicationCardsCreateCommunicationCardRequest](../../models/components/v3incidentscommunicationcardscreatecommunicationcardrequest.md) | :heavy_check_mark:                                                                                                                                               | N/A                                                                                                                                                              |
| `opts`                                                                                                                                                           | [][operations.Option](../../models/operations/option.md)                                                                                                         | :heavy_minus_sign:                                                                                                                                               | The options for this request.                                                                                                                                    |

### Response

**[*operations.CommunicationCardsCreateCommunicationCardResponse](../../models/operations/communicationcardscreatecommunicationcardresponse.md), error**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| apierrors.CommunicationCardsCreateCommunicationCardBadRequestError          | 400                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardUnauthorizedError        | 401                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardPaymentRequiredError     | 402                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardForbiddenError           | 403                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardNotFoundError            | 404                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardConflictError            | 409                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardUnprocessableEntityError | 422                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardInternalServerError      | 500                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardBadGatewayError          | 502                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardServiceUnavailableError  | 503                                                                         | application/json                                                            |
| apierrors.CommunicationCardsCreateCommunicationCardGatewayTimeoutError      | 504                                                                         | application/json                                                            |
| apierrors.APIError                                                          | 4XX, 5XX                                                                    | \*/\*                                                                       |

## CommunicationCardsDeleteCommunicationCard

Delete communication card by providing communicationCardId for incidentId mentioned in params

Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `service-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_deleteCommunicationCard" method="delete" path="/v3/incidents/{IncidentId}/communication_cards/{communicationCardId}" -->
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

    res, err := s.IncidentsCommunicationCard.CommunicationCardsDeleteCommunicationCard(ctx, "<id>", "<id>")
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
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | Required                                                 |
| `communicationCardID`                                    | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.CommunicationCardsDeleteCommunicationCardResponse](../../models/operations/communicationcardsdeletecommunicationcardresponse.md), error**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| apierrors.CommunicationCardsDeleteCommunicationCardBadRequestError          | 400                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardUnauthorizedError        | 401                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardPaymentRequiredError     | 402                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardForbiddenError           | 403                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardNotFoundError            | 404                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardConflictError            | 409                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardUnprocessableEntityError | 422                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardInternalServerError      | 500                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardBadGatewayError          | 502                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardServiceUnavailableError  | 503                                                                         | application/json                                                            |
| apierrors.CommunicationCardsDeleteCommunicationCardGatewayTimeoutError      | 504                                                                         | application/json                                                            |
| apierrors.APIError                                                          | 4XX, 5XX                                                                    | \*/\*                                                                       |

## CommunicationCardsUpdateCommunicationCard

Update Communication Card

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_updateCommunicationCard" method="put" path="/v3/incidents/{IncidentId}/communication_cards/{communicationCardId}" -->
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

    res, err := s.IncidentsCommunicationCard.CommunicationCardsUpdateCommunicationCard(ctx, "<id>", "<id>", components.V3IncidentsCommunicationCardsUpdateCommunicationCardRequest{
        Title: "<value>",
        Type: "<value>",
        URL: "https://major-cantaloupe.com/",
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

| Parameter                                                                                                                                                        | Type                                                                                                                                                             | Required                                                                                                                                                         | Description                                                                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                                                                                            | :heavy_check_mark:                                                                                                                                               | The context to use for the request.                                                                                                                              |
| `incidentID`                                                                                                                                                     | *string*                                                                                                                                                         | :heavy_check_mark:                                                                                                                                               | Required                                                                                                                                                         |
| `communicationCardID`                                                                                                                                            | *string*                                                                                                                                                         | :heavy_check_mark:                                                                                                                                               | N/A                                                                                                                                                              |
| `v3IncidentsCommunicationCardsUpdateCommunicationCardRequest`                                                                                                    | [components.V3IncidentsCommunicationCardsUpdateCommunicationCardRequest](../../models/components/v3incidentscommunicationcardsupdatecommunicationcardrequest.md) | :heavy_check_mark:                                                                                                                                               | N/A                                                                                                                                                              |
| `opts`                                                                                                                                                           | [][operations.Option](../../models/operations/option.md)                                                                                                         | :heavy_minus_sign:                                                                                                                                               | The options for this request.                                                                                                                                    |

### Response

**[*operations.CommunicationCardsUpdateCommunicationCardResponse](../../models/operations/communicationcardsupdatecommunicationcardresponse.md), error**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| apierrors.CommunicationCardsUpdateCommunicationCardBadRequestError          | 400                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardUnauthorizedError        | 401                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardPaymentRequiredError     | 402                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardForbiddenError           | 403                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardNotFoundError            | 404                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardConflictError            | 409                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardUnprocessableEntityError | 422                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardInternalServerError      | 500                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardBadGatewayError          | 502                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardServiceUnavailableError  | 503                                                                         | application/json                                                            |
| apierrors.CommunicationCardsUpdateCommunicationCardGatewayTimeoutError      | 504                                                                         | application/json                                                            |
| apierrors.APIError                                                          | 4XX, 5XX                                                                    | \*/\*                                                                       |