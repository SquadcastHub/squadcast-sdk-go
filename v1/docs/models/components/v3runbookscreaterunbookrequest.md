# V3RunbooksCreateRunbookRequest

Represents the request body for creating a new runbook.


## Fields

| Field                                                                             | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `Name`                                                                            | *string*                                                                          | :heavy_check_mark:                                                                | The name of the runbook.                                                          |
| `Steps`                                                                           | [][components.V3RunbooksStep](../../models/components/v3runbooksstep.md)          | :heavy_check_mark:                                                                | The steps that make up the runbook.                                               |
| `OwnerID`                                                                         | *string*                                                                          | :heavy_check_mark:                                                                | The ID of the team that owns this runbook.                                        |
| `EntityOwner`                                                                     | [*components.CommonV3EntityOwner](../../models/components/commonv3entityowner.md) | :heavy_minus_sign:                                                                | The owner of the entity.                                                          |