---
description: >-
  The `MicroHIDData` class is used for custom items of type `MicroHID`. It
  allows you to customize the properties of MicroHIDs.
icon: transformer-bolt
---

# MicroHID

**Properties**

| Property         | Type    | Description                               |
| ---------------- | ------- | ----------------------------------------- |
| `Damage`         | `float` | The amount of damage done to a player.    |
| `Energy`         | `float` | The amount of energy in the MicroHID.     |
| `CanExplode`     | `bool`  | Whether the MicroHID can explode.         |
| `InfiniteEnergy` | `bool`  | Whether the MicroHID has infinite energy. |
| `Broken`         | `bool`  | Whether the MicroHID is broken.           |

**Example:**

```yaml
CustomItemType: MicroHID
CustomData:
  damage: 2.5
  energy: 1.0
  can_explode: false
  infinite_energy: true
  broken: false
```
