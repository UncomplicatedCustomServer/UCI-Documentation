---
description: >-
  The `MedikitData` class is used for custom items of type `Medikit`. It allows
  you to customize the properties of medikits.
icon: suitcase-medical
---

# Medikit

**Properties**

| Property      | Type    | Description                                            |
| ------------- | ------- | ------------------------------------------------------ |
| `Health`      | `float` | The amount of health that will be regenerated.         |
| `MoreThanMax` | `bool`  | Whether the value can surpass the player's max health. |

**Example:**

```yaml
CustomItemType: Medikit
CustomData:
  health: 100.0
  more_than_max: true
```
