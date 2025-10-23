---
description: >-
  The `FlashlightData` class is used for custom items of type `Light`. It allows
  you to customize the properties of flashlights.
icon: flashlight
---

# Flashlight

**Properties**

| Property         | Type           | Description                                                                                          |
| ---------------- | -------------- | ---------------------------------------------------------------------------------------------------- |
| `HexColor`       | `string`       | The hexadecimal color of the light.                                                                  |
| `LightType`      | `LightType`    | The type of light. Available values are: `Spot`, `Directional`, `Point`, `Area`, `Rectangle`, `Disc` |
| `Intensity`      | `float`        | The intensity of the light.                                                                          |
| `ShadowType`     | `LightShadows` | The type of shadows. Available values are: `None`, `Hard`, `Soft`                                    |
| `ShadowStrength` | `float`        | The strength of the shadows.                                                                         |
| `Range`          | `float`        | The range of the light in meters.                                                                    |
| `SpotLightAngle` | `float`        | The angle of the spotlight.                                                                          |
| `Shape`          | `LightShape`   | The shape of the light if it's a spotlight.                                                          |

**Example:**

```yaml
CustomItemType: Light
CustomData:
  hex_color: "#FF0000"
  light_type: Spot
  intensity: 1.5
  shadow_type: Soft
  shadow_strength: 0.8
  range: 15.0
  spot_light_angle: 45.0
  shape: Cone
```
