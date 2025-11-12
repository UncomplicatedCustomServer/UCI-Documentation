# Effect

## CustomFlag: Effect

**Description:** Applies a game effect when the item is used, with control over intensity, duration, stacking, and clearing on unequip.

**Parameters:**

* `effect_event` — The event that triggers the effect (`EffectWhenUsed`, `EffectShot`, or `EffectWhenEquiped`).
* [`effect`](../enums/external/effects.md) — Which effect to apply (e.g., `Flashed`).
* `effect_intensity` — Intensity/strength of the applied effect.
* `effect_duration` — How long the effect lasts (seconds).
* `add_duration_if_active` — If `true`, adding the effect while it’s active increases the duration instead of replacing it.
* `clear_on_unequip` — If `true`, effect is cleared when the item is unequipped.

**Example Yaml context:**

```yaml
flag_settings:
  effect_settings:
  - effect_event: EffectWhenUsed
    effect: Flashed
    effect_intensity: 1
    effect_duration: 1
    add_duration_if_active: true
    clear_on_unequip: true
```
