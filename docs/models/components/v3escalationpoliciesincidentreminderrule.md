# V3EscalationPoliciesIncidentReminderRule

Represents a rule for sending incident reminders.


## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `Via`                                                  | []*string*                                             | :heavy_check_mark:                                     | The notification methods to use for the reminder.      |
| `TimeInterval`                                         | *int*                                                  | :heavy_check_mark:                                     | The interval in minutes at which to send the reminder. |
| `Till`                                                 | *int*                                                  | :heavy_check_mark:                                     | The duration in minutes for which to send reminders.   |