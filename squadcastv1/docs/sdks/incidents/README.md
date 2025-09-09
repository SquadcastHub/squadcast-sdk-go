# Incidents
(*Incidents*)

## Overview

### Available Operations

* [IncidentsBulkAcknowledgeIncidents](#incidentsbulkacknowledgeincidents) - Bulk Acknowledge Incidents
* [IncidentsIncidentExport](#incidentsincidentexport) - Incident Export
* [IncidentsIncidentExportAsync](#incidentsincidentexportasync) - Incident Export Async
* [IncidentsBulkIncidentsPriorityUpdate](#incidentsbulkincidentspriorityupdate) - Bulk Incidents Priority Update
* [IncidentsBulkResolveIncidents](#incidentsbulkresolveincidents) - Bulk Resolve Incidents
* [IncidentsGetIncidentByID](#incidentsgetincidentbyid) - Get Incident by ID
* [IncidentsAcknowledgeIncident](#incidentsacknowledgeincident) - Acknowledge Incident
* [IncidentsGetIncidentEvents](#incidentsgetincidentevents) - Get Incident Events
* [IncidentsMarkIncidentSloFalsePositive](#incidentsmarkincidentslofalsepositive) - Mark Incident SLO False Positive
* [IncidentsIncidentPriorityUpdate](#incidentsincidentpriorityupdate) - Incident Priority Update
* [IncidentsReassignIncident](#incidentsreassignincident) - Reassign Incident
* [IncidentsResolveIncident](#incidentsresolveincident) - Resolve Incident
* [IncidentsGetIncidentsStatusByRequestids](#incidentsgetincidentsstatusbyrequestids) - Get Incidents Status By RequestIDs

## IncidentsBulkAcknowledgeIncidents

- This endpoint is used to bulk acknowledge the incident by IDs.
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_bulkAcknowledgeIncidents" method="post" path="/v3/incidents/acknowledge" -->
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

    res, err := s.Incidents.IncidentsBulkAcknowledgeIncidents(ctx, components.V3IncidentsBulkIncidentIDsRequest{
        IncidentIds: []string{
            "<value 1>",
            "<value 2>",
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

| Parameter                                                                                                    | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                        | :heavy_check_mark:                                                                                           | The context to use for the request.                                                                          |
| `request`                                                                                                    | [components.V3IncidentsBulkIncidentIDsRequest](../../models/components/v3incidentsbulkincidentidsrequest.md) | :heavy_check_mark:                                                                                           | The request object to use for the request.                                                                   |
| `opts`                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                     | :heavy_minus_sign:                                                                                           | The options for this request.                                                                                |

### Response

**[*operations.IncidentsBulkAcknowledgeIncidentsResponse](../../models/operations/incidentsbulkacknowledgeincidentsresponse.md), error**

### Errors

| Error Type                                                          | Status Code                                                         | Content Type                                                        |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| apierrors.IncidentsBulkAcknowledgeIncidentsBadRequestError          | 400                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsUnauthorizedError        | 401                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsPaymentRequiredError     | 402                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsForbiddenError           | 403                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsNotFoundError            | 404                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsConflictError            | 409                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsUnprocessableEntityError | 422                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsInternalServerError      | 500                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsBadGatewayError          | 502                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsServiceUnavailableError  | 503                                                                 | application/json                                                    |
| apierrors.IncidentsBulkAcknowledgeIncidentsGatewayTimeoutError      | 504                                                                 | application/json                                                    |
| apierrors.APIError                                                  | 4XX, 5XX                                                            | \*/\*                                                               |

## IncidentsIncidentExport

- This endpoint is used to export the incident details into a `csv` or `json` file.
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.
- Header field/value: `Content-Type`: `text/csv`


Query Params:

```
type: csv or json
start_time: filter by date range
end_time: filter by date range
services: filter by services
sources: filter by alert sources
assigned_to: filter by assignee
status: filter by incident status
slo_affecting: filetr by slo affected
slos: filter by slos
tags: filter by tags key=value

 ```

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_incidentExport" method="get" path="/v3/incidents/export" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/types"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"github.com/SquadcastHub/squadcast-sdk-go/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Incidents.IncidentsIncidentExport(ctx, operations.IncidentsIncidentExportRequest{
        StartTime: types.MustTimeFromString("2023-02-02T07:53:59.590Z"),
        EndTime: types.MustTimeFromString("2023-02-03T13:28:22.839Z"),
        Type: components.V3IncidentsExportFormatCsv,
        OwnerID: "<id>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `request`                                                                                              | [operations.IncidentsIncidentExportRequest](../../models/operations/incidentsincidentexportrequest.md) | :heavy_check_mark:                                                                                     | The request object to use for the request.                                                             |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.IncidentsIncidentExportResponse](../../models/operations/incidentsincidentexportresponse.md), error**

### Errors

| Error Type                                                | Status Code                                               | Content Type                                              |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| apierrors.IncidentsIncidentExportPaymentRequiredError     | 402                                                       | application/json                                          |
| apierrors.IncidentsIncidentExportForbiddenError           | 403                                                       | application/json                                          |
| apierrors.IncidentsIncidentExportNotFoundError            | 404                                                       | application/json                                          |
| apierrors.IncidentsIncidentExportConflictError            | 409                                                       | application/json                                          |
| apierrors.IncidentsIncidentExportUnprocessableEntityError | 422                                                       | application/json                                          |
| apierrors.IncidentsIncidentExportInternalServerError      | 500                                                       | application/json                                          |
| apierrors.IncidentsIncidentExportBadGatewayError          | 502                                                       | application/json                                          |
| apierrors.IncidentsIncidentExportServiceUnavailableError  | 503                                                       | application/json                                          |
| apierrors.IncidentsIncidentExportGatewayTimeoutError      | 504                                                       | application/json                                          |
| apierrors.APIError                                        | 4XX, 5XX                                                  | \*/\*                                                     |

## IncidentsIncidentExportAsync

*   This is an async API, once the request is made the export will start in our workers. You will get a download link to your registered Email ID once the export is completed


### Payload

| Key | Value | Example |
| --- | --- | --- |
| type | csv / json | “csv” |
| start_time | Date in ISO Format | “2020-01-01T00:00:00.000Z” |
| end_time | Date in ISO Format | “2020-04-01T00:00:00.000Z” |
| owner_id | Team ID | “611262a9d5b4ea846b534a3f” |

### Incident Filters

| Key | Value | Example |
| --- | --- | --- |
| statuses | Array of triggered / resolved / acknowledged / suppressed | \[“triggered”, “acknowleged”\] |
| tags | Array of tags in format “KEY=VALUE” | \[“severity=high”, “severity=low”\] |
| sources | Array of Alert Source IDs | \[“6077f7225fdc7075e371685f”\] |
| services | Array of Service IDs | \["62385fb309bc474014180828"\] |
| assigned_to | Array of Assigned to user IDs | \["625e40c9a9bd76370bf9f7fb"\] |

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_incidentExportAsync" method="post" path="/v3/incidents/export/async" -->
```go
package main

import(
	"context"
	"os"
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/components"
	"github.com/SquadcastHub/squadcast-sdk-go/types"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Incidents.IncidentsIncidentExportAsync(ctx, components.V3IncidentsIncidentExportAsyncRequest{
        OwnerID: "<id>",
        Type: components.V3IncidentsExportFormatCsv,
        StartTime: types.MustTimeFromString("2024-12-29T12:56:54.559Z"),
        EndTime: types.MustTimeFromString("2025-08-25T17:31:33.747Z"),
        IncidentFilters: components.V3IncidentsExportIncidentsFilter{
            Services: []string{},
            Sources: []string{},
            ServiceOwner: components.V3IncidentsServiceOwnerFilter{
                UserIDs: []string{
                    "<value 1>",
                },
                SquadIDs: []string{
                    "<value 1>",
                    "<value 2>",
                    "<value 3>",
                },
            },
            AssignedTo: []string{
                "<value 1>",
                "<value 2>",
                "<value 3>",
            },
            AssignedToUserIDsAndTheirSquads: []string{
                "<value 1>",
                "<value 2>",
            },
            Statuses: []string{
                "<value 1>",
                "<value 2>",
                "<value 3>",
            },
            Priority: []components.V3IncidentsIncidentPriority{
                components.V3IncidentsIncidentPriorityP5,
            },
            Tags: []string{},
            Notes: "<value>",
        },
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                | :heavy_check_mark:                                                                                                   | The context to use for the request.                                                                                  |
| `request`                                                                                                            | [components.V3IncidentsIncidentExportAsyncRequest](../../models/components/v3incidentsincidentexportasyncrequest.md) | :heavy_check_mark:                                                                                                   | The request object to use for the request.                                                                           |
| `opts`                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                             | :heavy_minus_sign:                                                                                                   | The options for this request.                                                                                        |

### Response

**[*operations.IncidentsIncidentExportAsyncResponse](../../models/operations/incidentsincidentexportasyncresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.IncidentsIncidentExportAsyncBadRequestError          | 400                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncForbiddenError           | 403                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncNotFoundError            | 404                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncConflictError            | 409                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncInternalServerError      | 500                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.IncidentsIncidentExportAsyncGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## IncidentsBulkIncidentsPriorityUpdate

- This endpoint is used to bulk update incident priority.

- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_bulkIncidentsPriorityUpdate" method="put" path="/v3/incidents/priority" -->
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

    res, err := s.Incidents.IncidentsBulkIncidentsPriorityUpdate(ctx, components.V3IncidentsBulkIncidentsPriorityUpdateRequest{
        IncidentIds: []string{},
        Priority: "<value>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                            | Type                                                                                                                                 | Required                                                                                                                             | Description                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                | :heavy_check_mark:                                                                                                                   | The context to use for the request.                                                                                                  |
| `request`                                                                                                                            | [components.V3IncidentsBulkIncidentsPriorityUpdateRequest](../../models/components/v3incidentsbulkincidentspriorityupdaterequest.md) | :heavy_check_mark:                                                                                                                   | The request object to use for the request.                                                                                           |
| `opts`                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                             | :heavy_minus_sign:                                                                                                                   | The options for this request.                                                                                                        |

### Response

**[*operations.IncidentsBulkIncidentsPriorityUpdateResponse](../../models/operations/incidentsbulkincidentspriorityupdateresponse.md), error**

### Errors

| Error Type                                                             | Status Code                                                            | Content Type                                                           |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| apierrors.IncidentsBulkIncidentsPriorityUpdateBadRequestError          | 400                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateUnauthorizedError        | 401                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdatePaymentRequiredError     | 402                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateForbiddenError           | 403                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateNotFoundError            | 404                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateConflictError            | 409                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateUnprocessableEntityError | 422                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateInternalServerError      | 500                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateBadGatewayError          | 502                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateServiceUnavailableError  | 503                                                                    | application/json                                                       |
| apierrors.IncidentsBulkIncidentsPriorityUpdateGatewayTimeoutError      | 504                                                                    | application/json                                                       |
| apierrors.APIError                                                     | 4XX, 5XX                                                               | \*/\*                                                                  |

## IncidentsBulkResolveIncidents

- This endpoint is used to bulk resolve the incident by IDs.
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_bulkResolveIncidents" method="post" path="/v3/incidents/resolve" -->
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

    res, err := s.Incidents.IncidentsBulkResolveIncidents(ctx, components.V3IncidentsBulkIncidentIDsRequest{
        IncidentIds: []string{
            "<value 1>",
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

| Parameter                                                                                                    | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                        | :heavy_check_mark:                                                                                           | The context to use for the request.                                                                          |
| `request`                                                                                                    | [components.V3IncidentsBulkIncidentIDsRequest](../../models/components/v3incidentsbulkincidentidsrequest.md) | :heavy_check_mark:                                                                                           | The request object to use for the request.                                                                   |
| `opts`                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                     | :heavy_minus_sign:                                                                                           | The options for this request.                                                                                |

### Response

**[*operations.IncidentsBulkResolveIncidentsResponse](../../models/operations/incidentsbulkresolveincidentsresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.IncidentsBulkResolveIncidentsBadRequestError          | 400                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsForbiddenError           | 403                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsNotFoundError            | 404                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsConflictError            | 409                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsInternalServerError      | 500                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.IncidentsBulkResolveIncidentsGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## IncidentsGetIncidentByID

- This endpoint is used to get the incident details by ID.
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_getIncidentById" method="get" path="/v3/incidents/{incidentID}" -->
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

    res, err := s.Incidents.IncidentsGetIncidentByID(ctx, "<id>")
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

**[*operations.IncidentsGetIncidentByIDResponse](../../models/operations/incidentsgetincidentbyidresponse.md), error**

### Errors

| Error Type                                                 | Status Code                                                | Content Type                                               |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| apierrors.IncidentsGetIncidentByIDBadRequestError          | 400                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDUnauthorizedError        | 401                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDPaymentRequiredError     | 402                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDForbiddenError           | 403                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDNotFoundError            | 404                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDConflictError            | 409                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDUnprocessableEntityError | 422                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDInternalServerError      | 500                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDBadGatewayError          | 502                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDServiceUnavailableError  | 503                                                        | application/json                                           |
| apierrors.IncidentsGetIncidentByIDGatewayTimeoutError      | 504                                                        | application/json                                           |
| apierrors.APIError                                         | 4XX, 5XX                                                   | \*/\*                                                      |

## IncidentsAcknowledgeIncident

- This endpoint is used to acknowledge the incident by ID.
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_acknowledgeIncident" method="post" path="/v3/incidents/{incidentID}/acknowledge" -->
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

    res, err := s.Incidents.IncidentsAcknowledgeIncident(ctx, "<id>")
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

**[*operations.IncidentsAcknowledgeIncidentResponse](../../models/operations/incidentsacknowledgeincidentresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.IncidentsAcknowledgeIncidentBadRequestError          | 400                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentForbiddenError           | 403                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentNotFoundError            | 404                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentConflictError            | 409                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentInternalServerError      | 500                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.IncidentsAcknowledgeIncidentGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## IncidentsGetIncidentEvents

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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go"
	"github.com/SquadcastHub/squadcast-sdk-go/models/operations"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Incidents.IncidentsGetIncidentEvents(ctx, operations.IncidentsGetIncidentEventsRequest{
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

## IncidentsMarkIncidentSloFalsePositive

- This endpoint is used to mark incident slo false positive.

- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_markIncidentSloFalsePositive" method="patch" path="/v3/incidents/{incidentID}/mark-slo-incident-false-postive/{value}" -->
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

    res, err := s.Incidents.IncidentsMarkIncidentSloFalsePositive(ctx, "<id>", "<value>")
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
| `value`                                                  | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.IncidentsMarkIncidentSloFalsePositiveResponse](../../models/operations/incidentsmarkincidentslofalsepositiveresponse.md), error**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| apierrors.IncidentsMarkIncidentSloFalsePositiveBadRequestError          | 400                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveUnauthorizedError        | 401                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositivePaymentRequiredError     | 402                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveForbiddenError           | 403                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveNotFoundError            | 404                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveConflictError            | 409                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveUnprocessableEntityError | 422                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveInternalServerError      | 500                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveBadGatewayError          | 502                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveServiceUnavailableError  | 503                                                                     | application/json                                                        |
| apierrors.IncidentsMarkIncidentSloFalsePositiveGatewayTimeoutError      | 504                                                                     | application/json                                                        |
| apierrors.APIError                                                      | 4XX, 5XX                                                                | \*/\*                                                                   |

## IncidentsIncidentPriorityUpdate

- This endpoint is used to update incident priority by ID.

- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_incidentPriorityUpdate" method="patch" path="/v3/incidents/{incidentID}/priority" -->
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

    res, err := s.Incidents.IncidentsIncidentPriorityUpdate(ctx, "<id>", components.V3IncidentsIncidentPriorityUpdateRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                  | Type                                                                                                                       | Required                                                                                                                   | Description                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                                                      | :heavy_check_mark:                                                                                                         | The context to use for the request.                                                                                        |
| `incidentID`                                                                                                               | *string*                                                                                                                   | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `v3IncidentsIncidentPriorityUpdateRequest`                                                                                 | [components.V3IncidentsIncidentPriorityUpdateRequest](../../models/components/v3incidentsincidentpriorityupdaterequest.md) | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `opts`                                                                                                                     | [][operations.Option](../../models/operations/option.md)                                                                   | :heavy_minus_sign:                                                                                                         | The options for this request.                                                                                              |

### Response

**[*operations.IncidentsIncidentPriorityUpdateResponse](../../models/operations/incidentsincidentpriorityupdateresponse.md), error**

### Errors

| Error Type                                                        | Status Code                                                       | Content Type                                                      |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| apierrors.IncidentsIncidentPriorityUpdateBadRequestError          | 400                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateUnauthorizedError        | 401                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdatePaymentRequiredError     | 402                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateForbiddenError           | 403                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateNotFoundError            | 404                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateConflictError            | 409                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateUnprocessableEntityError | 422                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateInternalServerError      | 500                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateBadGatewayError          | 502                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateServiceUnavailableError  | 503                                                               | application/json                                                  |
| apierrors.IncidentsIncidentPriorityUpdateGatewayTimeoutError      | 504                                                               | application/json                                                  |
| apierrors.APIError                                                | 4XX, 5XX                                                          | \*/\*                                                             |

## IncidentsReassignIncident

- This endpoint is used to reassign the unresolved incident to any user or escalation policy or squads by ID.
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.
- `type` can be either `user` or `escalationpolicy` or `squad`

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_reassignIncident" method="post" path="/v3/incidents/{incidentID}/reassign" -->
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

    res, err := s.Incidents.IncidentsReassignIncident(ctx, "<id>", components.V3IncidentsReassignIncidentRequest{
        ReassignTo: components.ReassignTo{
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

| Parameter                                                                                                      | Type                                                                                                           | Required                                                                                                       | Description                                                                                                    |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                                          | :heavy_check_mark:                                                                                             | The context to use for the request.                                                                            |
| `incidentID`                                                                                                   | *string*                                                                                                       | :heavy_check_mark:                                                                                             | N/A                                                                                                            |
| `v3IncidentsReassignIncidentRequest`                                                                           | [components.V3IncidentsReassignIncidentRequest](../../models/components/v3incidentsreassignincidentrequest.md) | :heavy_check_mark:                                                                                             | N/A                                                                                                            |
| `opts`                                                                                                         | [][operations.Option](../../models/operations/option.md)                                                       | :heavy_minus_sign:                                                                                             | The options for this request.                                                                                  |

### Response

**[*operations.IncidentsReassignIncidentResponse](../../models/operations/incidentsreassignincidentresponse.md), error**

### Errors

| Error Type                                                  | Status Code                                                 | Content Type                                                |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| apierrors.IncidentsReassignIncidentBadRequestError          | 400                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentUnauthorizedError        | 401                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentPaymentRequiredError     | 402                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentForbiddenError           | 403                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentNotFoundError            | 404                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentConflictError            | 409                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentUnprocessableEntityError | 422                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentInternalServerError      | 500                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentBadGatewayError          | 502                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentServiceUnavailableError  | 503                                                         | application/json                                            |
| apierrors.IncidentsReassignIncidentGatewayTimeoutError      | 504                                                         | application/json                                            |
| apierrors.APIError                                          | 4XX, 5XX                                                    | \*/\*                                                       |

## IncidentsResolveIncident

- This endpoint is used to resolve the incident by ID.

- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

- Resolution Reason is mandatory / optional based on the organization feature settings (Only for Premium and Enterprise Orgs) [Read more](https://support.squadcast.com/incidents-page/incidents-details#understanding-resolution-reason)

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_resolveIncident" method="post" path="/v3/incidents/{incidentID}/resolve" -->
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

    res, err := s.Incidents.IncidentsResolveIncident(ctx, "<id>", components.V3IncidentsResolveIncidentRequest{
        ResolutionReason: components.ResolutionReason{
            Message: "<value>",
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

| Parameter                                                                                                    | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                        | :heavy_check_mark:                                                                                           | The context to use for the request.                                                                          |
| `incidentID`                                                                                                 | *string*                                                                                                     | :heavy_check_mark:                                                                                           | N/A                                                                                                          |
| `v3IncidentsResolveIncidentRequest`                                                                          | [components.V3IncidentsResolveIncidentRequest](../../models/components/v3incidentsresolveincidentrequest.md) | :heavy_check_mark:                                                                                           | N/A                                                                                                          |
| `opts`                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                     | :heavy_minus_sign:                                                                                           | The options for this request.                                                                                |

### Response

**[*operations.IncidentsResolveIncidentResponse](../../models/operations/incidentsresolveincidentresponse.md), error**

### Errors

| Error Type                                                 | Status Code                                                | Content Type                                               |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| apierrors.IncidentsResolveIncidentBadRequestError          | 400                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentUnauthorizedError        | 401                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentPaymentRequiredError     | 402                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentForbiddenError           | 403                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentNotFoundError            | 404                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentConflictError            | 409                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentUnprocessableEntityError | 422                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentInternalServerError      | 500                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentBadGatewayError          | 502                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentServiceUnavailableError  | 503                                                        | application/json                                           |
| apierrors.IncidentsResolveIncidentGatewayTimeoutError      | 504                                                        | application/json                                           |
| apierrors.APIError                                         | 4XX, 5XX                                                   | \*/\*                                                      |

## IncidentsGetIncidentsStatusByRequestids

- This endpoint is used to get the status of incidents given list of request_ids
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

# Response
- The response contains the mapping from `request_ids` to incident status.
- `status` field can be one of - `suppressed`, `discarded`, `deduplicated`, `created`, `error`.
-  status is `error` if the `request_id` is invalid. Both `incident_id` and `event_id` field won't be present if `status` is `error`
-  status is `suppressed` if the incident was suppressed due to suppression rules.
-  status is `deduplicated` if the incident was deduplicated due to deduplication rules.
-  status is `discarded` if the incident was discarded due to some deduplication rule. `incident_id` field won't be present if `status` is `discarded`.
-  otherwise, the status is `created`

### Example Usage

<!-- UsageSnippet language="go" operationID="Incidents_getIncidentsStatusByRequestids" method="post" path="/v3/requests/status" -->
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

    res, err := s.Incidents.IncidentsGetIncidentsStatusByRequestids(ctx, components.V3IncidentsIngestionStatusRequest{
        RequestIds: []string{
            "<value 1>",
            "<value 2>",
            "<value 3>",
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

| Parameter                                                                                                    | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                        | :heavy_check_mark:                                                                                           | The context to use for the request.                                                                          |
| `request`                                                                                                    | [components.V3IncidentsIngestionStatusRequest](../../models/components/v3incidentsingestionstatusrequest.md) | :heavy_check_mark:                                                                                           | The request object to use for the request.                                                                   |
| `opts`                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                     | :heavy_minus_sign:                                                                                           | The options for this request.                                                                                |

### Response

**[*operations.IncidentsGetIncidentsStatusByRequestidsResponse](../../models/operations/incidentsgetincidentsstatusbyrequestidsresponse.md), error**

### Errors

| Error Type                                                                | Status Code                                                               | Content Type                                                              |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| apierrors.IncidentsGetIncidentsStatusByRequestidsBadRequestError          | 400                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsUnauthorizedError        | 401                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsPaymentRequiredError     | 402                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsForbiddenError           | 403                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsNotFoundError            | 404                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsConflictError            | 409                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsUnprocessableEntityError | 422                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsInternalServerError      | 500                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsBadGatewayError          | 502                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsServiceUnavailableError  | 503                                                                       | application/json                                                          |
| apierrors.IncidentsGetIncidentsStatusByRequestidsGatewayTimeoutError      | 504                                                                       | application/json                                                          |
| apierrors.APIError                                                        | 4XX, 5XX                                                                  | \*/\*                                                                     |