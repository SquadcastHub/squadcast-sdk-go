# Users
(*Users*)

## Overview

### Available Operations

* [GetAll](#getall) - Get All Users
* [Add](#add) - Add User
* [UpdateOrgLevelPermissions](#updateorglevelpermissions) - Update Org Level Permissions
* [Delete](#delete) - Delete User
* [GetRoles](#getroles) - Get User Roles
* [RemoveFromOrg](#removefromorg) - Remove User From Org
* [GetByID](#getbyid) - Get User By ID
* [Update](#update) - Update User by userID

## GetAll

Returns all the users of the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_getAllUsers" method="get" path="/v3/users" -->
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

    res, err := s.Users.GetAll(ctx)
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

**[*operations.UsersGetAllUsersResponse](../../models/operations/usersgetallusersresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.UsersGetAllUsersBadRequestError          | 400                                                | application/json                                   |
| apierrors.UsersGetAllUsersUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.UsersGetAllUsersPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.UsersGetAllUsersForbiddenError           | 403                                                | application/json                                   |
| apierrors.UsersGetAllUsersNotFoundError            | 404                                                | application/json                                   |
| apierrors.UsersGetAllUsersConflictError            | 409                                                | application/json                                   |
| apierrors.UsersGetAllUsersUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.UsersGetAllUsersInternalServerError      | 500                                                | application/json                                   |
| apierrors.UsersGetAllUsersBadGatewayError          | 502                                                | application/json                                   |
| apierrors.UsersGetAllUsersServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.UsersGetAllUsersGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |

## Add

Add user to the organization with given role if not exists. Returns the user object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_addUser" method="post" path="/v3/users" -->
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

    res, err := s.Users.Add(ctx, components.V3UsersAddUserRequest{
        Email: "Clovis_Reynolds@hotmail.com",
        Role: components.V3UsersAddUserRequestRoleAccountOwner,
        FirstName: "Yvonne",
        LastName: "Kozey",
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

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `request`                                                                            | [components.V3UsersAddUserRequest](../../models/components/v3usersadduserrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |
| `opts`                                                                               | [][operations.Option](../../models/operations/option.md)                             | :heavy_minus_sign:                                                                   | The options for this request.                                                        |

### Response

**[*operations.UsersAddUserResponse](../../models/operations/usersadduserresponse.md), error**

### Errors

| Error Type                                     | Status Code                                    | Content Type                                   |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| apierrors.UsersAddUserBadRequestError          | 400                                            | application/json                               |
| apierrors.UsersAddUserUnauthorizedError        | 401                                            | application/json                               |
| apierrors.UsersAddUserPaymentRequiredError     | 402                                            | application/json                               |
| apierrors.UsersAddUserForbiddenError           | 403                                            | application/json                               |
| apierrors.UsersAddUserNotFoundError            | 404                                            | application/json                               |
| apierrors.UsersAddUserConflictError            | 409                                            | application/json                               |
| apierrors.UsersAddUserUnprocessableEntityError | 422                                            | application/json                               |
| apierrors.UsersAddUserInternalServerError      | 500                                            | application/json                               |
| apierrors.UsersAddUserBadGatewayError          | 502                                            | application/json                               |
| apierrors.UsersAddUserServiceUnavailableError  | 503                                            | application/json                               |
| apierrors.UsersAddUserGatewayTimeoutError      | 504                                            | application/json                               |
| apierrors.APIError                             | 4XX, 5XX                                       | \*/\*                                          |

## UpdateOrgLevelPermissions

Update Org Level Permissions

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_updateOrgLevelPermissions" method="put" path="/v3/users/abilities" -->
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

    res, err := s.Users.UpdateOrgLevelPermissions(ctx, components.V3UsersUpdateUserAbilitiesRequest{
        Data: []components.V3UsersUpdateUserAbilitiesRequestData{},
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
| `request`                                                                                                    | [components.V3UsersUpdateUserAbilitiesRequest](../../models/components/v3usersupdateuserabilitiesrequest.md) | :heavy_check_mark:                                                                                           | The request object to use for the request.                                                                   |
| `opts`                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                     | :heavy_minus_sign:                                                                                           | The options for this request.                                                                                |

### Response

**[*operations.UsersUpdateOrgLevelPermissionsResponse](../../models/operations/usersupdateorglevelpermissionsresponse.md), error**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| apierrors.UsersUpdateOrgLevelPermissionsBadRequestError          | 400                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsUnauthorizedError        | 401                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsPaymentRequiredError     | 402                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsForbiddenError           | 403                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsNotFoundError            | 404                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsConflictError            | 409                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsUnprocessableEntityError | 422                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsInternalServerError      | 500                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsBadGatewayError          | 502                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsServiceUnavailableError  | 503                                                              | application/json                                                 |
| apierrors.UsersUpdateOrgLevelPermissionsGatewayTimeoutError      | 504                                                              | application/json                                                 |
| apierrors.APIError                                               | 4XX, 5XX                                                         | \*/\*                                                            |

## Delete

This API replaces the swap_user for all the entities in Squadcast with user_id provided and deletes the user.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_deleteUser" method="put" path="/v3/users/delete-user" -->
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

    res, err := s.Users.Delete(ctx, operations.UsersDeleteUserRequest{
        UserID: "<id>",
        SwapUserID: "<id>",
        SuppressIncidents: true,
        ReassignIncidents: true,
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

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `ctx`                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                  | :heavy_check_mark:                                                                     | The context to use for the request.                                                    |
| `request`                                                                              | [operations.UsersDeleteUserRequest](../../models/operations/usersdeleteuserrequest.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |
| `opts`                                                                                 | [][operations.Option](../../models/operations/option.md)                               | :heavy_minus_sign:                                                                     | The options for this request.                                                          |

### Response

**[*operations.UsersDeleteUserResponse](../../models/operations/usersdeleteuserresponse.md), error**

### Errors

| Error Type                                        | Status Code                                       | Content Type                                      |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| apierrors.UsersDeleteUserBadRequestError          | 400                                               | application/json                                  |
| apierrors.UsersDeleteUserUnauthorizedError        | 401                                               | application/json                                  |
| apierrors.UsersDeleteUserPaymentRequiredError     | 402                                               | application/json                                  |
| apierrors.UsersDeleteUserForbiddenError           | 403                                               | application/json                                  |
| apierrors.UsersDeleteUserNotFoundError            | 404                                               | application/json                                  |
| apierrors.UsersDeleteUserConflictError            | 409                                               | application/json                                  |
| apierrors.UsersDeleteUserUnprocessableEntityError | 422                                               | application/json                                  |
| apierrors.UsersDeleteUserInternalServerError      | 500                                               | application/json                                  |
| apierrors.UsersDeleteUserBadGatewayError          | 502                                               | application/json                                  |
| apierrors.UsersDeleteUserServiceUnavailableError  | 503                                               | application/json                                  |
| apierrors.UsersDeleteUserGatewayTimeoutError      | 504                                               | application/json                                  |
| apierrors.APIError                                | 4XX, 5XX                                          | \*/\*                                             |

## GetRoles

Returns all available user roles.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_getUserRoles" method="get" path="/v3/users/roles" -->
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

    res, err := s.Users.GetRoles(ctx)
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

**[*operations.UsersGetUserRolesResponse](../../models/operations/usersgetuserrolesresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.UsersGetUserRolesBadRequestError          | 400                                                 | application/json                                    |
| apierrors.UsersGetUserRolesUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.UsersGetUserRolesPaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.UsersGetUserRolesForbiddenError           | 403                                                 | application/json                                    |
| apierrors.UsersGetUserRolesNotFoundError            | 404                                                 | application/json                                    |
| apierrors.UsersGetUserRolesConflictError            | 409                                                 | application/json                                    |
| apierrors.UsersGetUserRolesUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.UsersGetUserRolesInternalServerError      | 500                                                 | application/json                                    |
| apierrors.UsersGetUserRolesBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.UsersGetUserRolesServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.UsersGetUserRolesGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

## RemoveFromOrg

Remove user from organization. Upon sccess the user will be removed from the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_removeUserFromOrg" method="delete" path="/v3/users/{userID}" -->
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

    res, err := s.Users.RemoveFromOrg(ctx, "<id>")
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
| `userID`                                                 | *string*                                                 | :heavy_check_mark:                                       | (Required) user id                                       |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.UsersRemoveUserFromOrgResponse](../../models/operations/usersremoveuserfromorgresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.UsersRemoveUserFromOrgBadRequestError          | 400                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgForbiddenError           | 403                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgNotFoundError            | 404                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgConflictError            | 409                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgInternalServerError      | 500                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.UsersRemoveUserFromOrgGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## GetByID

Returns a users details of the given `userID` in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_getUserById" method="get" path="/v3/users/{userID}" -->
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

    res, err := s.Users.GetByID(ctx, "<id>")
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
| `userID`                                                 | *string*                                                 | :heavy_check_mark:                                       | (Required) user id                                       |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.UsersGetUserByIDResponse](../../models/operations/usersgetuserbyidresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.UsersGetUserByIDBadRequestError          | 400                                                | application/json                                   |
| apierrors.UsersGetUserByIDUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.UsersGetUserByIDPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.UsersGetUserByIDForbiddenError           | 403                                                | application/json                                   |
| apierrors.UsersGetUserByIDNotFoundError            | 404                                                | application/json                                   |
| apierrors.UsersGetUserByIDConflictError            | 409                                                | application/json                                   |
| apierrors.UsersGetUserByIDUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.UsersGetUserByIDInternalServerError      | 500                                                | application/json                                   |
| apierrors.UsersGetUserByIDBadGatewayError          | 502                                                | application/json                                   |
| apierrors.UsersGetUserByIDServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.UsersGetUserByIDGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |

## Update

Update User by userID.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Users_updateUserByID" method="put" path="/v3/users/{userID}" -->
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

    res, err := s.Users.Update(ctx, "<id>", components.V3UsersUpdateUserRequest{
        Role: components.V3UsersUpdateUserRequestRoleUser,
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

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `ctx`                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                      | :heavy_check_mark:                                                                         | The context to use for the request.                                                        |
| `userID`                                                                                   | *string*                                                                                   | :heavy_check_mark:                                                                         | (Required) user id                                                                         |
| `v3UsersUpdateUserRequest`                                                                 | [components.V3UsersUpdateUserRequest](../../models/components/v3usersupdateuserrequest.md) | :heavy_check_mark:                                                                         | N/A                                                                                        |
| `opts`                                                                                     | [][operations.Option](../../models/operations/option.md)                                   | :heavy_minus_sign:                                                                         | The options for this request.                                                              |

### Response

**[*operations.UsersUpdateUserByIDResponse](../../models/operations/usersupdateuserbyidresponse.md), error**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| apierrors.UsersUpdateUserByIDBadRequestError          | 400                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDUnauthorizedError        | 401                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDPaymentRequiredError     | 402                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDForbiddenError           | 403                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDNotFoundError            | 404                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDConflictError            | 409                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDUnprocessableEntityError | 422                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDInternalServerError      | 500                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDBadGatewayError          | 502                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDServiceUnavailableError  | 503                                                   | application/json                                      |
| apierrors.UsersUpdateUserByIDGatewayTimeoutError      | 504                                                   | application/json                                      |
| apierrors.APIError                                    | 4XX, 5XX                                              | \*/\*                                                 |