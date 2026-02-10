---
icon: ban
---

# CantDrop

This module prevents players from dropping the custom item it is attached to. When a player attempts to drop the item, the action is disallowed, and a configurable message (either a hint or a broadcast) is sent to the player, explaining why the item cannot be dropped.

### Configuration

| Value             | Description                                                                                                                                                              |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `HintOrBroadcast` | Specifies whether to send a "Hint" or a "Broadcast" message to the player when they attempt to drop the item. Valid values are `Hint` or `Broadcast` (case-insensitive). |
| `Message`         | The message text to display to the player. You can use the placeholder `%name%` within the message, which will be replaced by the custom item's name.                    |
| `Duration`        | The duration, in seconds, for which the hint or broadcast message will be displayed to the player. This value must be an unsigned integer.                               |

### Example

```yaml
custom_modules:
  CantDrop:
  - HintOrBroadcast: Broadcast
    Message: The %name% is bound to you and cannot be dropped!
    Duration: 7
```
