# Services
(*Services*)

## Overview

### Available Operations

* [List](#list) - Get All Services
* [Create](#create) - Create Service
* [GetByName](#getbyname) - Get Services By Name
* [GetByID](#getbyid) - Get Service By ID
* [Update](#update) - Update Service
* [Delete](#delete) - Delete Service
* [CreateOrUpdateAptaConfig](#createorupdateaptaconfig) - Auto Pause Transient Alerts (APTA)
* [UpsertIagConfig](#upsertiagconfig) - Intelligent Alert Grouping (IAG)
* [UpdateNotificationDelayConfig](#updatenotificationdelayconfig) - Delayed Notification Config
* [CreateOrUpdateDependencies](#createorupdatedependencies) - Create or Update Dependencies
* [CreateOrUpdateNotificationTemplateOverlay](#createorupdatenotificationtemplateoverlay) - Create or Update Notification Template Overlay
* [GetAllDedupKeyOverlays](#getalldedupkeyoverlays) - Get All Dedup Key Overlay by Service
* [UpdateDedupKeyOverlay](#updatededupkeyoverlay) - Update Dedup Key Overlay
* [GetRoutingRules](#getroutingrules) - Get Routing Rules
* [CreateOrUpdateSuppressionRules](#createorupdatesuppressionrules) - Create or Update Suppression Rules
* [CreateOrUpdateTaggingRules](#createorupdatetaggingrules) - Create or Update Tagging Rules

## List

Get All Services

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_getServices" method="get" path="/v3/services" -->
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

    res, err := s.Services.List(ctx, nil, nil, nil)
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

## Create

Create Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_createService" method="post" path="/v3/services" -->
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

    res, err := s.Services.Create(ctx, "<id>", components.V3ServicesCreateServiceRequest{
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

## GetByName

Get Services By Name

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_getServicesByName" method="get" path="/v3/services/by-name" -->
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

    res, err := s.Services.GetByName(ctx, "<value>", "<id>")
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

## GetByID

Get Service By ID

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_getServiceById" method="get" path="/v3/services/{serviceID}" -->
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

    res, err := s.Services.GetByID(ctx, "<id>")
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

## Update

Update Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_updateService" method="put" path="/v3/services/{serviceID}" -->
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

    res, err := s.Services.Update(ctx, "<id>", components.V3ServicesUpdateServiceRequest{})
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

## Delete

Delete Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_deleteService" method="delete" path="/v3/services/{serviceID}" -->
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

    res, err := s.Services.Delete(ctx, "<id>")
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

## CreateOrUpdateAptaConfig

Auto Pause Transient Alerts (APTA)

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_createOrUpdateAPTAConfig" method="put" path="/v3/services/{serviceID}/apta-config" -->
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

    res, err := s.Services.CreateOrUpdateAptaConfig(ctx, "<id>", components.V3ServicesAPTAConfigRequest{
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

## UpsertIagConfig

Intelligent Alert Grouping (IAG)

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_createOrUpdateIAGConfig" method="put" path="/v3/services/{serviceID}/iag-config" -->
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

    res, err := s.Services.UpsertIagConfig(ctx, "<id>", components.V3ServicesIAGConfigRequest{
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

## UpdateNotificationDelayConfig

Delayed Notification Config

### Example Usage

<!-- UsageSnippet language="go" operationID="Services_delayedNotificationConfig" method="put" path="/v3/services/{serviceID}/notification-delay-config" -->
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

    res, err := s.Services.UpdateNotificationDelayConfig(ctx, "<id>", components.V3ServicesNotificationDelayConfigRequest{
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

## CreateOrUpdateDependencies

Create or Update Dependencies

### Example Usage

<!-- UsageSnippet language="go" operationID="Dependencies_createOrUpdateDependencies" method="post" path="/v3/services/{serviceID}/dependencies" -->
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

    res, err := s.Services.CreateOrUpdateDependencies(ctx, "<id>", components.V3ServicesDependenciesCreateOrUpdateDependenciesRequest{
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

## CreateOrUpdateNotificationTemplateOverlay

Create or Update Notification Template Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_createOrUpdateNotificationTemplateOverlay" method="put" path="/v3/services/{serviceID}/overlays/custom-content/{alertSource}" -->
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

    res, err := s.Services.CreateOrUpdateNotificationTemplateOverlay(ctx, "<id>", "<value>", components.V3ServicesOverlayUpdateCustomContentTemplateOverlayRequest{
        OverlayTemplateType: "<value>",
        MessageOverlay: components.MessageOverlay{
            Template: "<value>",
        },
        DescriptionOverlay: components.DescriptionOverlay{
            Template: "<value>",
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

| Parameter                                                                                                                                                      | Type                                                                                                                                                           | Required                                                                                                                                                       | Description                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                                                                                          | :heavy_check_mark:                                                                                                                                             | The context to use for the request.                                                                                                                            |
| `serviceID`                                                                                                                                                    | *string*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                             | N/A                                                                                                                                                            |
| `alertSource`                                                                                                                                                  | *string*                                                                                                                                                       | :heavy_check_mark:                                                                                                                                             | N/A                                                                                                                                                            |
| `v3ServicesOverlayUpdateCustomContentTemplateOverlayRequest`                                                                                                   | [components.V3ServicesOverlayUpdateCustomContentTemplateOverlayRequest](../../models/components/v3servicesoverlayupdatecustomcontenttemplateoverlayrequest.md) | :heavy_check_mark:                                                                                                                                             | N/A                                                                                                                                                            |
| `opts`                                                                                                                                                         | [][operations.Option](../../models/operations/option.md)                                                                                                       | :heavy_minus_sign:                                                                                                                                             | The options for this request.                                                                                                                                  |

### Response

**[*operations.OverlayCreateOrUpdateNotificationTemplateOverlayResponse](../../models/operations/overlaycreateorupdatenotificationtemplateoverlayresponse.md), error**

### Errors

| Error Type                                                                         | Status Code                                                                        | Content Type                                                                       |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayBadRequestError          | 400                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayUnauthorizedError        | 401                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayPaymentRequiredError     | 402                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayForbiddenError           | 403                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayNotFoundError            | 404                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayConflictError            | 409                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayUnprocessableEntityError | 422                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayInternalServerError      | 500                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayBadGatewayError          | 502                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayServiceUnavailableError  | 503                                                                                | application/json                                                                   |
| apierrors.OverlayCreateOrUpdateNotificationTemplateOverlayGatewayTimeoutError      | 504                                                                                | application/json                                                                   |
| apierrors.APIError                                                                 | 4XX, 5XX                                                                           | \*/\*                                                                              |

## GetAllDedupKeyOverlays

Get All Dedup Key Overlay by Service

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_getAllDedupKeyOverlayByService" method="get" path="/v3/services/{serviceID}/overlays/dedup-key" -->
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

    res, err := s.Services.GetAllDedupKeyOverlays(ctx, "<id>")
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

**[*operations.OverlayGetAllDedupKeyOverlayByServiceResponse](../../models/operations/overlaygetalldedupkeyoverlaybyserviceresponse.md), error**

### Errors

| Error Type                                                              | Status Code                                                             | Content Type                                                            |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceBadRequestError          | 400                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceUnauthorizedError        | 401                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServicePaymentRequiredError     | 402                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceForbiddenError           | 403                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceNotFoundError            | 404                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceConflictError            | 409                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceUnprocessableEntityError | 422                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceInternalServerError      | 500                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceBadGatewayError          | 502                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceServiceUnavailableError  | 503                                                                     | application/json                                                        |
| apierrors.OverlayGetAllDedupKeyOverlayByServiceGatewayTimeoutError      | 504                                                                     | application/json                                                        |
| apierrors.APIError                                                      | 4XX, 5XX                                                                | \*/\*                                                                   |

## UpdateDedupKeyOverlay

Update Dedup Key Overlay

### Example Usage

<!-- UsageSnippet language="go" operationID="Overlay_updateDedupKeyOverlay" method="put" path="/v3/services/{serviceID}/overlays/dedup-key/{alertSource}" -->
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

    res, err := s.Services.UpdateDedupKeyOverlay(ctx, "<id>", "<value>", components.V3ServicesOverlayUpdateDedupKeyOverlayRequest{
        OverlayTemplateType: "<value>",
        DedupKeyOverlay: components.DedupKeyOverlay{
            Template: "<value>",
            Duration: 360400,
        },
    })
    if err != nil {
        log.Fatal(err)
    }
    if res.OneOf != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                            | Type                                                                                                                                 | Required                                                                                                                             | Description                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                | :heavy_check_mark:                                                                                                                   | The context to use for the request.                                                                                                  |
| `serviceID`                                                                                                                          | *string*                                                                                                                             | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `alertSource`                                                                                                                        | *string*                                                                                                                             | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `v3ServicesOverlayUpdateDedupKeyOverlayRequest`                                                                                      | [components.V3ServicesOverlayUpdateDedupKeyOverlayRequest](../../models/components/v3servicesoverlayupdatededupkeyoverlayrequest.md) | :heavy_check_mark:                                                                                                                   | N/A                                                                                                                                  |
| `opts`                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                             | :heavy_minus_sign:                                                                                                                   | The options for this request.                                                                                                        |

### Response

**[*operations.OverlayUpdateDedupKeyOverlayResponse](../../models/operations/overlayupdatededupkeyoverlayresponse.md), error**

### Errors

| Error Type                                                     | Status Code                                                    | Content Type                                                   |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| apierrors.OverlayUpdateDedupKeyOverlayBadRequestError          | 400                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayUnauthorizedError        | 401                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayPaymentRequiredError     | 402                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayForbiddenError           | 403                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayNotFoundError            | 404                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayConflictError            | 409                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayUnprocessableEntityError | 422                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayInternalServerError      | 500                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayBadGatewayError          | 502                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayServiceUnavailableError  | 503                                                            | application/json                                               |
| apierrors.OverlayUpdateDedupKeyOverlayGatewayTimeoutError      | 504                                                            | application/json                                               |
| apierrors.APIError                                             | 4XX, 5XX                                                       | \*/\*                                                          |

## GetRoutingRules

Get Routing Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="RoutingRules_getRoutingRules" method="get" path="/v3/services/{serviceID}/routing-rules" -->
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

    res, err := s.Services.GetRoutingRules(ctx, "<id>")
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

**[*operations.RoutingRulesGetRoutingRulesResponse](../../models/operations/routingrulesgetroutingrulesresponse.md), error**

### Errors

| Error Type                                                    | Status Code                                                   | Content Type                                                  |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| apierrors.RoutingRulesGetRoutingRulesBadRequestError          | 400                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesUnauthorizedError        | 401                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesPaymentRequiredError     | 402                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesForbiddenError           | 403                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesNotFoundError            | 404                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesConflictError            | 409                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesUnprocessableEntityError | 422                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesInternalServerError      | 500                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesBadGatewayError          | 502                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesServiceUnavailableError  | 503                                                           | application/json                                              |
| apierrors.RoutingRulesGetRoutingRulesGatewayTimeoutError      | 504                                                           | application/json                                              |
| apierrors.APIError                                            | 4XX, 5XX                                                      | \*/\*                                                         |

## CreateOrUpdateSuppressionRules

Create or Update Suppression Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="SuppressionRules_createOrUpdateSuppressionRules" method="post" path="/v3/services/{serviceID}/suppression-rules" -->
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

    res, err := s.Services.CreateOrUpdateSuppressionRules(ctx, "<id>", components.V3ServicesSuppressionRulesCreateOrUpdateSuppressionRulesRequest{
        Rules: []components.V3ServicesSuppressionRulesSuppressionRule{},
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

| Parameter                                                                                                                                                                | Type                                                                                                                                                                     | Required                                                                                                                                                                 | Description                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                                                                    | :heavy_check_mark:                                                                                                                                                       | The context to use for the request.                                                                                                                                      |
| `serviceID`                                                                                                                                                              | *string*                                                                                                                                                                 | :heavy_check_mark:                                                                                                                                                       | N/A                                                                                                                                                                      |
| `v3ServicesSuppressionRulesCreateOrUpdateSuppressionRulesRequest`                                                                                                        | [components.V3ServicesSuppressionRulesCreateOrUpdateSuppressionRulesRequest](../../models/components/v3servicessuppressionrulescreateorupdatesuppressionrulesrequest.md) | :heavy_check_mark:                                                                                                                                                       | N/A                                                                                                                                                                      |
| `opts`                                                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                                                 | :heavy_minus_sign:                                                                                                                                                       | The options for this request.                                                                                                                                            |

### Response

**[*operations.SuppressionRulesCreateOrUpdateSuppressionRulesResponse](../../models/operations/suppressionrulescreateorupdatesuppressionrulesresponse.md), error**

### Errors

| Error Type                                                                       | Status Code                                                                      | Content Type                                                                     |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesBadRequestError          | 400                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesUnauthorizedError        | 401                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesPaymentRequiredError     | 402                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesForbiddenError           | 403                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesNotFoundError            | 404                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesConflictError            | 409                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesUnprocessableEntityError | 422                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesInternalServerError      | 500                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesBadGatewayError          | 502                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesServiceUnavailableError  | 503                                                                              | application/json                                                                 |
| apierrors.SuppressionRulesCreateOrUpdateSuppressionRulesGatewayTimeoutError      | 504                                                                              | application/json                                                                 |
| apierrors.APIError                                                               | 4XX, 5XX                                                                         | \*/\*                                                                            |

## CreateOrUpdateTaggingRules

Create or Update Tagging Rules

### Example Usage

<!-- UsageSnippet language="go" operationID="TaggingRules_createOrUpdateTaggingRules" method="post" path="/v3/services/{serviceID}/tagging-rules" -->
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

    res, err := s.Services.CreateOrUpdateTaggingRules(ctx, "<id>", components.V3ServicesTaggingRulesCreateOrUpdateTaggingRulesRequest{
        Rules: []components.V3ServicesTaggingRulesTagRule{
            components.V3ServicesTaggingRulesTagRule{},
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
| `v3ServicesTaggingRulesCreateOrUpdateTaggingRulesRequest`                                                                                                | [components.V3ServicesTaggingRulesCreateOrUpdateTaggingRulesRequest](../../models/components/v3servicestaggingrulescreateorupdatetaggingrulesrequest.md) | :heavy_check_mark:                                                                                                                                       | N/A                                                                                                                                                      |
| `opts`                                                                                                                                                   | [][operations.Option](../../models/operations/option.md)                                                                                                 | :heavy_minus_sign:                                                                                                                                       | The options for this request.                                                                                                                            |

### Response

**[*operations.TaggingRulesCreateOrUpdateTaggingRulesResponse](../../models/operations/taggingrulescreateorupdatetaggingrulesresponse.md), error**

### Errors

| Error Type                                                               | Status Code                                                              | Content Type                                                             |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesBadRequestError          | 400                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesUnauthorizedError        | 401                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesPaymentRequiredError     | 402                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesForbiddenError           | 403                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesNotFoundError            | 404                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesConflictError            | 409                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesUnprocessableEntityError | 422                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesInternalServerError      | 500                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesBadGatewayError          | 502                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesServiceUnavailableError  | 503                                                                      | application/json                                                         |
| apierrors.TaggingRulesCreateOrUpdateTaggingRulesGatewayTimeoutError      | 504                                                                      | application/json                                                         |
| apierrors.APIError                                                       | 4XX, 5XX                                                                 | \*/\*                                                                    |