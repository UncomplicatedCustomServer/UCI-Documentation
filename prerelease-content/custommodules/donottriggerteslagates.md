---
icon: ban
---

# DoNotTriggerTeslaGates

This module prevents players from triggering Tesla gates by intercepting the `TriggeringTesla` event and setting its `IsAllowed` property to `false`. When this module is active, any player attempting to trigger a Tesla gate will not succeed, effectively disabling Tesla gate functionality for players.

#### Configuration

This module does not have any specific configurable properties.

| Value | Description |
| ----- | ----------- |
|       |             |

#### Example

```yaml
custom_modules:
  DoNotTriggerTeslaGates: []
```
