# IncidentsTags
(*IncidentsTags*)

## Overview

### Available Operations

* [TagsUpdateTag](#tagsupdatetag) - Update Tag
* [TagsAppendTag](#tagsappendtag) - Append Tag

## TagsUpdateTag

Update Tag

### Example Usage

<!-- UsageSnippet language="go" operationID="Tags_updateTag" method="put" path="/v3/incidents/{IncidentId}/tags" -->
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

    res, err := s.IncidentsTags.TagsUpdateTag(ctx, "<id>", components.V3IncidentsTagsUpdateTagRequest{
        Tags: components.V3IncidentsTagsUpdateTagRequestTags{},
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

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                    | :heavy_check_mark:                                                                                       | The context to use for the request.                                                                      |
| `incidentID`                                                                                             | *string*                                                                                                 | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `v3IncidentsTagsUpdateTagRequest`                                                                        | [components.V3IncidentsTagsUpdateTagRequest](../../models/components/v3incidentstagsupdatetagrequest.md) | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `opts`                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                 | :heavy_minus_sign:                                                                                       | The options for this request.                                                                            |

### Response

**[*operations.TagsUpdateTagResponse](../../models/operations/tagsupdatetagresponse.md), error**

### Errors

| Error Type                                      | Status Code                                     | Content Type                                    |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| apierrors.TagsUpdateTagBadRequestError          | 400                                             | application/json                                |
| apierrors.TagsUpdateTagUnauthorizedError        | 401                                             | application/json                                |
| apierrors.TagsUpdateTagPaymentRequiredError     | 402                                             | application/json                                |
| apierrors.TagsUpdateTagForbiddenError           | 403                                             | application/json                                |
| apierrors.TagsUpdateTagNotFoundError            | 404                                             | application/json                                |
| apierrors.TagsUpdateTagConflictError            | 409                                             | application/json                                |
| apierrors.TagsUpdateTagUnprocessableEntityError | 422                                             | application/json                                |
| apierrors.TagsUpdateTagInternalServerError      | 500                                             | application/json                                |
| apierrors.TagsUpdateTagBadGatewayError          | 502                                             | application/json                                |
| apierrors.TagsUpdateTagServiceUnavailableError  | 503                                             | application/json                                |
| apierrors.TagsUpdateTagGatewayTimeoutError      | 504                                             | application/json                                |
| apierrors.APIError                              | 4XX, 5XX                                        | \*/\*                                           |

## TagsAppendTag

Append Tag

### Example Usage

<!-- UsageSnippet language="go" operationID="Tags_appendTag" method="patch" path="/v3/incidents/{IncidentId}/tags" -->
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

    res, err := s.IncidentsTags.TagsAppendTag(ctx, "<id>", components.V3IncidentsTagsAppendTagRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                    | :heavy_check_mark:                                                                                       | The context to use for the request.                                                                      |
| `incidentID`                                                                                             | *string*                                                                                                 | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `v3IncidentsTagsAppendTagRequest`                                                                        | [components.V3IncidentsTagsAppendTagRequest](../../models/components/v3incidentstagsappendtagrequest.md) | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `opts`                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                 | :heavy_minus_sign:                                                                                       | The options for this request.                                                                            |

### Response

**[*operations.TagsAppendTagResponse](../../models/operations/tagsappendtagresponse.md), error**

### Errors

| Error Type                                      | Status Code                                     | Content Type                                    |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| apierrors.TagsAppendTagBadRequestError          | 400                                             | application/json                                |
| apierrors.TagsAppendTagUnauthorizedError        | 401                                             | application/json                                |
| apierrors.TagsAppendTagPaymentRequiredError     | 402                                             | application/json                                |
| apierrors.TagsAppendTagForbiddenError           | 403                                             | application/json                                |
| apierrors.TagsAppendTagNotFoundError            | 404                                             | application/json                                |
| apierrors.TagsAppendTagConflictError            | 409                                             | application/json                                |
| apierrors.TagsAppendTagUnprocessableEntityError | 422                                             | application/json                                |
| apierrors.TagsAppendTagInternalServerError      | 500                                             | application/json                                |
| apierrors.TagsAppendTagBadGatewayError          | 502                                             | application/json                                |
| apierrors.TagsAppendTagServiceUnavailableError  | 503                                             | application/json                                |
| apierrors.TagsAppendTagGatewayTimeoutError      | 504                                             | application/json                                |
| apierrors.APIError                              | 4XX, 5XX                                        | \*/\*                                           |