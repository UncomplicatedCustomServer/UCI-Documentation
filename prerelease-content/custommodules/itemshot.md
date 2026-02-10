---
icon: baseball
---

# ItemShot

The `ItemShot` module is designed to spawn an item or grenade when a player fires their weapon. It allows for the configuration of various physical properties (velocity, upward trajectory, and rotational torque) to be applied to the spawned object, enabling diverse projectile behaviors. It supports spawning standard SCP:SL items, throwable grenades (with optional impact detonation), or custom items.

### Configuration

| Value                    | Description                                                                                                                                                                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `IsGrenade`              | Set to `true` if the module should treat the spawned item as a throwable grenade, enabling specific grenade spawning logic.                                                                                         |
| `GrenadeExplodeOnImpact` | If `IsGrenade` is `true`, setting this to `true` makes the spawned grenade explode immediately upon collision.                                                                                                      |
| `IsCustomItem`           | Set to `true` if the item to be spawned is a custom item defined elsewhere in your configuration. If `true`, `CustomItemId` will be used. If `false`, `ItemType` will be used.                                      |
| `Velocity`               | The initial speed (magnitude) at which the item is propelled forward from the player's camera or the firearm's barrel tip.                                                                                          |
| `UpwardsFactor`          | A float multiplier determining how much an upward force is added to the item's initial trajectory, influencing its arc. A higher value results in a more pronounced arc.                                            |
| `Torque`                 | The initial rotational force applied to the item upon spawning, defined as X, Y, Z components. This controls how the item spins while in the air.                                                                   |
| `CustomItemId`           | The unique numerical identifier (`uint`) of the custom item to spawn. This property is only used if `IsCustomItem` is `true`.                                                                                       |
| `ItemType`               | The standard Unity/SCP:SL `ItemType` to spawn. This property is only used if `IsCustomItem` is `false` and is used for both regular items and grenades (if `IsGrenade` is true). Example: `GrenadeHE`, `KeycardO5`. |

### Example

```yaml
custom_modules:
  ItemShot:
  - IsGrenade: true
    GrenadeExplodeOnImpact: false
    IsCustomItem: false
    Velocity: 25.0
    UpwardsFactor: 0.7
    Torque: '0, 100, 0'
    CustomItemId: 0 # Not used if IsCustomItem is false
    ItemType: 'GrenadeFlash' # Spawns a flashbang
  - IsGrenade: false
    GrenadeExplodeOnImpact: false # Not relevant for non-grenades
    IsCustomItem: true
    Velocity: 18.0
    UpwardsFactor: 0.2
    Torque: '50, 50, 50'
    CustomItemId: 12345 # Spawns a custom item with ID 12345
    ItemType: 'None' # Not used if IsCustomItem is true
```
