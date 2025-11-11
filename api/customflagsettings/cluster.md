# Cluster

## CustomFlag: Cluster

**Description:** Spawns a cluster of items when triggered (e.g., grenades spawning multiple pickups).

**Parameters:**

* `item_to_spawn` — Item ID or name to spawn (e.g., `KeycardJanitor`).
* `amount_to_spawn` — Number of items to spawn.
* `scp_damage_multiplier` — Damage multiplier to apply to SCPs (if applicable).
* `fuse_time` — Delay (seconds) before spawned cluster or its effect triggers.

**Example Yaml context:**

```yaml
flag_settings:
  cluster_settings:
  - item_to_spawn: KeycardJanitor
    amount_to_spawn: 6
    scp_damage_multiplier: 5
    fuse_time: 5
```
