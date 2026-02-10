---
icon: raygun
---

# DieOn

This module causes a player to die or vaporize when they use or drop a custom item, based on configurable conditions. It allows specifying a custom death message and whether the player should vaporize.

| Value          | Description                                                                                                                                                                                                          |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `DeathMessage` | The message displayed when the player dies. The placeholder `%name%` will be replaced with the custom item's configured name.                                                                                        |
| `Vaporize`     | If `true`, the player will vaporize instead of just dying. If `false`, they will die and display the `DeathMessage`.                                                                                                 |
| `Trigger`      | Specifies when the module's effect should trigger. Possible values are `OnUse` (when the item is used) and `OnDropped` (when the item is dropped). Note that only one trigger can be configured per module instance. |

### Example

```yaml
custom_modules:
  DieOn:
  - DeathMessage: "You were too clumsy with %name%!"
    Vaporize: false
    Trigger: OnDropped
  - DeathMessage: "You vaporized into thin air after using %name%!"
    Vaporize: true
    Trigger: OnUse
```
