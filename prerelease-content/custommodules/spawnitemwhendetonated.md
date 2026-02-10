---
icon: explosion
---

# SpawnItemWhenDetonated

This custom module allows for an item to be spawned at the location of a detonated projectile. The spawned item can be configured to be a Custom Item (either UncomplicatedCustomItems or Exiled), a normal in-game item, or a specific SCP-244 item.

### Configuration

| Value             | Description                                                                                                                                             |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ItemType`        | The type of item to spawn. Accepts "uci", "exi", or "normal".                                                                                           |
| `ItemId`          | The ID of the item to spawn. This corresponds to the Custom Item ID for "uci" or "exi", or the `ItemType` enum value for "normal".                      |
| `TimeTillDespawn` | The time in seconds before the spawned item automatically despawns. Set to 0 for no despawn.                                                            |
| `Chance`          | The percentage chance (0-100) that the item will spawn.                                                                                                 |
| `Pickupable`      | A boolean indicating whether the spawned item can be picked up by players. If `false`, the item's weight is set to a very high value to prevent pickup. |

### Example

```yaml
custom_modules:
  SpawnItemWhenDetonated:
  - ItemType: 'uci'
    ItemId: 123
    TimeTillDespawn: 30.0
    Chance: 75.0
    Pickupable: true
  - ItemType: 'normal'
    ItemId: 0 # This would correspond to ItemType.None
    TimeTillDespawn: 15.5
    Chance: 50.0
    Pickupable: false
```
