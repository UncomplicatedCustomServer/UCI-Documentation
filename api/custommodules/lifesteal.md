---
icon: heart-pulse
---

# LifeSteal

The `LifeSteal` module grants the attacker health regeneration when they deal damage to another player. It can be configured to heal a fixed amount or a percentage of the damage dealt, based on the `PercentageBased` property.

### Configuration

| Value                 | Description                                                                                                                      |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `PercentageBased`     | A boolean value. If `true`, the attacker heals a percentage of the damage dealt. If `false`, the attacker heals a fixed amount.  |
| `LifeStealAmount`     | A float value. The fixed amount of health the attacker regains when dealing damage. Used only when `PercentageBased` is `false`. |
| `LifeStealPercentage` | A float value. The percentage of damage dealt that the attacker regains as health. Used only when `PercentageBased` is `true`.   |

### Example

```yaml
custom_modules:
  LifeSteal:
  - PercentageBased: true
    LifeStealAmount: 0.0 # This value is ignored when PercentageBased is true
    LifeStealPercentage: 10.0 # Attacker heals 10% of the damage they deal
```
