# Components
(*StatusPages.Components*)

## Overview

### Available Operations

* [List](#list) - List Components
* [Create](#create) - Create Component
* [DeleteByID](#deletebyid) - Delete Component By ID
* [GetByID](#getbyid) - Get Component By ID
* [UpdateByID](#updatebyid) - Update Component By ID

## List

List Components

### Example Usage

<!-- UsageSnippet language="go" operationID="Components_listComponents" method="get" path="/v4/statuspages/{statuspageID}/components" -->
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

    res, err := s.StatusPages.Components.List(ctx, "<id>")
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

**[*operations.ComponentsListComponentsResponse](../../models/operations/componentslistcomponentsresponse.md), error**

### Errors

| Error Type                                                 | Status Code                                                | Content Type                                               |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| apierrors.ComponentsListComponentsBadRequestError          | 400                                                        | application/json                                           |
| apierrors.ComponentsListComponentsUnauthorizedError        | 401                                                        | application/json                                           |
| apierrors.ComponentsListComponentsPaymentRequiredError     | 402                                                        | application/json                                           |
| apierrors.ComponentsListComponentsForbiddenError           | 403                                                        | application/json                                           |
| apierrors.ComponentsListComponentsNotFoundError            | 404                                                        | application/json                                           |
| apierrors.ComponentsListComponentsConflictError            | 409                                                        | application/json                                           |
| apierrors.ComponentsListComponentsUnprocessableEntityError | 422                                                        | application/json                                           |
| apierrors.ComponentsListComponentsInternalServerError      | 500                                                        | application/json                                           |
| apierrors.ComponentsListComponentsBadGatewayError          | 502                                                        | application/json                                           |
| apierrors.ComponentsListComponentsServiceUnavailableError  | 503                                                        | application/json                                           |
| apierrors.ComponentsListComponentsGatewayTimeoutError      | 504                                                        | application/json                                           |
| apierrors.APIError                                         | 4XX, 5XX                                                   | \*/\*                                                      |

## Create

Create Component

### Example Usage

<!-- UsageSnippet language="go" operationID="Components_createComponent" method="post" path="/v4/statuspages/{statuspageID}/components" -->
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

    res, err := s.StatusPages.Components.Create(ctx, "<id>", components.V4StatusPagesComponentsCreateComponentRequest{
        Name: "<value>",
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

| Parameter                                                                                                                            | Type                                                                                                                                 | Required                                                                                                                             | Description                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                | :heavy_check_mark:                                                                                                                   | The context to use for the request.                                                                                                  |
| `statuspageID`                                                                                                                       | *string*                                                                                                                             | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `v4StatusPagesComponentsCreateComponentRequest`                                                                                      | [components.V4StatusPagesComponentsCreateComponentRequest](../../models/components/v4statuspagescomponentscreatecomponentrequest.md) | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `opts`                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                             | :heavy_minus_sign:                                                                                                                   | The options for this request.                                                                                                        |

### Response

**[*operations.ComponentsCreateComponentResponse](../../models/operations/componentscreatecomponentresponse.md), error**

### Errors

| Error Type                                                  | Status Code                                                 | Content Type                                                |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| apierrors.ComponentsCreateComponentBadRequestError          | 400                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentUnauthorizedError        | 401                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentPaymentRequiredError     | 402                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentForbiddenError           | 403                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentNotFoundError            | 404                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentConflictError            | 409                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentUnprocessableEntityError | 422                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentInternalServerError      | 500                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentBadGatewayError          | 502                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentServiceUnavailableError  | 503                                                         | application/json                                            |
| apierrors.ComponentsCreateComponentGatewayTimeoutError      | 504                                                         | application/json                                            |
| apierrors.APIError                                          | 4XX, 5XX                                                    | \*/\*                                                       |

## DeleteByID

Delete Component By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Components_deleteComponentById" method="delete" path="/v4/statuspages/{statuspageID}/components/{component_id}" -->
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

    res, err := s.StatusPages.Components.DeleteByID(ctx, "<id>", "<id>")
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
| `componentID`                                            | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ComponentsDeleteComponentByIDResponse](../../models/operations/componentsdeletecomponentbyidresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.ComponentsDeleteComponentByIDBadRequestError          | 400                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDForbiddenError           | 403                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDNotFoundError            | 404                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDConflictError            | 409                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDInternalServerError      | 500                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.ComponentsDeleteComponentByIDGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |

## GetByID

Get Component By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Components_getComponentById" method="get" path="/v4/statuspages/{statuspageID}/components/{component_id}" -->
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

    res, err := s.StatusPages.Components.GetByID(ctx, "<id>", "<id>")
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
| `componentID`                                            | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ComponentsGetComponentByIDResponse](../../models/operations/componentsgetcomponentbyidresponse.md), error**

### Errors

| Error Type                                                   | Status Code                                                  | Content Type                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| apierrors.ComponentsGetComponentByIDBadRequestError          | 400                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDUnauthorizedError        | 401                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDPaymentRequiredError     | 402                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDForbiddenError           | 403                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDNotFoundError            | 404                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDConflictError            | 409                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDUnprocessableEntityError | 422                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDInternalServerError      | 500                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDBadGatewayError          | 502                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDServiceUnavailableError  | 503                                                          | application/json                                             |
| apierrors.ComponentsGetComponentByIDGatewayTimeoutError      | 504                                                          | application/json                                             |
| apierrors.APIError                                           | 4XX, 5XX                                                     | \*/\*                                                        |

## UpdateByID

Update Component By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Components_updateComponentById" method="put" path="/v4/statuspages/{statuspageID}/components/{component_id}" -->
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

    res, err := s.StatusPages.Components.UpdateByID(ctx, "<id>", "<id>", components.V4StatusPagesComponentsUpdateComponentByIDRequest{
        Name: "<value>",
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
| `statuspageID`                                                                                                                               | *string*                                                                                                                                     | :heavy_check_mark:                                                                                                                           | N/A                                                                                                                                          |
| `componentID`                                                                                                                                | *string*                                                                                                                                     | :heavy_check_mark:                                                                                                                           | N/A                                                                                                                                          |
| `v4StatusPagesComponentsUpdateComponentByIDRequest`                                                                                          | [components.V4StatusPagesComponentsUpdateComponentByIDRequest](../../models/components/v4statuspagescomponentsupdatecomponentbyidrequest.md) | :heavy_check_mark:                                                                                                                           | N/A                                                                                                                                          |
| `opts`                                                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                                                     | :heavy_minus_sign:                                                                                                                           | The options for this request.                                                                                                                |

### Response

**[*operations.ComponentsUpdateComponentByIDResponse](../../models/operations/componentsupdatecomponentbyidresponse.md), error**

### Errors

| Error Type                                                      | Status Code                                                     | Content Type                                                    |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| apierrors.ComponentsUpdateComponentByIDBadRequestError          | 400                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDUnauthorizedError        | 401                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDPaymentRequiredError     | 402                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDForbiddenError           | 403                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDNotFoundError            | 404                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDConflictError            | 409                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDUnprocessableEntityError | 422                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDInternalServerError      | 500                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDBadGatewayError          | 502                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDServiceUnavailableError  | 503                                                             | application/json                                                |
| apierrors.ComponentsUpdateComponentByIDGatewayTimeoutError      | 504                                                             | application/json                                                |
| apierrors.APIError                                              | 4XX, 5XX                                                        | \*/\*                                                           |