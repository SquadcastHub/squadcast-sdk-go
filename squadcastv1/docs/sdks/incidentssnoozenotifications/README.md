# IncidentsSnoozeNotifications
(*IncidentsSnoozeNotifications*)

## Overview

### Available Operations

* [SnoozeNotificationsSnoozeIncidentNotifications](#snoozenotificationssnoozeincidentnotifications) - Snooze Incident Notifications
* [SnoozeNotificationsUnsnoozeIncidentNotifications](#snoozenotificationsunsnoozeincidentnotifications) - Unsnooze Incident Notifications

## SnoozeNotificationsSnoozeIncidentNotifications

Snooze Incident Notifications

### Example Usage

<!-- UsageSnippet language="go" operationID="SnoozeNotifications_snoozeIncidentNotifications" method="put" path="/v3/incidents/{incidentID}/snooze" -->
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

    res, err := s.IncidentsSnoozeNotifications.SnoozeNotificationsSnoozeIncidentNotifications(ctx, "<id>", components.V3IncidentsSnoozeNotificationsSnoozeIncidentRequest{
        SnoozeDurationInMins: 42279,
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

| Parameter                                                                                                                                        | Type                                                                                                                                             | Required                                                                                                                                         | Description                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                                                                            | :heavy_check_mark:                                                                                                                               | The context to use for the request.                                                                                                              |
| `incidentID`                                                                                                                                     | *string*                                                                                                                                         | :heavy_check_mark:                                                                                                                               | N/A                                                                                                                                              |
| `v3IncidentsSnoozeNotificationsSnoozeIncidentRequest`                                                                                            | [components.V3IncidentsSnoozeNotificationsSnoozeIncidentRequest](../../models/components/v3incidentssnoozenotificationssnoozeincidentrequest.md) | :heavy_check_mark:                                                                                                                               | N/A                                                                                                                                              |
| `opts`                                                                                                                                           | [][operations.Option](../../models/operations/option.md)                                                                                         | :heavy_minus_sign:                                                                                                                               | The options for this request.                                                                                                                    |

### Response

**[*operations.SnoozeNotificationsSnoozeIncidentNotificationsResponse](../../models/operations/snoozenotificationssnoozeincidentnotificationsresponse.md), error**

### Errors

| Error Type                                                                       | Status Code                                                                      | Content Type                                                                     |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsBadRequestError          | 400                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsUnauthorizedError        | 401                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsPaymentRequiredError     | 402                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsForbiddenError           | 403                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsNotFoundError            | 404                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsConflictError            | 409                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsUnprocessableEntityError | 422                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsInternalServerError      | 500                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsBadGatewayError          | 502                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsServiceUnavailableError  | 503                                                                              | application/json                                                                 |
| apierrors.SnoozeNotificationsSnoozeIncidentNotificationsGatewayTimeoutError      | 504                                                                              | application/json                                                                 |
| apierrors.APIError                                                               | 4XX, 5XX                                                                         | \*/\*                                                                            |

## SnoozeNotificationsUnsnoozeIncidentNotifications

Unsnooze Incident Notifications

### Example Usage

<!-- UsageSnippet language="go" operationID="SnoozeNotifications_unsnoozeIncidentNotifications" method="put" path="/v3/incidents/{incidentID}/unsnooze" -->
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

    res, err := s.IncidentsSnoozeNotifications.SnoozeNotificationsUnsnoozeIncidentNotifications(ctx, "<id>", components.V3IncidentsSnoozeNotificationsUnsnoozeIncidentRequest{
        ReassignTo: components.V3IncidentsSnoozeNotificationsReassignTo{
            ID: "<id>",
            Type: "<value>",
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
| `incidentID`                                                                                                                                         | *string*                                                                                                                                             | :heavy_check_mark:                                                                                                                                   | N/A                                                                                                                                                  |
| `v3IncidentsSnoozeNotificationsUnsnoozeIncidentRequest`                                                                                              | [components.V3IncidentsSnoozeNotificationsUnsnoozeIncidentRequest](../../models/components/v3incidentssnoozenotificationsunsnoozeincidentrequest.md) | :heavy_check_mark:                                                                                                                                   | N/A                                                                                                                                                  |
| `opts`                                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                                             | :heavy_minus_sign:                                                                                                                                   | The options for this request.                                                                                                                        |

### Response

**[*operations.SnoozeNotificationsUnsnoozeIncidentNotificationsResponse](../../models/operations/snoozenotificationsunsnoozeincidentnotificationsresponse.md), error**

### Errors

| Error Type                                                                         | Status Code                                                                        | Content Type                                                                       |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsBadRequestError          | 400                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsUnauthorizedError        | 401                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsPaymentRequiredError     | 402                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsForbiddenError           | 403                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsNotFoundError            | 404                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsConflictError            | 409                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsUnprocessableEntityError | 422                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsInternalServerError      | 500                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsBadGatewayError          | 502                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsServiceUnavailableError  | 503                                                                                | application/json                                                                   |
| apierrors.SnoozeNotificationsUnsnoozeIncidentNotificationsGatewayTimeoutError      | 504                                                                                | application/json                                                                   |
| apierrors.APIError                                                                 | 4XX, 5XX                                                                           | \*/\*                                                                              |