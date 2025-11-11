# DieOnUse

## CustomFlag: DieOnUse

**Description:** Kills the user when the item is used; supports death message and vaporize on death.

**Parameters:**

* `death_message` — Message displayed on death (supports placeholders).
* `vaporize` — If `true`, body is vaporized.

**Example Yaml context:**

```yaml
flag_settings:
  die_on_use_settings:
  - death_message: 'Killed by %name%'
    vaporize: false
```
