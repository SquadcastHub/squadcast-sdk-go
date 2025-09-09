# IncidentsAdditionalResponders
(*IncidentsAdditionalResponders*)

## Overview

### Available Operations

* [AdditionalRespondersGetAdditionalResponders](#additionalrespondersgetadditionalresponders) - Get Additional Responders
* [AdditionalRespondersAddAdditionalResponders](#additionalrespondersaddadditionalresponders) - Add Additional Responders
* [AdditionalRespondersRemoveAdditionalResponders](#additionalrespondersremoveadditionalresponders) - Remove Additional Responders

## AdditionalRespondersGetAdditionalResponders

- This endpoint is used to get the incident additional responders.

- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="AdditionalResponders_getAdditionalResponders" method="get" path="/v3/incidents/{incidentID}/additional-responders" -->
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

    res, err := s.IncidentsAdditionalResponders.AdditionalRespondersGetAdditionalResponders(ctx, "<id>")
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

**[*operations.AdditionalRespondersGetAdditionalRespondersResponse](../../models/operations/additionalrespondersgetadditionalrespondersresponse.md), error**

### Errors

| Error Type                                                                    | Status Code                                                                   | Content Type                                                                  |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| apierrors.AdditionalRespondersGetAdditionalRespondersBadRequestError          | 400                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersUnauthorizedError        | 401                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersPaymentRequiredError     | 402                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersForbiddenError           | 403                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersNotFoundError            | 404                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersConflictError            | 409                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersUnprocessableEntityError | 422                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersInternalServerError      | 500                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersBadGatewayError          | 502                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersServiceUnavailableError  | 503                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersGetAdditionalRespondersGatewayTimeoutError      | 504                                                                           | application/json                                                              |
| apierrors.APIError                                                            | 4XX, 5XX                                                                      | \*/\*                                                                         |

## AdditionalRespondersAddAdditionalResponders

- This endpoint is used to add additional responders to an Incident.

- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="AdditionalResponders_addAdditionalResponders" method="put" path="/v3/incidents/{incidentID}/additional-responders" -->
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

    res, err := s.IncidentsAdditionalResponders.AdditionalRespondersAddAdditionalResponders(ctx, "<id>", components.V3IncidentsAdditionalRespondersAddAdditionalRespondersRequest{
        AdditionalResponders: []components.AdditionalResponder{},
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

| Parameter                                                                                                                                                            | Type                                                                                                                                                                 | Required                                                                                                                                                             | Description                                                                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                                                                                | :heavy_check_mark:                                                                                                                                                   | The context to use for the request.                                                                                                                                  |
| `incidentID`                                                                                                                                                         | *string*                                                                                                                                                             | :heavy_check_mark:                                                                                                                                                   | N/A                                                                                                                                                                  |
| `v3IncidentsAdditionalRespondersAddAdditionalRespondersRequest`                                                                                                      | [components.V3IncidentsAdditionalRespondersAddAdditionalRespondersRequest](../../models/components/v3incidentsadditionalrespondersaddadditionalrespondersrequest.md) | :heavy_check_mark:                                                                                                                                                   | N/A                                                                                                                                                                  |
| `opts`                                                                                                                                                               | [][operations.Option](../../models/operations/option.md)                                                                                                             | :heavy_minus_sign:                                                                                                                                                   | The options for this request.                                                                                                                                        |

### Response

**[*operations.AdditionalRespondersAddAdditionalRespondersResponse](../../models/operations/additionalrespondersaddadditionalrespondersresponse.md), error**

### Errors

| Error Type                                                                    | Status Code                                                                   | Content Type                                                                  |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| apierrors.AdditionalRespondersAddAdditionalRespondersBadRequestError          | 400                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersUnauthorizedError        | 401                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersPaymentRequiredError     | 402                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersForbiddenError           | 403                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersNotFoundError            | 404                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersConflictError            | 409                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersUnprocessableEntityError | 422                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersInternalServerError      | 500                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersBadGatewayError          | 502                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersServiceUnavailableError  | 503                                                                           | application/json                                                              |
| apierrors.AdditionalRespondersAddAdditionalRespondersGatewayTimeoutError      | 504                                                                           | application/json                                                              |
| apierrors.APIError                                                            | 4XX, 5XX                                                                      | \*/\*                                                                         |

## AdditionalRespondersRemoveAdditionalResponders

- This endpoint is used to remove an additional responder from an Incident.

- Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="AdditionalResponders_removeAdditionalResponders" method="delete" path="/v3/incidents/{incidentID}/additional-responders/{responderID}" -->
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

    res, err := s.IncidentsAdditionalResponders.AdditionalRespondersRemoveAdditionalResponders(ctx, "<id>", "<id>")
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
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `responderID`                                            | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.AdditionalRespondersRemoveAdditionalRespondersResponse](../../models/operations/additionalrespondersremoveadditionalrespondersresponse.md), error**

### Errors

| Error Type                                                                       | Status Code                                                                      | Content Type                                                                     |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersBadRequestError          | 400                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersUnauthorizedError        | 401                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersPaymentRequiredError     | 402                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersForbiddenError           | 403                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersNotFoundError            | 404                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersConflictError            | 409                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersUnprocessableEntityError | 422                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersInternalServerError      | 500                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersBadGatewayError          | 502                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersServiceUnavailableError  | 503                                                                              | application/json                                                                 |
| apierrors.AdditionalRespondersRemoveAdditionalRespondersGatewayTimeoutError      | 504                                                                              | application/json                                                                 |
| apierrors.APIError                                                               | 4XX, 5XX                                                                         | \*/\*                                                                            |