# HumeShield

## CustomFlag: HumeShield

**Description:** Provides a regenerating Hume Shield with rate, max value, and cooldown.

**Parameters:**

* `regen_rate` — Rate at which shield regenerates per second (or plugin-defined unit).
* `max_hume_shield` — Maximum shield capacity.
* `regen_cool_down` — Seconds to wait before regeneration resumes after damage.

**Example Yaml context:**

```yaml
flag_settings:
  hume_shield_settings:
  - regen_rate: 2
    max_hume_shield: 90
    regen_cool_down: 1
```
