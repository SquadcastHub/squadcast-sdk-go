# V4StatusPagesMaintenancesCreateMaintenanceResponse


## Fields

| Field                                     | Type                                      | Required                                  | Description                               |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| `ID`                                      | *int64*                                   | :heavy_check_mark:                        | N/A                                       |
| `Title`                                   | *string*                                  | :heavy_check_mark:                        | N/A                                       |
| `PageID`                                  | *int64*                                   | :heavy_check_mark:                        | N/A                                       |
| `Note`                                    | *string*                                  | :heavy_check_mark:                        | N/A                                       |
| `Components`                              | []*int64*                                 | :heavy_minus_sign:                        | N/A                                       |
| `StartTime`                               | [time.Time](https://pkg.go.dev/time#Time) | :heavy_check_mark:                        | N/A                                       |
| `EndTime`                                 | [time.Time](https://pkg.go.dev/time#Time) | :heavy_check_mark:                        | N/A                                       |