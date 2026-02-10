---
icon: layer-plus
---

# Effect

The `Effect` module allows custom items to apply a specified status effect to a player under various conditions. It provides granular control over the effect's properties such as its name, intensity, duration, and when it should be triggered or removed.

### Configuration

| Value                 | Description                                                                                                                                                                                                                                                                 |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `EffectName`          | The internal name of the status effect to be applied. Examples include `Scp207`, `Scp185`, `Scp268`, `Poisoned`, etc.                                                                                                                                                       |
| `Intensity`           | A byte value representing the intensity of the effect. Higher values typically result in a stronger effect, depending on the specific status effect.                                                                                                                        |
| `Duration`            | A float value representing how long the effect should last in seconds. If set to a negative value (e.g., `-1.0`), the effect will last indefinitely until explicitly removed or overwritten.                                                                                |
| `AddDurationIfActive` | A boolean value. If `true`, when the effect is applied to a player who already has it, the new duration will be added to the remaining duration. If `false`, the existing effect's duration is reset to the new duration.                                                   |
| `ClearOnUnequip`      | A boolean value. If `true`, the effect will be automatically removed from the player when the custom item is unequipped (i.e., the player switches to another item).                                                                                                        |
| `Trigger`             | An enum value specifying when the effect should be applied. Possible values include: `OnShot` (when the player shoots a weapon), `OnUse` (when the player uses the item), `OnChangedItem` (when the player equips the item), `OnAdded` (when the player picks up the item). |

### Example

```yaml
custom_modules:
  Effect:
  - EffectName: 'Scp207'
    Intensity: 1
    Duration: 10.0
    AddDurationIfActive: true
    ClearOnUnequip: false
    Trigger: OnUse
  - EffectName: 'Scp185'
    Intensity: 2
    Duration: -1.0
    AddDurationIfActive: false
    ClearOnUnequip: true
    Trigger: OnChangedItem
```
