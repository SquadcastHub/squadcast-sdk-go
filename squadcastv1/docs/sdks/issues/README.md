# Issues
(*StatusPages.Issues*)

## Overview

### Available Operations

* [List](#list) - List Issues
* [Delete](#delete) - Delete Issue By ID
* [GetByID](#getbyid) - Get Issue By ID
* [ListStates](#liststates) - List Status Page Issue States

## List

List Issues

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_listIssues" method="get" path="/v4/statuspages/{statuspageID}/issues" -->
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

    res, err := s.StatusPages.Issues.List(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.V4StatusPagesIssuesListIssuesResponse != nil {
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

**[*operations.IssuesListIssuesResponse](../../models/operations/issueslistissuesresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.IssuesListIssuesBadRequestError          | 400                                                | application/json                                   |
| apierrors.IssuesListIssuesUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.IssuesListIssuesPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.IssuesListIssuesForbiddenError           | 403                                                | application/json                                   |
| apierrors.IssuesListIssuesNotFoundError            | 404                                                | application/json                                   |
| apierrors.IssuesListIssuesConflictError            | 409                                                | application/json                                   |
| apierrors.IssuesListIssuesUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.IssuesListIssuesInternalServerError      | 500                                                | application/json                                   |
| apierrors.IssuesListIssuesBadGatewayError          | 502                                                | application/json                                   |
| apierrors.IssuesListIssuesServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.IssuesListIssuesGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |

## Delete

Delete Issue By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_deleteIssueById" method="delete" path="/v4/statuspages/{statuspageID}/issues/{issue_id}" -->
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

    res, err := s.StatusPages.Issues.Delete(ctx, "<id>", "<id>")
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
| `issueID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.IssuesDeleteIssueByIDResponse](../../models/operations/issuesdeleteissuebyidresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.IssuesDeleteIssueByIDBadRequestError          | 400                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDForbiddenError           | 403                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDNotFoundError            | 404                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDConflictError            | 409                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDInternalServerError      | 500                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.IssuesDeleteIssueByIDGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## GetByID

Get Issue By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_getIssueById" method="get" path="/v4/statuspages/{statuspageID}/issues/{issue_id}" -->
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

    res, err := s.StatusPages.Issues.GetByID(ctx, "<id>", "<id>")
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
| `issueID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.IssuesGetIssueByIDResponse](../../models/operations/issuesgetissuebyidresponse.md), error**

### Errors

| Error Type                                           | Status Code                                          | Content Type                                         |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| apierrors.IssuesGetIssueByIDBadRequestError          | 400                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDUnauthorizedError        | 401                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDPaymentRequiredError     | 402                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDForbiddenError           | 403                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDNotFoundError            | 404                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDConflictError            | 409                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDUnprocessableEntityError | 422                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDInternalServerError      | 500                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDBadGatewayError          | 502                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDServiceUnavailableError  | 503                                                  | application/json                                     |
| apierrors.IssuesGetIssueByIDGatewayTimeoutError      | 504                                                  | application/json                                     |
| apierrors.APIError                                   | 4XX, 5XX                                             | \*/\*                                                |

## ListStates

List Status Page Issue States

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_listStatusPageIssueStates" method="get" path="/v4/statuspages/{statuspageID}/states" -->
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

    res, err := s.StatusPages.Issues.ListStates(ctx, "<id>")
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

**[*operations.IssuesListStatusPageIssueStatesResponse](../../models/operations/issuesliststatuspageissuestatesresponse.md), error**

### Errors

| Error Type                                                        | Status Code                                                       | Content Type                                                      |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| apierrors.IssuesListStatusPageIssueStatesBadRequestError          | 400                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesUnauthorizedError        | 401                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesPaymentRequiredError     | 402                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesForbiddenError           | 403                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesNotFoundError            | 404                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesConflictError            | 409                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesUnprocessableEntityError | 422                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesInternalServerError      | 500                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesBadGatewayError          | 502                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesServiceUnavailableError  | 503                                                               | application/json                                                  |
| apierrors.IssuesListStatusPageIssueStatesGatewayTimeoutError      | 504                                                               | application/json                                                  |
| apierrors.APIError                                                | 4XX, 5XX                                                          | \*/\*                                                             |