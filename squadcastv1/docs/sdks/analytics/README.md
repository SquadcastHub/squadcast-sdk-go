# Analytics
(*Analytics*)

## Overview

### Available Operations

* [GetOrganization](#getorganization) - Get Org level analytics
* [GetTeam](#getteam) - Get Team level analytics

## GetOrganization

Get Org level analytics

### Example Usage

<!-- UsageSnippet language="go" operationID="Analytics_getOrgAnalytics" method="get" path="/v3/analyticsv2/organization" -->
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

    res, err := s.Analytics.GetOrganization(ctx, "<value>", "<value>", nil, nil)
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
| `from`                                                   | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `to`                                                     | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `teamID`                                                 | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `userID`                                                 | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.AnalyticsGetOrgAnalyticsResponse](../../models/operations/analyticsgetorganalyticsresponse.md), error**

### Errors

| Error Type                                                 | Status Code                                                | Content Type                                               |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| apierrors.AnalyticsGetOrgAnalyticsBadRequestError          | 400                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsUnauthorizedError        | 401                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsPaymentRequiredError     | 402                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsForbiddenError           | 403                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsNotFoundError            | 404                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsConflictError            | 409                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsUnprocessableEntityError | 422                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsInternalServerError      | 500                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsBadGatewayError          | 502                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsServiceUnavailableError  | 503                                                        | application/json                                           |
| apierrors.AnalyticsGetOrgAnalyticsGatewayTimeoutError      | 504                                                        | application/json                                           |
| apierrors.APIError                                         | 4XX, 5XX                                                   | \*/\*                                                      |

## GetTeam

Get Team level analytics

### Example Usage

<!-- UsageSnippet language="go" operationID="Analytics_getTeamAnalytics" method="get" path="/v3/analyticsv2/team" -->
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

    res, err := s.Analytics.GetTeam(ctx, operations.AnalyticsGetTeamAnalyticsRequest{
        OwnerID: "<id>",
        From: "<value>",
        To: "<value>",
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

| Parameter                                                                                                  | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                                      | :heavy_check_mark:                                                                                         | The context to use for the request.                                                                        |
| `request`                                                                                                  | [operations.AnalyticsGetTeamAnalyticsRequest](../../models/operations/analyticsgetteamanalyticsrequest.md) | :heavy_check_mark:                                                                                         | The request object to use for the request.                                                                 |
| `opts`                                                                                                     | [][operations.Option](../../models/operations/option.md)                                                   | :heavy_minus_sign:                                                                                         | The options for this request.                                                                              |

### Response

**[*operations.AnalyticsGetTeamAnalyticsResponse](../../models/operations/analyticsgetteamanalyticsresponse.md), error**

### Errors

| Error Type                                                  | Status Code                                                 | Content Type                                                |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| apierrors.AnalyticsGetTeamAnalyticsBadRequestError          | 400                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsUnauthorizedError        | 401                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsPaymentRequiredError     | 402                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsForbiddenError           | 403                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsNotFoundError            | 404                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsConflictError            | 409                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsUnprocessableEntityError | 422                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsInternalServerError      | 500                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsBadGatewayError          | 502                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsServiceUnavailableError  | 503                                                         | application/json                                            |
| apierrors.AnalyticsGetTeamAnalyticsGatewayTimeoutError      | 504                                                         | application/json                                            |
| apierrors.APIError                                          | 4XX, 5XX                                                    | \*/\*                                                       |