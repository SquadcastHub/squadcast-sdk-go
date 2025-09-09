# Services
(*Services*)

## Overview

### Available Operations

* [ServicesGetServices](#servicesgetservices) - Get All Services
* [ServicesCreateService](#servicescreateservice) - Create Service
* [ServicesGetServicesByName](#servicesgetservicesbyname) - Get Services By Name
* [ServicesGetServiceByID](#servicesgetservicebyid) - Get Service By ID
* [ServicesUpdateService](#servicesupdateservice) - Update Service
* [ServicesDeleteService](#servicesdeleteservice) - Delete Service
* [ServicesCreateOrUpdateAPTAConfig](#servicescreateorupdateaptaconfig) - Auto Pause Transient Alerts (APTA)
* [ServicesCreateOrUpdateIAGConfig](#servicescreateorupdateiagconfig) - Intelligent Alert Grouping (IAG)
* [ServicesDelayedNotificationConfig](#servicesdelayednotificationconfig) - Delayed Notification Config

## ServicesGetServices

Get All Services

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_getServices" method="get" path="/v3/services" -->
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

    res, err := s.Services.ServicesGetServices(ctx, nil, nil, nil)
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
| `ownerID`                                                | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `entityOwner`                                            | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `name`                                                   | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ServicesGetServicesResponse](../../models/operations/servicesgetservicesresponse.md), error**

### Errors

| Error Type                                            | Status Code                                           | Content Type                                          |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| apierrors.ServicesGetServicesBadRequestError          | 400                                                   | application/json                                      |
| apierrors.ServicesGetServicesUnauthorizedError        | 401                                                   | application/json                                      |
| apierrors.ServicesGetServicesPaymentRequiredError     | 402                                                   | application/json                                      |
| apierrors.ServicesGetServicesForbiddenError           | 403                                                   | application/json                                      |
| apierrors.ServicesGetServicesNotFoundError            | 404                                                   | application/json                                      |
| apierrors.ServicesGetServicesConflictError            | 409                                                   | application/json                                      |
| apierrors.ServicesGetServicesUnprocessableEntityError | 422                                                   | application/json                                      |
| apierrors.ServicesGetServicesInternalServerError      | 500                                                   | application/json                                      |
| apierrors.ServicesGetServicesBadGatewayError          | 502                                                   | application/json                                      |
| apierrors.ServicesGetServicesServiceUnavailableError  | 503                                                   | application/json                                      |
| apierrors.ServicesGetServicesGatewayTimeoutError      | 504                                                   | application/json                                      |
| apierrors.APIError                                    | 4XX, 5XX                                              | \*/\*                                                 |

## ServicesCreateService

Create Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_createService" method="post" path="/v3/services" -->
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

    res, err := s.Services.ServicesCreateService(ctx, "<id>", components.V3ServicesCreateServiceRequest{
        Name: "<value>",
        EscalationPolicyID: "<id>",
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

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `ownerID`                                                                                              | *string*                                                                                               | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `v3ServicesCreateServiceRequest`                                                                       | [components.V3ServicesCreateServiceRequest](../../models/components/v3servicescreateservicerequest.md) | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.ServicesCreateServiceResponse](../../models/operations/servicescreateserviceresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.ServicesCreateServiceBadRequestError          | 400                                                     | application/json                                        |
| apierrors.ServicesCreateServiceUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.ServicesCreateServicePaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.ServicesCreateServiceForbiddenError           | 403                                                     | application/json                                        |
| apierrors.ServicesCreateServiceNotFoundError            | 404                                                     | application/json                                        |
| apierrors.ServicesCreateServiceConflictError            | 409                                                     | application/json                                        |
| apierrors.ServicesCreateServiceUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.ServicesCreateServiceInternalServerError      | 500                                                     | application/json                                        |
| apierrors.ServicesCreateServiceBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.ServicesCreateServiceServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.ServicesCreateServiceGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## ServicesGetServicesByName

Get Services By Name

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_getServicesByName" method="get" path="/v3/services/by-name" -->
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

    res, err := s.Services.ServicesGetServicesByName(ctx, "<value>", "<id>")
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
| `name`                                                   | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ServicesGetServicesByNameResponse](../../models/operations/servicesgetservicesbynameresponse.md), error**

### Errors

| Error Type                                                  | Status Code                                                 | Content Type                                                |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| apierrors.ServicesGetServicesByNameBadRequestError          | 400                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameUnauthorizedError        | 401                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNamePaymentRequiredError     | 402                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameForbiddenError           | 403                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameNotFoundError            | 404                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameConflictError            | 409                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameUnprocessableEntityError | 422                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameInternalServerError      | 500                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameBadGatewayError          | 502                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameServiceUnavailableError  | 503                                                         | application/json                                            |
| apierrors.ServicesGetServicesByNameGatewayTimeoutError      | 504                                                         | application/json                                            |
| apierrors.APIError                                          | 4XX, 5XX                                                    | \*/\*                                                       |

## ServicesGetServiceByID

Get Service By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_getServiceById" method="get" path="/v3/services/{serviceID}" -->
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

    res, err := s.Services.ServicesGetServiceByID(ctx, "<id>")
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
| `serviceID`                                              | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ServicesGetServiceByIDResponse](../../models/operations/servicesgetservicebyidresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.ServicesGetServiceByIDBadRequestError          | 400                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDForbiddenError           | 403                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDNotFoundError            | 404                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDConflictError            | 409                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDInternalServerError      | 500                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.ServicesGetServiceByIDGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## ServicesUpdateService

Update Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_updateService" method="put" path="/v3/services/{serviceID}" -->
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

    res, err := s.Services.ServicesUpdateService(ctx, "<id>", components.V3ServicesUpdateServiceRequest{})
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
| `serviceID`                                                                                            | *string*                                                                                               | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `v3ServicesUpdateServiceRequest`                                                                       | [components.V3ServicesUpdateServiceRequest](../../models/components/v3servicesupdateservicerequest.md) | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `opts`                                                                                                 | [][operations.Option](../../models/operations/option.md)                                               | :heavy_minus_sign:                                                                                     | The options for this request.                                                                          |

### Response

**[*operations.ServicesUpdateServiceResponse](../../models/operations/servicesupdateserviceresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.ServicesUpdateServiceBadRequestError          | 400                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.ServicesUpdateServicePaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceForbiddenError           | 403                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceNotFoundError            | 404                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceConflictError            | 409                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceInternalServerError      | 500                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.ServicesUpdateServiceGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## ServicesDeleteService

Delete Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_deleteService" method="delete" path="/v3/services/{serviceID}" -->
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

    res, err := s.Services.ServicesDeleteService(ctx, "<id>")
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
| `serviceID`                                              | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.ServicesDeleteServiceResponse](../../models/operations/servicesdeleteserviceresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.ServicesDeleteServiceBadRequestError          | 400                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.ServicesDeleteServicePaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceForbiddenError           | 403                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceNotFoundError            | 404                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceConflictError            | 409                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceInternalServerError      | 500                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.ServicesDeleteServiceGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## ServicesCreateOrUpdateAPTAConfig

Auto Pause Transient Alerts (APTA)

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_createOrUpdateAPTAConfig" method="put" path="/v3/services/{serviceID}/apta-config" -->
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

    res, err := s.Services.ServicesCreateOrUpdateAPTAConfig(ctx, "<id>", components.V3ServicesAPTAConfigRequest{
        IsEnabled: false,
        TimeoutInMins: 680029,
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
| `serviceID`                                                                                      | *string*                                                                                         | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `v3ServicesAPTAConfigRequest`                                                                    | [components.V3ServicesAPTAConfigRequest](../../models/components/v3servicesaptaconfigrequest.md) | :heavy_check_mark:                                                                               | N/A                                                                                              |
| `opts`                                                                                           | [][operations.Option](../../models/operations/option.md)                                         | :heavy_minus_sign:                                                                               | The options for this request.                                                                    |

### Response

**[*operations.ServicesCreateOrUpdateAPTAConfigResponse](../../models/operations/servicescreateorupdateaptaconfigresponse.md), error**

### Errors

| Error Type                                                         | Status Code                                                        | Content Type                                                       |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| apierrors.ServicesCreateOrUpdateAPTAConfigBadRequestError          | 400                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigUnauthorizedError        | 401                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigPaymentRequiredError     | 402                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigForbiddenError           | 403                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigNotFoundError            | 404                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigConflictError            | 409                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigUnprocessableEntityError | 422                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigInternalServerError      | 500                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigBadGatewayError          | 502                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigServiceUnavailableError  | 503                                                                | application/json                                                   |
| apierrors.ServicesCreateOrUpdateAPTAConfigGatewayTimeoutError      | 504                                                                | application/json                                                   |
| apierrors.APIError                                                 | 4XX, 5XX                                                           | \*/\*                                                              |

## ServicesCreateOrUpdateIAGConfig

Intelligent Alert Grouping (IAG)

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_createOrUpdateIAGConfig" method="put" path="/v3/services/{serviceID}/iag-config" -->
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

    res, err := s.Services.ServicesCreateOrUpdateIAGConfig(ctx, "<id>", components.V3ServicesIAGConfigRequest{
        IsEnabled: true,
        RollingWindowInMins: 246036,
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

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `serviceID`                                                                                    | *string*                                                                                       | :heavy_check_mark:                                                                             | N/A                                                                                            |
| `v3ServicesIAGConfigRequest`                                                                   | [components.V3ServicesIAGConfigRequest](../../models/components/v3servicesiagconfigrequest.md) | :heavy_check_mark:                                                                             | N/A                                                                                            |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*operations.ServicesCreateOrUpdateIAGConfigResponse](../../models/operations/servicescreateorupdateiagconfigresponse.md), error**

### Errors

| Error Type                                                        | Status Code                                                       | Content Type                                                      |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| apierrors.ServicesCreateOrUpdateIAGConfigBadRequestError          | 400                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigUnauthorizedError        | 401                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigPaymentRequiredError     | 402                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigForbiddenError           | 403                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigNotFoundError            | 404                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigConflictError            | 409                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigUnprocessableEntityError | 422                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigInternalServerError      | 500                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigBadGatewayError          | 502                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigServiceUnavailableError  | 503                                                               | application/json                                                  |
| apierrors.ServicesCreateOrUpdateIAGConfigGatewayTimeoutError      | 504                                                               | application/json                                                  |
| apierrors.APIError                                                | 4XX, 5XX                                                          | \*/\*                                                             |

## ServicesDelayedNotificationConfig

Delayed Notification Config

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_delayedNotificationConfig" method="put" path="/v3/services/{serviceID}/notification-delay-config" -->
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

    res, err := s.Services.ServicesDelayedNotificationConfig(ctx, "<id>", components.V3ServicesNotificationDelayConfigRequest{
        IsEnabled: false,
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
| `serviceID`                                                                                                                | *string*                                                                                                                   | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `v3ServicesNotificationDelayConfigRequest`                                                                                 | [components.V3ServicesNotificationDelayConfigRequest](../../models/components/v3servicesnotificationdelayconfigrequest.md) | :heavy_check_mark:                                                                                                         | N/A                                                                                                                        |
| `opts`                                                                                                                     | [][operations.Option](../../models/operations/option.md)                                                                   | :heavy_minus_sign:                                                                                                         | The options for this request.                                                                                              |

### Response

**[*operations.ServicesDelayedNotificationConfigResponse](../../models/operations/servicesdelayednotificationconfigresponse.md), error**

### Errors

| Error Type                                                          | Status Code                                                         | Content Type                                                        |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| apierrors.ServicesDelayedNotificationConfigBadRequestError          | 400                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigUnauthorizedError        | 401                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigPaymentRequiredError     | 402                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigForbiddenError           | 403                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigNotFoundError            | 404                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigConflictError            | 409                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigUnprocessableEntityError | 422                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigInternalServerError      | 500                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigBadGatewayError          | 502                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigServiceUnavailableError  | 503                                                                 | application/json                                                    |
| apierrors.ServicesDelayedNotificationConfigGatewayTimeoutError      | 504                                                                 | application/json                                                    |
| apierrors.APIError                                                  | 4XX, 5XX                                                            | \*/\*                                                               |