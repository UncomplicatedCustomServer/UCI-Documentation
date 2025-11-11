# ItemShot

## CustomFlag: ItemShot

**Description**\
When the firearm is shot it will spawn/launch an item or projectile according to these settings. Useful for thrown-projectile behavior, grenades, or items that are themselves projectiles spawned by weapons or other systems.

**Parameters**

* `is_grenade` — `bool` — If `true`, the projectile is treated as a grenade (explosive behavior may be handled elsewhere). Default: `false`.
* `grenade_explode_on_impact` — `bool` — If `true` the grenade will explode on impact instead of on a timer. Default: `false`.
* `is_custom_item` — `bool` — If `true`, the launched object is a custom item (use `custom_item_id`). If `false`, a built-in `item_type` is used. Default: `false`.
* `velocity` — `float` — Initial forward velocity of the launched projectile (units depend on game physics). Default: `0`.
* `upwards_factor` — `float` — Upward / vertical component multiplier applied to the launch. Default: `0`.
* `torque` — `Vector3` — Angular torque applied to the launched object (affects spin). Default: `Vector3(0,0,0)`.
* `custom_item_id` — `uint` — ID of the custom item to spawn if `is_custom_item` is `true`. Default: `0`.
* `item_type` — [`ItemType`](../enums/external/itemtype.md) — Built-in item type to spawn if `is_custom_item` is `false`. (Use your project’s `ItemType` enum; no default provided in class.)

**Behavior notes**

* If `is_custom_item` is `true`, the `custom_item_id` field must reference a valid custom item ID. If `false`, the engine will use `item_type`.
* `IsGrenade` typically affects collision/explosion logic; ensure your grenade handling code checks `grenade_explode_on_impact` accordingly.
* `Velocity`, `UpwardsFactor`, and `Torque` control physics. Tune them for desired projectile arc and spin.

**Example Yaml context**

```yaml
flag_settings:
  item_shot_settings:
  - is_grenade: true
    grenade_explode_on_impact: true
    is_custom_item: false
    velocity: 25.0
    upwards_factor: 0.2
    torque:
      x: 0
      y: 1
      z: 0
    custom_item_id: 0
    item_type: HEGrenade
```
