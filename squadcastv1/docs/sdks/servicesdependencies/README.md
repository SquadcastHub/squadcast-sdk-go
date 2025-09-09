# ServicesDependencies
(*ServicesDependencies*)

## Overview

### Available Operations

* [DependenciesCreateOrUpdateDependencies](#dependenciescreateorupdatedependencies) - Create or Update Dependencies

## DependenciesCreateOrUpdateDependencies

Create or Update Dependencies

### Example Usage

<!-- UsageSnippet language="go" operationID="Dependencies_createOrUpdateDependencies" method="post" path="/v3/services/{serviceID}/dependencies" -->
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

    res, err := s.ServicesDependencies.DependenciesCreateOrUpdateDependencies(ctx, "<id>", components.V3ServicesDependenciesCreateOrUpdateDependenciesRequest{
        Dependencies: []string{
            "<value 1>",
            "<value 2>",
            "<value 3>",
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

| Parameter                                                                                                                                                | Type                                                                                                                                                     | Required                                                                                                                                                 | Description                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                                                    | :heavy_check_mark:                                                                                                                                       | The context to use for the request.                                                                                                                      |
| `serviceID`                                                                                                                                              | *string*                                                                                                                                                 | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `v3ServicesDependenciesCreateOrUpdateDependenciesRequest`                                                                                                | [components.V3ServicesDependenciesCreateOrUpdateDependenciesRequest](../../models/components/v3servicesdependenciescreateorupdatedependenciesrequest.md) | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `opts`                                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                                 | :heavy_minus_sign:                                                                                                                                       | The options for this request.                                                                                                                            |

### Response

**[*operations.DependenciesCreateOrUpdateDependenciesResponse](../../models/operations/dependenciescreateorupdatedependenciesresponse.md), error**

### Errors

| Error Type                                                               | Status Code                                                              | Content Type                                                             |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| apierrors.DependenciesCreateOrUpdateDependenciesBadRequestError          | 400                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesUnauthorizedError        | 401                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesPaymentRequiredError     | 402                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesForbiddenError           | 403                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesNotFoundError            | 404                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesConflictError            | 409                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesUnprocessableEntityError | 422                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesInternalServerError      | 500                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesBadGatewayError          | 502                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesServiceUnavailableError  | 503                                                                      | application/json                                                         |
| apierrors.DependenciesCreateOrUpdateDependenciesGatewayTimeoutError      | 504                                                                      | application/json                                                         |
| apierrors.APIError                                                       | 4XX, 5XX                                                                 | \*/\*                                                                    |