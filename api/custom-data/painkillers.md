---
description: >-
  The `PainkillersData` class is used for custom items of type `Painkillers`. It
  allows you to customize the properties of painkillers.
icon: prescription-bottle
---

# Painkillers

**Properties**

| Property                 | Type    | Description                                     |
| ------------------------ | ------- | ----------------------------------------------- |
| `TickHeal`               | `float` | The amount of health granted every `TickTime`.  |
| `TimeBeforeStartHealing` | `float` | The time to wait before healing starts.         |
| `TickTime`               | `float` | The time between each `TickHeal`.               |
| `TotalHealing`           | `float` | The total amount of health that can be granted. |

**Example:**

```yaml
CustomItemType: Painkillers
CustomData:
  tick_heal: 5.0
  time_before_start_healing: 2.0
  tick_time: 1.0
  total_healing: 50.0
```
