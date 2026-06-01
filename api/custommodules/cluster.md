---
icon: hexagon-nodes
---

# Cluster

The `Cluster` module allows an item, typically a projectile, to spawn multiple instances of a specified item or projectile in a cluster around its explosion point. This is useful for creating items that fragment or scatter secondary effects upon impact or detonation, with configurable quantities, types, and projectile-specific properties like damage and fuse time.

### Configuration

| Value                 | Description                                                                                                                                                         |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ItemToSpawn`         | The `ItemType` of the item or projectile that will be spawned in the cluster.                                                                                       |
| `AmountToSpawn`       | The total number of additional items or projectiles to spawn in the cluster.                                                                                        |
| `ScpDamageMultiplier` | **(Explosive Projectiles Only)** A float value that multiplies the damage dealt to SCPs by the spawned grenades. Defaults to `1.0`.                                 |
| `FuseTime`            | **(Explosive Projectiles Only)** The fuse time in seconds for the spawned grenades before they detonate. The initial spawned grenade will have half this fuse time. |

### Example

```yaml
custom_modules:
  Cluster:
  - ItemToSpawn: GrenadeHE       # Spawns additional HE Grenades
    AmountToSpawn: 3             # Spawns 3 extra grenades
    ScpDamageMultiplier: 0.75    # Spawned grenades deal 75% SCP damage
    FuseTime: 1.0                # Spawned grenades have a 1-second fuse
```
