# V3TeamsAddTeamMemberRequest


## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `UserID`                                                      | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `RoleIds`                                                     | []*string*                                                    | :heavy_check_mark:                                            | this field is required if you are using RBAC permission model |
| `Role`                                                        | **string*                                                     | :heavy_minus_sign:                                            | this field is required if you are using OBAC permission model |