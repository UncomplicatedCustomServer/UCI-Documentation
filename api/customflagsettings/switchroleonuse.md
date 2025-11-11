# SwitchRoleOnUse

## CustomFlag: SwitchRoleOnUse

**Description**\
When the item is used, this setting can switch the player's role (class) after an optional delay. Supports switching to built-in roles or to custom role systems (UCR/ECR).

**Parameters**

* `delay` — `float?` — Seconds to wait before the role switch occurs. Default: `1`.
* `role_type` — `string?` — `"UCR"` or `"Normal"`. Leave blank to use default behavior. Default: `""`.
* `role_id` — `uint?` — Role identifier. If `role_type` is `Normal`, this should be the `RoleType` enum value. If `role_type` is `UCR`/`ECR`, this should be the custom role ID. Default: `1`.
* `spawn_flags` — [`RoleSpawnFlags`](../enums/external/rolespawnflags.md)`?` — For `Normal` role types, controls how the new role spawns: `None`, `AssignInventory`, `UseSpawnpoint`, or `All`. Default: `None`.
* `keep_location` — `bool?` — If `true`, the player remains at their current position after the role change (useful for role swaps without teleporting). Default: `false`.

**Behavior notes**

* `Delay` allows for animations/sfx before the switch completes.
* When using `role_type: Normal`, `spawn_flags` determines whether to give the new role its normal inventory, spawnpoint, or both.
* `RoleId` must match the expected identifier for the selected `role_type`. Be careful mixing `Normal` and `UCR` without correct IDs.

**Example Yaml context**

```yaml
flag_settings:
  switch_role_on_use_settings:
  - delay: 6
    role_type: "Normal"
    role_id: 0
    spawn_flags: "None"
    keep_location: true
```
