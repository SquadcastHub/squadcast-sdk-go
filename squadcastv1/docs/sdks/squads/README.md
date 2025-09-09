# Squads
(*Squads*)

## Overview

### Available Operations

* [Create](#create) - Create Squad
* [Delete](#delete) - Delete Squad
* [GetByID](#getbyid) - Get Squad By ID
* [Update](#update) - Update Squad
* [List](#list) - Get All Squads
* [RemoveMember](#removemember) - Remove Squad Member
* [UpdateMemberRole](#updatememberrole) - Update Squad Member
* [UpdateName](#updatename) - Update Squad Name

## Create

This endpoint is used to create a new squad.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-create` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_createSquad" method="post" path="/v3/squads" -->
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

    res, err := s.Squads.Create(ctx, components.V3SquadsCreateSquadRequest{
        Name: "<value>",
        Members: []string{
            "<value 1>",
        },
        OwnerID: "<id>",
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
| `request`                                                                                      | [components.V3SquadsCreateSquadRequest](../../models/components/v3squadscreatesquadrequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.SquadsCreateSquadResponse](../../models/operations/squadscreatesquadresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.SquadsCreateSquadBadRequestError          | 400                                                 | application/json                                    |
| apierrors.SquadsCreateSquadUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.SquadsCreateSquadPaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.SquadsCreateSquadForbiddenError           | 403                                                 | application/json                                    |
| apierrors.SquadsCreateSquadNotFoundError            | 404                                                 | application/json                                    |
| apierrors.SquadsCreateSquadConflictError            | 409                                                 | application/json                                    |
| apierrors.SquadsCreateSquadUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.SquadsCreateSquadInternalServerError      | 500                                                 | application/json                                    |
| apierrors.SquadsCreateSquadBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.SquadsCreateSquadServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.SquadsCreateSquadGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

## Delete

This endpoint is used to delete the squad. Squad should not be assigned to any incident or part of any escalation policy.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-update` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_deleteSquad" method="delete" path="/v3/squads/{squadID}" -->
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

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.SquadsDeleteSquadBadRequestError          | 400                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadPaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadForbiddenError           | 403                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadNotFoundError            | 404                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadConflictError            | 409                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadInternalServerError      | 500                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.SquadsDeleteSquadGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

## GetByID

This endpoint is used to get the squads details by id.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_getSquadById" method="get" path="/v3/squads/{squadID}" -->
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

    res, err := s.Squads.GetByID(ctx, "<id>")
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

**[*operations.SquadsGetSquadByIDResponse](../../models/operations/squadsgetsquadbyidresponse.md), error**

### Errors

| Error Type                                           | Status Code                                          | Content Type                                         |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| apierrors.SquadsGetSquadByIDBadRequestError          | 400                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDUnauthorizedError        | 401                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDPaymentRequiredError     | 402                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDForbiddenError           | 403                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDNotFoundError            | 404                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDConflictError            | 409                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDUnprocessableEntityError | 422                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDInternalServerError      | 500                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDBadGatewayError          | 502                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDServiceUnavailableError  | 503                                                  | application/json                                     |
| apierrors.SquadsGetSquadByIDGatewayTimeoutError      | 504                                                  | application/json                                     |
| apierrors.APIError                                   | 4XX, 5XX                                             | \*/\*                                                |

## Update

This endpoint is used to update the squads details.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `squad-update` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Squads_updateSquad" method="put" path="/v3/squads/{squadID}" -->
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

    res, err := s.Squads.Update(ctx, "<id>", components.V3SquadsUpdateSquadRequest{})
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
| `v3SquadsUpdateSquadRequest`                                                                   | [components.V3SquadsUpdateSquadRequest](../../models/components/v3squadsupdatesquadrequest.md) | :heavy_check_mark:                                                                             | N/A                                                                                            |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.SquadsUpdateSquadResponse](../../models/operations/squadsupdatesquadresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.SquadsUpdateSquadBadRequestError          | 400                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadPaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadForbiddenError           | 403                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadNotFoundError            | 404                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadConflictError            | 409                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadInternalServerError      | 500                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.SquadsUpdateSquadGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"log"
)

func main() {
    ctx := context.Background()

    s := squadcastsdk.New(
        squadcastsdk.WithSecurity(os.Getenv("SQUADCASTSDK_BEARER_AUTH")),
    )

    res, err := s.Squads.List(ctx)
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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/components"
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
	squadcastsdk "github.com/SquadcastHub/squadcast-sdk-go/squadcastv1"
	"github.com/SquadcastHub/squadcast-sdk-go/squadcastv1/models/components"
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