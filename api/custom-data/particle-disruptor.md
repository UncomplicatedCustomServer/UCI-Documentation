---
description: >-
  The `ParticleDisruptorData` class is used for custom items of type
  `ParticleDisruptor`. It allows you to customize the properties of particle
  disruptors.
icon: atom
---

# Particle Disruptor

**Properties**

| Property             | Type    | Description                                 |
| -------------------- | ------- | ------------------------------------------- |
| `BurstDamage`        | `float` | The damage of the ammo.                     |
| `ChargeDamage`       | `float` | The damage of a charged shot.               |
| `Penetration`        | `float` | The penetration of the firearm.             |
| `Inaccuracy`         | `float` | The inaccuracy of the firearm.              |
| `AimingInaccuracy`   | `float` | The inaccuracy of the firearm while aiming. |
| `EnableFriendlyFire` | `bool`  | Whether the item can damage teammates.      |

**Example:**

```yaml
CustomItemType: ParticleDisruptor
CustomData:
  burst_damage: 15.0
  charge_damage: 50.0
  penetration: 2.0
  inaccuracy: 0.5
  aiming_inaccuracy: 0.1
  enable_friendly_fire: false
```
