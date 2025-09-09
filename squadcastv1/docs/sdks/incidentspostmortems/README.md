# IncidentsPostmortems
(*IncidentsPostmortems*)

## Overview

### Available Operations

* [PostmortemsGetAllPostmortems](#postmortemsgetallpostmortems) - Get All Postmortems
* [PostmortemsDeletePostmortemByIncident](#postmortemsdeletepostmortembyincident) - Delete Postmortem By Incident
* [PostmortemsGetPostmortemByIncident](#postmortemsgetpostmortembyincident) - Get Postmortem By Incident
* [PostmortemsCreatePostmortem](#postmortemscreatepostmortem) - Create Postmortem
* [PostmortemsUpdatePostmortemByIncident](#postmortemsupdatepostmortembyincident) - Update Postmortem By Incident

## PostmortemsGetAllPostmortems

*   This endpoint is used to get all postmortems.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Postmortems_getAllPostmortems" method="get" path="/v3/incidents/postmortem" -->
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

    res, err := s.IncidentsPostmortems.PostmortemsGetAllPostmortems(ctx, "<value>", "<value>", "<id>", 221553)
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
| `fromDate`                                               | *string*                                                 | :heavy_check_mark:                                       | Provide date in RFC3339 format                           |
| `toDate`                                                 | *string*                                                 | :heavy_check_mark:                                       | Provide date in RFC3339 format                           |
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | Here owner_id represents team_id                         |
| `limit`                                                  | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.PostmortemsGetAllPostmortemsResponse](../../models/operations/postmortemsgetallpostmortemsresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.PostmortemsGetAllPostmortemsBadRequestError          | 400                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsForbiddenError           | 403                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsNotFoundError            | 404                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsConflictError            | 409                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsInternalServerError      | 500                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.PostmortemsGetAllPostmortemsGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## PostmortemsDeletePostmortemByIncident

*   This endpoint is used to delete a postmortem by incident.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Postmortems_deletePostmortemByIncident" method="delete" path="/v3/incidents/{incidentID}/postmortem" -->
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

    res, err := s.IncidentsPostmortems.PostmortemsDeletePostmortemByIncident(ctx, "<id>")
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

## PostmortemsGetPostmortemByIncident

*   This endpoint is used to get a postmortem by incident.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Postmortems_getPostmortemByIncident" method="get" path="/v3/incidents/{incidentID}/postmortem" -->
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

    res, err := s.IncidentsPostmortems.PostmortemsGetPostmortemByIncident(ctx, "<id>")
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

## PostmortemsCreatePostmortem

*   This endpoint is used to create a postmortem.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Postmortems_createPostmortem" method="post" path="/v3/incidents/{incidentID}/postmortem" -->
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

    res, err := s.IncidentsPostmortems.PostmortemsCreatePostmortem(ctx, "<id>", components.V3IncidentsPostmortemsCreatePostmortemRequest{
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

## PostmortemsUpdatePostmortemByIncident

- This endpoint is used to update a postmortem by incident.
- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Postmortems_updatePostmortemByIncident" method="put" path="/v3/incidents/{incidentID}/postmortem" -->
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

    res, err := s.IncidentsPostmortems.PostmortemsUpdatePostmortemByIncident(ctx, "<id>", components.V3IncidentsPostmortemsUpdatePostmortemRequest{})
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
| `v3IncidentsPostmortemsUpdatePostmortemRequest`                                                                                      | [components.V3IncidentsPostmortemsUpdatePostmortemRequest](../../models/components/v3incidentspostmortemsupdatepostmortemrequest.md) | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `opts`                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                             | :heavy_minus_sign:                                                                                                                   | The options for this request.                                                                                                        |

### Response

**[*operations.PostmortemsUpdatePostmortemByIncidentResponse](../../models/operations/postmortemsupdatepostmortembyincidentresponse.md), error**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| apierrors.PostmortemsUpdatePostmortemByIncidentBadRequestError          | 400                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentUnauthorizedError        | 401                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentPaymentRequiredError     | 402                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentForbiddenError           | 403                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentNotFoundError            | 404                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentConflictError            | 409                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentUnprocessableEntityError | 422                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentInternalServerError      | 500                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentBadGatewayError          | 502                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentServiceUnavailableError  | 503                                                                     | application/json                                                        |
| apierrors.PostmortemsUpdatePostmortemByIncidentGatewayTimeoutError      | 504                                                                     | application/json                                                        |
| apierrors.APIError                                                      | 4XX, 5XX                                                                | \*/\*                                                                   |