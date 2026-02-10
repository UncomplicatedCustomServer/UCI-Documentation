---
icon: up
---

# Craftable

This custom module allows an item to be crafted via SCP-914. It defines the specific SCP-914 knob setting and original item required, along with a success chance for the crafting process. It supports crafting from both items placed directly into SCP-914 and items held in a player's inventory.

### Configuration

| Value          | Description                                                                                                                                                                                                                        |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `KnobSetting`  | Specifies the required SCP-914 knob setting (e.g., `1To1`, `Fine`, `Coarse`, `VeryFine`, `Rough`, `VeryRough`) for the crafting process. The value must be a valid `Scp914KnobSetting` enum member.                                |
| `OriginalItem` | Defines the type of item (e.g., `Medkit`, `KeycardScientist`) that needs to be put into SCP-914 to craft this custom item. The value must be a valid `ItemType` enum member.                                                       |
| `Chance`       | The probability (as a percentage from `0.0` to `100.0`) that the crafting of this custom item will succeed when the `OriginalItem` is processed with the specified `KnobSetting`. A value of `100.0` means it will always succeed. |

### Example

```yaml
  custom_modules:
    Craftable:
    - KnobSetting: "1To1" # Requires SCP-914 to be on the '1:1' setting
      OriginalItem: "Medkit" # Requires a standard Medkit
      Chance: 75.0 # 75% chance to craft successfully
```
