# StatusPages
(*StatusPages*)

## Overview

### Available Operations

* [List](#list) - List Status Pages
* [Create](#create) - Create Status Page
* [DeleteByID](#deletebyid) - Delete Status Page By ID
* [GetByID](#getbyid) - Get Status Page By ID
* [UpdateByID](#updatebyid) - Update Status Page By ID
* [CreateIssue](#createissue) - Create Issue
* [UpdateIssue](#updateissue) - Update Issue
* [ListMaintenances](#listmaintenances) - List Maintenances
* [GetMaintenanceByID](#getmaintenancebyid) - Get Maintenance By ID
* [GetStatuses](#getstatuses) - List Status Page Statuses

## List

List Status Pages

### Example Usage

<!-- UsageSnippet language="go" operationID="StatusPages_listStatusPages" method="get" path="/v4/statuspages" -->
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

    res, err := s.StatusPages.List(ctx, "<value>", "<value>", "<value>", "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.V4StatusPagesListStatusPagesResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `pageSize`                                               | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `pageNumber`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `filtersIsPublic`                                        | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `teamID`                                                 | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.StatusPagesListStatusPagesResponse](../../models/operations/statuspagesliststatuspagesresponse.md), error**

### Errors

| Error Type                                                   | Status Code                                                  | Content Type                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| apierrors.StatusPagesListStatusPagesBadRequestError          | 400                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesUnauthorizedError        | 401                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesPaymentRequiredError     | 402                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesForbiddenError           | 403                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesNotFoundError            | 404                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesConflictError            | 409                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesUnprocessableEntityError | 422                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesInternalServerError      | 500                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesBadGatewayError          | 502                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesServiceUnavailableError  | 503                                                          | application/json                                             |
| apierrors.StatusPagesListStatusPagesGatewayTimeoutError      | 504                                                          | application/json                                             |
| apierrors.APIError                                           | 4XX, 5XX                                                     | \*/\*                                                        |

## Create

Create Status Page

### Example Usage

<!-- UsageSnippet language="go" operationID="StatusPages_createStatusPage" method="post" path="/v4/statuspages" -->
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

    res, err := s.StatusPages.Create(ctx, components.V4StatusPagesCreateStatusPageRequest{
        Name: "<value>",
        DomainName: "failing-convection.com",
        LogoURL: "https://snarling-season.info",
        Timezone: "Pacific/Chuuk",
        TeamID: "<id>",
        ContactEmail: "<value>",
        OwnerType: components.V4StatusPagesCreateStatusPageRequestOwnerTypeTeam,
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

| Parameter                                                                                                          | Type                                                                                                               | Required                                                                                                           | Description                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                                              | :heavy_check_mark:                                                                                                 | The context to use for the request.                                                                                |
| `request`                                                                                                          | [components.V4StatusPagesCreateStatusPageRequest](../../models/components/v4statuspagescreatestatuspagerequest.md) | :heavy_check_mark:                                                                                                 | The request object to use for the request.                                                                         |
| `opts`                                                                                                             | [][operations.Option](../../models/operations/option.md)                                                           | :heavy_minus_sign:                                                                                                 | The options for this request.                                                                                      |

### Response

**[*operations.StatusPagesCreateStatusPageResponse](../../models/operations/statuspagescreatestatuspageresponse.md), error**

### Errors

| Error Type                                                    | Status Code                                                   | Content Type                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| apierrors.StatusPagesCreateStatusPageBadRequestError          | 400                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageUnauthorizedError        | 401                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPagePaymentRequiredError     | 402                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageForbiddenError           | 403                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageNotFoundError            | 404                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageConflictError            | 409                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageUnprocessableEntityError | 422                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageInternalServerError      | 500                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageBadGatewayError          | 502                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageServiceUnavailableError  | 503                                                           | application/json                                              |
| apierrors.StatusPagesCreateStatusPageGatewayTimeoutError      | 504                                                           | application/json                                              |
| apierrors.APIError                                            | 4XX, 5XX                                                      | \*/\*                                                         |

## DeleteByID

Delete Status Page By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="StatusPages_deleteStatusPageById" method="delete" path="/v4/statuspages/{statuspageID}" -->
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

    res, err := s.StatusPages.DeleteByID(ctx, "<id>")
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

**[*operations.StatusPagesDeleteStatusPageByIDResponse](../../models/operations/statuspagesdeletestatuspagebyidresponse.md), error**

### Errors

| Error Type                                                        | Status Code                                                       | Content Type                                                      |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| apierrors.StatusPagesDeleteStatusPageByIDBadRequestError          | 400                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDUnauthorizedError        | 401                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDPaymentRequiredError     | 402                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDForbiddenError           | 403                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDNotFoundError            | 404                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDConflictError            | 409                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDUnprocessableEntityError | 422                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDInternalServerError      | 500                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDBadGatewayError          | 502                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDServiceUnavailableError  | 503                                                               | application/json                                                  |
| apierrors.StatusPagesDeleteStatusPageByIDGatewayTimeoutError      | 504                                                               | application/json                                                  |
| apierrors.APIError                                                | 4XX, 5XX                                                          | \*/\*                                                             |

## GetByID

Get Status Page By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="StatusPages_getStatusPageById" method="get" path="/v4/statuspages/{statuspageID}" -->
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

    res, err := s.StatusPages.GetByID(ctx, "<id>")
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

**[*operations.StatusPagesGetStatusPageByIDResponse](../../models/operations/statuspagesgetstatuspagebyidresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.StatusPagesGetStatusPageByIDBadRequestError          | 400                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDForbiddenError           | 403                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDNotFoundError            | 404                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDConflictError            | 409                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDInternalServerError      | 500                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.StatusPagesGetStatusPageByIDGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## UpdateByID

Update Status Page By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="StatusPages_updateStatusPageById" method="put" path="/v4/statuspages/{statuspageID}" -->
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

    res, err := s.StatusPages.UpdateByID(ctx, "<id>", components.V4StatusPagesUpdateStatusPageByIDRequest{
        Name: "<value>",
        IsPublic: false,
        DomainName: "blank-brief.info",
        TeamID: "<id>",
        ThemeColor: components.V4StatusPagesUpdateStatusPageByIDRequestThemeColor{
            Primary: "<value>",
            Secondary: "<value>",
        },
        ContactEmail: "<value>",
        OwnerType: "<value>",
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

| Parameter                                                                                                                  | Type                                                                                                                       | Required                                                                                                                   | Description                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                                                      | :heavy_check_mark:                                                                                                         | The context to use for the request.                                                                                        |
| `statuspageID`                                                                                                             | *string*                                                                                                                   | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `v4StatusPagesUpdateStatusPageByIDRequest`                                                                                 | [components.V4StatusPagesUpdateStatusPageByIDRequest](../../models/components/v4statuspagesupdatestatuspagebyidrequest.md) | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `opts`                                                                                                                     | [][operations.Option](../../models/operations/option.md)                                                                   | :heavy_minus_sign:                                                                                                         | The options for this request.                                                                                              |

### Response

**[*operations.StatusPagesUpdateStatusPageByIDResponse](../../models/operations/statuspagesupdatestatuspagebyidresponse.md), error**

### Errors

| Error Type                                                        | Status Code                                                       | Content Type                                                      |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| apierrors.StatusPagesUpdateStatusPageByIDBadRequestError          | 400                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDUnauthorizedError        | 401                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDPaymentRequiredError     | 402                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDForbiddenError           | 403                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDNotFoundError            | 404                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDConflictError            | 409                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDUnprocessableEntityError | 422                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDInternalServerError      | 500                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDBadGatewayError          | 502                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDServiceUnavailableError  | 503                                                               | application/json                                                  |
| apierrors.StatusPagesUpdateStatusPageByIDGatewayTimeoutError      | 504                                                               | application/json                                                  |
| apierrors.APIError                                                | 4XX, 5XX                                                          | \*/\*                                                             |

## CreateIssue

Create Issue

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_createIssue" method="post" path="/v4/statuspages/{statuspageID}/issues" -->
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

    res, err := s.StatusPages.CreateIssue(ctx, "<id>", components.V4StatusPagesIssuesCreateIssueRequest{
        Title: "<value>",
        Components: []components.V4StatusPagesIssuesCreateIssueRequestComponent{
            components.V4StatusPagesIssuesCreateIssueRequestComponent{},
        },
        Issues: []components.V4StatusPagesIssuesCreateIssueRequestIssue{
            components.V4StatusPagesIssuesCreateIssueRequestIssue{},
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

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                | :heavy_check_mark:                                                                                                   | The context to use for the request.                                                                                  |
| `statuspageID`                                                                                                       | *string*                                                                                                             | :heavy_check_mark:                                                                                                   | N/A                                                                                                                  |
| `v4StatusPagesIssuesCreateIssueRequest`                                                                              | [components.V4StatusPagesIssuesCreateIssueRequest](../../models/components/v4statuspagesissuescreateissuerequest.md) | :heavy_check_mark:                                                                                                   | N/A                                                                                                                  |
| `opts`                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                             | :heavy_minus_sign:                                                                                                   | The options for this request.                                                                                        |

### Response

**[*operations.IssuesCreateIssueResponse](../../models/operations/issuescreateissueresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.IssuesCreateIssueBadRequestError          | 400                                                 | application/json                                    |
| apierrors.IssuesCreateIssueUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.IssuesCreateIssuePaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.IssuesCreateIssueForbiddenError           | 403                                                 | application/json                                    |
| apierrors.IssuesCreateIssueNotFoundError            | 404                                                 | application/json                                    |
| apierrors.IssuesCreateIssueConflictError            | 409                                                 | application/json                                    |
| apierrors.IssuesCreateIssueUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.IssuesCreateIssueInternalServerError      | 500                                                 | application/json                                    |
| apierrors.IssuesCreateIssueBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.IssuesCreateIssueServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.IssuesCreateIssueGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

## UpdateIssue

Update Issue

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_updateIssue" method="put" path="/v4/statuspages/{statuspageID}/issues/{issue_id}" -->
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

    res, err := s.StatusPages.UpdateIssue(ctx, "<id>", "<id>", components.V4StatusPagesIssuesUpdateIssueRequest{
        Title: "<value>",
        Components: []components.V4StatusPagesIssuesUpdateIssueRequestComponent{
            components.V4StatusPagesIssuesUpdateIssueRequestComponent{},
        },
        Issues: []components.V4StatusPagesIssuesUpdateIssueRequestIssue{
            components.V4StatusPagesIssuesUpdateIssueRequestIssue{},
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

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                | :heavy_check_mark:                                                                                                   | The context to use for the request.                                                                                  |
| `statuspageID`                                                                                                       | *string*                                                                                                             | :heavy_check_mark:                                                                                                   | N/A                                                                                                                  |
| `issueID`                                                                                                            | *string*                                                                                                             | :heavy_check_mark:                                                                                                   | N/A                                                                                                                  |
| `v4StatusPagesIssuesUpdateIssueRequest`                                                                              | [components.V4StatusPagesIssuesUpdateIssueRequest](../../models/components/v4statuspagesissuesupdateissuerequest.md) | :heavy_check_mark:                                                                                                   | N/A                                                                                                                  |
| `opts`                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                             | :heavy_minus_sign:                                                                                                   | The options for this request.                                                                                        |

### Response

**[*operations.IssuesUpdateIssueResponse](../../models/operations/issuesupdateissueresponse.md), error**

### Errors

| Error Type                                          | Status Code                                         | Content Type                                        |
| --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| apierrors.IssuesUpdateIssueBadRequestError          | 400                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueUnauthorizedError        | 401                                                 | application/json                                    |
| apierrors.IssuesUpdateIssuePaymentRequiredError     | 402                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueForbiddenError           | 403                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueNotFoundError            | 404                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueConflictError            | 409                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueUnprocessableEntityError | 422                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueInternalServerError      | 500                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueBadGatewayError          | 502                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueServiceUnavailableError  | 503                                                 | application/json                                    |
| apierrors.IssuesUpdateIssueGatewayTimeoutError      | 504                                                 | application/json                                    |
| apierrors.APIError                                  | 4XX, 5XX                                            | \*/\*                                               |

## ListMaintenances

List Maintenances

### Example Usage

<!-- UsageSnippet language="go" operationID="Maintenances_listMaintenances" method="get" path="/v4/statuspages/{statuspageID}/maintenance" -->
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

    res, err := s.StatusPages.ListMaintenances(ctx, "<id>", "<value>", "<value>")
    if err != nil {
        log.Fatal(err)
    }
    if res.V4StatusPagesMaintenancesListMaintenancesResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `statuspageID`                                           | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `startTime`                                              | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `endTime`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.MaintenancesListMaintenancesResponse](../../models/operations/maintenanceslistmaintenancesresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.MaintenancesListMaintenancesBadRequestError          | 400                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesForbiddenError           | 403                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesNotFoundError            | 404                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesConflictError            | 409                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesInternalServerError      | 500                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.MaintenancesListMaintenancesGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## GetMaintenanceByID

Get Maintenance By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Maintenances_getMaintenanceById" method="get" path="/v4/statuspages/{statuspageID}/maintenance/{maintenance_id}" -->
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

    res, err := s.StatusPages.GetMaintenanceByID(ctx, "<id>", "<id>")
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
| `maintenanceID`                                          | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.MaintenancesGetMaintenanceByIDResponse](../../models/operations/maintenancesgetmaintenancebyidresponse.md), error**

### Errors

| Error Type                                                       | Status Code                                                      | Content Type                                                     |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| apierrors.MaintenancesGetMaintenanceByIDBadRequestError          | 400                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDUnauthorizedError        | 401                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDPaymentRequiredError     | 402                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDForbiddenError           | 403                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDNotFoundError            | 404                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDConflictError            | 409                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDUnprocessableEntityError | 422                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDInternalServerError      | 500                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDBadGatewayError          | 502                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDServiceUnavailableError  | 503                                                              | application/json                                                 |
| apierrors.MaintenancesGetMaintenanceByIDGatewayTimeoutError      | 504                                                              | application/json                                                 |
| apierrors.APIError                                               | 4XX, 5XX                                                         | \*/\*                                                            |

## GetStatuses

List Status Page Statuses

### Example Usage

<!-- UsageSnippet language="go" operationID="StatusPages_listStatusPageStatuses" method="get" path="/v4/statuspages/{statuspageID}/status" -->
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

    res, err := s.StatusPages.GetStatuses(ctx, "<id>")
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

**[*operations.StatusPagesListStatusPageStatusesResponse](../../models/operations/statuspagesliststatuspagestatusesresponse.md), error**

### Errors

| Error Type                                                          | Status Code                                                         | Content Type                                                        |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| apierrors.StatusPagesListStatusPageStatusesBadRequestError          | 400                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesUnauthorizedError        | 401                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesPaymentRequiredError     | 402                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesForbiddenError           | 403                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesNotFoundError            | 404                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesConflictError            | 409                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesUnprocessableEntityError | 422                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesInternalServerError      | 500                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesBadGatewayError          | 502                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesServiceUnavailableError  | 503                                                                 | application/json                                                    |
| apierrors.StatusPagesListStatusPageStatusesGatewayTimeoutError      | 504                                                                 | application/json                                                    |
| apierrors.APIError                                                  | 4XX, 5XX                                                            | \*/\*                                                               |