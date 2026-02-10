---
icon: shield
---

# HumeShield

This custom module modifies player Hume Shield values based on specific game events. It allows configuration of the Hume Shield regeneration rate, maximum Hume Shield capacity, regeneration cooldown, and the events that trigger these changes.

### Configuration

| Value           | Description                                                                                                                        |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `RegenRate`     | The rate at which the player's Hume Shield regenerates.                                                                            |
| `MaxHumeShield` | The maximum amount of Hume Shield the player can possess.                                                                          |
| `RegenCoolDown` | The cooldown period before Hume Shield regeneration begins.                                                                        |
| `Trigger`       | The game event(s) that will trigger the Hume Shield modifications. Valid options include `OnAdded`, `OnChangedItem`, `OnUsedItem`. |

### Example

```yaml
custom_modules:
  HumeShield:
  - RegenRate: 10.5
    MaxHumeShield: 100
    RegenCoolDown: 5.0
    Trigger: 'OnAdded, OnChangedItem'
```
