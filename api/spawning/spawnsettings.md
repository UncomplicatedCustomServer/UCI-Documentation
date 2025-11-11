# SpawnSettings

**Description**\
A single spawn rule describing _one_ possible way an item may spawn (chance, coordinates, rotation, locker options, room/zone lists, and replacement options).

**Parameters**

* `chance` — `float` (0–100) — Percent chance this `SpawnData` entry will result in a spawn. Default: `30`.
* `coords` — `Vector3` — Explicit coordinates for spawn. If non-zero/used, these coordinates take precedence over dynamic spawn/zone lists.
* `rotation` — `Vector3` — Rotation for the spawned item.
* `locker_settings` — [`LockerSpawn`](lockerspawn.md) — Locker-specific spawn configuration (enable, locker type, room, zone, chamber, offset).
* `dynamic_spawn` — `array[`[`DynamicSpawn`](dynamicspawn.md)`]` — Room + coordinates pairs where the item is allowed to spawn. Used when `coords` is not specified.
* `zones` — `array[`[`FacilityZone`](../enums/external/facilityzone.md)`]` — Facility zones (enum) where the item may spawn. Used when both `coords` and `dynamic_spawn` are empty.
* `replace_existing_pickup` — `bool` — If `true`, this spawn entry will replace an existing in-game pickup instead of spawning on the floor.
* `force_item` — `bool` — If `true` and `replace_existing_pickup` is used, only pickups of the same item type will be replaced.
* `replace_items_in_pedestals` — `bool?` — If `true`, this spawn entry can replace items located in SCP pedestals.

**Precedence summary**

1. If `coords` is provided on the `SpawnData` entry, those coordinates are used.
2. Else, if `dynamic_spawn` has entries, the system will use one of those `DynamicSpawn` (room + coords) entries.
3. Else, the `zones` list is used to pick a spawn location within the given facility zone(s).

**Example Yaml context**

{% code expandable="true" %}
```yaml
spawn:
  do_spawn: true
  spawn_settings:
  - chance: 40
    coords:
      x: 10
      y: 1
      z: -3
    rotation:
      x: 0
      y: 0
      z: 0
    replace_existing_pickup: false

  - chance: 25
    dynamic_spawn:
    - room: Lcz914
      coords:
        x: 1
        y: 1
        z: 1
    zones:
    - HeavyContainment
    replace_existing_pickup: true
    force_item: true
    replace_items_in_pedestals: false
```
{% endcode %}
