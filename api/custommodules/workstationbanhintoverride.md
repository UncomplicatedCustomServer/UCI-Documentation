---
icon: hammer-brush
---

# WorkstationBanHintOverride

This module allows you to override the default hint message and duration displayed when a player is banned from using a workstation. When configured, it replaces the standard workstation ban notification with a custom hint message that appears for a specified duration.

### Configuration

| Value    | Description                                                                                                                                     |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Hint     | The custom hint message to display when a player is banned from using a workstation. This text will override the default ban notification.      |
| Duration | The time, in seconds, that the custom hint message will be displayed to the player. This determines how long the override hint remains visible. |

### Example

```yaml
custom_modules:
  WorkstationBanHintOverride:
    - Hint: "You are temporarily banned from using workstations!"
      Duration: 5.0    # Hint displays for 5 seconds
    - Hint: "Access denied - Cooldown in effect"
      Duration: 3.5    # Alternative hint displays for 3.5 seconds
```
