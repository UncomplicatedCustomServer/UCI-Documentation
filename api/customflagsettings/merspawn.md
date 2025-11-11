# MERSpawn

## CustomFlag: **MERSpawn**

**Description:** Configuration for MER related spawning behavior (locker spawning, replacement, and schematic).

**Parameters:**

* `locker_spawning` — If `true`, spawn via locker placement.
* `replace_primitive` — If `true`, replace primitive spawns with this object.
* `schematic_name` — Name of the schematic to use.
* `object_name` — Object name (name of the primitive or locker).

**Example Yaml context:**

```yaml
flag_settings:
  mer_spawn_settings:
  - locker_spawning: false
    replace_primitive: false
    schematic_name: Test
    object_name: ''
```
