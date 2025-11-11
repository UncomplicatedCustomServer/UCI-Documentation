# ItemGlow

* **CustomFlag:** ItemGlow
* **Description:** When the CustomItem is a pickup the area around the pickup will glow the specified parameters.
* **Parameters:**
  * `GlowColor` — The color of the item's glow, represented as a hex color string (e.g., `#00FF00`)
  * `Intensity` — The Intensity of the glow on the CustomItem pickup
  * `Range` — The Range of the glow on the CustomItem pickup.
* **Example Yaml context:**

```yaml
flag_settings:
  item_glow_settings:
  - glow_color: '#00FF00'
    intensity: 1
    range: 2
```

&#x20;
