# V3AuditLogsAuditLogResponse

Represents an audit log entry response


## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `ID`                                                                       | *int*                                                                      | :heavy_check_mark:                                                         | N/A                                                                        |
| `Resource`                                                                 | *string*                                                                   | :heavy_check_mark:                                                         | N/A                                                                        |
| `Action`                                                                   | *string*                                                                   | :heavy_check_mark:                                                         | N/A                                                                        |
| `Actor`                                                                    | [components.V3AuditLogsActor](../../models/components/v3auditlogsactor.md) | :heavy_check_mark:                                                         | Represents an actor (user) in audit logs                                   |
| `Client`                                                                   | *string*                                                                   | :heavy_check_mark:                                                         | N/A                                                                        |
| `Timestamp`                                                                | *string*                                                                   | :heavy_check_mark:                                                         | N/A                                                                        |
| `Team`                                                                     | [components.V3AuditLogsTeam](../../models/components/v3auditlogsteam.md)   | :heavy_check_mark:                                                         | Represents a team in audit logs                                            |