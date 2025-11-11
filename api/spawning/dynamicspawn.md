# DynamicSpawn

**Description**\
List of specific room + coordinate pairs where the item may spawn. Useful when you need precise room control but want the spawn system to pick one of several positions in that room.

**Parameters**

* `room` — `string` — Room identifier/name (e.g., `"Lcz914"`).
* `coords` — `Vector3` — Local coordinates inside the specified room.

**Example Yaml context**

```yaml
spawn:
  spawn_settings:
  - chance: 50
    dynamic_spawn:
    - room: Lcz914
      coords:
        x: 1
        y: 1
        z: 1
    - room: HczWarhead
      coords:
        x: 2
        y: 0.5
        z: -4
```
