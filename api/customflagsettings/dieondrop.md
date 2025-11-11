# DieOnDrop

## CustomFlag: DieOnDrop

**Description:** Causes the item holder to die when they drop the item; supports a death message and vaporization.

**Parameters:**

* `death_message` — Message displayed on death; supports placeholders (e.g., `%name%`).
* `vaporize` — If `true`, the body is vaporized on death.

**Example Yaml context:**

```yaml
flag_settings:
  die_on_drop_settings:
  - death_message: 'Dropped %name%'
    vaporize: true
```
