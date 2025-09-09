# IncidentsAutoPauseTransientAlertsAPTA
(*IncidentsAutoPauseTransientAlertsAPTA*)

## Overview

### Available Operations

* [AptaMarkAsNotTransient](#aptamarkasnottransient) - Mark as Not Transient
* [AptaMarkAsTransient](#aptamarkastransient) - Mark as Transient

## AptaMarkAsNotTransient

Mark as Not Transient

### Example Usage

<!-- UsageSnippet language="go" operationID="Apta_markAsNotTransient" method="put" path="/v3/incidents/{incidentID}/mark-as-non-transient" -->
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

    res, err := s.IncidentsAutoPauseTransientAlertsAPTA.AptaMarkAsNotTransient(ctx, "<id>")
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
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.AptaMarkAsNotTransientResponse](../../models/operations/aptamarkasnottransientresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.AptaMarkAsNotTransientBadRequestError          | 400                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientForbiddenError           | 403                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientNotFoundError            | 404                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientConflictError            | 409                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientInternalServerError      | 500                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.AptaMarkAsNotTransientGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## AptaMarkAsTransient

Mark as Transient

### Example Usage

<!-- UsageSnippet language="go" operationID="Apta_markAsTransient" method="put" path="/v3/incidents/{incidentID}/mark-as-transient" -->
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

    res, err := s.IncidentsAutoPauseTransientAlertsAPTA.AptaMarkAsTransient(ctx, "<id>")
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
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.AptaMarkAsTransientResponse](../../models/operations/aptamarkastransientresponse.md), error**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| apierrors.AptaMarkAsTransientBadRequestError          | 400                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientUnauthorizedError        | 401                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientPaymentRequiredError     | 402                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientForbiddenError           | 403                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientNotFoundError            | 404                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientConflictError            | 409                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientUnprocessableEntityError | 422                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientInternalServerError      | 500                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientBadGatewayError          | 502                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientServiceUnavailableError  | 503                                                   | application/json                                      |
| apierrors.AptaMarkAsTransientGatewayTimeoutError      | 504                                                   | application/json                                      |
| apierrors.APIError                                    | 4XX, 5XX                                              | \*/\*                                                 |