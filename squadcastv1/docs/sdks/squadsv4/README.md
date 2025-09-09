# SquadsV4
(*SquadsV4*)

## Overview

### Available Operations

* [SquadsGetAllSquads](#squadsgetallsquads) - Get All Squads
* [SquadsCreateSquadV4](#squadscreatesquadv4) - Create Squad
* [SquadsGetSquadByIDV4](#squadsgetsquadbyidv4) - Get Squad By ID
* [SquadsUpdateSquadV4](#squadsupdatesquadv4) - Update Squad
* [SquadsRemoveSquadMember](#squadsremovesquadmember) - Remove Squad Member
* [SquadsUpdateSquadMember](#squadsupdatesquadmember) - Update Squad Member
* [SquadsUpdateSquadName](#squadsupdatesquadname) - Update Squad Name

## SquadsGetAllSquads

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

    res, err := s.SquadsV4.SquadsGetAllSquads(ctx)
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
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SquadsGetAllSquadsResponse](../../models/operations/squadsgetallsquadsresponse.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## SquadsCreateSquadV4

This endpoint is used to create a new squad.
The role will be considered only if your organization is on the OBAC permission model; otherwise, the role field will be ignored, and only the member will be added to the squad.

Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-create` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_createSquadV4" method="post" path="/v4/squads" -->
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

    res, err := s.SquadsV4.SquadsCreateSquadV4(ctx, components.V4SquadsCreateSquadRequest{
        OwnerID: "<id>",
        Name: "<value>",
        Members: []components.V4SquadsSquadMember{
            components.V4SquadsSquadMember{
                UserID: "<id>",
            },
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

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `request`                                                                                      | [components.V4SquadsCreateSquadRequest](../../models/components/v4squadscreatesquadrequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.SquadsCreateSquadV4Response](../../models/operations/squadscreatesquadv4response.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## SquadsGetSquadByIDV4

This endpoint is used to get the squads details by id.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_getSquadByIdV4" method="get" path="/v4/squads/{squadID}" -->
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

    res, err := s.SquadsV4.SquadsGetSquadByIDV4(ctx, "<id>")
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
| `squadID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.SquadsGetSquadByIDV4Response](../../models/operations/squadsgetsquadbyidv4response.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## SquadsUpdateSquadV4

This endpoint is used to update squad.

The role will be considered only if your organization is on the OBAC permission model; otherwise, the role field will be ignored, and only the member will be added to the squad.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-create` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_updateSquadV4" method="put" path="/v4/squads/{squadID}" -->
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

    res, err := s.SquadsV4.SquadsUpdateSquadV4(ctx, "<id>", components.V4SquadsUpdateSquadRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `squadID`                                                                                      | *string*                                                                                       | :heavy_check_mark:                                                                             | N/A                                                                                            |
| `v4SquadsUpdateSquadRequest`                                                                   | [components.V4SquadsUpdateSquadRequest](../../models/components/v4squadsupdatesquadrequest.md) | :heavy_check_mark:                                                                             | N/A                                                                                            |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.SquadsUpdateSquadV4Response](../../models/operations/squadsupdatesquadv4response.md), error**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| apierrors.CommonV4Error           | 400, 401, 402, 403, 404, 409, 422 | application/json                  |
| apierrors.CommonV4Error           | 500, 502, 503, 504                | application/json                  |
| apierrors.APIError                | 4XX, 5XX                          | \*/\*                             |

## SquadsRemoveSquadMember

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

    res, err := s.SquadsV4.SquadsRemoveSquadMember(ctx, "<id>", "<id>", "<value>")
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

## SquadsUpdateSquadMember

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

    res, err := s.SquadsV4.SquadsUpdateSquadMember(ctx, "<id>", "<id>", "<value>", components.V4SquadsUpdateSquadMemberRequest{
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

## SquadsUpdateSquadName

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

    res, err := s.SquadsV4.SquadsUpdateSquadName(ctx, "<id>", components.V4SquadsUpdateSquadNameRequest{
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