# EscalationPolicies
(*EscalationPolicies*)

## Overview

### Available Operations

* [GetByTeam](#getbyteam) - Get Escalation Policy By team
* [Create](#create) - Create Escalation Policies
* [Remove](#remove) - Remove Escalation Policy
* [GetByID](#getbyid) - Get Escalation Policy By ID
* [Update](#update) - Update Escalation Policy

## GetByTeam

Returns all escalation policy details of the given `ownerID` (teamId) in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="EscalationPolicies_getEscalationPolicyByTeam" method="get" path="/v3/escalation-policies" -->
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

    res, err := s.EscalationPolicies.GetByTeam(ctx, "<id>", nil, nil)
    if err != nil {
        log.Fatal(err)
    }
    if res.Object != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                       | Type                                                                                                            | Required                                                                                                        | Description                                                                                                     |
| --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                           | [context.Context](https://pkg.go.dev/context#Context)                                                           | :heavy_check_mark:                                                                                              | The context to use for the request.                                                                             |
| `ownerID`                                                                                                       | *string*                                                                                                        | :heavy_check_mark:                                                                                              | here owner_id represents team_id, if  team_id is not provided, it will return escalation policies of all teams. |
| `pageNumber`                                                                                                    | **string*                                                                                                       | :heavy_minus_sign:                                                                                              | N/A                                                                                                             |
| `pageSize`                                                                                                      | **string*                                                                                                       | :heavy_minus_sign:                                                                                              | N/A                                                                                                             |
| `opts`                                                                                                          | [][operations.Option](../../models/operations/option.md)                                                        | :heavy_minus_sign:                                                                                              | The options for this request.                                                                                   |

### Response

**[*operations.EscalationPoliciesGetEscalationPolicyByTeamResponse](../../models/operations/escalationpoliciesgetescalationpolicybyteamresponse.md), error**

### Errors

| Error Type                                                                    | Status Code                                                                   | Content Type                                                                  |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamBadRequestError          | 400                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamUnauthorizedError        | 401                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamPaymentRequiredError     | 402                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamForbiddenError           | 403                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamNotFoundError            | 404                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamConflictError            | 409                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamUnprocessableEntityError | 422                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamInternalServerError      | 500                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamBadGatewayError          | 502                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamServiceUnavailableError  | 503                                                                           | application/json                                                              |
| apierrors.EscalationPoliciesGetEscalationPolicyByTeamGatewayTimeoutError      | 504                                                                           | application/json                                                              |
| apierrors.APIError                                                            | 4XX, 5XX                                                                      | \*/\*                                                                         |

## Create

Add escalation policy to the organization. Returns the escalation policy object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="EscalationPolicies_createEscalationPolicies" method="post" path="/v3/escalation-policies" -->
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

    res, err := s.EscalationPolicies.Create(ctx, components.V3EscalationPoliciesCreateEscalationPolicyRequest{
        OwnerID: "<id>",
        Name: "<value>",
        Description: "properly aw gerbil address co-producer guzzle delight difficult",
        Repetition: 549305,
        RepeatAfter: 226311,
        Rules: []components.V3EscalationPoliciesEscalationPolicyRule{
            components.V3EscalationPoliciesEscalationPolicyRule{
                EscalationTime: 646220,
                Via: []string{
                    "<value 1>",
                    "<value 2>",
                },
                RoundrobinEnabled: true,
                RoundrobinNextIndex: 685302,
                Entities: []components.V3EscalationPoliciesEscalationEntity{},
                EscalateWithinRoundrobin: true,
                Repetition: 149319,
                RepeatAfter: 619552,
            },
        },
        EnableIncidentReminders: false,
        IncidentReminderRules: []components.V3EscalationPoliciesIncidentReminderRule{},
        EnableIncidentRetrigger: false,
        RetriggerAfter: 660610,
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

| Parameter                                                                                                                                    | Type                                                                                                                                         | Required                                                                                                                                     | Description                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                                                        | :heavy_check_mark:                                                                                                                           | The context to use for the request.                                                                                                          |
| `request`                                                                                                                                    | [components.V3EscalationPoliciesCreateEscalationPolicyRequest](../../models/components/v3escalationpoliciescreateescalationpolicyrequest.md) | :heavy_check_mark:                                                                                                                           | The request object to use for the request.                                                                                                   |
| `opts`                                                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                                                     | :heavy_minus_sign:                                                                                                                           | The options for this request.                                                                                                                |

### Response

**[*operations.EscalationPoliciesCreateEscalationPoliciesResponse](../../models/operations/escalationpoliciescreateescalationpoliciesresponse.md), error**

### Errors

| Error Type                                                                   | Status Code                                                                  | Content Type                                                                 |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| apierrors.EscalationPoliciesCreateEscalationPoliciesBadRequestError          | 400                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesUnauthorizedError        | 401                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesPaymentRequiredError     | 402                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesForbiddenError           | 403                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesNotFoundError            | 404                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesConflictError            | 409                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesUnprocessableEntityError | 422                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesInternalServerError      | 500                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesBadGatewayError          | 502                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesServiceUnavailableError  | 503                                                                          | application/json                                                             |
| apierrors.EscalationPoliciesCreateEscalationPoliciesGatewayTimeoutError      | 504                                                                          | application/json                                                             |
| apierrors.APIError                                                           | 4XX, 5XX                                                                     | \*/\*                                                                        |

## Remove

Remove escalation policy from the organization. Upon success, the escalation policy will be removed from the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="EscalationPolicies_removeEscalationPolicy" method="delete" path="/v3/escalation-policies/{escalationPolicyID}" -->
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

    res, err := s.EscalationPolicies.Remove(ctx, "<id>")
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
| `escalationPolicyID`                                     | *string*                                                 | :heavy_check_mark:                                       | (Required) escalation policy ID                          |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.EscalationPoliciesRemoveEscalationPolicyResponse](../../models/operations/escalationpoliciesremoveescalationpolicyresponse.md), error**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| apierrors.EscalationPoliciesRemoveEscalationPolicyBadRequestError          | 400                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyUnauthorizedError        | 401                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyPaymentRequiredError     | 402                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyForbiddenError           | 403                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyNotFoundError            | 404                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyConflictError            | 409                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyUnprocessableEntityError | 422                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyInternalServerError      | 500                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyBadGatewayError          | 502                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyServiceUnavailableError  | 503                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesRemoveEscalationPolicyGatewayTimeoutError      | 504                                                                        | application/json                                                           |
| apierrors.APIError                                                         | 4XX, 5XX                                                                   | \*/\*                                                                      |

## GetByID

Returns an escalation policy details of the given `escalationPolicyID` in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="EscalationPolicies_getEscalationPolicyById" method="get" path="/v3/escalation-policies/{escalationPolicyID}" -->
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

    res, err := s.EscalationPolicies.GetByID(ctx, "<id>")
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
| `escalationPolicyID`                                     | *string*                                                 | :heavy_check_mark:                                       | (Required) escalation policy ID                          |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.EscalationPoliciesGetEscalationPolicyByIDResponse](../../models/operations/escalationpoliciesgetescalationpolicybyidresponse.md), error**

### Errors

| Error Type                                                                  | Status Code                                                                 | Content Type                                                                |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDBadRequestError          | 400                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDUnauthorizedError        | 401                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDPaymentRequiredError     | 402                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDForbiddenError           | 403                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDNotFoundError            | 404                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDConflictError            | 409                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDUnprocessableEntityError | 422                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDInternalServerError      | 500                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDBadGatewayError          | 502                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDServiceUnavailableError  | 503                                                                         | application/json                                                            |
| apierrors.EscalationPoliciesGetEscalationPolicyByIDGatewayTimeoutError      | 504                                                                         | application/json                                                            |
| apierrors.APIError                                                          | 4XX, 5XX                                                                    | \*/\*                                                                       |

## Update

Update organization escalation policy details.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="EscalationPolicies_updateEscalationPolicy" method="post" path="/v3/escalation-policies/{escalationPolicyID}" -->
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

    example, fileErr := os.Open("example.file")
    if fileErr != nil {
        panic(fileErr)
    }

    res, err := s.EscalationPolicies.Update(ctx, "<id>", example)
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
| `escalationPolicyID`                                     | *string*                                                 | :heavy_check_mark:                                       | (Required) escalation policy ID                          |
| `v3EscalationPoliciesUpdateEscalationPolicyRequest`      | *any*                                                    | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.EscalationPoliciesUpdateEscalationPolicyResponse](../../models/operations/escalationpoliciesupdateescalationpolicyresponse.md), error**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| apierrors.EscalationPoliciesUpdateEscalationPolicyBadRequestError          | 400                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyUnauthorizedError        | 401                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyPaymentRequiredError     | 402                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyForbiddenError           | 403                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyNotFoundError            | 404                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyConflictError            | 409                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyUnprocessableEntityError | 422                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyInternalServerError      | 500                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyBadGatewayError          | 502                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyServiceUnavailableError  | 503                                                                        | application/json                                                           |
| apierrors.EscalationPoliciesUpdateEscalationPolicyGatewayTimeoutError      | 504                                                                        | application/json                                                           |
| apierrors.APIError                                                         | 4XX, 5XX                                                                   | \*/\*                                                                      |