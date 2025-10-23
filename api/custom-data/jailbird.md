---
description: >-
  The `JailbirdData` class is used for custom items of type `Jailbird`. It
  allows you to customize the properties of jailbird items.
icon: sword
---

# Jailbird

**Properties**

| Property        | Type    | Description                                             |
| --------------- | ------- | ------------------------------------------------------- |
| `MeleeDamage`   | `float` | The amount of damage dealt with a melee hit.            |
| `ChargeDamage`  | `float` | The amount of damage dealt with a charge hit.           |
| `FlashDuration` | `float` | The duration of the `Flashed` effect on being hit.      |
| `Radius`        | `float` | The radius of the jailbird's hit registration.          |
| `TotalCharges`  | `int`   | The number of times the item has been charged and used. |

**Example:**

```yaml
CustomItemType: Jailbird
CustomData:
  melee_damage: 10.0
  charge_damage: 30.0
  flash_duration: 3.0
  radius: 2.0
  total_charges: 5
  destroy_after_use: true
```
