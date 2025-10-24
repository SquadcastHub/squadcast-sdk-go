# CommunicationCard
(*Incidents.CommunicationCard*)

## Overview

### Available Operations

* [Update](#update) - Update Communication Card

## Update

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

    res, err := s.Incidents.CommunicationCard.Update(ctx, "<id>", "<id>", components.V3IncidentsCommunicationCardsUpdateCommunicationCardRequest{
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