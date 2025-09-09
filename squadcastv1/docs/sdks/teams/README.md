# Teams
(*Teams*)

## Overview

### Available Operations

* [TeamsGetAllTeams](#teamsgetallteams) - Get All Teams
* [TeamsCreateTeam](#teamscreateteam) - Create Team
* [TeamsGetTeamByID](#teamsgetteambyid) - Get Team By ID
* [TeamsUpdateTeam](#teamsupdateteam) - Update Team
* [TeamsRemoveTeam](#teamsremoveteam) - Remove Team
* [TeamsGetAllTeamMembers](#teamsgetallteammembers) - Get All Team Members
* [TeamsAddTeamMember](#teamsaddteammember) - Add Team Member
* [TeamsAddBulkTeamMember](#teamsaddbulkteammember) - Add Bulk Team Member
* [TeamsRemoveTeamMember](#teamsremoveteammember) - Remove Team Member
* [TeamsUpdateTeamMember](#teamsupdateteammember) - Update Team Member
* [TeamsGetAllTeamRoles](#teamsgetallteamroles) - Get All Team Roles
* [TeamsCreateTeamRole](#teamscreateteamrole) - Create Team Role
* [TeamsRemoveTeamRole](#teamsremoveteamrole) - Remove Team Role
* [TeamsUpdateTeamRole](#teamsupdateteamrole) - Update Team Role

## TeamsGetAllTeams

Returns all the teams of the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_getAllTeams" method="get" path="/v3/teams" -->
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

    res, err := s.Teams.TeamsGetAllTeams(ctx)
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

**[*operations.TeamsGetAllTeamsResponse](../../models/operations/teamsgetallteamsresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.TeamsGetAllTeamsBadRequestError          | 400                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsForbiddenError           | 403                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsNotFoundError            | 404                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsConflictError            | 409                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsInternalServerError      | 500                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsBadGatewayError          | 502                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.TeamsGetAllTeamsGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |

## TeamsCreateTeam

Add team to the organization. Returns the team object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_createTeam" method="post" path="/v3/teams" -->
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

    res, err := s.Teams.TeamsCreateTeam(ctx, components.V3TeamsCreateTeamRequest{
        Name: "<value>",
        MemberIds: []string{
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

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `ctx`                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                      | :heavy_check_mark:                                                                         | The context to use for the request.                                                        |
| `request`                                                                                  | [components.V3TeamsCreateTeamRequest](../../models/components/v3teamscreateteamrequest.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |
| `opts`                                                                                     | [][operations.Option](../../models/operations/option.md)                                   | :heavy_minus_sign:                                                                         | The options for this request.                                                              |

### Response

**[*operations.TeamsCreateTeamResponse](../../models/operations/teamscreateteamresponse.md), error**

### Errors

| Error Type                                        | Status Code                                       | Content Type                                      |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| apierrors.TeamsCreateTeamBadRequestError          | 400                                               | application/json                                  |
| apierrors.TeamsCreateTeamUnauthorizedError        | 401                                               | application/json                                  |
| apierrors.TeamsCreateTeamPaymentRequiredError     | 402                                               | application/json                                  |
| apierrors.TeamsCreateTeamForbiddenError           | 403                                               | application/json                                  |
| apierrors.TeamsCreateTeamNotFoundError            | 404                                               | application/json                                  |
| apierrors.TeamsCreateTeamConflictError            | 409                                               | application/json                                  |
| apierrors.TeamsCreateTeamUnprocessableEntityError | 422                                               | application/json                                  |
| apierrors.TeamsCreateTeamInternalServerError      | 500                                               | application/json                                  |
| apierrors.TeamsCreateTeamBadGatewayError          | 502                                               | application/json                                  |
| apierrors.TeamsCreateTeamServiceUnavailableError  | 503                                               | application/json                                  |
| apierrors.TeamsCreateTeamGatewayTimeoutError      | 504                                               | application/json                                  |
| apierrors.APIError                                | 4XX, 5XX                                          | \*/\*                                             |

## TeamsGetTeamByID

Returns a team details of the given `teamID` in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_getTeamById" method="get" path="/v3/teams/{teamId}" -->
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

    res, err := s.Teams.TeamsGetTeamByID(ctx, "<id>")
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
| `teamID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.TeamsGetTeamByIDResponse](../../models/operations/teamsgetteambyidresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.TeamsGetTeamByIDBadRequestError          | 400                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDForbiddenError           | 403                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDNotFoundError            | 404                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDConflictError            | 409                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDInternalServerError      | 500                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDBadGatewayError          | 502                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.TeamsGetTeamByIDGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |

## TeamsUpdateTeam

Update organization team details.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_updateTeam" method="put" path="/v3/teams/{teamId}" -->
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

    res, err := s.Teams.TeamsUpdateTeam(ctx, "<id>", components.V3TeamsUpdateTeamRequest{
        Members: []components.V3TeamsUpdateTeamRequestMember{},
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
| `teamID`                                                                                   | *string*                                                                                   | :heavy_check_mark:                                                                         | N/A                                                                                        |
| `v3TeamsUpdateTeamRequest`                                                                 | [components.V3TeamsUpdateTeamRequest](../../models/components/v3teamsupdateteamrequest.md) | :heavy_check_mark:                                                                         | N/A                                                                                        |
| `opts`                                                                                     | [][operations.Option](../../models/operations/option.md)                                   | :heavy_minus_sign:                                                                         | The options for this request.                                                              |

### Response

**[*operations.TeamsUpdateTeamResponse](../../models/operations/teamsupdateteamresponse.md), error**

### Errors

| Error Type                                        | Status Code                                       | Content Type                                      |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| apierrors.TeamsUpdateTeamBadRequestError          | 400                                               | application/json                                  |
| apierrors.TeamsUpdateTeamUnauthorizedError        | 401                                               | application/json                                  |
| apierrors.TeamsUpdateTeamPaymentRequiredError     | 402                                               | application/json                                  |
| apierrors.TeamsUpdateTeamForbiddenError           | 403                                               | application/json                                  |
| apierrors.TeamsUpdateTeamNotFoundError            | 404                                               | application/json                                  |
| apierrors.TeamsUpdateTeamConflictError            | 409                                               | application/json                                  |
| apierrors.TeamsUpdateTeamUnprocessableEntityError | 422                                               | application/json                                  |
| apierrors.TeamsUpdateTeamInternalServerError      | 500                                               | application/json                                  |
| apierrors.TeamsUpdateTeamBadGatewayError          | 502                                               | application/json                                  |
| apierrors.TeamsUpdateTeamServiceUnavailableError  | 503                                               | application/json                                  |
| apierrors.TeamsUpdateTeamGatewayTimeoutError      | 504                                               | application/json                                  |
| apierrors.APIError                                | 4XX, 5XX                                          | \*/\*                                             |

## TeamsRemoveTeam

Remove team from the organization. Upon success, the team will be removed from the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_removeTeam" method="delete" path="/v3/teams/{teamId}" -->
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

    res, err := s.Teams.TeamsRemoveTeam(ctx, "<id>")
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
| `teamID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.TeamsRemoveTeamResponse](../../models/operations/teamsremoveteamresponse.md), error**

### Errors

| Error Type                                        | Status Code                                       | Content Type                                      |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| apierrors.TeamsRemoveTeamBadRequestError          | 400                                               | application/json                                  |
| apierrors.TeamsRemoveTeamUnauthorizedError        | 401                                               | application/json                                  |
| apierrors.TeamsRemoveTeamPaymentRequiredError     | 402                                               | application/json                                  |
| apierrors.TeamsRemoveTeamForbiddenError           | 403                                               | application/json                                  |
| apierrors.TeamsRemoveTeamNotFoundError            | 404                                               | application/json                                  |
| apierrors.TeamsRemoveTeamConflictError            | 409                                               | application/json                                  |
| apierrors.TeamsRemoveTeamUnprocessableEntityError | 422                                               | application/json                                  |
| apierrors.TeamsRemoveTeamInternalServerError      | 500                                               | application/json                                  |
| apierrors.TeamsRemoveTeamBadGatewayError          | 502                                               | application/json                                  |
| apierrors.TeamsRemoveTeamServiceUnavailableError  | 503                                               | application/json                                  |
| apierrors.TeamsRemoveTeamGatewayTimeoutError      | 504                                               | application/json                                  |
| apierrors.APIError                                | 4XX, 5XX                                          | \*/\*                                             |

## TeamsGetAllTeamMembers

Returns all the team members of the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_getAllTeamMembers" method="get" path="/v3/teams/{teamId}/members" -->
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

    res, err := s.Teams.TeamsGetAllTeamMembers(ctx, "<id>")
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
| `teamID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.TeamsGetAllTeamMembersResponse](../../models/operations/teamsgetallteammembersresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.TeamsGetAllTeamMembersBadRequestError          | 400                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersForbiddenError           | 403                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersNotFoundError            | 404                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersConflictError            | 409                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersInternalServerError      | 500                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.TeamsGetAllTeamMembersGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## TeamsAddTeamMember

Add team member to the team.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_addTeamMember" method="post" path="/v3/teams/{teamId}/members" -->
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

    res, err := s.Teams.TeamsAddTeamMember(ctx, "<id>", components.V3TeamsAddTeamMemberRequest{
        UserID: "<id>",
        RoleIds: []string{},
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

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `teamID`                                                                                         | *string*                                                                                         | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `v3TeamsAddTeamMemberRequest`                                                                    | [components.V3TeamsAddTeamMemberRequest](../../models/components/v3teamsaddteammemberrequest.md) | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `opts`                                                                                           | [][operations.Option](../../models/operations/option.md)                                         | :heavy_minus_sign:                                                                               | The options for this request.                                                                    |

### Response

**[*operations.TeamsAddTeamMemberResponse](../../models/operations/teamsaddteammemberresponse.md), error**

### Errors

| Error Type                                           | Status Code                                          | Content Type                                         |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| apierrors.TeamsAddTeamMemberBadRequestError          | 400                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberUnauthorizedError        | 401                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberPaymentRequiredError     | 402                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberForbiddenError           | 403                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberNotFoundError            | 404                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberConflictError            | 409                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberUnprocessableEntityError | 422                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberInternalServerError      | 500                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberBadGatewayError          | 502                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberServiceUnavailableError  | 503                                                  | application/json                                     |
| apierrors.TeamsAddTeamMemberGatewayTimeoutError      | 504                                                  | application/json                                     |
| apierrors.APIError                                   | 4XX, 5XX                                             | \*/\*                                                |

## TeamsAddBulkTeamMember

Add team member to the team.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_addBulkTeamMember" method="post" path="/v3/teams/{teamId}/members/bulk" -->
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

    res, err := s.Teams.TeamsAddBulkTeamMember(ctx, "<id>", components.V3TeamsAddBulkTeamMemberRequest{
        Members: []components.V3TeamsAddBulkTeamMemberRequestMember{
            components.V3TeamsAddBulkTeamMemberRequestMember{
                UserID: "<id>",
                RoleIds: []string{
                    "<value 1>",
                    "<value 2>",
                },
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

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                    | :heavy_check_mark:                                                                                       | The context to use for the request.                                                                      |
| `teamID`                                                                                                 | *string*                                                                                                 | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `v3TeamsAddBulkTeamMemberRequest`                                                                        | [components.V3TeamsAddBulkTeamMemberRequest](../../models/components/v3teamsaddbulkteammemberrequest.md) | :heavy_check_mark:                                                                                       | N/A                                                                                                      |
| `opts`                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                 | :heavy_minus_sign:                                                                                       | The options for this request.                                                                            |

### Response

**[*operations.TeamsAddBulkTeamMemberResponse](../../models/operations/teamsaddbulkteammemberresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.TeamsAddBulkTeamMemberBadRequestError          | 400                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberForbiddenError           | 403                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberNotFoundError            | 404                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberConflictError            | 409                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberInternalServerError      | 500                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.TeamsAddBulkTeamMemberGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## TeamsRemoveTeamMember

Remove team member from the team. Upon success, the team member will be removed from the team.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_removeTeamMember" method="delete" path="/v3/teams/{teamId}/members/{memberId}" -->
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

    res, err := s.Teams.TeamsRemoveTeamMember(ctx, "<id>", "<id>")
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
| `teamID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `memberID`                                               | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.TeamsRemoveTeamMemberResponse](../../models/operations/teamsremoveteammemberresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.TeamsRemoveTeamMemberBadRequestError          | 400                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberForbiddenError           | 403                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberNotFoundError            | 404                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberConflictError            | 409                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberInternalServerError      | 500                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.TeamsRemoveTeamMemberGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## TeamsUpdateTeamMember

Update team member.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_updateTeamMember" method="patch" path="/v3/teams/{teamId}/members/{memberId}" -->
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

    res, err := s.Teams.TeamsUpdateTeamMember(ctx, "<id>", "<id>", components.V3TeamsUpdateTeamMemberRequest{})
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
| `teamID`                                                                                               | *string*                                                                                               | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `memberID`                                                                                             | *string*                                                                                               | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `v3TeamsUpdateTeamMemberRequest`                                                                       | [components.V3TeamsUpdateTeamMemberRequest](../../models/components/v3teamsupdateteammemberrequest.md) | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.TeamsUpdateTeamMemberResponse](../../models/operations/teamsupdateteammemberresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.TeamsUpdateTeamMemberBadRequestError          | 400                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberForbiddenError           | 403                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberNotFoundError            | 404                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberConflictError            | 409                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberInternalServerError      | 500                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.TeamsUpdateTeamMemberGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## TeamsGetAllTeamRoles

Returns all the roles of the teamId mentioned in params.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_getAllTeamRoles" method="get" path="/v3/teams/{teamId}/roles" -->
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

    res, err := s.Teams.TeamsGetAllTeamRoles(ctx, "<id>")
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
| `teamID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.TeamsGetAllTeamRolesResponse](../../models/operations/teamsgetallteamrolesresponse.md), error**

### Errors

| Error Type                                             | Status Code                                            | Content Type                                           |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| apierrors.TeamsGetAllTeamRolesBadRequestError          | 400                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesUnauthorizedError        | 401                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesPaymentRequiredError     | 402                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesForbiddenError           | 403                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesNotFoundError            | 404                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesConflictError            | 409                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesUnprocessableEntityError | 422                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesInternalServerError      | 500                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesBadGatewayError          | 502                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesServiceUnavailableError  | 503                                                    | application/json                                       |
| apierrors.TeamsGetAllTeamRolesGatewayTimeoutError      | 504                                                    | application/json                                       |
| apierrors.APIError                                     | 4XX, 5XX                                               | \*/\*                                                  |

## TeamsCreateTeamRole

Add team's role to the team with given ability if not exists. Returns the role object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_createTeamRole" method="post" path="/v3/teams/{teamId}/roles" -->
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

    res, err := s.Teams.TeamsCreateTeamRole(ctx, "<id>", components.V3TeamsCreateTeamRoleRequest{
        Name: "<value>",
        Abilities: components.V3TeamsAbilities{},
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

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                              | :heavy_check_mark:                                                                                 | The context to use for the request.                                                                |
| `teamID`                                                                                           | *string*                                                                                           | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `v3TeamsCreateTeamRoleRequest`                                                                     | [components.V3TeamsCreateTeamRoleRequest](../../models/components/v3teamscreateteamrolerequest.md) | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `opts`                                                                                             | [][operations.Option](../../models/operations/option.md)                                           | :heavy_minus_sign:                                                                                 | The options for this request.                                                                      |

### Response

**[*operations.TeamsCreateTeamRoleResponse](../../models/operations/teamscreateteamroleresponse.md), error**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| apierrors.TeamsCreateTeamRoleBadRequestError          | 400                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleUnauthorizedError        | 401                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRolePaymentRequiredError     | 402                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleForbiddenError           | 403                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleNotFoundError            | 404                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleConflictError            | 409                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleUnprocessableEntityError | 422                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleInternalServerError      | 500                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleBadGatewayError          | 502                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleServiceUnavailableError  | 503                                                   | application/json                                      |
| apierrors.TeamsCreateTeamRoleGatewayTimeoutError      | 504                                                   | application/json                                      |
| apierrors.APIError                                    | 4XX, 5XX                                              | \*/\*                                                 |

## TeamsRemoveTeamRole

Remove team's role from the team. Upon success, the team's role will be removed from the team.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_removeTeamRole" method="delete" path="/v3/teams/{teamId}/roles/{roleId}" -->
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

    res, err := s.Teams.TeamsRemoveTeamRole(ctx, "<id>", "<id>")
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
| `teamID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `roleID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.TeamsRemoveTeamRoleResponse](../../models/operations/teamsremoveteamroleresponse.md), error**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| apierrors.TeamsRemoveTeamRoleBadRequestError          | 400                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleUnauthorizedError        | 401                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRolePaymentRequiredError     | 402                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleForbiddenError           | 403                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleNotFoundError            | 404                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleConflictError            | 409                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleUnprocessableEntityError | 422                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleInternalServerError      | 500                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleBadGatewayError          | 502                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleServiceUnavailableError  | 503                                                   | application/json                                      |
| apierrors.TeamsRemoveTeamRoleGatewayTimeoutError      | 504                                                   | application/json                                      |
| apierrors.APIError                                    | 4XX, 5XX                                              | \*/\*                                                 |

## TeamsUpdateTeamRole

Update team's role abilities and name.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Teams_updateTeamRole" method="put" path="/v3/teams/{teamId}/roles/{roleId}" -->
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

    res, err := s.Teams.TeamsUpdateTeamRole(ctx, "<id>", "<id>", components.V3TeamsUpdateTeamRoleRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                              | :heavy_check_mark:                                                                                 | The context to use for the request.                                                                |
| `teamID`                                                                                           | *string*                                                                                           | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `roleID`                                                                                           | *string*                                                                                           | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `v3TeamsUpdateTeamRoleRequest`                                                                     | [components.V3TeamsUpdateTeamRoleRequest](../../models/components/v3teamsupdateteamrolerequest.md) | :heavy_check_mark:                                                                                 | N/A                                                                                                |
| `opts`                                                                                             | [][operations.Option](../../models/operations/option.md)                                           | :heavy_minus_sign:                                                                                 | The options for this request.                                                                      |

### Response

**[*operations.TeamsUpdateTeamRoleResponse](../../models/operations/teamsupdateteamroleresponse.md), error**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| apierrors.TeamsUpdateTeamRoleBadRequestError          | 400                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleUnauthorizedError        | 401                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRolePaymentRequiredError     | 402                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleForbiddenError           | 403                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleNotFoundError            | 404                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleConflictError            | 409                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleUnprocessableEntityError | 422                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleInternalServerError      | 500                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleBadGatewayError          | 502                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleServiceUnavailableError  | 503                                                   | application/json                                      |
| apierrors.TeamsUpdateTeamRoleGatewayTimeoutError      | 504                                                   | application/json                                      |
| apierrors.APIError                                    | 4XX, 5XX                                              | \*/\*                                                 |