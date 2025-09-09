# StatusPagesSubscribers
(*StatusPagesSubscribers*)

## Overview

### Available Operations

* [StatusPagesListSubscribers](#statuspageslistsubscribers) - List Subscribers

## StatusPagesListSubscribers

List Subscribers

### Example Usage

<!-- UsageSnippet language="go" operationID="StatusPages_listSubscribers" method="get" path="/v4/statuspages/{statuspageID}/subscribers" -->
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

    res, err := s.StatusPagesSubscribers.StatusPagesListSubscribers(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res.V4StatusPagesListSubscribersResponse != nil {
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

**[*operations.StatusPagesListSubscribersResponse](../../models/operations/statuspageslistsubscribersresponse.md), error**

### Errors

| Error Type                                                   | Status Code                                                  | Content Type                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| apierrors.StatusPagesListSubscribersBadRequestError          | 400                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersUnauthorizedError        | 401                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersPaymentRequiredError     | 402                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersForbiddenError           | 403                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersNotFoundError            | 404                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersConflictError            | 409                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersUnprocessableEntityError | 422                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersInternalServerError      | 500                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersBadGatewayError          | 502                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersServiceUnavailableError  | 503                                                          | application/json                                             |
| apierrors.StatusPagesListSubscribersGatewayTimeoutError      | 504                                                          | application/json                                             |
| apierrors.APIError                                           | 4XX, 5XX                                                     | \*/\*                                                        |