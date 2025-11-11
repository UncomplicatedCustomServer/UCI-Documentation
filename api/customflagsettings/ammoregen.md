# AmmoRegen

## CustomFlag: AmmoRegen

**Description:** Regenerates ammo for the user over time.

**Parameters:**

* `regen_delay` — Seconds to wait before regeneration starts.
* `regen_interval` — Seconds between each regeneration tick.
* `ammo_per_interval` — Amount of ammo restored each interval.

**Example Yaml context:**

```yaml
flag_settings:
  ammo_regen_settings:
  - regen_delay: 5
    regen_interval: 1
    ammo_per_interval: 1
```
