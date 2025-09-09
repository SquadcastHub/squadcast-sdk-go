# Webforms
(*Webforms*)

## Overview

### Available Operations

* [WebformsGetAllWebforms](#webformsgetallwebforms) - Get All Webforms
* [WebformsCreateWebform](#webformscreatewebform) - Create Webform
* [WebformsUpdateWebform](#webformsupdatewebform) - Update Webform
* [WebformsRemoveWebform](#webformsremovewebform) - Remove Webform
* [WebformsGetWebformByID](#webformsgetwebformbyid) - Get Webform By ID

## WebformsGetAllWebforms

Returns all webforms of the given `owner_id` (teamId) in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webforms_getAllWebforms" method="get" path="/v3/webform" -->
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

    res, err := s.Webforms.WebformsGetAllWebforms(ctx, "<id>", nil, nil)
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
| `ownerID`                                                | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `pageNumber`                                             | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `pageSize`                                               | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WebformsGetAllWebformsResponse](../../models/operations/webformsgetallwebformsresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.WebformsGetAllWebformsBadRequestError          | 400                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsForbiddenError           | 403                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsNotFoundError            | 404                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsConflictError            | 409                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsInternalServerError      | 500                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.WebformsGetAllWebformsGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |

## WebformsCreateWebform

Add a webform to the organization. Returns the webform object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webforms_createWebform" method="post" path="/v3/webform" -->
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

    res, err := s.Webforms.WebformsCreateWebform(ctx, components.V3WebformsCreateOrUpdateWebformRequest{
        OwnerID: "<id>",
        Name: "<value>",
        IsCname: false,
        IsCaptchaEnabled: false,
        CaptchaSecret: components.V3WebformsRecaptchaSecrets{
            SiteKey: "<value>",
            Secret: "<value>",
        },
        FormOwnerType: "<value>",
        FormOwnerID: "<id>",
        Services: []components.V3WebformsWFService{},
        Header: "<value>",
        Title: "<value>",
        FooterText: "<value>",
        FooterLink: "<value>",
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

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                  | :heavy_check_mark:                                                                                                     | The context to use for the request.                                                                                    |
| `request`                                                                                                              | [components.V3WebformsCreateOrUpdateWebformRequest](../../models/components/v3webformscreateorupdatewebformrequest.md) | :heavy_check_mark:                                                                                                     | The request object to use for the request.                                                                             |
| `opts`                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                               | :heavy_minus_sign:                                                                                                     | The options for this request.                                                                                          |

### Response

**[*operations.WebformsCreateWebformResponse](../../models/operations/webformscreatewebformresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.WebformsCreateWebformBadRequestError          | 400                                                     | application/json                                        |
| apierrors.WebformsCreateWebformUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.WebformsCreateWebformPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.WebformsCreateWebformForbiddenError           | 403                                                     | application/json                                        |
| apierrors.WebformsCreateWebformNotFoundError            | 404                                                     | application/json                                        |
| apierrors.WebformsCreateWebformConflictError            | 409                                                     | application/json                                        |
| apierrors.WebformsCreateWebformUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.WebformsCreateWebformInternalServerError      | 500                                                     | application/json                                        |
| apierrors.WebformsCreateWebformBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.WebformsCreateWebformServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.WebformsCreateWebformGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## WebformsUpdateWebform

Update a webform to the organization. Returns the webform object in response.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webforms_updateWebform" method="put" path="/v3/webform/{webformId}" -->
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

    res, err := s.Webforms.WebformsUpdateWebform(ctx, 926692, components.V3WebformsCreateOrUpdateWebformRequest{
        OwnerID: "<id>",
        Name: "<value>",
        IsCname: true,
        IsCaptchaEnabled: true,
        CaptchaSecret: components.V3WebformsRecaptchaSecrets{
            SiteKey: "<value>",
            Secret: "<value>",
        },
        FormOwnerType: "<value>",
        FormOwnerID: "<id>",
        Services: []components.V3WebformsWFService{
            components.V3WebformsWFService{
                ServiceID: "<id>",
                Name: "<value>",
                Alias: "<value>",
            },
        },
        Header: "<value>",
        Title: "<value>",
        FooterText: "<value>",
        FooterLink: "<value>",
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

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                                  | :heavy_check_mark:                                                                                                     | The context to use for the request.                                                                                    |
| `webformID`                                                                                                            | *int64*                                                                                                                | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `v3WebformsCreateOrUpdateWebformRequest`                                                                               | [components.V3WebformsCreateOrUpdateWebformRequest](../../models/components/v3webformscreateorupdatewebformrequest.md) | :heavy_check_mark:                                                                                                     | N/A                                                                                                                    |
| `opts`                                                                                                                 | [][operations.Option](../../models/operations/option.md)                                                               | :heavy_minus_sign:                                                                                                     | The options for this request.                                                                                          |

### Response

**[*operations.WebformsUpdateWebformResponse](../../models/operations/webformsupdatewebformresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.WebformsUpdateWebformBadRequestError          | 400                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformForbiddenError           | 403                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformNotFoundError            | 404                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformConflictError            | 409                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformInternalServerError      | 500                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.WebformsUpdateWebformGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## WebformsRemoveWebform

Remove a webform from the organization.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `user-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webforms_removeWebform" method="delete" path="/v3/webform/{webformId}" -->
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

    res, err := s.Webforms.WebformsRemoveWebform(ctx, 842504, nil)
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
| `webformID`                                              | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `ownerID`                                                | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WebformsRemoveWebformResponse](../../models/operations/webformsremovewebformresponse.md), error**

### Errors

| Error Type                                              | Status Code                                             | Content Type                                            |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| apierrors.WebformsRemoveWebformBadRequestError          | 400                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformUnauthorizedError        | 401                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformPaymentRequiredError     | 402                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformForbiddenError           | 403                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformNotFoundError            | 404                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformConflictError            | 409                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformUnprocessableEntityError | 422                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformInternalServerError      | 500                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformBadGatewayError          | 502                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformServiceUnavailableError  | 503                                                     | application/json                                        |
| apierrors.WebformsRemoveWebformGatewayTimeoutError      | 504                                                     | application/json                                        |
| apierrors.APIError                                      | 4XX, 5XX                                                | \*/\*                                                   |

## WebformsGetWebformByID

Returns a webform details of the given `webformId` in the request param.
Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `read` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Webforms_getWebformById" method="get" path="/v3/webform/{webformId}" -->
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

    res, err := s.Webforms.WebformsGetWebformByID(ctx, 831002, nil)
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
| `webformID`                                              | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `ownerID`                                                | **string*                                                | :heavy_minus_sign:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.WebformsGetWebformByIDResponse](../../models/operations/webformsgetwebformbyidresponse.md), error**

### Errors

| Error Type                                               | Status Code                                              | Content Type                                             |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| apierrors.WebformsGetWebformByIDBadRequestError          | 400                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDUnauthorizedError        | 401                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDPaymentRequiredError     | 402                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDForbiddenError           | 403                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDNotFoundError            | 404                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDConflictError            | 409                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDUnprocessableEntityError | 422                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDInternalServerError      | 500                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDBadGatewayError          | 502                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDServiceUnavailableError  | 503                                                      | application/json                                         |
| apierrors.WebformsGetWebformByIDGatewayTimeoutError      | 504                                                      | application/json                                         |
| apierrors.APIError                                       | 4XX, 5XX                                                 | \*/\*                                                    |