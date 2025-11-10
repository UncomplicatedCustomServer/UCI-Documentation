---
icon: candy
---

# Candy

### Class Definition

```csharp
public class CandyData : Data, ICandyData
{
    public virtual CandyKindID CandyType { get; set; }
    public virtual string EatingMessage { get; set; }
    public virtual float EatingMessageDuration { get; set; }
    public virtual bool DestroyOnUse { get; set; }
    public virtual float Chance { get; set; }
    public virtual bool ApplyEffects { get; set; }
    public virtual bool AllowSpawningAsItem { get; set; }
}
```

### Properties

The following table details each property available in the `CandyData` configuration.

| Property Name           | Type          | Description                                                                                                                   |
| ----------------------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `CandyType`             | `CandyKindID` | The specific type of the candy.                                                                                               |
| `EatingMessage`         | `string`      | The message displayed to the player when they consume the candy.                                                              |
| `EatingMessageDuration` | `float`       | How long, in seconds, the `EatingMessage` is displayed on the screen.                                                         |
| `DestroyOnUse`          | `bool`        | If `true`, the candy item is consumed and removed from inventory after use. If `false`, it remains.                           |
| `Chance`                | `float`       | The probability (0 to 100) of a certain effect or outcome occurring when the candy is used. For example, 50 for a 50% chance. |
| `ApplyEffects`          | `bool`        | If `true`, any associated effects (e.g., buffs, debuffs, healing) will be applied upon consumption.                           |
| `AllowSpawningAsItem`   | `bool`        | If `true`, this candy can be spawned as a item when the round starts.                                                         |

### Example Configuration (YAML)

Below is an example of how you might configure these properties in a typical YAML file that would be loaded into this data class.

```yaml
CustomData:
  candy_type: Red
  eating_message: "You feel a delightful sugar rush!"
  eating_message_duration: 3.0
  destroy_on_use: true
  chance: 0.75
  apply_effects: true
  allow_spawning_as_item: false
```
