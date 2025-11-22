# AuditLogsListAuditLogsRequest


## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `PageSize`                                               | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `PageNumber`                                             | *int64*                                                  | :heavy_check_mark:                                       | N/A                                                      |
| `StartDate`                                              | [types.Date](../../types/date.md)                        | :heavy_check_mark:                                       | N/A                                                      |
| `EndDate`                                                | [types.Date](../../types/date.md)                        | :heavy_check_mark:                                       | N/A                                                      |
| `Action`                                                 | []*string*                                               | :heavy_minus_sign:                                       | N/A                                                      |
| `Resource`                                               | []*string*                                               | :heavy_minus_sign:                                       | N/A                                                      |
| `Actor`                                                  | []*string*                                               | :heavy_minus_sign:                                       | N/A                                                      |
| `Team`                                                   | []*string*                                               | :heavy_minus_sign:                                       | N/A                                                      |
| `Client`                                                 | [][operations.Client](../../models/operations/client.md) | :heavy_minus_sign:                                       | N/A                                                      |