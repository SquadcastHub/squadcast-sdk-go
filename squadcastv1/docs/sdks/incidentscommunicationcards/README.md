# IncidentsCommunicationCards
(*Incidents.CommunicationCards*)

## Overview

### Available Operations

* [GetAll](#getall) - Get All Communication Card
* [Create](#create) - Create Communication Card
* [Delete](#delete) - Delete Communication Card

## GetAll

*   This endpoint is used to get all the communication card details for incidentId metioned in params.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_getAllCommunicationCard" method="get" path="/v3/incidents/{IncidentId}/communication_cards" -->
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

    res, err := s.Incidents.CommunicationCards.GetAll(ctx, "<id>")
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

## Create

Create Communication Card

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_createCommunicationCard" method="post" path="/v3/incidents/{IncidentId}/communication_cards" -->
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

    res, err := s.Incidents.CommunicationCards.Create(ctx, "<id>", components.V3IncidentsCommunicationCardsCreateCommunicationCardRequest{
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

## Delete

Delete communication card by providing communicationCardId for incidentId mentioned in params

Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `service-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="CommunicationCards_deleteCommunicationCard" method="delete" path="/v3/incidents/{IncidentId}/communication_cards/{communicationCardId}" -->
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

    res, err := s.Incidents.CommunicationCards.Delete(ctx, "<id>", "<id>")
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