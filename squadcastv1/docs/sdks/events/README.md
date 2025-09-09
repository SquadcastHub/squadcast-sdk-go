# Events
(*Incidents.Events*)

## Overview

### Available Operations

* [List](#list) - Get Incident Events

## List

- This endpoint is used to get all the deduped incident events details by either ID or number.
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

Query Params:
```
offset - non zero value
limit - non zero value, maximum is 10
sort - sort it by either asc or desc
deduped - if set to true, it will return only the deduplicated events. if set to false, it will return only the non-deduplicated event, otherwise it will return all the events
```

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_getIncidentEvents" method="get" path="/v3/incidents/{incidentID}/events" -->
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

    res, err := s.Incidents.Events.List(ctx, operations.IncidentsGetIncidentEventsRequest{
        IncidentID: "<id>",
        Offset: "<value>",
        Limit: "<value>",
        Sort: "<value>",
        Deduped: "<value>",
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

| Parameter                                                                                                    | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                        | :heavy_check_mark:                                                                                           | The context to use for the request.                                                                          |
| `request`                                                                                                    | [operations.IncidentsGetIncidentEventsRequest](../../models/operations/incidentsgetincidenteventsrequest.md) | :heavy_check_mark:                                                                                           | The request object to use for the request.                                                                   |
| `opts`                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                     | :heavy_minus_sign:                                                                                           | The options for this request.                                                                                |

### Response

**[*operations.IncidentsGetIncidentEventsResponse](../../models/operations/incidentsgetincidenteventsresponse.md), error**

### Errors

| Error Type                                                   | Status Code                                                  | Content Type                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| apierrors.IncidentsGetIncidentEventsBadRequestError          | 400                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsUnauthorizedError        | 401                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsPaymentRequiredError     | 402                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsForbiddenError           | 403                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsNotFoundError            | 404                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsConflictError            | 409                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsUnprocessableEntityError | 422                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsInternalServerError      | 500                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsBadGatewayError          | 502                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsServiceUnavailableError  | 503                                                          | application/json                                             |
| apierrors.IncidentsGetIncidentEventsGatewayTimeoutError      | 504                                                          | application/json                                             |
| apierrors.APIError                                           | 4XX, 5XX                                                     | \*/\*                                                        |