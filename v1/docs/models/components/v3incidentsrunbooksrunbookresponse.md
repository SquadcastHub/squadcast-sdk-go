# V3IncidentsRunbooksRunbookResponse


## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `ID`                                                 | **string*                                            | :heavy_minus_sign:                                   | N/A                                                  |
| `IncidentID`                                         | *string*                                             | :heavy_check_mark:                                   | N/A                                                  |
| `RunbookID`                                          | *string*                                             | :heavy_check_mark:                                   | N/A                                                  |
| `Name`                                               | *string*                                             | :heavy_check_mark:                                   | N/A                                                  |
| `Steps`                                              | [][components.Step](../../models/components/step.md) | :heavy_check_mark:                                   | N/A                                                  |
| `Deleted`                                            | **bool*                                              | :heavy_minus_sign:                                   | N/A                                                  |
| `DeletedAt`                                          | [*time.Time](https://pkg.go.dev/time#Time)           | :heavy_minus_sign:                                   | N/A                                                  |