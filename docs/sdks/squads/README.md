# Squads
(*Squads*)

## Overview

### Available Operations

* [List](#list) - Get All Squads
* [RemoveMember](#removemember) - Remove Squad Member
* [UpdateMemberRole](#updatememberrole) - Update Squad Member
* [UpdateName](#updatename) - Update Squad Name
* [Delete](#delete) - Delete Squad

## List

This endpoint is used to get all the squads details of your organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_getAllSquads" method="get" path="/v4/squads" -->
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

    res, err := s.Squads.List(ctx, "<id>")
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
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SquadsGetAllSquadsResponse](../../models/operations/squadsgetallsquadsresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## RemoveMember

This endpoint is used to update squad member's role.

If you're attempting to remove a member whose role is 'owner', and that 'owner' is the last squad owner, then the 'replaceWith' query parameter is required. Setting 'replaceWith' to 'member' will promote another member as the owner, and the specified member will be removed.

Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-create` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_removeSquadMember" method="delete" path="/v4/squads/{squadID}/members/{memberID}" -->
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

    res, err := s.Squads.RemoveMember(ctx, "<id>", "<id>", "<value>")
    if err != nil {
        log.Fatal(err)
    }
    if res.V4SquadsRemoveSquadMemberResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `squadID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `memberID`                                               | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `replaceWith`                                            | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SquadsRemoveSquadMemberResponse](../../models/operations/squadsremovesquadmemberresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## UpdateMemberRole

This endpoint is used to update a squad member's role and is only accessible if your organization is using the OBAC permission model.

If you're attempting to update a member's role from 'owner' to 'member', and that 'owner' is the last squad owner, then the 'replaceWith' query parameter is required. Setting 'replaceWith' to 'member' will promote the member to the role of owner.

Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-create` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_updateSquadMember" method="put" path="/v4/squads/{squadID}/members/{memberID}" -->
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

    res, err := s.Squads.UpdateMemberRole(ctx, "<id>", "<id>", "<value>", components.V4SquadsUpdateSquadMemberRequest{
        Role: "<value>",
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.V4SquadsUpdateSquadMemberResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                  | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                                      | :heavy_check_mark:                                                                                         | The context to use for the request.                                                                        |
| `squadID`                                                                                                  | *string*                                                                                                   | :heavy_check_mark:                                                                                         | N/A                                                                                                        |
| `memberID`                                                                                                 | *string*                                                                                                   | :heavy_check_mark:                                                                                         | N/A                                                                                                        |
| `replaceWith`                                                                                              | *string*                                                                                                   | :heavy_check_mark:                                                                                         | N/A                                                                                                        |
| `v4SquadsUpdateSquadMemberRequest`                                                                         | [components.V4SquadsUpdateSquadMemberRequest](../../models/components/v4squadsupdatesquadmemberrequest.md) | :heavy_check_mark:                                                                                         | N/A                                                                                                        |
| `opts`                                                                                                     | [][operations.Option](../../models/operations/option.md)                                                   | :heavy_minus_sign:                                                                                         | The options for this request.                                                                              |

### Response

**[*operations.SquadsUpdateSquadMemberResponse](../../models/operations/squadsupdatesquadmemberresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## UpdateName

This endpoint is used to update squad's name.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-create` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_updateSquadName" method="put" path="/v4/squads/{squadID}/name" -->
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

    res, err := s.Squads.UpdateName(ctx, "<id>", components.V4SquadsUpdateSquadNameRequest{
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

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `squadID`                                                                                              | *string*                                                                                               | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `v4SquadsUpdateSquadNameRequest`                                                                       | [components.V4SquadsUpdateSquadNameRequest](../../models/components/v4squadsupdatesquadnamerequest.md) | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.SquadsUpdateSquadNameResponse](../../models/operations/squadsupdatesquadnameresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## Delete

This endpoint is used to delete the squad. Squad should not be assigned to any incident or part of any escalation policy.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-update` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_deleteSquad" method="delete" path="/v4/squads/{squadID}" -->
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

    res, err := s.Squads.Delete(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.Body != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `squadID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SquadsDeleteSquadResponse](../../models/operations/squadsdeletesquadresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |