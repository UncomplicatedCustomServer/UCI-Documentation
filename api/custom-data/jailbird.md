---
icon: sword
---

# Jailbird

### Properties

| Property        | Type                                                          | Description                                                  |
| --------------- | ------------------------------------------------------------- | ------------------------------------------------------------ |
| `MeleeDamage`   | `float`                                                       | The amount of damage dealt with a Jailbird melee hit.        |
| `ChargeDamage`  | `float`                                                       | The amount of damage dealt with a Jailbird charge hit.       |
| `FlashDuration` | `float`                                                       | The duration in seconds that the effect is applied when hit. |
| `Radius`        | `float`                                                       | The radius of the Jailbird's hit register.                   |
| `WearState`     | [`JailbirdWearState`](../enums/external/jailbirdwearstate.md) | The current of the wear on the Jailbird.                     |

### Example

```yaml
CustomItemType: Jailbird
CustomData:
  melee_damage: 3
  charge_damage: 3
  flash_duration: 3
  radius: 3
  wear_state: Healthy
```

