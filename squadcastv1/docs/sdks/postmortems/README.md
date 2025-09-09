# Postmortems
(*Incidents.Postmortems*)

## Overview

### Available Operations

* [DeleteByIncident](#deletebyincident) - Delete Postmortem By Incident
* [GetByIncident](#getbyincident) - Get Postmortem By Incident
* [Create](#create) - Create Postmortem

## DeleteByIncident

*   This endpoint is used to delete a postmortem by incident.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Postmortems_deletePostmortemByIncident" method="delete" path="/v3/incidents/{incidentID}/postmortem" -->
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

    res, err := s.Incidents.Postmortems.DeleteByIncident(ctx, "<id>")
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

**[*operations.PostmortemsDeletePostmortemByIncidentResponse](../../models/operations/postmortemsdeletepostmortembyincidentresponse.md), error**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| apierrors.PostmortemsDeletePostmortemByIncidentBadRequestError          | 400                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentUnauthorizedError        | 401                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentPaymentRequiredError     | 402                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentForbiddenError           | 403                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentNotFoundError            | 404                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentConflictError            | 409                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentUnprocessableEntityError | 422                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentInternalServerError      | 500                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentBadGatewayError          | 502                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentServiceUnavailableError  | 503                                                                     | application/json                                                        |
| apierrors.PostmortemsDeletePostmortemByIncidentGatewayTimeoutError      | 504                                                                     | application/json                                                        |
| apierrors.APIError                                                      | 4XX, 5XX                                                                | \*/\*                                                                   |

## GetByIncident

*   This endpoint is used to get a postmortem by incident.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Postmortems_getPostmortemByIncident" method="get" path="/v3/incidents/{incidentID}/postmortem" -->
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

    res, err := s.Incidents.Postmortems.GetByIncident(ctx, "<id>")
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

**[*operations.PostmortemsGetPostmortemByIncidentResponse](../../models/operations/postmortemsgetpostmortembyincidentresponse.md), error**

### Errors

| Error Type                                                           | Status Code                                                          | Content Type                                                         |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| apierrors.PostmortemsGetPostmortemByIncidentBadRequestError          | 400                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentUnauthorizedError        | 401                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentPaymentRequiredError     | 402                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentForbiddenError           | 403                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentNotFoundError            | 404                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentConflictError            | 409                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentUnprocessableEntityError | 422                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentInternalServerError      | 500                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentBadGatewayError          | 502                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentServiceUnavailableError  | 503                                                                  | application/json                                                     |
| apierrors.PostmortemsGetPostmortemByIncidentGatewayTimeoutError      | 504                                                                  | application/json                                                     |
| apierrors.APIError                                                   | 4XX, 5XX                                                             | \*/\*                                                                |

## Create

*   This endpoint is used to create a postmortem.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Postmortems_createPostmortem" method="post" path="/v3/incidents/{incidentID}/postmortem" -->
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

    res, err := s.Incidents.Postmortems.Create(ctx, "<id>", components.V3IncidentsPostmortemsCreatePostmortemRequest{
        OwnerID: "<id>",
        Title: "<value>",
        Postmortem: "<value>",
        Status: components.V3IncidentsPostmortemsPostmortemStatusPublished,
        FollowUps: []components.V3IncidentsPostmortemsPostmortemFollowUp{},
        Attachments: []components.V3IncidentsPostmortemsPostmortemAttachmentRequest{
            components.V3IncidentsPostmortemsPostmortemAttachmentRequest{},
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

| Parameter                                                                                                                            | Type                                                                                                                                 | Required                                                                                                                             | Description                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                | :heavy_check_mark:                                                                                                                   | The context to use for the request.                                                                                                  |
| `incidentID`                                                                                                                         | *string*                                                                                                                             | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `v3IncidentsPostmortemsCreatePostmortemRequest`                                                                                      | [components.V3IncidentsPostmortemsCreatePostmortemRequest](../../models/components/v3incidentspostmortemscreatepostmortemrequest.md) | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `opts`                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                             | :heavy_minus_sign:                                                                                                                   | The options for this request.                                                                                                        |

### Response

**[*operations.PostmortemsCreatePostmortemResponse](../../models/operations/postmortemscreatepostmortemresponse.md), error**

### Errors

| Error Type                                                    | Status Code                                                   | Content Type                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| apierrors.PostmortemsCreatePostmortemBadRequestError          | 400                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemUnauthorizedError        | 401                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemPaymentRequiredError     | 402                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemForbiddenError           | 403                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemNotFoundError            | 404                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemConflictError            | 409                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemUnprocessableEntityError | 422                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemInternalServerError      | 500                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemBadGatewayError          | 502                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemServiceUnavailableError  | 503                                                           | application/json                                              |
| apierrors.PostmortemsCreatePostmortemGatewayTimeoutError      | 504                                                           | application/json                                              |
| apierrors.APIError                                            | 4XX, 5XX                                                      | \*/\*                                                         |