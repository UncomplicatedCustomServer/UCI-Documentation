# Craftable

## CustomFlag: Craftable

**Description:** Makes the item craftable in 914 configure knob setting, original item used in crafting, and chance.

**Parameters:**

* `knob_setting` — Crafting knob/quality (e.g., `Coarse`).
* `original_item` — Name/ID of the base item used to craft.
* `chance` — Percent chance to successfully craft.

**Example Yaml context:**

```yaml
flag_settings:
  craftable_settings:
  - knob_setting: Coarse
    original_item: Adrenaline
    chance: 100
```
