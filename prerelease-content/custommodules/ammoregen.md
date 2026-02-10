---
icon: bullseye-arrow
---

# AmmoRegen

This module provides custom ammo regeneration functionality for an item, allowing configuration of regeneration delay, interval, and amount. When the item is shot, the module automatically pauses any ongoing ammo regeneration for a specified duration.

### Configuration

| Value             | Description                                                                                                                          |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `RegenDelay`      | The delay, in seconds, before ammo regeneration resumes after the item is shot. This value dictates how long regeneration is paused. |
| `RegenInterval`   | The time, in seconds, between each ammo regeneration tick. This defines how frequently ammo is added.                                |
| `AmmoPerInterval` | The amount of ammo regenerated per `RegenInterval`. This specifies how much ammo is restored in each tick.                           |

### Example

```yaml
custom_modules:
  AmmoRegen:
  - RegenDelay: 3.0       # Regeneration pauses for 3 seconds after shooting
    RegenInterval: 1.5    # Ammo regenerates every 1.5 seconds
    AmmoPerInterval: 2    # 2 rounds are regenerated per interval
```
