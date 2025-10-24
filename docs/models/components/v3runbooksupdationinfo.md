# V3RunbooksUpdationInfo

Represents information about the creation or updation of an entity.


## Fields

| Field                                                                             | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `UserName`                                                                        | *string*                                                                          | :heavy_check_mark:                                                                | The full name of the user who performed the action.                               |
| `UsernameForDisplay`                                                              | *string*                                                                          | :heavy_check_mark:                                                                | The display name of the user who performed the action.                            |
| `UserID`                                                                          | *string*                                                                          | :heavy_check_mark:                                                                | The ID of the user who performed the action.                                      |
| `At`                                                                              | [time.Time](https://pkg.go.dev/time#Time)                                         | :heavy_check_mark:                                                                | The timestamp of the action.                                                      |
| `EntityOwner`                                                                     | [*components.CommonV3EntityOwner](../../models/components/commonv3entityowner.md) | :heavy_minus_sign:                                                                | The owner of the entity at the time of the action.                                |