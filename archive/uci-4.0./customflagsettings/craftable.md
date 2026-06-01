# Craftable

{% include "../../../.gitbook/includes/archive-msg.md" %}

**Description:** Makes the item craftable in 914 configure knob setting, original item used in crafting, and chance.

**Parameters:**

* `knob_setting` — [`Scp914KnobSetting`](../../../api/enums/external/scp914knobsetting.md) value for the crafting knob or quality.
* `original_item` — [`ItemType`](../../../api/enums/external/itemtype.md) value for the base item used to craft.
* `chance` — Percent chance to successfully craft.

**Example Yaml context:**

```yaml
flag_settings:
  craftable_settings:
  - knob_setting: Coarse
    original_item: Adrenaline
    chance: 100
```
