---
icon: shuffle
---

# SwitchRoleOn

This custom module allows players to switch to a different role under specific conditions. It can trigger on various player actions and allows for a delay before the role switch occurs, optionally preserving the player's current location.

### Configuration

| Value          | Description                                                                                                                                                                                                     |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Delay`        | The time in seconds to wait before switching the player's role. A value of 0 means the role switch is immediate.                                                                                                |
| `RoleType`     | The type of role to switch to. Supported values are: `Normal` (for standard SCP: Secret Laboratory roles), `UCR` (for Uncomplicated Custom Roles), and `ECR` (for Exiled Custom Roles, if Exiled is installed). |
| `RoleId`       | The ID of the role to switch to. This should be a `RoleTypeId` enum value for `Normal` roles, or the numerical ID for `UCR` or `ECR` roles.                                                                     |
| `SpawnFlags`   | Flags to determine how the player should spawn into the new role (e.g., `None`, `TeleportDuringSpawn`). This is applicable for `Normal` roles.                                                                  |
| `KeepLocation` | If `true`, the player's position will be reset to their location before the role switch after a short delay.                                                                                                    |
| `Trigger`      | The event that triggers the role switch. Supported values are: `OnShot`, `OnUse`, `OnChangedItem`, `OnAdded` (for picking up an item).                                                                          |

### Example

```yaml
custom_modules:
  SwitchRoleOn:
  - Delay: 0.5
    RoleType: 'Normal'
    RoleId: 1 # Example: ClassD
    SpawnFlags: 'None'
    KeepLocation: true
    Trigger: 'OnUse'
  - Delay: 0
    RoleType: 'UCR'
    RoleId: 123 # Example UCR Role ID
    SpawnFlags: 'None'
    KeepLocation: false
    Trigger: 'OnShot'
  - Delay: 1.0
    RoleType: 'ECR' # Only if Exiled is installed
    RoleId: 456 # Example ECR Role ID
    SpawnFlags: 'None'
    KeepLocation: true
    Trigger: 'OnAdded'
```
