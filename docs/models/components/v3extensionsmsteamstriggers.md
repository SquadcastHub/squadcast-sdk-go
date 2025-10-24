# V3ExtensionsMSTeamsTriggers

Defines the trigger conditions for sending alerts.


## Fields

| Field                                                                                                  | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `AllActive`                                                                                            | *bool*                                                                                                 | :heavy_check_mark:                                                                                     | If true, all alerts are sent, and the 'custom' list is ignored.                                        |
| `Custom`                                                                                               | [][components.V3ExtensionsMSTeamsEventClass](../../models/components/v3extensionsmsteamseventclass.md) | :heavy_check_mark:                                                                                     | A list of specific event classes to send alerts for. This is used when 'all_active' is false.          |