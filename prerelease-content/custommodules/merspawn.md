---
icon: wrench
---

# MERSpawn

This custom module is designed to control the spawning behavior of a custom item, allowing for detailed configuration regarding its placement and instantiation within the game world. It supports specifying whether an item can spawn in lockers, replace existing primitives, and defines the schematic and object names to use for its representation.

### Configuration

| Value              | Description                                                                                 |
| ------------------ | ------------------------------------------------------------------------------------------- |
| `LockerSpawning`   | A boolean value indicating whether the custom item can spawn inside lockers.                |
| `ReplacePrimitive` | A boolean value determining if a primitive object should be replaced when this item spawns. |
| `SchematicName`    | The name of the schematic to be used when spawning this custom item.                        |
| `ObjectName`       | The name of the game object to be used when spawning this custom item.                      |

### Example

Here's an example of how to configure the `MERSpawn` module within your `custom_modules` YAML configuration:

```yaml
custom_modules:
  MERSpawn:
  - LockerSpawning: true
    ReplacePrimitive: false
    SchematicName: 'MyWeaponSchematic'
    ObjectName: 'SpecialWeaponModel'
```
