---
icon: explosion
---

# ExplosiveBullets

The `ExplosiveBullets` custom module transforms regular bullet impacts into explosions. When a player places a bullet hole, this module triggers an immediate explosion at the impact location, dealing damage within a configurable radius.

### Configuration

| Value          | Description                                                                                               |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| `DamageRadius` | The maximum radius (in game units) within which the triggered explosion will deal damage upon detonation. |

### Example

```yaml
custom_modules:
  ExplosiveBullets:
  - DamageRadius: 5.0
```
