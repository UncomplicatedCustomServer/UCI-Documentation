---
description: >-
  The `FlashGrenadeData` class is used for custom items of type `FlashGrenade`.
  It allows you to customize the properties of flash grenades.
icon: explosion
---

# Flash Grenade

**Properties**

| Property                     | Type    | Description                                                                         |
| ---------------------------- | ------- | ----------------------------------------------------------------------------------- |
| `MinimalDurationEffect`      | `float` | The minimum duration of the flash effect.                                           |
| `AdditionalBlindedEffect`    | `float` | The additional duration of the `Blinded` effect.                                    |
| `SurfaceDistanceIntensifier` | `float` | How much the flash grenade's effect is intensified when it explodes on the surface. |
| `FuseTime`                   | `float` | The duration of the fuse.                                                           |
| `PinPullTime`                | `float` | The time it takes to pull the pin.                                                  |
| `ExplodeOnImpact`            | `bool`  | Whether or not the grenade will explode when it impacts another object              |
| `Repickable`                 | `bool`  | Determines if the grenade explodes upon impacting another object.                   |

**Example:**

```yaml
CustomItemType: FlashGrenade
CustomData:
  minimal_duration_effect: 3.0
  additional_blinded_effect: 7.0
  surface_distance_intensifier: 10.0
  fuse_time: 2.5
  pin_pull_time: 0.5
  explode_on_impact: true
  repickable: true
```
