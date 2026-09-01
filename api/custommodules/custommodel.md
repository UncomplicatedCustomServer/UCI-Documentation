---
description: Attach a schematic model and event-driven animations to a custom item.
icon: pen-paintbrush
---

# CustomModel

`CustomModel` Attaches a schematic model to a custom item. The model follows the held item or its world pickup. You can play configured animations when item-related events occur.

The schematic must be available through TME or MER. The module retries spawning until an integration becomes available.

### Configuration

| Value            | Description                                                                           |
| ---------------- | ------------------------------------------------------------------------------------- |
| `SchematicName`  | Name of the schematic to spawn. The schematic must be loaded in TME or MER.           |
| `AnimatorName`   | Optional animator to target. Use this when the schematic contains multiple animators. |
| `PositionOffset` | Position offset from the held item or pickup. Defaults to `(0, 0, 0)`.                |
| `RotationOffset` | Rotation offset, in degrees. Defaults to `(0, 0, 0)`.                                 |
| `Scale`          | Model scale. Defaults to `(1, 1, 1)`.                                                 |
| `Animations`     | Maps a [`TriggerOn`](../enums/internal/triggeron.md) event to an animation name.      |

`Animations` supports `OnShot`, `OnUse`, `OnReload`, `OnChangedItem`, `OnAdded`, `OnDropped`, `OnDeath`, `OnHurt`, `OnDoorInteracted`, and `OnInspected`.

### Example

```yaml
custom_modules:
  CustomModel:
  - SchematicName: PlasmaRifleModel
    AnimatorName: WeaponAnimator
    PositionOffset:
      x: 0.0
      y: -0.1
      z: 0.2
    RotationOffset:
      x: 0.0
      y: 90.0
      z: 0.0
    Scale:
      x: 1.0
      y: 1.0
      z: 1.0
    Animations:
      OnAdded: Equip
      OnShot: Fire
      OnReload: Reload
      OnInspected: Inspect
```
