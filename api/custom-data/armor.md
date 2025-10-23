---
description: >-
  The `ArmorData` class is used for custom items of type `Armor`. It allows you
  to customize the properties of armor items.
icon: shield-halved
---

# Armor

**Properties**

| Property                 | Type    | Description                                 |
| ------------------------ | ------- | ------------------------------------------- |
| `HeadProtection`         | `int`   | The armor's head protection value.          |
| `BodyProtection`         | `int`   | The armor's body protection value.          |
| `StaminaUseMultiplier`   | `float` | The stamina drain multiplier of this armor. |
| `StaminaRegenMultiplier` | `float` | The stamina regeneration multiplier.        |

#### Example:

```yaml
CustomItemType: Armor
CustomData:
  head_protection: 50
  body_protection: 75
  stamina_use_multiplier: 1.2
  stamina_regen_multiplier: 0.9
```
