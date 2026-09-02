---
icon: explosion
---

# ExplosiveBullets

The `ExplosiveBullets` custom module transforms regular bullet impacts into explosions. When a player places a bullet hole, this module triggers an immediate explosion at the impact location, dealing damage within a configurable radius.

### Configuration

| Value                    | Description                                                                                               |
| ------------------------ | --------------------------------------------------------------------------------------------------------- |
| `DamageRadius`           | The maximum radius (in game units) within which the triggered explosion will deal damage upon detonation. |
| `SCPDamageMultiplier`    | The damage multiplier applied to scps.                                                                    |
| `DoorDamageMultiplier`   | The damage multiplier applied to doors.                                                                   |
| `PlayerDamageMultiplier` | The damage multiplier applied to non scp players                                                          |

### Example

```yaml
custom_modules:
  ExplosiveBullets:
  - DamageRadius: 5.0
    SCPDamageMultiplier: 0.2
    DoorDamageMultiplier: 0.5
    PlayerDamageMultiplier: 0.2
```
