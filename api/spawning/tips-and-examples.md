# Tips & Examples



* If you want a reliably-fixed spawn at a single coordinate, put the `coords` directly on the `SpawnData` entry and set `chance: 100`.
* Use `dynamic_spawn` to provide several named room positions; the spawn system can pick among them (good for themed item placements).
* Use `zones` for loose placement rules (e.g., “spawn somewhere in HeavyContainment”); `dynamic_spawn` overrides `zones` when present.
* To have the item replace existing pickups instead of adding new floor pickups, set `replace_existing_pickup: true`. Use `force_item: true` to only replace the same item type.
* To place items in lockers/racks, set `locker_settings.enable: true` and configure `locker_type` / `room` / `zone`.
* Combine multiple `spawn_settings` entries with different `chance` values to express multiple alternative spawn behaviors (e.g., 60% floor spawn in ZoneA, 10% locker spawn in ZoneB, etc.).

**Combined example showing several options**

{% code expandable="true" %}
```yaml
spawn:
  do_spawn: true
  count: 3
  spawn_settings:
  - chance: 50
    coords:
      x: 10
      y: 1
      z: -3
    rotation:
      x: 0
      y: 0
      z: 0
      w: 1

  - chance: 30
    locker_settings:
      enable: true
      locker_type: RifleRack
      room: HczWarhead
      zone: HeavyContainment
      chamber: 0

  - chance: 20
    dynamic_spawn:
    - room: Lcz914
      coords: { x: 2, y: 1, z: -1 }
    zones:
    - Entrance
    replace_existing_pickup: true
    force_item: false
```
{% endcode %}
