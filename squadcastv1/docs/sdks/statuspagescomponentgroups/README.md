# StatusPagesComponentGroups
(*StatusPagesComponentGroups*)

## Overview

### Available Operations

* [ComponentGroupsListComponentGroups](#componentgroupslistcomponentgroups) - List Component Groups
* [ComponentGroupsCreateComponentGroup](#componentgroupscreatecomponentgroup) - Create Component Group
* [ComponentGroupsDeleteComponentGroupByID](#componentgroupsdeletecomponentgroupbyid) - Delete Component Group By ID
* [ComponentGroupsGetComponentGroupByID](#componentgroupsgetcomponentgroupbyid) - Get Component Group By ID

## ComponentGroupsListComponentGroups

List Component Groups

### Example Usage

<!-- UsageSnippet language="go" operationID="ComponentGroups_listComponentGroups" method="get" path="/v4/statuspages/{statuspageID}/groups" -->
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

    res, err := s.StatusPagesComponentGroups.ComponentGroupsListComponentGroups(ctx, "<id>")
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
| `statuspageID`                                           | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ComponentGroupsListComponentGroupsResponse](../../models/operations/componentgroupslistcomponentgroupsresponse.md), error**

### Errors

| Error Type                                                           | Status Code                                                          | Content Type                                                         |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| apierrors.ComponentGroupsListComponentGroupsBadRequestError          | 400                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsUnauthorizedError        | 401                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsPaymentRequiredError     | 402                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsForbiddenError           | 403                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsNotFoundError            | 404                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsConflictError            | 409                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsUnprocessableEntityError | 422                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsInternalServerError      | 500                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsBadGatewayError          | 502                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsServiceUnavailableError  | 503                                                                  | application/json                                                     |
| apierrors.ComponentGroupsListComponentGroupsGatewayTimeoutError      | 504                                                                  | application/json                                                     |
| apierrors.APIError                                                   | 4XX, 5XX                                                             | \*/\*                                                                |

## ComponentGroupsCreateComponentGroup

Create Component Group

### Example Usage

<!-- UsageSnippet language="go" operationID="ComponentGroups_createComponentGroup" method="post" path="/v4/statuspages/{statuspageID}/groups" -->
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

    res, err := s.StatusPagesComponentGroups.ComponentGroupsCreateComponentGroup(ctx, "<id>", components.V4StatusPagesComponentGroupsCreateComponentGroupRequest{
        Name: "<value>",
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
| `statuspageID`                                                                                                                                           | *string*                                                                                                                                                 | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `v4StatusPagesComponentGroupsCreateComponentGroupRequest`                                                                                                | [components.V4StatusPagesComponentGroupsCreateComponentGroupRequest](../../models/components/v4statuspagescomponentgroupscreatecomponentgrouprequest.md) | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `opts`                                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                                 | :heavy_minus_sign:                                                                                                                                       | The options for this request.                                                                                                                            |

### Response

**[*operations.ComponentGroupsCreateComponentGroupResponse](../../models/operations/componentgroupscreatecomponentgroupresponse.md), error**

### Errors

| Error Type                                                            | Status Code                                                           | Content Type                                                          |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| apierrors.ComponentGroupsCreateComponentGroupBadRequestError          | 400                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupUnauthorizedError        | 401                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupPaymentRequiredError     | 402                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupForbiddenError           | 403                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupNotFoundError            | 404                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupConflictError            | 409                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupUnprocessableEntityError | 422                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupInternalServerError      | 500                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupBadGatewayError          | 502                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupServiceUnavailableError  | 503                                                                   | application/json                                                      |
| apierrors.ComponentGroupsCreateComponentGroupGatewayTimeoutError      | 504                                                                   | application/json                                                      |
| apierrors.APIError                                                    | 4XX, 5XX                                                              | \*/\*                                                                 |

## ComponentGroupsDeleteComponentGroupByID

Delete Component Group By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="ComponentGroups_deleteComponentGroupById" method="delete" path="/v4/statuspages/{statuspageID}/groups/{group_id}" -->
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

    res, err := s.StatusPagesComponentGroups.ComponentGroupsDeleteComponentGroupByID(ctx, "<id>", "<id>")
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
| `statuspageID`                                           | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `groupID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ComponentGroupsDeleteComponentGroupByIDResponse](../../models/operations/componentgroupsdeletecomponentgroupbyidresponse.md), error**

### Errors

| Error Type                                                                | Status Code                                                               | Content Type                                                              |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| apierrors.ComponentGroupsDeleteComponentGroupByIDBadRequestError          | 400                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDUnauthorizedError        | 401                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDPaymentRequiredError     | 402                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDForbiddenError           | 403                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDNotFoundError            | 404                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDConflictError            | 409                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDUnprocessableEntityError | 422                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDInternalServerError      | 500                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDBadGatewayError          | 502                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDServiceUnavailableError  | 503                                                                       | application/json                                                          |
| apierrors.ComponentGroupsDeleteComponentGroupByIDGatewayTimeoutError      | 504                                                                       | application/json                                                          |
| apierrors.APIError                                                        | 4XX, 5XX                                                                  | \*/\*                                                                     |

## ComponentGroupsGetComponentGroupByID

Get Component Group By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="ComponentGroups_getComponentGroupById" method="get" path="/v4/statuspages/{statuspageID}/groups/{group_id}" -->
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

    res, err := s.StatusPagesComponentGroups.ComponentGroupsGetComponentGroupByID(ctx, "<id>", "<id>")
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
| `statuspageID`                                           | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `groupID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ComponentGroupsGetComponentGroupByIDResponse](../../models/operations/componentgroupsgetcomponentgroupbyidresponse.md), error**

### Errors

| Error Type                                                             | Status Code                                                            | Content Type                                                           |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| apierrors.ComponentGroupsGetComponentGroupByIDBadRequestError          | 400                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDUnauthorizedError        | 401                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDPaymentRequiredError     | 402                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDForbiddenError           | 403                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDNotFoundError            | 404                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDConflictError            | 409                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDUnprocessableEntityError | 422                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDInternalServerError      | 500                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDBadGatewayError          | 502                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDServiceUnavailableError  | 503                                                                    | application/json                                                       |
| apierrors.ComponentGroupsGetComponentGroupByIDGatewayTimeoutError      | 504                                                                    | application/json                                                       |
| apierrors.APIError                                                     | 4XX, 5XX                                                               | \*/\*                                                                  |