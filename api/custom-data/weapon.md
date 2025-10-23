---
description: >-
  The `WeaponData` class is used for custom items of type `Weapon`. It allows
  you to customize the properties of firearms.
icon: gun
---

# Weapon

**Properties**

| Property                | Type     | Description                                        |
| ----------------------- | -------- | -------------------------------------------------- |
| `Damage`                | `float`  | The damage of the ammo.                            |
| `MaxBarrelAmmo`         | `int`    | The maximum number of ammunitions in the barrel.   |
| `MaxAmmo`               | `int`    | The maximum number of ammunitions.                 |
| `MaxMagazineAmmo`       | `int`    | The maximum number of ammunitions in the magazine. |
| `AmmoDrain`             | `int`    | The amount of ammunition drained per shot.         |
| `Penetration`           | `float`  | The penetration of the firearm.                    |
| `Inaccuracy`            | `float`  | The inaccuracy of the firearm.                     |
| `AimingInaccuracy`      | `float`  | The inaccuracy of the firearm while aiming.        |
| `DamageFalloffDistance` | `float`  | How quickly the damage drops over distance.        |
| `Attachments`           | `string` | The weapon attachments.                            |
| `EnableFriendlyFire`    | `bool`   | Whether the item can damage teammates.             |

**Example:**

```yaml
CustomItemType: Weapon
CustomData:
  damage: 25.0
  max_barrel_ammo: 1
  max_ammo: 100
  max_magazine_ammo: 20
  ammo_drain: 1
  penetration: 1.5
  inaccuracy: 0.2
  aiming_inaccuracy: 0.05
  damage_falloff_distance: 50.0
  attachments: "Scope, Silencer"
  enable_friendly_fire: true
```
