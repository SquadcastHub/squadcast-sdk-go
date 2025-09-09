# Notes
(*Notes*)

## Overview

### Available Operations

* [List](#list) - Get All Notes

## List

*   This endpoint is used to get all the note details of incidentID mentioned params.
*   Requires `access_token` as a `Bearer {{token}}` in the `Authorization` header.

### Example Usage

<!-- UsageSnippet language="go" operationID="Notes_getAllNotes" method="get" path="/v3/incidents/{IncidentId}/warroom" -->
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

    res, err := s.Notes.List(ctx, "<id>")
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