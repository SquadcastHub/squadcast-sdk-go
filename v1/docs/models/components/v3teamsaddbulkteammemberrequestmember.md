# V3TeamsAddBulkTeamMemberRequestMember


## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `UserID`                                                      | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `Role`                                                        | **string*                                                     | :heavy_minus_sign:                                            | this field is required if you are using OBAC permission model |
| `RoleIds`                                                     | []*string*                                                    | :heavy_check_mark:                                            | this field is required if you are using RBAC permission model |