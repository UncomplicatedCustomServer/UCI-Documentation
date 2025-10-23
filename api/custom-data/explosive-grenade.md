---
description: >-
  The `ExplosiveGrenadeData` class is used for custom items of type
  `ExplosiveGrenade`. It allows you to customize the properties of explosive
  grenades.
icon: bomb
---

# Explosive Grenade

**Properties**

| Property              | Type    | Description                                                       |
| --------------------- | ------- | ----------------------------------------------------------------- |
| `MaxRadius`           | `float` | The maximum radius of the grenade's explosion.                    |
| `ScpDamageMultiplier` | `float` | The damage multiplier against SCP players.                        |
| `BurnDuration`        | `float` | How long the `Burned` effect will last.                           |
| `DeafenDuration`      | `float` | How long the `Deafened` effect will last.                         |
| `ConcussDuration`     | `float` | How long the `Concussed` effect will last.                        |
| `FuseTime`            | `float` | The duration of the fuse.                                         |
| `PinPullTime`         | `float` | The time it takes to pull the pin.                                |
| `Repickable`          | `bool`  | Whether players can pick up the grenade after it has been thrown. |

#### Example:

```yaml
CustomItemType: ExplosiveGrenade
CustomData:
  max_radius: 10.0
  scp_damage_multiplier: 2.0
  burn_duration: 5.0
  deafen_duration: 8.0
  concuss_duration: 4.0
  fuse_time: 3.5
  pin_pull_time: 0.5
  repickable: false
```
