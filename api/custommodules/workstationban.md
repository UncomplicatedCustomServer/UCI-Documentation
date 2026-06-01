---
icon: ban
---

# WorkstationBan

The `WorkstationBan` module prevents players from changing attachments at workstations. When a player attempts to change attachments, this module intercepts the event, sends them a hint message, and disallows the action.

### Configuration

| Value                        | Description                                                                                                                                                                                       |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `WorkstationBanHint`         | The hint message to display to the player when they are banned from workstations. The placeholder `%name%` will be replaced with the name of the custom item associated with the workstation ban. |
| `WorkstationBanHintDuration` | The duration (in seconds) for which the hint message will be displayed to the player.                                                                                                             |

### Example

```yaml
custom_modules:
  WorkstationBan: []
```
