# V3IncidentsNotificationDelayPolicy

Policy for delaying notifications.


## Fields

| Field                                                                            | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `IsNotificationDelayed`                                                          | *bool*                                                                           | :heavy_check_mark:                                                               | N/A                                                                              |
| `DelayedUntil`                                                                   | [time.Time](https://pkg.go.dev/time#Time)                                        | :heavy_check_mark:                                                               | N/A                                                                              |
| `AssignTo`                                                                       | [components.V3IncidentsAssignTo](../../models/components/v3incidentsassignto.md) | :heavy_check_mark:                                                               | Represents the assignment target for delayed notifications.                      |