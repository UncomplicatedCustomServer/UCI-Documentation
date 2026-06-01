---
icon: burst
---

# BurstFire

The `BurstFire` module limits a weapon to firing a set number of shots in quick succession before enforcing a cooldown period. Once the burst limit is reached, the weapon is temporarily prevented from firing until the cooldown expires and the shot counter resets. When `ForceFire` is enabled, the remaining shots in the burst are automatically fired after the initial trigger pull.

#### Configuration

| Value                      | Description                                                                                                                                                                                 |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `BurstAmount`              | The number of shots in a single burst before the cooldown is triggered.                                                                                                                     |
| `CoolDown`                 | The duration in seconds the player must wait after completing a burst before they can fire again.                                                                                           |
| `ForceFire`                | Set to `true` to automatically fire the remaining burst shots server-side after the first trigger pull. Set to `false` to require manual trigger pulls for each shot up to the burst limit. |
| `TimingBetweenForcedShots` | The delay in seconds between each automatically fired shot when `ForceFire` is `true`. Has no effect if `ForceFire` is `false`.                                                             |

#### Example

```yaml
custom_modules:
  BurstFire:
  - BurstAmount: 3
    CoolDown: 1.5
    ForceFire: true
    TimingBetweenForcedShots: 0.1
```
