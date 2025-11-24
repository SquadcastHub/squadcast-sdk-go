# V3AuditLogsFilters

Represents filters used in audit log queries


## Fields

| Field                                                                        | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `StartDate`                                                                  | [types.Date](../../types/date.md)                                            | :heavy_check_mark:                                                           | N/A                                                                          |
| `EndDate`                                                                    | [types.Date](../../types/date.md)                                            | :heavy_check_mark:                                                           | N/A                                                                          |
| `Resource`                                                                   | []*string*                                                                   | :heavy_minus_sign:                                                           | N/A                                                                          |
| `Action`                                                                     | []*string*                                                                   | :heavy_minus_sign:                                                           | N/A                                                                          |
| `Actor`                                                                      | [][components.V3AuditLogsActor](../../models/components/v3auditlogsactor.md) | :heavy_minus_sign:                                                           | N/A                                                                          |
| `Team`                                                                       | [][components.V3AuditLogsTeam](../../models/components/v3auditlogsteam.md)   | :heavy_minus_sign:                                                           | N/A                                                                          |
| `Client`                                                                     | []*string*                                                                   | :heavy_minus_sign:                                                           | N/A                                                                          |