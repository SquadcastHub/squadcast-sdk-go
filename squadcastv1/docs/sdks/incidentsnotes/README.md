# IncidentsNotes
(*IncidentsNotes*)

## Overview

### Available Operations

* [NotesCreateNotes](#notescreatenotes) - Create Notes
* [NotesGetAllNotes](#notesgetallnotes) - Get All Notes
* [NotesDeleteNote](#notesdeletenote) - Delete Note
* [NotesUpdateNote](#notesupdatenote) - Update Note

## NotesCreateNotes

Create Notes

### Example Usage

<!-- UsageSnippet language="go" operationID="Notes_createNotes" method="post" path="/v3/incidents/{IncidentId}/warroom" -->
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

    res, err := s.IncidentsNotes.NotesCreateNotes(ctx, "<id>", components.V3IncidentsNotesCreateNoteRequest{
        Message: "<value>",
        Attachments: []string{
            "<value 1>",
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

| Parameter                                                                                                    | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                        | :heavy_check_mark:                                                                                           | The context to use for the request.                                                                          |
| `incidentID`                                                                                                 | *string*                                                                                                     | :heavy_check_mark:                                                                                           | Required                                                                                                     |
| `v3IncidentsNotesCreateNoteRequest`                                                                          | [components.V3IncidentsNotesCreateNoteRequest](../../models/components/v3incidentsnotescreatenoterequest.md) | :heavy_check_mark:                                                                                           | N/A                                                                                                          |
| `opts`                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                     | :heavy_minus_sign:                                                                                           | The options for this request.                                                                                |

### Response

**[*operations.NotesCreateNotesResponse](../../models/operations/notescreatenotesresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.NotesCreateNotesBadRequestError          | 400                                                | application/json                                   |
| apierrors.NotesCreateNotesUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.NotesCreateNotesPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.NotesCreateNotesForbiddenError           | 403                                                | application/json                                   |
| apierrors.NotesCreateNotesNotFoundError            | 404                                                | application/json                                   |
| apierrors.NotesCreateNotesConflictError            | 409                                                | application/json                                   |
| apierrors.NotesCreateNotesUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.NotesCreateNotesInternalServerError      | 500                                                | application/json                                   |
| apierrors.NotesCreateNotesBadGatewayError          | 502                                                | application/json                                   |
| apierrors.NotesCreateNotesServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.NotesCreateNotesGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |

## NotesGetAllNotes

*   This endpoint is used to get all the note details of incidentID mentioned params.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Notes_getAllNotes" method="get" path="/v3/incidents/{IncidentId}/warroom" -->
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

    res, err := s.IncidentsNotes.NotesGetAllNotes(ctx, "<id>")
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

**[*operations.NotesGetAllNotesResponse](../../models/operations/notesgetallnotesresponse.md), error**

### Errors

| Error Type                                         | Status Code                                        | Content Type                                       |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| apierrors.NotesGetAllNotesBadRequestError          | 400                                                | application/json                                   |
| apierrors.NotesGetAllNotesUnauthorizedError        | 401                                                | application/json                                   |
| apierrors.NotesGetAllNotesPaymentRequiredError     | 402                                                | application/json                                   |
| apierrors.NotesGetAllNotesForbiddenError           | 403                                                | application/json                                   |
| apierrors.NotesGetAllNotesNotFoundError            | 404                                                | application/json                                   |
| apierrors.NotesGetAllNotesConflictError            | 409                                                | application/json                                   |
| apierrors.NotesGetAllNotesUnprocessableEntityError | 422                                                | application/json                                   |
| apierrors.NotesGetAllNotesInternalServerError      | 500                                                | application/json                                   |
| apierrors.NotesGetAllNotesBadGatewayError          | 502                                                | application/json                                   |
| apierrors.NotesGetAllNotesServiceUnavailableError  | 503                                                | application/json                                   |
| apierrors.NotesGetAllNotesGatewayTimeoutError      | 504                                                | application/json                                   |
| apierrors.APIError                                 | 4XX, 5XX                                           | \*/\*                                              |

## NotesDeleteNote

delete note from incidentId mentioned in params.

Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header with `service-write` scope.

### Example Usage

<!-- UsageSnippet language="go" operationID="Notes_deleteNote" method="delete" path="/v3/incidents/{IncidentId}/warroom/{NoteId}" -->
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

    res, err := s.IncidentsNotes.NotesDeleteNote(ctx, "<id>", "<id>")
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
| `incidentID`                                             | *string*                                                 | :heavy_check_mark:                                       | Required                                                 |
| `noteID`                                                 | *string*                                                 | :heavy_check_mark:                                       | Required                                                 |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*operations.NotesDeleteNoteResponse](../../models/operations/notesdeletenoteresponse.md), error**

### Errors

| Error Type                                        | Status Code                                       | Content Type                                      |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| apierrors.NotesDeleteNoteBadRequestError          | 400                                               | application/json                                  |
| apierrors.NotesDeleteNoteUnauthorizedError        | 401                                               | application/json                                  |
| apierrors.NotesDeleteNotePaymentRequiredError     | 402                                               | application/json                                  |
| apierrors.NotesDeleteNoteForbiddenError           | 403                                               | application/json                                  |
| apierrors.NotesDeleteNoteNotFoundError            | 404                                               | application/json                                  |
| apierrors.NotesDeleteNoteConflictError            | 409                                               | application/json                                  |
| apierrors.NotesDeleteNoteUnprocessableEntityError | 422                                               | application/json                                  |
| apierrors.NotesDeleteNoteInternalServerError      | 500                                               | application/json                                  |
| apierrors.NotesDeleteNoteBadGatewayError          | 502                                               | application/json                                  |
| apierrors.NotesDeleteNoteServiceUnavailableError  | 503                                               | application/json                                  |
| apierrors.NotesDeleteNoteGatewayTimeoutError      | 504                                               | application/json                                  |
| apierrors.APIError                                | 4XX, 5XX                                          | \*/\*                                             |

## NotesUpdateNote

This API can be used to update a Note or a Resolution reason associated with an incident

### Example Usage

<!-- UsageSnippet language="go" operationID="Notes_updateNote" method="put" path="/v3/incidents/{IncidentId}/warroom/{NoteId}" -->
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

    res, err := s.IncidentsNotes.NotesUpdateNote(ctx, "<id>", "<id>", components.V3IncidentsNotesUpdateNoteRequest{
        Message: "<value>",
        Attachments: []string{},
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

| Parameter                                                                                                    | Type                                                                                                         | Required                                                                                                     | Description                                                                                                  |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                                        | :heavy_check_mark:                                                                                           | The context to use for the request.                                                                          |
| `incidentID`                                                                                                 | *string*                                                                                                     | :heavy_check_mark:                                                                                           | Required                                                                                                     |
| `noteID`                                                                                                     | *string*                                                                                                     | :heavy_check_mark:                                                                                           | N/A                                                                                                          |
| `v3IncidentsNotesUpdateNoteRequest`                                                                          | [components.V3IncidentsNotesUpdateNoteRequest](../../models/components/v3incidentsnotesupdatenoterequest.md) | :heavy_check_mark:                                                                                           | N/A                                                                                                          |
| `opts`                                                                                                       | [][operations.Option](../../models/operations/option.md)                                                     | :heavy_minus_sign:                                                                                           | The options for this request.                                                                                |

### Response

**[*operations.NotesUpdateNoteResponse](../../models/operations/notesupdatenoteresponse.md), error**

### Errors

| Error Type                                        | Status Code                                       | Content Type                                      |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| apierrors.NotesUpdateNoteBadRequestError          | 400                                               | application/json                                  |
| apierrors.NotesUpdateNoteUnauthorizedError        | 401                                               | application/json                                  |
| apierrors.NotesUpdateNotePaymentRequiredError     | 402                                               | application/json                                  |
| apierrors.NotesUpdateNoteForbiddenError           | 403                                               | application/json                                  |
| apierrors.NotesUpdateNoteNotFoundError            | 404                                               | application/json                                  |
| apierrors.NotesUpdateNoteConflictError            | 409                                               | application/json                                  |
| apierrors.NotesUpdateNoteUnprocessableEntityError | 422                                               | application/json                                  |
| apierrors.NotesUpdateNoteInternalServerError      | 500                                               | application/json                                  |
| apierrors.NotesUpdateNoteBadGatewayError          | 502                                               | application/json                                  |
| apierrors.NotesUpdateNoteServiceUnavailableError  | 503                                               | application/json                                  |
| apierrors.NotesUpdateNoteGatewayTimeoutError      | 504                                               | application/json                                  |
| apierrors.APIError                                | 4XX, 5XX                                          | \*/\*                                             |