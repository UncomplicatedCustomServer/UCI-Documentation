---
icon: masks-theater
---

# Disguise

This module allows custom items to apply a visual disguise to a player, changing their displayed role appearance, broadcasting a custom message, and setting unique custom info. The disguise can be triggered upon item use or pickup, and can optionally be removed if the player takes damage or drops the item.

### Configuration

| Value               | Description                                                                                                                                                                                                                                                                                                                                             |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `RevealWhenDamaged` | A boolean value. If set to `true`, the disguise will be automatically removed, reverting the player's appearance to their actual role, if they take any damage.                                                                                                                                                                                         |
| `RoleId`            | A `RoleTypeId` enum value. Specifies the role (e.g., `Scientist`, `ClassD`, `Guard`, `FacilityGuard`) that the player will appear as when disguised. The available values correspond to the `PlayerRoles.RoleTypeId` enumeration in Unity/SCP:SL.                                                                                                       |
| `DisguiseMessage`   | A string. This message will be broadcast to the player (displayed on their screen) when the disguise is successfully applied.                                                                                                                                                                                                                           |
| `CustomInfo`        | A string. This text will be displayed as custom information on the player's nametag (usually above their head) while they are disguised. Leave empty (`''`) to not display custom info.                                                                                                                                                                 |
| `Trigger`           | A `TriggerOn` enum value. Determines when the disguise effect is activated. Valid options include `OnUse` (when the custom item is used by the player) or `OnAdded` (when the custom item is picked up by the player). The available values correspond to the `UncomplicatedCustomItems.API.CustomModuleAPI.CustomModules.Enums.TriggerOn` enumeration. |

### Example

```yaml
custom_modules:
  Disguise:
  - RevealWhenDamaged: true
    RoleId: 'Scientist' # Example: Change appearance to a Scientist
    DisguiseMessage: 'You are now disguised as a Scientist! Be careful not to take damage.'
    CustomInfo: '[DISGUISED SCIENTIST]'
    Trigger: 'OnUse' # Apply disguise when the item is used
```
