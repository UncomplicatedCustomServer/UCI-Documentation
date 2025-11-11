# SpawnItemWhenDetonated

## CustomFlag: SpawnItemWhenDetonated

**Description:** Spawns an item when the subject detonates/activates. Configure type, ID, despawn time, chance, and pickupability.

**Parameters:**

* `item_type` — `UCI`, `ECI`, or `Normal`.
* `item_id` — Numeric ID for `Normal`-type items (or plugin-specific ID).
* `time_till_despawn` — Seconds until spawned item despawns.
* `chance` — Percent chance the spawn will occur (0–100).
* `pickupable` — `true` if the spawned item can be picked up.

**Example Yaml context:**

```yaml
flag_settings:
  spawn_item_when_detonated_settings:
  - item_type: Normal
    item_id: 1
    time_till_despawn: 6
    chance: 100
    pickupable: false
```
