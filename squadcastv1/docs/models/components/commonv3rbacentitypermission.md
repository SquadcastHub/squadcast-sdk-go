# CommonV3RBACEntityPermission

Represents a permission granted to a user for a specific entity.


## Fields

| Field                                                        | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `UserID`                                                     | *string*                                                     | :heavy_check_mark:                                           | The ID of the user receiving the permission.                 |
| `Abilities`                                                  | [components.Abilities](../../models/components/abilities.md) | :heavy_check_mark:                                           | A map of abilities granted to the user.                      |