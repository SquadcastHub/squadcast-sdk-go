# SchedulesListSchedulesRequest


## Fields

| Field                     | Type                      | Required                  | Description               |
| ------------------------- | ------------------------- | ------------------------- | ------------------------- |
| `TeamID`                  | *string*                  | :heavy_check_mark:        | N/A                       |
| `ScheduleIDs`             | []*int64*                 | :heavy_minus_sign:        | N/A                       |
| `Participants`            | []*string*                | :heavy_minus_sign:        | N/A                       |
| `ScheduleName`            | **string*                 | :heavy_minus_sign:        | N/A                       |
| `MyOnCall`                | **bool*                   | :heavy_minus_sign:        | N/A                       |
| `YouAndYourSquads`        | **bool*                   | :heavy_minus_sign:        | N/A                       |
| `Search`                  | **string*                 | :heavy_minus_sign:        | N/A                       |
| `HidePaused`              | **bool*                   | :heavy_minus_sign:        | N/A                       |
| `OwnerID`                 | **string*                 | :heavy_minus_sign:        | N/A                       |
| `EscalationPolicies`      | []*string*                | :heavy_minus_sign:        | N/A                       |
| `WithoutEscalationPolicy` | **bool*                   | :heavy_minus_sign:        | N/A                       |
| `PageSize`                | **int64*                  | :heavy_minus_sign:        | N/A                       |
| `Cursor`                  | **string*                 | :heavy_minus_sign:        | N/A                       |