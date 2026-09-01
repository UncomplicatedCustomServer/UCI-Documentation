---
icon: burst
---

# DestroyOn

Destroys the custom item when the configured trigger fires.

#### Configuration

| Value     | Description                                                                                                                                                                                      |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `Trigger` | Specifies when the item should be destroyed. Possible values are `OnShot`, `OnUse`, `OnReload`, `OnChangedItem`, `OnAdded`, `OnDropped`, `OnDeath`, `OnHurt`, `OnDoorInteracted`, `OnInspected`. |

#### Example

```yaml
custom_modules:
  DestroyOn:
  - Trigger: OnUse
  - Trigger: OnDropped
  - Trigger: OnShot
```
