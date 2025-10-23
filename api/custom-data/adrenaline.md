---
description: >-
  The `AdrenalineData` class is used for custom items of type `Adrenaline`. It
  allows you to customize the effects of adrenaline items.
icon: syringe
---

# Adrenaline

**Properties**

| Property     | Type    | Description                                                      |
| ------------ | ------- | ---------------------------------------------------------------- |
| `Amount`     | `float` | The amount of Artificial Health Points (AHP) to give the player. |
| `Decay`      | `float` | The decay speed of the AHP.                                      |
| `Efficacy`   | `float` | The efficacy of the AHP.                                         |
| `Sustain`    | `float` | The delay before the AHP starts to decay.                        |
| `Persistant` | `bool`  | Whether the AHP should be persistent.                            |

**Example:**

```yaml
CustomItemType: Adrenaline
CustomData:
  amount: 50.0
  decay: 1.0
  efficacy: 0.8
  sustain: 10.0
  persistant: false
```
