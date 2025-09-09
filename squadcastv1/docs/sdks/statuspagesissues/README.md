# StatusPagesIssues
(*StatusPagesIssues*)

## Overview

### Available Operations

* [IssuesListIssues](#issueslistissues) - List Issues
* [IssuesCreateIssue](#issuescreateissue) - Create Issue
* [IssuesDeleteIssueByID](#issuesdeleteissuebyid) - Delete Issue By ID
* [IssuesGetIssueByID](#issuesgetissuebyid) - Get Issue By ID
* [IssuesUpdateIssue](#issuesupdateissue) - Update Issue
* [IssuesListStatusPageIssueStates](#issuesliststatuspageissuestates) - List Status Page Issue States

## IssuesListIssues

List Issues

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_listIssues" method="get" path="/v4/statuspages/{statuspageID}/issues" -->
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

    res, err := s.StatusPagesIssues.IssuesListIssues(ctx, "<id>")
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

## IssuesCreateIssue

Create Issue

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_createIssue" method="post" path="/v4/statuspages/{statuspageID}/issues" -->
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

    res, err := s.StatusPagesIssues.IssuesCreateIssue(ctx, "<id>", components.V4StatusPagesIssuesCreateIssueRequest{
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

## IssuesDeleteIssueByID

Delete Issue By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_deleteIssueById" method="delete" path="/v4/statuspages/{statuspageID}/issues/{issue_id}" -->
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

    res, err := s.StatusPagesIssues.IssuesDeleteIssueByID(ctx, "<id>", "<id>")
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

## IssuesGetIssueByID

Get Issue By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_getIssueById" method="get" path="/v4/statuspages/{statuspageID}/issues/{issue_id}" -->
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

    res, err := s.StatusPagesIssues.IssuesGetIssueByID(ctx, "<id>", "<id>")
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

## IssuesUpdateIssue

Update Issue

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_updateIssue" method="put" path="/v4/statuspages/{statuspageID}/issues/{issue_id}" -->
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

    res, err := s.StatusPagesIssues.IssuesUpdateIssue(ctx, "<id>", "<id>", components.V4StatusPagesIssuesUpdateIssueRequest{
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

## IssuesListStatusPageIssueStates

List Status Page Issue States

### Example Usage

<!-- UsageSnippet language="go" operationID="Issues_listStatusPageIssueStates" method="get" path="/v4/statuspages/{statuspageID}/states" -->
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

    res, err := s.StatusPagesIssues.IssuesListStatusPageIssueStates(ctx, "<id>")
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