# V3IncidentsTagsNotificationDelayPolicy

Policy for delaying notifications.


## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `IsNotificationDelayed`                                                                  | *bool*                                                                                   | :heavy_check_mark:                                                                       | N/A                                                                                      |
| `DelayedUntil`                                                                           | [time.Time](https://pkg.go.dev/time#Time)                                                | :heavy_check_mark:                                                                       | N/A                                                                                      |
| `AssignTo`                                                                               | [components.V3IncidentsTagsAssignTo](../../models/components/v3incidentstagsassignto.md) | :heavy_check_mark:                                                                       | Represents the assignment target for delayed notifications.                              |