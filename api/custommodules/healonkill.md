---
icon: suitcase-medical
---

# HealOnKill

This module provides a mechanism to heal the player who kills another player. It allows for configuring the amount of health restored and can convert excess healing into Artificial Health (AHP) if the player's health is already full.

### Configuration

| Value                | Description                                                                                                                                                                                                |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `HealAmount`         | The amount of health to restore to the player upon killing an enemy. This value can be a float.                                                                                                            |
| `ConvertToAhpIfFull` | If `true`, and the player's health is already at maximum, the `HealAmount` will be converted into Artificial Health (AHP) instead of regular health. If `false`, healing will not occur if health is full. |

### Example

```yaml
custom_modules:
  HealOnKill:
  - HealAmount: 25.0
    ConvertToAhpIfFull: true
```
